# Brand Strategy Analyzer

### AI-Driven Brand Intelligence Engine

> From raw consumer data to comprehensive brand strategy and 100-post content calendars -- powered by LLM analysis, web crawling, and automated quality review.

---

## Why This Exists

Brand strategy consulting traditionally costs tens of thousands of dollars and takes weeks. It requires consumer research, competitive analysis, positioning workshops, and content planning -- all done manually by teams of strategists and creatives.

This project compresses that entire workflow into an AI-powered pipeline. Feed it a brand brief, and it orchestrates web crawling, consumer sentiment analysis (including 18,700+ Dcard discussion posts), LLM-driven strategy generation, and iterative quality review. The output is not a vague summary -- it is a production-ready brand strategy with consumer pain point analysis, positioning frameworks, multi-concept creative directions, and a detailed 100-post content calendar complete with hooks, captions, hashtags, and engagement predictions.

Built from 15+ years of agency experience at Ogilvy, translated into reproducible AI systems.

---

## Architecture

```
Brand Brief Input
       |
  LLM Interactive Briefing
  (brand, product, audience, goals)
       |
  +----+----+
  |         |
URL Planner    Dcard Crawler
(SerpAPI       (Playwright + anti-detection
 search)        + 18,700+ post analysis)
  |         |
  +----+----+
       |
  Raw HTML Storage (local-first, gzip)
       |
  Trafilatura Content Extraction
       |
  LLM Analysis Engine
  (brand positioning, consumer insights)
       |
  Quality Review & Optimization
  (automated scoring + second-pass refinement)
       |
  +----+----+----+
  |    |    |    |
Brand  Consumer  Content   Final
Strategy Positioning Strategy Report
Report   Analysis    (100-post (Markdown
(HTML)   (HTML)      calendar)  + HTML)
       |
  Firestore Storage
  (tasks, briefs, URL plans)
```

### Delivered Outputs (Real Project Example)

| Deliverable | Description |
|-------------|-------------|
| **Brand Strategy Report** | Complete positioning analysis with 3 distinct creative directions, taglines in English and Chinese, brand voice guidelines |
| **Consumer Positioning Analysis** | Deep-dive into target audience pain points, purchase drivers, and emotional triggers based on 18,700+ social discussions |
| **100-Post Content Calendar** | Full Instagram content strategy with data-backed topic selection, keyword heat mapping, engagement predictions, and audience pain point alignment |
| **Final Report** | End-to-end documentation of methodology, findings, and strategic recommendations |

### Sample Strategy Output

The system generated three complete brand concepts for a lifestyle brand:

- **Concept A** -- "Design the Invisible": Positioning around intangible value and sensory experience
- **Concept B** -- "Recharge Your Soul": Mental wellness and digital detox positioning
- **Concept C** -- "Scent of Living": Experience curation and lifestyle editorial positioning

Each concept includes headline, body copy, category taglines, and deployment recommendations.

---

## Core Modules

| Module | Purpose |
|--------|---------|
| **MarketSense Engine** | Full pipeline: crawling, analysis, quality review, optimization |
| `briefing.py` | Interactive or automated LLM brief generation |
| `crawler.py` | Playwright-based web scraping with anti-detection (stealth, dynamic UA rotation, human behavior simulation) |
| `analyzer.py` | LLM-powered content analysis and strategy extraction |
| `quality_review.py` | Automated quality scoring with second-pass optimization |
| `url_planner.py` / `url_search.py` | SerpAPI integration for research URL generation |
| `dcard_crawler.py` | Specialized Dcard social platform crawler with authenticated sessions |
| `reporting.py` / `main_dashboard.py` | Statistics dashboard: block rates, latency, quality scores |
| `task_queue.py` | Firestore-backed task management with lease locking |

---

## Tech Stack

| Layer | Technology |
|-------|------------|
| **LLM Engine** | GPT-4 / Claude (configurable) |
| **Web Crawling** | Playwright, playwright-stealth, Trafilatura |
| **Anti-Detection** | Dynamic User-Agent rotation, WebGL spoofing, mouse trajectory simulation, adaptive throttling |
| **Data Storage** | Firebase Firestore, local raw HTML (gzip) |
| **Search** | SerpAPI (real search results for URL planning) |
| **Orchestration** | GitHub Copilot SDK multi-agent workflows |
| **Testing** | pytest (17 tests covering parsing, reports, briefs, URL planning, quality review) |

---

## Quick Start

```bash
# Install dependencies
cd brand-strategy-analyzer
pip install -r requirements.txt
playwright install

# Run interactive brand briefing
python -m marketsense.main_brief

# Plan research URLs via real search
python -m marketsense.main_url_planner

# Execute full pipeline (crawl + analyze + quality review)
python -m marketsense.run_pipeline

# Generate dashboard
python -m marketsense.main_dashboard
```

---

## Author

**Huang Akai (Kai)** -- Founder @ Universal FAW Labs | Creative Technologist | Ex-Ogilvy | 15+ years experience

---

## License

MIT
