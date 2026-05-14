# TradeShadow

A personalised AI market analysis tool for forex traders. TradeShadow learns the way you trade — your pairs, sessions, setups, and timing — then scans 50+ currency pairs for matches in your style. It surfaces setups; it does not give signals or advice. The decision is always yours.

> **Status:** Prototype. Front-end only. No live broker connection, no real-time data feed. Sample profiles are bundled for exploration.

## What it does

- **Analyse Style** — paste an MT4/MT5 trade history (or load one of 8 sample profiles) and TradeShadow builds a Strategy DNA profile: dominant setups, preferred pairs, session windows, average hold time, and risk/reward.
- **Scanner** — once a profile exists, the scanner generates matching setups across forex majors and minors, with each card showing a match score broken down by which of your DNA traits the setup satisfies.
- **Strategy DNA** — analytical breakdown of your trading: pattern frequency, session distribution, pair performance, weekly rhythm. Filterable by week / month / all-time.
- **Discipline** — compares recent trades against your DNA and flags deviations (out-of-session trades, low R:R wins, drift from your top setups).
- **My Journal** — chart-based trade journal with TradingView mini-charts, structured tagging, and AI-suggested confluences.
- **Practice Mode** — pick a style template, then make take/skip decisions on 12 mixed setups; the system builds a DNA from your decisions.
- **Playbook** — a strategy library with the mechanics behind each setup (FVG, AOI, SMA confluence, liquidity sweeps, flag patterns, inducement, supply/demand).
- **Macro Brief** — central bank stances, key economic indicators, and the fundamental drivers that move the eight major currencies.
- **Live News & Calendar** — news feed and economic calendar with impact tagging.
- **Market Windows** — live session clocks, 24-hour timeline highlighting prime trading windows.
- **Risk Settings** — position sizing, max daily risk, lot cap, prop firm mode.

## Architecture

A single self-contained `index.html` (~13k lines) with all CSS, JS, and sample data inlined. No build step, no server, no dependencies — open it in a browser and it runs.

The only external dependencies (loaded from CDN at runtime):
- TradingView widget for chart embedding
- Google Fonts (Cormorant Garamond, Jost, JetBrains Mono)
- Anthropic API (optional — used by AI Style Learning and the help chatbot; falls back to a deterministic parser if unavailable)

Why one file? Easier to share, easier to host on GitHub Pages, and the project is a prototype demonstrating the product concept rather than a production stack.

## Run locally

```bash
git clone <repo-url>
cd tradeshadow
open index.html   # or just double-click it
```

For GitHub Pages: push to `main`, enable Pages from `/ (root)`, and the live URL will serve `index.html` directly.

## Sample profiles

Eight bundled profiles (A–H) demonstrate distinct trading styles:

| ID | Style | Pairs | Session | WR | RR |
|----|-------|-------|---------|----|-----|
| A | Area of Interest Trader | GBP · EUR · JPY | London 08–12 GMT | 89% | 1:3.5 |
| B | Supply & Demand Trader | XAU · GBP · EUR | London 09–17 GMT | 83% | 1:3.2 |
| C | Fair Value Gap Trader | JPY · AUD · NZD | Asian 01–06 GMT | 67% | 1:2.0 |
| D | Liquidity Hunter | GBP · EUR · CAD | NY Extension 14–17 GMT | 78% | 1:2.6 |
| E | Fibonacci Confluence | EUR · GBP · AUD | London multi-day | 61% | 1:3.8 |
| F | Flag Pattern Trader | GBP/USD · JPY · AUD | London 08–17 GMT | 83% | 1:3.0 |
| G | SMA Confluence | EUR · GBP | London 07–11 GMT | 78% | 1:1.9 |
| H | Inducement Sniper | EUR · GBP · CAD · CHF | London 08–17 GMT | 72% | 1:4.0 |

Each profile has 18 trades, 10 deep journal entries, and produces a distinct scanner output, DNA, and discipline report.

## Browser support

Tested on Chrome / Edge / Safari. Mobile-responsive from 380px upward. Installable as a PWA (manifest + icon embedded inline).

## Disclaimer

TradeShadow does not provide financial advice. It does not predict markets, generate signals, or place trades. It is a tool for traders who already have a strategy and want to scale their own analysis across more pairs.

The sample data is fictional. Any resemblance to real trades is coincidental.

## License

This is a final-year industry project (academic prototype). Not licensed for commercial use without permission.
