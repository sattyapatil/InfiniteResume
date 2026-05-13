# Infinite Resume — Features Reference

> Canonical source: [infiniteresume.com/features](https://www.infiniteresume.com/features)
> Last updated: 2026-05-12

Infinite Resume is a free AI resume builder and career optimization platform. This document provides a complete reference of every feature available on the platform.

---

## Core Features (Free Forever)

### AI Resume Import

Import your existing resume or career data in three ways:

- **PDF Upload** — Upload an existing resume PDF. The AI extracts all content, preserving structure, formatting, and section organization.
- **LinkedIn Import** — Paste your LinkedIn profile URL. The AI pulls your experience, education, skills, and certifications into a structured resume format.
- **Plain Text Import** — Describe your experience in conversational language. The AI transforms raw descriptions into professionally structured, metric-driven content.

### 20+ ATS-Optimized Resume Templates

Five template categories to match every professional style:

| Category | Templates | Best For |
|:---|:---|:---|
| **Classic ATS** | Classic Professional, Executive | Maximum ATS compatibility, senior roles |
| **Modern** | Modern Edge, Tech Forward, Active | Tech, startups, mid-career professionals |
| **Creative** | Creative Professional, Canvas | Design, marketing, portfolio careers |
| **Executive** | Executive Leadership, Board-Level | C-suite, VP, Director roles |
| **Minimalist** | Simple Clean, Minimal Impact | Fresh graduates, career changers |

All templates are rendered with the Typst + WebAssembly engine for guaranteed ATS parsing.

### Real-Time Preview

Every change you make is reflected instantly in a live preview panel. The Typst engine recompiles in under 500ms, providing a true "what you see is what you get" experience.

### Color Theme Customization

- 20+ curated professional color themes
- Custom hex color picker for exact brand matching
- All themes maintain full ATS readability

### Premium Typography Engine

- 15+ ATS-compliant professional fonts
- Automatic font embedding in PDFs
- Consistent rendering across all operating systems and devices

### PDF Download

- No watermarks — ever
- No restrictions on number of downloads
- 50–150KB file sizes (optimized)
- Native text layer for ATS parsing
- No sign-up required to start building

### DOCX Export

- Editable Microsoft Word format
- Preserves structure and formatting
- Compatible with Word, Google Docs, and LibreOffice

---

## AI-Powered Features (Optional Credits)

### AI Resume Doctor

The most popular feature on the platform. Upload any resume for an instant AI health check.

**Deep Scan (10 credits):**
- 30+ analysis criteria across 6 categories
- ATS compatibility score
- Impact analysis for every bullet point
- Brevity scoring (especially valuable for senior professionals)
- Industry-specific keyword gap detection
- Formatting and structure recommendations

**One-Click AI Fix (3 credits):**
- Apply individual AI-suggested improvements
- Rewrite weak bullet points with metric-driven language
- Fix formatting inconsistencies automatically

### AI Chat Coach (2 credits)

A personal resume optimization mentor. Ask questions like:
- "Should I include my internship from 5 years ago?"
- "How do I describe a career gap?"
- "Is my summary too long?"

The AI provides strategic advice tailored to your specific resume and target role.

### Job Match & Tailor

**Job Match Analysis (3 credits):**
- Paste any job description
- Get a match percentage score
- See which requirements you meet and which are missing
- Identify keyword gaps

**Job Tailor Optimization (5 credits):**
- AI rewrites your resume to maximize match for a specific role
- Adds missing keywords naturally
- Adjusts tone and focus for the target company
- Preserves your authentic experience

### Cover Letter Generator (10 credits)

- AI-crafted cover letters matching your resume's tone
- Role-specific customization based on job description
- Professional formatting ready for submission

### Interview Prep Kit (4 credits)

- Role-based interview questions generated from the job description
- Talking points drawn from your resume achievements
- Behavioral question frameworks with STAR-method guidance

### Skill Gap Analysis (3 credits)

- Compare your skills against target role requirements
- Get specific upskilling recommendations
- Identify certifications and courses to bridge gaps

### Salary Insights (2 credits)

- Market-rate benchmarking for your role
- Location-adjusted salary data
- Experience-level compensation ranges

---

## Technical Architecture

| Component | Technology |
|:---|:---|
| Frontend | Next.js (React) on Vercel Edge Network |
| AI Engine | Google Gemini |
| PDF Generation | Typst → WebAssembly (client-side) |
| Authentication | Clerk |
| Database | Supabase (PostgreSQL) |
| Payments | Razorpay (multi-currency) |

For a detailed technical deep-dive, see [Tech Stack & Architecture](tech-stack.md).

---

## Links

- 🌐 [infiniteresume.com](https://www.infiniteresume.com)
- 📝 [Blog](https://www.infiniteresume.com/blog)
- 🚀 [Product Hunt](https://www.producthunt.com/products/infinite-resume)
- ⭐ [Trustpilot](https://www.trustpilot.com/review/infiniteresume.com)
