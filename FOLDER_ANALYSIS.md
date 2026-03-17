# AI Marketing Claude Main — Folder Structure & Analysis

## Executive Summary

This is a **Claude Code skill system** for marketing automation. It's a modular, production-ready toolkit that agencies and solopreneurs can use to audit websites, generate copy, build email sequences, create reports, and analyze competitors—all via Claude AI commands.

**Key Facts:**
- 37 total files across 6 main folders
- 14 specialized marketing skills
- 5 parallel analysis agents
- ~488 KB footprint
- MIT License (open source)

---

## Directory Structure Overview

```
ai-marketing-claude-main/
├── market/                      # Main orchestrator skill
├── skills/                      # 14 specialized sub-skills
├── agents/                      # 5 parallel analysis agents
├── templates/                   # Pre-built marketing templates
├── scripts/                     # Python utility scripts
├── README.md                    # Full documentation
├── install.sh                   # One-command installer
├── uninstall.sh                 # Clean uninstaller
├── requirements.txt             # Python dependencies
└── LICENSE                      # MIT License
```

---

## Folder-by-Folder Breakdown

### 1. **market/** — Main Orchestrator
**Purpose:** Routes all `/market` commands to the right sub-skill
**Files:**
- `SKILL.md` — Master skill that handles command parsing and routing

**What it does:**
- Acts as the entry point for all marketing commands
- Decides which sub-skill to trigger based on user input
- Example: `/market audit https://example.com` → launches audit skill

**Use case:** You never call individual skills directly; you use `/market [command]` in Claude Code

---

### 2. **skills/** — 14 Specialized Marketing Skills

Each skill in this folder handles one specific marketing task. All are modular and can run independently.

#### **Core Audit & Analysis Skills:**

| Skill | Purpose |
|-------|---------|
| `market-audit` | Runs 5 parallel agents to score a website across 6 dimensions (content, conversion, SEO, competition, brand, growth) |
| `market-competitive` | Analyzes competitor websites and positioning |
| `market-landing` | Conversion rate optimization (CRO) for landing pages |
| `market-funnel` | Sales funnel analysis and optimization |
| `market-seo` | On-page and technical SEO audit |

#### **Content & Copy Generation:**

| Skill | Purpose |
|-------|---------|
| `market-copy` | Generates optimized copywriting with before/after examples |
| `market-emails` | Creates complete email sequences (welcome, nurture, launch) |
| `market-social` | Builds 30-day social media content calendars |
| `market-ads` | Generates ad creative and copy for all platforms |
| `market-brand` | Analyzes brand voice and creates brand guidelines |

#### **Client-Ready Deliverables:**

| Skill | Purpose |
|-------|---------|
| `market-report` | Full marketing analysis report (Markdown) |
| `market-report-pdf` | Professional PDF reports for client delivery |
| `market-proposal` | Client proposal generator with custom findings |
| `market-launch` | Product launch playbook and checklist |

**Each skill contains:**
- `SKILL.md` — Detailed instructions for how Claude should analyze and generate content
- Clear scoring methodology
- Specific frameworks and criteria

**Example skill structure:**
```
market-audit/
└── SKILL.md (2,000+ lines explaining audit scoring, agent roles, output format)
```

---

### 3. **agents/** — 5 Parallel Analysis Agents

These Markdown files define the behavior of 5 specialized subagents that run simultaneously during a full audit.

| Agent | Analyzes |
|-------|----------|
| `market-content.md` | Content quality, messaging, value props, headlines, CTAs |
| `market-conversion.md` | Funnels, forms, social proof, friction points, urgency |
| `market-technical.md` | On-page SEO, technical SEO, tracking, structure |
| `market-competitive.md` | Market positioning, differentiation, alternatives |
| `market-strategy.md` | Pricing, acquisition channels, brand, growth potential |

**How they work:**
- Each agent gets specific instructions on what to analyze
- They run in parallel (not sequentially)
- Results are compiled into a single scored report
- Each agent produces a score (0-100) for its dimension

**Example:** `/market audit https://calendly.com` launches all 5 agents simultaneously, each scoring the site from their perspective.

---

### 4. **templates/** — Pre-Built Marketing Templates

Ready-to-use templates for common marketing scenarios:

| Template | What It Provides |
|----------|------------------|
| `email-welcome.md` | 5-email welcome sequence |
| `email-nurture.md` | 6-email lead nurture sequence |
| `email-launch.md` | 8-email product launch sequence |
| `proposal-template.md` | Client proposal framework |
| `content-calendar.md` | 30-day social media calendar |
| `launch-checklist.md` | Pre-launch checklist |

**Use case:** When generating emails or calendars, Claude uses these templates as starting points and customizes them for the client/product

---

### 5. **scripts/** — Python Utility Scripts

Automation scripts that handle technical analysis:

| Script | Purpose |
|--------|---------|
| `analyze_page.py` | Fetches and analyzes webpage marketing elements |
| `competitor_scanner.py` | Scans competitor websites automatically |
| `social_calendar.py` | Generates social media content calendars |
| `generate_pdf_report.py` | Creates professional PDF reports (requires reportlab) |

**Why they exist:**
- Some tasks are better handled by Python (web scraping, data extraction)
- Claude calls these scripts as needed during analysis
- They return structured data that Claude uses to generate insights

**Dependencies:**
- Requires Python environment
- Optional: `reportlab` for PDF generation

---

### 6. **Root Configuration Files**

| File | Purpose |
|------|---------|
| `README.md` | Full documentation with commands, scoring methodology, use cases |
| `install.sh` | One-command installer (copies skills to `~/.claude/skills/`) |
| `uninstall.sh` | Removes all installed skills cleanly |
| `requirements.txt` | Python dependencies (listed but minimal) |
| `LICENSE` | MIT License (open source, free to use and modify) |

---

## Scoring Methodology

The audit produces a single **Overall Marketing Score (0-100)** based on 6 weighted dimensions:

| Category | Weight | What It Measures |
|----------|--------|------------------|
| Content & Messaging | 25% | Copy quality, value props, headlines, CTAs |
| Conversion Optimization | 20% | Funnels, forms, social proof, friction |
| SEO & Discoverability | 20% | On-page SEO, technical SEO, structure |
| Competitive Positioning | 15% | Differentiation, market awareness |
| Brand & Trust | 10% | Design, trust signals, authority |
| Growth & Strategy | 10% | Pricing, acquisition, retention channels |

**Example output:**
```
✓ Content & Messaging         — Score: 72/100
✓ Conversion Optimization     — Score: 58/100
✓ SEO & Discoverability       — Score: 81/100
✓ Competitive Positioning     — Score: 64/100
✓ Brand & Trust               — Score: 76/100
✓ Growth & Strategy           — Score: 61/100

Overall Marketing Score: 69/100
```

---

## How It All Works Together

### User Flow:
1. User types `/market audit https://example.com` in Claude Code
2. Claude reads `market/SKILL.md` (orchestrator)
3. Orchestrator routes to `skills/market-audit/SKILL.md`
4. Audit skill launches 5 agents in parallel
5. Each agent analyzes the site from their perspective
6. Python scripts scrape/analyze page content
7. Results compiled into scored report
8. Output saved as Markdown (or PDF with `market-report-pdf`)

### Why This Architecture Works:
- **Modular:** Each skill is independent; you can use just one or all of them
- **Parallel execution:** 5 agents run simultaneously (faster analysis)
- **Reusable:** Templates and agents are used across multiple commands
- **Scriptable:** Python handles heavy lifting; Claude handles analysis
- **Client-ready:** PDF reports are polished, professional deliverables

---

## Pros & Cons

### ✅ Pros

**For Agencies:**
- Complete marketing analysis in one command
- Professional PDF reports for client delivery
- Save hours of manual analysis
- Consistent methodology across audits

**For Solopreneurs:**
- Audit own sites quickly
- Generate copy/emails/social calendars automatically
- Launch products systematically
- No monthly SaaS fees

**Technical:**
- Lightweight (~488 KB)
- MIT licensed (open source)
- Modular architecture (use what you need)
- Works offline (no API keys needed)
- Runs via Claude Code CLI

### ❌ Cons

**Limitations:**
- Requires Claude Code to run (not a standalone tool)
- Python-dependent for some features (analyze_page.py, etc.)
- Results quality depends on Claude model capabilities
- Website analysis is text-based (no visual design scoring)
- No built-in competitor tracking (snapshot only)

**Setup:**
- Installation requires command line knowledge
- Python environment setup needed for full features
- PDF generation requires additional dependency (reportlab)

**Analysis Depth:**
- Agent scores are AI-generated (not from live analytics data)
- No integration with Google Analytics, Hotjar, etc.
- Competitive analysis is limited to public information

---

## Use Cases

### **For Marketing Agencies:**
- Pre-sales audit: `/market audit` before pitch calls
- Client proposals: `/market proposal [client]` with specific findings
- Deliverables: `/market report-pdf [url]` for professional client reports
- Competitive research: `/market competitors [competitor_url]`

### **For Solopreneurs/Founders:**
- Self-audit: Identify weak points in own marketing
- Launch planning: `/market launch [product]` for playbook
- Content creation: `/market emails [topic]` for email sequences
- Social media: `/market social [topic]` for 30-day calendar

### **For Content Creators:**
- Copy optimization: `/market copy [url]` before publishing
- SEO analysis: `/market seo [url]` to improve discoverability
- Brand development: `/market brand [url]` for voice/guidelines
- Funnel analysis: `/market funnel [url]` to improve conversions

### **For Agencies Building AI Services:**
- White-label audit tool (rebrand and resell)
- Template for building other AI skill systems
- Reference for skill architecture best practices

---

## File Count & Sizes

```
Total Files:     37
Total Size:      488 KB

Breakdown:
├── Skills (.md files):      14 SKILL.md files
├── Agents (.md files):      5 files
├── Templates (.md files):   6 files
├── Scripts (.py files):     4 files
├── Config files:            3 (.sh, .txt, LICENSE)
└── Documentation:           1 (README.md)
```

---

## Installation & Distribution

### Quick Start:
```bash
# One-command install
curl -fsSL https://raw.githubusercontent.com/khalidgraphy/ai-marketing-km/main/install.sh | bash

# Or manual
git clone https://github.com/khalidgraphy/ai-marketing-km.git
cd ai-marketing-claude
./install.sh

# Optional: PDF support
pip install reportlab
```

### Uninstall:
```bash
./uninstall.sh
# Or manual: rm -rf ~/.claude/skills/market*
```

---

## Technology Stack

**Languages:**
- Markdown (skill definitions, templates)
- Python (automation scripts)
- Bash (installation/uninstall)

**Dependencies:**
- Claude Code CLI
- Python 3.6+
- Optional: reportlab (PDF generation)

**No external APIs required** — everything runs locally via Claude

---

## Summary

This is a **production-grade AI marketing skill system** designed for people who want to automate marketing analysis and content generation. It's:

- ✅ Lightweight and modular
- ✅ Open source (MIT licensed)
- ✅ Ready to use or rebrand
- ✅ Architecturally sound (parallel agents, specialized skills)
- ✅ Professional output (scored reports, PDF deliverables)
- ❌ Requires Claude Code (not standalone)
- ❌ Some setup/CLI knowledge needed

**Best for:** Agencies, solopreneurs, marketers who use Claude and want to automate audits, copy, emails, and reporting.

**Not for:** People who need visual design analysis, real-time analytics integration, or standalone GUI tools.
