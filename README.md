# fullstack-ai-builder

> **Stop spending 3 weeks on boilerplate. Ship a working AI-powered full-stack app in a weekend.**

[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/g2445153409-lgtm/fullstack-ai-builder/pulls)
[![Made with Claude](https://img.shields.io/badge/Made%20with-Claude-orange.svg)](https://claude.ai)

---

## The Problem Nobody Talks About

You have an idea. A real one. Maybe it's an internal tool that would save your team 10 hours a week, or a SaaS you've been sketching in Notion for months.

Then you open a blank terminal and... nothing happens.

Not because you can't code. Because **the gap between "idea" and "deployed product" is filled with decisions nobody warned you about**: Which database? Which AI provider? How do I handle auth? Do I even need a backend?

Most tutorials skip straight to the fun part. This repo doesn't.

---

## What This Is

`fullstack-ai-builder` is a **battle-tested methodology** for shipping AI-powered full-stack applications — fast.

It's the distilled playbook from building dozens of internal tools and AI-integrated products, optimized for:

- 🧑‍💼 **Founders** who need to validate ideas before hiring engineers
- ⚡ **Indie hackers** who want to ship, not architect
- 🏢 **Teams** replacing Excel/WeChat workflows with real software
- 🤖 **AI-curious developers** who want to integrate LLMs without the headache

---

## The 3-Phase Framework

### Phase 1 — Clarify (30 min)
**The "Three Questions" method** that turns vague ideas into precise specs:

```
Q1: What repetitive task costs you time every week?     → Your pain point
Q2: What's the ONE feature that solves 80% of it?      → Your MVP
Q3: Who uses this — 1 person, 10, or 10,000?           → Your architecture
```

No code until you can answer all three. This single step saves weeks.

### Phase 2 — Design (30 min)
**Decision trees, not debates.**

```
Users < 3?        → Single HTML file + localStorage (zero infrastructure)
Users 4–50?       → Supabase (Postgres + auto-generated API, free tier)
Users 50–∞?       → Supabase now, migrate later (code barely changes)

Need AI?
├── Image/OCR     → Qwen-VL (fast in CN) or Gemini 1.5 Pro
├── Text/Extract  → DeepSeek Chat (90% cheaper than GPT-4, same quality)
└── Complex RAG   → Claude API
```

### Phase 3 — Ship (3–6 hours)
Single-file architecture. No build step. No `npm install`. Drag to Vercel, done.

---

## The Stack (Covers 90% of Projects)

| Layer | Choice | Why | Free Tier |
|-------|--------|-----|-----------|
| Frontend | Vanilla HTML + React (CDN) | Zero config, runs anywhere | ∞ |
| Database | Supabase | Postgres reliability, REST API auto-generated | 500MB |
| AI — Vision | Qwen-VL | Fast in mainland CN, generous free quota | 1M tokens/mo |
| AI — Text | DeepSeek Chat | Best price/performance ratio available today | Pay-as-you-go |
| Hosting | Vercel | Global CDN, drag-and-drop deploy | ∞ |
| CDN | Cloudflare | Wrap Vercel for CN speed boost | ∞ |

**First month cost: $0.** Seriously.

---

## Proven Project Patterns (Copy-Paste Ready)

### Meeting Notes → Action Items (2–3 days)
```
Pain:     Paper notes nobody reads
Stack:    HTML + Supabase + Qwen-VL (OCR) or DeepSeek (text extract)
AI role:  Extract action items, owners, deadlines from raw notes
Cost:     ~¥0–5/month in API calls
```

### Sales CRM (3–5 days)
```
Pain:     Customer data scattered across WeChat, Excel, email
Stack:    HTML + Supabase
AI role:  Optional — score lead temperature, suggest follow-up timing
Cost:     $0
```

### Internal Task Board (1–2 days)
```
Pain:     No single view of what's in progress
Stack:    HTML + Supabase (or localStorage for 1-person use)
AI role:  Not needed
Cost:     $0
```

---

## Getting Started

### 1. Answer the Three Questions
Write them down. Seriously. Don't skip this.

### 2. Pick Your Stack
Use the decision trees above. The answer is almost always "Supabase + DeepSeek."

### 3. Use the Prompt Template
```
I need to build a [system name] for [core use case].
Primary users: [description]. Current pain: [pain point].

Core features (max 2):
1. [Feature 1]
2. [Feature 2]

Tech constraints:
- Single HTML file
- React via CDN (no npm)
- Supabase backend (URL: xxx, Key: xxx)
- Mobile + desktop responsive
- [AI provider] for [specific task]

Data model:
- Main table: [name], fields: [list]
- Sub-table: [name], fields: [list]

Confirm you understand, then generate the complete code.
```

### 4. Test in 4 Phases
```
☐ Phase 1: Does the UI render? Check console for JS errors (F12)
☐ Phase 2: Does local storage read/write? Refresh and check persistence
☐ Phase 3: Does Supabase connect? Check Network tab for API responses
☐ Phase 4: Does AI return structured data in the expected format?
```

### 5. Deploy to Vercel
```
1. Go to vercel.com
2. Sign in with GitHub
3. Click "Add New Project" → "Upload"
4. Drag your index.html
5. Done. You have a public URL.
```

---

## AI Prompt Engineering (The Part Most Tutorials Skip)

### The Golden Rule
**Always constrain the output format before describing the task.**

```
❌ "Extract the action items from this meeting note"
✅ "Return ONLY a JSON array. Schema: [{text, owner, due_date, priority}].
    If a field is unclear, use null. No explanations, no markdown, just JSON.
    Task: extract action items from the following meeting note: ..."
```

The difference: one gives you prose, one gives you parseable data.

### Handling Errors Like a Senior Dev

| Symptom | Cause | Fix |
|---------|-------|-----|
| White screen | JS error blocking render | F12 → Console → read the red text |
| `null` from localStorage | `file://` protocol restriction | Use `memStorage` fallback |
| CORS error | Supabase RLS not configured | Enable Row Level Security in dashboard |
| AI returns 403 | Wrong API key or quota exceeded | Verify key, check billing dashboard |
| AI returns 429 | Rate limit hit | Add `setTimeout(fn, 1000)` retry |
| Mobile layout broken | Missing viewport meta | Add `<meta name="viewport" ...>` |

---

## Pre-Launch Checklist

```
☐ Core flow works end-to-end (input → AI → save → display)
☐ Data persists correctly across page refreshes
☐ Error states show user-friendly messages (not stack traces)
☐ Works in Chrome, Firefox, Safari
☐ Mobile layout has no horizontal scroll
☐ API keys are NOT hardcoded in frontend source
☐ Supabase RLS policies are enabled
☐ First load time < 3 seconds on a 4G connection
```

---

## The Mindset

> *"The best code is no code at all. The second best is simple code you completely understand."*

> *"Make it work. Make it right. Make it fast. In that order — and stop at step one if users are already happy."*

Your job is to **understand the problem deeply**. The AI's job is to write the implementation. This repo teaches you how to do the first part well enough that the second part almost handles itself.

---

## Contributing

Found a pattern that works? A stack combination that saved you time? Open a PR. This methodology improves with real-world data.

---

## License

MIT — use it, fork it, ship with it.

---

<p align="center">
  Built for people who ship. ⚡
</p>
