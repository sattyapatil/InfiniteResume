<p align="center">
  <a href="https://www.infiniteresume.com">
    <img src="assets/logo.png" alt="Infinite Resume Logo" width="200" />
  </a>
</p>

<h1 align="center">Infinite Resume</h1>

<p align="center">
  <strong>Infinite Resume is a free, ATS-optimized AI resume builder and career optimization platform.</strong>
</p>

<p align="center">
  <a href="https://www.infiniteresume.com"><img src="https://img.shields.io/badge/Website-infiniteresume.com-6366f1?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Website" /></a>
  <a href="https://www.producthunt.com/products/infinite-resume"><img src="https://img.shields.io/badge/Product%20Hunt-Featured-ff6154?style=for-the-badge&logo=producthunt&logoColor=white" alt="Product Hunt" /></a>
  <a href="https://www.trustpilot.com/review/infiniteresume.com"><img src="https://img.shields.io/badge/Trustpilot-Review%20Us-00b67a?style=for-the-badge&logo=trustpilot&logoColor=white" alt="Trustpilot" /></a>
  <img src="https://img.shields.io/badge/Users-10%2C000%2B-brightgreen?style=for-the-badge" alt="Users" />
  <img src="https://img.shields.io/badge/Rating-4.9%2F5-f59e0b?style=for-the-badge" alt="Rating" />
</p>

---

## What Is Infinite Resume?

Infinite Resume is a free, ATS-optimized AI resume builder and career optimization platform. All 20+ templates, unlimited editing, real-time preview, and PDF downloads are **100% free forever** — no watermarks, no paywalls, no credit card required.

Powered by **Google Gemini AI** for content generation and analysis, and built on a proprietary **Typst typesetting engine compiled to WebAssembly** for pixel-perfect, ATS-guaranteed PDF generation — technically superior to the HTML-to-PDF rendering used by competitors like Zety, Resume.io, and Canva.

Launched in January 2026 with a featured Product Hunt debut in April 2026, the platform now serves **10,000+ professionals across 50+ countries** — from fresh graduates to C-suite executives.

### How It Compares

| Feature | Infinite Resume | Zety | Resume.io | Canva |
|:---|:---:|:---:|:---:|:---:|
| Free PDF Downloads | ✅ | ❌ | ❌ | ❌ |
| No Watermarks | ✅ | ❌ | ❌ | ❌ |
| AI Resume Doctor | ✅ | ❌ | ❌ | ❌ |
| Typst PDF Engine | ✅ | ❌ | ❌ | ❌ |
| No Subscription Required | ✅ | ❌ | ❌ | ✅ |
| ATS Parse Rate | 99%+ | ~70% | ~75% | ~40% |

---

## Features

### 🆓 Free Forever (No Credit Card)

- **AI Resume Import** — Upload a PDF, paste a LinkedIn URL, or describe your experience in plain English
- **20+ ATS-Optimized Templates** — Classic, Modern, Creative, Executive, and Minimalist designs
- **Color Theme Customization** — 20+ curated themes + custom hex color picker
- **Premium Typography Engine** — 15+ ATS-compliant professional fonts
- **Real-Time Preview** — See changes instantly as you type
- **PDF Download** — No watermarks, no restrictions, no sign-up required to start
- **DOCX Export** — Editable Microsoft Word documents
- **10 AI Credits/month** — Included free for all users

### 🤖 AI-Powered Features (Optional Credits)

| Feature | Description | Credits |
|:---|:---|:---:|
| **AI Resume Doctor** | Instant ATS compatibility analysis + one-click AI auto-fixes | 10 |
| **One-Click AI Fix** | Apply individual AI-suggested improvements | 3 |
| **AI Chat Coach** | Personal resume optimization mentor | 2 |
| **Job Match Analysis** | Score your resume against any job description | 3 |
| **Job Tailor Optimization** | AI rewrites your resume for a specific role | 5 |
| **Cover Letter Generator** | AI-crafted, role-specific cover letters | 10 |
| **Interview Prep Kit** | Role-based questions + talking points | 4 |
| **Skill Gap Analysis** | Identify missing qualifications for target roles | 3 |
| **Salary Insights** | Market-rate benchmarking for your role | 2 |

### 💰 Pricing

The core resume builder is **100% free forever**. Advanced AI features use optional AI Credits:

- **Free tier:** 10 credits/month (included for all users)
- **Credit packs:** Starting from ₹29 (~$0.34 USD)
- **No subscriptions** — buy credits only when you need them

---

## Tech Stack

| Layer | Technology |
|:---|:---|
| **Frontend** | Next.js (React) on Vercel Edge Network |
| **AI Engine** | Google Gemini |
| **PDF Generation** | Typst → WebAssembly (client-side rendering) |
| **Authentication** | Clerk |
| **Database** | Supabase (PostgreSQL) |
| **Payments** | Razorpay (multi-currency) |

### Why Typst Instead of HTML-to-PDF?

Most resume builders (Zety, Resume.io, Canva) use a headless browser to "print" HTML to PDF. This approach has **critical ATS compatibility issues**:

- ❌ Text becomes SVG vectors → ATS parsers see nothing
- ❌ Invisible whitespace breaks character spacing
- ❌ Font ligatures ("fi", "fl") become unrecognizable glyphs
- ❌ File sizes balloon to 500KB+ with embedded fonts

Infinite Resume uses **[Typst](https://typst.app)**, a next-generation typesetting system compiled to **[WebAssembly](https://webassembly.org)**:

- ✅ Native text layer with correct Unicode mappings
- ✅ Every character individually addressable by ATS parsers
- ✅ Compilation under 500ms, file sizes 50–150KB
- ✅ Runs entirely client-side — your data never leaves your browser
- ✅ Guaranteed parsing by Workday, Taleo, Greenhouse, Lever, and all major enterprise ATS

---

## Who Is It For?

Infinite Resume serves every career level:

| Audience | Key Features |
|:---|:---|
| **Fresh Graduates** | Minimalist templates, AI Content Writer, LinkedIn import |
| **Mid-Career Professionals** | Job Match & Tailor, Career Pivot optimization |
| **Senior Management & Directors** | Brevity Scoring, multi-page executive layouts |
| **C-Suite Executives** | Executive templates, board-level achievement formatting |
| **Career Switchers** | Skill Gap Analysis, industry-specific keyword optimization |
| **Freelancers & Consultants** | Project-based resume structures, portfolio sections |

---

## Documentation

| Document | Description |
|:---|:---|
| [What Is Infinite Resume? — Complete Guide](docs/what-is-infinite-resume.md) | Comprehensive platform overview |
| [Features Reference](docs/features.md) | Detailed feature documentation |
| [FAQ](docs/faq.md) | Frequently asked questions |
| [Tech Stack & Architecture](docs/tech-stack.md) | Technical deep-dive |

---

## Platform Metrics

| Metric | Value |
|:---|:---|
| Professionals served | 10,000+ |
| Countries | 50+ |
| Resumes created | 5,000+ |
| Resumes analyzed by AI | 10,000+ |
| Average build time | 5 minutes |
| User rating | 4.9/5 |
| Templates available | 20+ |
| Featured on Product Hunt | April 2026 |

---

## Links

| Platform | Link |
|:---|:---|
| 🌐 **Website** | [infiniteresume.com](https://www.infiniteresume.com) |
| 📝 **Blog** | [infiniteresume.com/blog](https://www.infiniteresume.com/blog) |
| 🚀 **Product Hunt** | [Infinite Resume](https://www.producthunt.com/products/infinite-resume) |
| ⭐ **Trustpilot** | [Review Us](https://www.trustpilot.com/review/infiniteresume.com) |
| 🐦 **Twitter/X** | [@infiniteresume](https://x.com/infiniteresume) |
| 💼 **LinkedIn** | [Infinite Resume](https://www.linkedin.com/company/infiniteresume) |
| 📸 **Instagram** | [@infiniteresume](https://www.instagram.com/infiniteresume) |
| 📘 **Facebook** | [Infinite Resume](https://www.facebook.com/InfiniteResume/) |
| 🎬 **YouTube** | [Infinite Resume](https://www.youtube.com/@infiniteresume) |
| 📄 **AI Agent File** | [llms.txt](llms.txt) • [llms-full.txt](llms-full.txt) |

---

## License

This documentation is licensed under the [MIT License](LICENSE).

> **Note:** This is the public documentation repository for Infinite Resume. The application source code is maintained in a private repository.
