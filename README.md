# Claude Market Skills by KM — by Kreative Minds

Type a simple command in [Claude Code](https://docs.anthropic.com/en/docs/claude-code) and get a full marketing analysis in minutes — no agency, no expensive tools, no technical skills needed. Audit any website, generate copy, write email sequences, build social media calendars, analyze competitors, and produce professional PDF reports, all from your terminal.

**Made by [Kreative Minds](https://kreativeminds.ae) — free to use for personal projects, perfect for freelancers, founders, and anyone who wants professional marketing output without the agency price tag.**

---

## What This Does

Type a command in Claude Code and get instant, actionable marketing analysis. Here are real examples you can try right now:

**Audit a website:**
```
> /market audit https://kreativeminds.ae

Launching 5 parallel agents...
✓ SEO analysis complete — 14 issues found
✓ Page speed: 68/100 — needs improvement
✓ Copy analysis: Headlines weak, CTAs unclear
✓ Competitor gap: 3 rivals outranking on key terms
✓ PDF report saved → reports/kreativeminds-audit.pdf
```

**Generate website copy:**
```
> /market copy https://khalidgraphy.com --tone professional

Analyzing site structure...
✓ Hero headline: "Turn Visitors Into Clients — Without Rewriting Everything"
✓ About section rewritten for clarity
✓ 3 CTA variations generated
✓ Copy file saved → output/khalidgraphy-copy.md
```

**Write an email sequence:**
```
> /market email "Social media management for small businesses" --emails 5

Writing 5-email nurture sequence...
✓ Email 1: Welcome + value hook
✓ Email 2: Pain point story
✓ Email 3: Case study / social proof
✓ Email 4: Objection handling
✓ Email 5: Clear offer + CTA
✓ Saved → output/email-sequence.md
```

**Analyze competitors:**
```
> /market compete https://kreativeminds.ae

Scanning market landscape...
✓ Top 5 competitors identified
✓ Their keywords, pricing & positioning mapped
✓ Your gaps and opportunities listed
✓ Report saved → reports/competitor-analysis.pdf
```

**Build a social media calendar:**
```
> /market social "Digital marketing agency Dubai" --days 30

Planning 30-day content calendar...
✓ 30 post ideas generated (LinkedIn, Instagram, X)
✓ Best posting times per platform
✓ Hashtag strategy included
✓ Calendar saved → output/social-calendar.md
```

---

## How It Works

When you run a command, Claude Code launches multiple specialized AI agents working in parallel — each one focusing on a different part of the analysis.

**Step 1 — You type a command** in your terminal (examples above). No forms, no dashboards, no logins.

**Step 2 — Agents go to work.** Depending on the command, Claude Code will:
- Crawl the target website and read its content
- Score SEO, page speed, copy quality, and UX
- Search for competitor sites and compare them side by side
- Generate rewritten copy, email drafts, or a content calendar
- Run a scoring system that shows you a 0–100 readiness score

**Step 3 — You get a report.** Results are saved as Markdown files and PDF reports in an `output/` or `reports/` folder. You can open, share, or edit them like any document.

**Step 4 — Use the output.** Copy the email sequence into Mailchimp. Paste the website copy into your CMS. Share the competitor report with your team. Everything is in plain language — no jargon.

No coding knowledge is required. If you can type, you can use this.

---

## What You Get

| Command | What It Produces |
|---|---|
| `/market audit [url]` | Full website audit with SEO, copy, speed, and UX scores |
| `/market copy [url]` | Rewritten headlines, CTAs, and page copy |
| `/market email "[topic]"` | 5–7 email nurture sequence ready to send |
| `/market compete [url]` | Competitor comparison with gap analysis |
| `/market social "[topic]"` | 30-day social media calendar with post ideas |
| `/market report [url]` | All of the above combined into one PDF report |

---

## Who Is This For?

- **Freelancers** who want to deliver agency-level audits to clients without the overhead
- **Founders** who need to understand why their website isn't converting
- **Marketing teams** who want to move faster without adding headcount
- **Consultants** who want to add professional reports to their service offering
- **Anyone** curious about AI-powered marketing tools

Tested on real websites including [kreativeminds.ae](https://kreativeminds.ae) and [khalidgraphy.com](https://khalidgraphy.com).

---

## How to Install

**Step 1** — Make sure you have [Claude Code](https://docs.anthropic.com/en/docs/claude-code) installed and working.

**Step 2** — Clone this repo:
```bash
git clone https://github.com/khalidgraphy/claude-market-skills-by-KM.git
cd claude-market-skills-by-KM
```

**Step 3** — Run the install script:
```bash
chmod +x install.sh
./install.sh
```

**Step 4** — Start Claude Code and try a command:
```bash
> /market audit https://yourwebsite.com
```

That's it. The skills are now loaded and ready to use.

---

## File Structure

```
claude-market-skills-by-KM/
├── market/              ← Main entry skill (start here)
│   └── SKILL.md
├── skills/              ← Individual skill modules
│   ├── market-audit/
│   ├── market-copy/
│   ├── market-email/
│   ├── market-social/
│   └── market-compete/
├── agents/              ← AI agent definitions
│   ├── market-content.md
│   └── market-competitive.md
├── scripts/             ← Python helpers for PDF and scoring
├── templates/           ← Report templates
├── install.sh           ← One-command setup
└── README.md
```

---

## License

**Non-Commercial Use Only.**

You may use, copy, and modify these files for personal and non-commercial projects. You may not sell this work, include it in paid products, or remove the copyright notice.

© Kreative Minds. All rights reserved. Credit must be kept.

See the [LICENSE](./LICENSE) file for full terms.

---

## Built By

**[Kreative Minds](https://kreativeminds.ae)** — A creative marketing studio based in Dubai helping businesses grow with smart, practical tools.

Follow the work: [khalidgraphy.com](https://khalidgraphy.com)
