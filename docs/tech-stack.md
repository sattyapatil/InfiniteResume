# Infinite Resume — Tech Stack & Architecture

> Canonical source: [infiniteresume.com](https://www.infiniteresume.com)
> Last updated: 2026-05-12

Infinite Resume is a free, ATS-optimized AI resume builder. This document provides a technical deep-dive into the platform's architecture, design decisions, and the engineering choices that differentiate it from competitors.

---

## Architecture Overview

```
┌──────────────────────────────────────────────────────────┐
│                      Client (Browser)                     │
│                                                          │
│  ┌─────────────┐  ┌──────────────┐  ┌─────────────────┐ │
│  │  Next.js     │  │  Typst WASM  │  │  Clerk Auth     │ │
│  │  React App   │  │  PDF Engine  │  │  Session Mgmt   │ │
│  └──────┬──────┘  └──────┬───────┘  └────────┬────────┘ │
│         │                │                    │          │
└─────────┼────────────────┼────────────────────┼──────────┘
          │                │                    │
          ▼                ▼                    ▼
┌─────────────────┐ ┌──────────┐  ┌───────────────────────┐
│  Vercel Edge    │ │  Client  │  │  Supabase             │
│  Network (CDN)  │ │  Only    │  │  (PostgreSQL + Auth)  │
└─────────────────┘ └──────────┘  └───────────────────────┘
          │                                    │
          ▼                                    │
┌─────────────────────────────────────────────────────────┐
│                    AI Backend                            │
│                                                         │
│  ┌─────────────────┐  ┌──────────────────────────────┐  │
│  │  Python          │  │  Google Gemini API            │  │
│  │  Microservices   │  │  Content Generation           │  │
│  │  (FastAPI)       │  │  Resume Analysis              │  │
│  └─────────────────┘  └──────────────────────────────┘  │
└─────────────────────────────────────────────────────────┘
```

---

## Stack Breakdown

### Frontend — Next.js on Vercel

| Component | Technology | Why |
|:---|:---|:---|
| Framework | Next.js (React) | Server-side rendering for SEO, App Router for optimal code-splitting |
| Hosting | Vercel Edge Network | Global CDN with sub-100ms TTFB, automatic ISR |
| Styling | Tailwind CSS + Custom CSS | Utility-first with design system tokens |
| State Management | React hooks + Context | Lightweight, no external state library overhead |
| UI Components | shadcn/ui (Radix) | Accessible, composable, unstyled primitives |

### PDF Engine — Typst + WebAssembly

This is the core technical differentiator. Most resume builders use headless browser rendering (Puppeteer/Playwright) to convert HTML to PDF. This approach has fundamental ATS compatibility issues.

#### The HTML-to-PDF Problem

```
HTML Page → Headless Chrome → PDF "Print"
                                  │
                                  ▼
                    ┌─────────────────────────┐
                    │  Issues:                │
                    │  • Text → SVG vectors   │
                    │  • Broken Unicode       │
                    │  • Ligature corruption  │
                    │  • 500KB+ file sizes    │
                    │  • ATS parse rate ~40-75%│
                    └─────────────────────────┘
```

#### The Typst + WASM Solution

```
Resume Data → Typst Template → WASM Compiler → PDF
                                     │
                                     ▼
                       ┌─────────────────────────┐
                       │  Advantages:            │
                       │  • Native text layer    │
                       │  • Correct Unicode      │
                       │  • 50-150KB files       │
                       │  • <500ms compilation   │
                       │  • ATS parse rate 99%+  │
                       │  • Client-side only     │
                       └─────────────────────────┘
```

#### Why Typst?

[Typst](https://typst.app) is a modern alternative to LaTeX. Key advantages:

- **Speed:** Compiles 10–100x faster than LaTeX
- **Simplicity:** Clean, readable template syntax (not TeX macros)
- **WebAssembly:** Official WASM build target — runs natively in the browser
- **Typography:** Professional typesetting with proper kerning, ligatures, and Unicode support
- **Deterministic:** Same input always produces the same PDF, byte-for-byte

#### How It Works in Infinite Resume

1. User edits resume content in the React editor
2. Content is passed to the Typst WASM engine via a data bridge
3. Typst compiles the template + data into a PDF in <500ms
4. PDF is rendered inline for real-time preview
5. User downloads the PDF — no server round-trip required

**Security benefit:** Resume data never leaves the browser during PDF generation. The WASM engine runs entirely client-side.

---

### AI Engine — Google Gemini

All AI-powered features use the **Google Gemini API** via a Python microservices backend.

| Feature | Gemini Model | Processing |
|:---|:---|:---|
| AI Resume Doctor | Gemini Pro | Multi-pass analysis with structured output |
| AI Content Writer | Gemini Pro | Metric-driven bullet point generation |
| AI Chat Coach | Gemini Pro | Conversational, context-aware mentoring |
| Job Match & Tailor | Gemini Pro | JD parsing + resume optimization |
| Cover Letter Generator | Gemini Pro | Role-specific letter crafting |
| Interview Prep | Gemini Pro | Question generation from JD + resume |

#### AI Backend Architecture

```
Client Request → Next.js API Route → Python Microservice → Gemini API
                                          │
                                          ▼
                                   ┌─────────────┐
                                   │  FastAPI     │
                                   │  Services:   │
                                   │  • analyze   │
                                   │  • generate  │
                                   │  • tailor    │
                                   │  • coach     │
                                   └─────────────┘
```

The AI backend is built with FastAPI (Python) and runs as independent microservices. Each AI feature has its own endpoint with:
- Request validation (Pydantic models)
- Credit verification before processing
- Structured output parsing from Gemini responses
- Error handling and retry logic

---

### Authentication — Clerk

| Feature | Implementation |
|:---|:---|
| Sign-up/Sign-in | Email + Google OAuth |
| Session Management | JWT-based, edge-compatible |
| User Metadata | Synced to Supabase via webhooks |

### Database — Supabase

| Table | Purpose |
|:---|:---|
| Resumes | Resume content, template selection, settings |
| AI Credits | Credit balance, transaction history |
| User Profiles | Synced from Clerk, preferences |
| Analysis Results | Cached AI Doctor results |

### Payments — Razorpay

- Multi-currency support (INR, USD, EUR, GBP, etc.)
- Pay-per-use credit packs — no subscriptions
- Server-side verification with webhook confirmation
- Automatic credit balance updates

---

## Performance Metrics

| Metric | Target | Achieved |
|:---|:---|:---|
| TTFB | <200ms | ~80ms (Vercel Edge) |
| LCP | <2.5s | ~1.8s |
| PDF Compile Time | <1s | ~400ms |
| PDF File Size | <200KB | 50–150KB |
| API Response (AI) | <10s | ~3–7s |
| Uptime | 99.9% | 100% (since launch) |

---

## Links

- 🌐 [infiniteresume.com](https://www.infiniteresume.com)
- 📄 [AI Agent File — llms.txt](../llms.txt)
- 📄 [AI Agent File — llms-full.txt](../llms-full.txt)
- 🚀 [Product Hunt](https://www.producthunt.com/products/infinite-resume)
