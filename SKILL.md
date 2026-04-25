# fullstack-ai-builder Skill

## What This Skill Does

This skill guides you through building and shipping AI-powered full-stack web applications — fast. It covers the complete path from idea to deployed product using a battle-tested 3-phase methodology.

**Invoke this skill when users want to:**
- Build a web app or internal tool from scratch
- Integrate AI APIs (OpenAI, DeepSeek, Qwen, Claude, Gemini) into a product
- Ship a working prototype quickly without a dedicated engineering team
- Choose between tech stack options (database, hosting, AI provider)
- Design a data model for a new application
- Deploy a frontend application to Vercel, Netlify, or GitHub Pages

## The 3-Phase Framework

### Phase 1 — Clarify (30 min)
Use the **Three Questions Method**:
1. What repetitive task costs the user time every week? → Pain point
2. What's the ONE feature that solves 80% of it? → MVP scope
3. Who uses this — 1 person, 10, or 10,000? → Architecture decision

### Phase 2 — Design (30 min)
Use decision trees to pick the right stack:

**By user count:**
- 1–3 users → Single HTML file + localStorage (zero infrastructure)
- 4–50 users → Supabase (Postgres + auto REST API, free tier)
- 50+ users → Supabase now, custom backend later

**By AI need:**
- Image/OCR → Qwen-VL or Gemini 1.5 Pro
- Text extraction/structuring → DeepSeek Chat (best price/performance)
- Complex reasoning → Claude API or GPT-4o

### Phase 3 — Ship (3–6 hours)
Generate a single HTML file with React (CDN), connect to Supabase if needed, test in 4 phases, deploy to Vercel.

## Recommended Tech Stack

| Layer | Choice | Free Tier |
|-------|--------|-----------|
| Frontend | Vanilla HTML + React via CDN | ∞ |
| Database | Supabase | 500MB |
| AI (vision) | Qwen-VL | 1M tokens/mo |
| AI (text) | DeepSeek Chat | Pay-as-you-go |
| Hosting | Vercel | ∞ |

## Key Prompt Templates

### Initial Request Template
```
I need to build a [system name] for [core use case].
Users: [description]. Pain point: [pain point].

Core features (max 2):
1. [Feature 1]
2. [Feature 2]

Tech: Single HTML file, React CDN, Supabase, [AI provider] for [task].

Data model:
- Main table: [name], fields: [list]
- Sub-table: [name], fields: [list]

Generate complete code.
```

### AI Output Format Template
```
Return ONLY a JSON array. Schema: [{field1, field2, field3}].
If a field is unclear, use null. No explanations, no markdown, just JSON.
Task: [describe the extraction task]
Input: [the actual content]
```

### Bug Fix Template
```
Problem: Clicking [button] expected [result] but got [actual result]
Error: [console error message]
Location: around function [function name]
Fix only the broken part, preserve everything else.
```

## 4-Phase Testing Protocol

```
Phase 1: Does the UI render? Check F12 console for JS errors
Phase 2: Does localStorage read/write? Refresh and check persistence
Phase 3: Does Supabase connect? Check Network tab for API responses
Phase 4: Does AI return structured data in the expected format?
```

## Common Error Quick-Reference

| Error | Cause | Fix |
|-------|-------|-----|
| White screen | JS error blocking render | F12 → read red text |
| null from localStorage | file:// protocol | Use memStorage fallback |
| CORS error | Supabase RLS not set | Enable RLS in dashboard |
| AI 403 | Bad API key | Check key and billing |
| AI 429 | Rate limit | Add setTimeout(fn, 1000) |

## Pre-Launch Checklist

- [ ] Core flow works end-to-end
- [ ] Data persists across refreshes
- [ ] Errors show friendly messages
- [ ] Works in Chrome, Firefox, Safari
- [ ] Mobile layout OK (no horizontal scroll)
- [ ] API keys NOT hardcoded in frontend
- [ ] Supabase RLS enabled
- [ ] Load time < 3s on 4G

## Deploy in 5 Minutes (Vercel)

1. Go to vercel.com
2. Sign in with GitHub
3. Click "Add New Project" → "Upload"
4. Drag your index.html
5. Get a public URL immediately

## Cost Estimate

**Month 1: $0** — Vercel free, Supabase free tier, AI free quotas
**After users pay:** User revenue covers infrastructure costs

## Philosophy

> "Make it work. Make it right. Make it fast. In that order — stop at step one if users are happy."

Your job: understand the problem deeply.
AI's job: write the implementation.
This skill: bridges the gap.
