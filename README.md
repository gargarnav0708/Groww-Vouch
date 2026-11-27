# Groww Vouch

> **Cut through market hype. Verify what management promised against what they actually delivered before you buy.**

Groww Vouch is a mobile-first stock diligence companion built for retail investors. 

---

### The Origin & Problem

Every month, millions of first-time retail investors in India enter the equity markets. Too many of them end up burning their hard-earned savings. 

They don't lose money because they lack ambition; they lose money because **information discovery in public markets is broken**:
1. **The noise trap:** Social media, Telegram channels, and speculative tips encourage emotional buying without any understanding of the underlying business.
2. **The diligence barrier:** Reading 100-page Annual Reports and 25-page earnings call transcripts takes hours and requires financial expertise that everyday investors don't have.
3. **The accountability gap:** Management teams frequently make ambitious guidance statements on concalls, but retail investors have no easy way of knowing whether those targets were ever met or quietly abandoned.

**Groww Vouch fixes this in 60 seconds.** Before an investor places a trade on a tip or impulse, Vouch gives them verified, bite-sized truth directly from official filings.

---

### Core Product Capabilities

#### 1. "Did They Keep Their Word?" (Promised vs. Delivered)
- Finds the company's last 4 quarterly earnings call transcripts.
- Extracts explicit forward-looking management guidance (growth targets, margin promises, capex plans).
- Compares those promises against actual delivered financials, grading management's credibility with a verified scorecard.
- **Rule:** Every promise is grounded verbatim in the transcript; every verdict links directly to the cited PDF page.

#### 2. "The Numbers That Matter" (Quarterly Results in 10 Seconds)
- When quarterly results are released, Vouch parses the filing and surfaces the core numbers: **Revenue, EBITDA, PBT, and PAT**, alongside quarter-on-quarter (QoQ) and year-on-year (YoY) momentum.
- **Verify, don't trust:** Numbers are mechanically checked before they appear on screen. The math must reconcile mathematically (`PBT − Tax = PAT`) across all columns, or the card is flagged as unverified.

#### 3. "What Changed Today" (Swipeable Daily Digest)
- Ingests end-of-day market movements and raw exchange announcements across a user's watchlist.
- Triages filings into an explainable 17-category taxonomy, filtering out routine compliance paperwork and surfacing material developments on swipeable cards.
- On top management changes (CEO/CFO), Vouch automatically pulls the incoming executive's professional bio directly from the regulatory filing.

#### 4. Ask Vouch (Contextual Diligence Copilot)
- Available on every screen to answer questions like: *"Why did profit drop this quarter?"* or *"Did management guide on margins?"*
- Answers are strictly grounded in indexed company disclosures with clickable citations.

---

### How to Run Locally

#### Prerequisites
- Python 3.10 or later
- Internet access for live exchange and market data

#### Quickstart
```bash
# 1. Clone repository
git clone https://github.com/gargarnav0708/Groww-Vouch.git
cd Groww-Vouch

# 2. Set up virtual environment
python3 -m venv .venv
source .venv/bin/activate

# 3. Install dependencies
pip install -r backend/requirements.txt

# 4. Start local server
python3 -m uvicorn backend.app.main:app --host 127.0.0.1 --port 8001
```

Open `http://127.0.0.1:8001` in your browser (mobile view recommended) or on your phone via your local Wi-Fi IP.

---

### Testing & Evals

The application includes an automated test suite of **72 pytest unit tests** verifying data pipeline ingestion, mechanical validation checks, token budgeting, prompt failovers, and quote grounding:

```bash
pytest backend/tests/
```
All 72 tests pass.
