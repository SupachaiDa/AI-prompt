# Portfolio Analysis — Reusable AI Prompt Kit

Paste one of these prompts into a fresh session with an AI assistant that has **web search + file-creation** abilities, and attach the files noted. Three prompts:

1. **Full quarterly refresh** — rebuilds the whole analysis with fresh data (use after earnings season).
2. **Quick price & valuation update** — light touch (use monthly / between earnings).
3. **Add a new holding** — slots one new stock into the existing format.

Usage tips are at the bottom. **Always tell the AI today's date** and **insist it web-searches** — otherwise it will hand you stale numbers from its training data.

---

## PROMPT 1 — Full quarterly refresh

```
You are a professional equity research analyst and portfolio manager. Today's date is [INSERT TODAY'S DATE].

I've attached:
1. My holdings file (tickers, share counts/Volume, Cost, and my own target/catalyst notes).
2. My current analysis file — reproduce its exact format.

GOAL: Produce an UPDATED analysis Excel file in the same format, with fully refreshed data, plus a short written summary of what changed.

IMPORTANT: Prices, financials, catalysts, ownership and macro conditions change constantly — DO NOT rely on your training data. Web-search to verify every current figure. Prefer primary sources (latest 10-Q/10-K/6-K, earnings releases, company IR pages) and reputable financial data sites, and note the source/date for key numbers. This is research to support my own decisions, not personalized investment advice, and you are not my advisor.

STEP 1 — Read my holdings file. Extract the current ticker list, company names, share counts and cost basis. If I've added or removed positions, mirror that (add/drop rows). Treat any ETF (e.g., SCHD) as "n/a — fund," not a single-company analysis.

STEP 2 — Establish the current macro backdrop with a few searches: the central-bank policy rate and stance (e.g., the Fed), the latest inflation print, and the main geopolitical/sector themes affecting these holdings. Fold this into each "Macro & industry" cell.

STEP 3 — For EACH ticker, search for the latest:
- Most recent quarterly results: total revenue, revenue BY SEGMENT (with % split), net income/profit, adjusted EBITDA, gross margin.
- Balance sheet: cash & equivalents, total debt, quarterly cash burn or free cash flow, and any runway guidance.
- Guidance and upcoming catalysts WITH DATES (earnings dates, product launches, clinical readouts, deal closes, listings).
- Dilution signals: share-count trend, ATM programs, convertibles, stock-funded M&A, buybacks.
- Ownership: founder/CEO stake and voting control; notable institutional/fund holders and star investors (e.g., ARK/Cathie Wood, SoftBank, private-equity sponsors, strategic corporates) — or note if it's retail-driven / passive-only.
- Current share price (with date) and analyst consensus price target.
- Valuation multiples appropriate to the company type (P/E, PEG, EV/EBITDA, EV/Sales, P/B, EV-vs-cash, etc.).

STEP 4 — Write ONE ROW PER TICKER with these columns, IN THIS ORDER and IN THESE EXACT FORMATS:

A. Ticker
B. Company
C. Sector / theme
D. "1. Revenue by segment (% of revenue: current $ / upcoming)" — one line per segment as "~X% [Segment]: today ~$Y/qtr (or /yr)", then a final line "Upcoming: [what scales and when]".
   Example:
   ~68% Space Systems: today ~$137M/qtr.
   ~32% Launch (Electron + HASTE): ~$64M/qtr.
   Upcoming: Neutron rocket opens a new customer tier (H2/2026).
E. "2. Catalysts — ordered by date, with est. stock-price impact (0-10)" — first line "Ordered by date (impact /10):" then bullet lines "• [Date] – [event] – [0-10]", EARLIEST FIRST. Impact = your subjective estimate of how much the event could move the share price (EITHER direction), NOT the probability it happens.
   Example:
   • ~Aug 2026 – Q2 earnings – 4
   • H2 2026 – NEUTRON maiden launch – 9
F. "3. Financial health — does it have enough cash?" — LEAD with a one-word verdict in caps (STRONG / VERY STRONG / HEALTHY / ADEQUATE / ADEQUATE BUT LEVERAGED / CASH-RICH / BURNING CASH / TIGHT / STRETCHED), then the key numbers (cash, burn or FCF, debt) and a plain answer on whether it must raise capital.
   Example: "TIGHT — the weakest here. Only ~$145M cash vs a $76M quarterly loss; depends on continued equity raises."
G. "4. Dilution risk" — LOW / MODERATE / HIGH (or NEGATIVE if buying back) + a one-line reason.
H. "5. Key leaders & their stake" — founder/CEO and whether they hold voting control (super-voting shares), plus major holders; THEN a separate line beginning "Funds / famous investors:" naming notable funds/star investors (ARK/Cathie Wood, SoftBank, PE sponsors, strategic corporates) — or state "retail-driven / passive-only (Vanguard/BlackRock)".
I. "6. Macro & industry trend" — how the current macro (rates, inflation, geopolitics, sector cycle) affects THIS name; explicitly flag its rate-sensitivity.
J. "7. Competition" — main competitors and the company's position.
K. "Approx. price (~[DATE])" — current share price with date; note if volatile. UPDATE the header date.
L. "Valuation method" — the method appropriate to THIS company type: P/E + PEG for profitable growth; EV/EBITDA; EV/Sales for unprofitable-but-revenue; EV-vs-cash for pre-revenue; rNPV/pipeline for clinical-stage biotech; P/E + P/B for financials/brokers.
M. "Valuation view (over / under / fair)" — LEAD with OVERVALUED / FAIRLY VALUED / UNDERVALUED / SPECULATIVE, then the key metric value and a one-line rationale (vs its own history, peers, growth rate, or analyst consensus).

STEP 5 — PRESERVE MY HOLDINGS COLUMNS. My file has extra columns to the right of the analysis (Volume, Cost, Total Value). Do NOT overwrite or delete them — refresh only the analysis columns A–M and keep my holdings columns in place unchanged.

STEP 6 — Add a portfolio-level summary (a short section below the table AND in your chat reply): diversification read (concentration by single name and by theme), an approximate performance read (current price vs my cost per position, and overall), and the top 2–3 things to watch.

FORMATTING & STYLE (match the existing file):
- Font Arial 10. Row 1 = title. Row 2 = a dated disclaimer (data-as-of date; prices point-in-time; "analysis, not personalized investment advice"; "catalyst impact 0-10 is a subjective estimate of share-price reaction").
- Header row (row 3): navy fill (#1F3B57), white bold text, wrapped, centered.
- Data cells: wrapped text, top-aligned; a light sector-based fill; thin borders; no gridlines; freeze panes at D4; row height ~200.
- Keep every cell concise.

OUTPUT: a single .xlsx with an "Analysis" tab, presented as a downloadable file, plus a short written summary of what changed since the previous version (biggest price movers, new catalysts, any rating changes).
```

---

## PROMPT 2 — Quick price & valuation update (between earnings)

```
You are an equity analyst. Today's date is [INSERT TODAY'S DATE]. Attached is my stock analysis Excel file.

Do a LIGHT refresh only — web-search current data, don't use training-data prices:
1. For every ticker, look up the current share price and the latest analyst consensus target.
2. Update (a) the "Approx. price" column and its header date, and (b) the "Valuation view" column — keep the SAME valuation method, just re-judge over/under-valued against the new price and any changed multiples.
3. In your chat reply, FLAG any holding whose financial health or catalyst status has MATERIALLY changed since the file's "data as of" date — e.g., a new earnings report, a big capital raise, or a catalyst that has now occurred — so I know whether a full refresh is warranted.
Leave all other columns unchanged. Return the updated .xlsx.
```

---

## PROMPT 3 — Add a new holding

```
You are an equity analyst. Today's date is [INSERT TODAY'S DATE]. Attached is my stock analysis Excel file.

I'm adding [TICKER(S)]. Web-search current data and add one row per new ticker in the EXACT same 13-column format as the existing rows:
Ticker · Company · Sector · (1) Revenue by segment "~X%: today ~$Y" + Upcoming · (2) Catalysts ordered by date with impact 0-10 · (3) Financial-health verdict (STRONG/…/TIGHT) + does it have enough cash · (4) Dilution risk · (5) Key leaders & stake + a "Funds / famous investors:" line · (6) Macro & industry · (7) Competition · Approx. price (dated) · Valuation method (appropriate to the company type) · Valuation view (over/under/fair + rationale).
Match the existing styling and keep every other row and my holdings columns unchanged. Return the updated .xlsx.
```

---

## Usage notes

- **State today's date** in the prompt every time — assistants often assume a stale date, which corrupts "current price," catalyst timing, and macro.
- **Attach both files** for a full refresh: your holdings file (for the ticker list + cost basis) and the latest analysis file (for the format). For quick updates, just the analysis file.
- **Insist on web search / cite sources.** Without live search the output is stale. Asking for the source + date on key figures lets you spot-check.
- **When to run which:**
  - *Full refresh* — after each earnings season (roughly early Aug, early Nov, mid-Feb, early May) or when a big catalyst lands.
  - *Quick update* — monthly, or any time you just want fresh prices and an over/under read.
- **Impact scores are subjective and symmetric** — a "9" means high potential to move the stock, up OR down (e.g., a rocket launch or a clinical readout), not a prediction of direction or a probability.
- **Valuation is a directional view, not a price target,** and none of this is personalized investment advice — treat it as a research scaffold for your own judgment.
- **Tweak freely:** add columns (e.g., an "ownership type" tag, or a separate likelihood-vs-impact split), change the verdict vocabulary, or ask for a companion timeline chart.
```
