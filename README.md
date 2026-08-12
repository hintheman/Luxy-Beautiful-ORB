# Luxy Beautiful ORB (dynamic multi-stage ORB)

A TradingView **Pine v6 indicator** for **Opening Range Breakout** trading, with dynamic multi-stage ranges (5 / 15 / 30 / 60 min), breakout & retest detection, filters, position sizing, and a live dashboard.

**How it's used here:** works on both **Futures and SPX**. The approach leans on **ORB 15, ORB 30, and ORB 60** together with **Fair Value Gaps (FVG)** — looking for ORB breakouts that trade **through an FVG** for higher-quality signals.

> 🙏 **Credit:** Original implementation by **OrenLuxy**. ORB concept based on **Mark Fisher**. Crypto session fix credited to **u/Crucialblockchain**. This copy is a lightly modified fork (see *Local modification* below); all original credit remains with the authors above.

## Features

- **Multi-stage ORB levels** — 5, 15, 30, 60-minute ranges, each toggle-able.
- **Breakout / retest / failed-break** detection with cycle counting.
- **Filters** — volume, trend (VWAP / EMA / SuperTrend / combos), and higher-timeframe bias.
- **Targets & risk** — TP1/1.5/2/3, multiple stop methods (ATR / Smart Adaptive / ORB% / Swing / % based …), R:R and position sizing.
- **FVG boxes**, mid-range line, and a session-aware **dashboard** ("Show Info Panel") with GOD-mode quality scoring.
- **Alerts** for breakouts, retests, failed breaks, stage completion, and trade management.

## Local modification — turn off / move the left info box

The original ORB **stage tag** (the little `ORB5/15/30/60` box that rides at the ORB High/Low) was hard-locked to a **left box** with no way to hide it. This fork adds an **Edge Label Style** input (in the *🎨 ORB Colors* group):

| Option | Result |
|---|---|
| **Left box** | Original look (colored box on the left) |
| **Right box** | Colored box on the right |
| **Text only** | Label text, no box background |
| **Off** | Hide the stage tags entirely |

*(Requires "Show Edge Labels" ON. The large stats panel is separately controlled by "Show Info Panel".)*

## How to use

1. Add the indicator to a liquid symbol on a **1–5 minute** chart during regular hours.
2. Enable the ORB stages you trade (5/15/30/60) and choose a stop method under *🎯 Targets & Risk*.
3. Optional: enable volume / trend / HTF filters to reduce false breakouts.
4. Set alerts on the breakout / retest / trade-management conditions you care about.

## Notes

- Pine v6, `indicator()` (visual/signals only — does **not** place orders).
- Best on liquid instruments (>1M daily volume); may whipsaw on choppy/range days.
- For **educational / research** use only. Not financial advice.
