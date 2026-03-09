<div align="center">

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:0a0a0f,50:0f1923,100:0a0a0f&height=180&section=header&text=BLACKLINE%2B&fontSize=80&fontColor=ffffff&fontAlignY=42&desc=Advanced%20Intelligence%20Suite%20for%20Rugplay.com&descAlignY=62&descSize=15&descColor=6366f1&animation=fadeIn" />

[![Version](https://img.shields.io/badge/version-4.0.0-6366f1?style=for-the-badge&labelColor=0a0a0f)](https://github.com/blacklineplus/blacklineplus)
[![Platform](https://img.shields.io/badge/rugplay.com-live-22c55e?style=for-the-badge&labelColor=0a0a0f)](https://rugplay.com)
[![Tampermonkey](https://img.shields.io/badge/Tampermonkey-required-f59e0b?style=for-the-badge&labelColor=0a0a0f)](https://www.tampermonkey.net/)
[![License](https://img.shields.io/badge/license-MIT-94a3b8?style=for-the-badge&labelColor=0a0a0f)](#license)

**Real-time trade feeds · Rugpull AI scoring · Bot detection · Wallet analysis · Portfolio tracking**

</div>

---

## What is Blackline+?

Blackline+ is a [Tampermonkey](https://www.tampermonkey.net/) userscript that layers a full intelligence suite directly onto [rugplay.com](https://rugplay.com). It intercepts live trade data, scores coins for rugpull risk, flags bots, and gives you a persistent dashboard — all without leaving the page.

No API keys. No external servers. Everything runs locally in your browser.

---

## Installation

**1. Install Tampermonkey**

| Browser | Link |
|---|---|
| Chrome | [Chrome Web Store](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo) |
| Firefox | [Firefox Add-ons](https://addons.mozilla.org/en-US/firefox/addon/tampermonkey/) |
| Edge | [Edge Add-ons](https://microsoftedge.microsoft.com/addons/detail/tampermonkey/iikmkjmpaadaobahmlepeloendndfphd) |

**2. Install the script**

Click the button below, or open Tampermonkey → *Create new script* → paste the contents of `blacklineplus_user.js`.

[![Install Script](https://img.shields.io/badge/Install%20Blackline%2B-click%20to%20install-6366f1?style=for-the-badge&labelColor=0a0a0f)](https://raw.githubusercontent.com/blacklineplus/blacklineplus/main/blacklineplus_user.js)

**3. Go to [rugplay.com](https://rugplay.com)**

The script activates automatically. Look for the Blackline+ status pill in the corner.

---

## Features

### 🔴 Live Trade Feed
A real-time panel that captures every buy and sell as it happens. Filterable by coin, user, and trade type. Up to 5,000 trades stored locally across sessions.

### 🧠 Rugpull AI Scorer
Every coin gets a 0–100 risk score based on sell/buy ratio, sell volume concentration, whale dumps, and recent trade velocity. Scores update live as new trades come in.

| Score | Label |
|---|---|
| 75 – 100 | 🔴 Critical Risk |
| 50 – 74 | 🟠 High Risk |
| 30 – 49 | 🟡 Medium Risk |
| 0 – 29 | 🟢 Low Risk |

Configurable alert threshold — get notified when a coin crosses your limit.

### 🤖 Bot Detector
Analyzes trade timing intervals, directional uniformity, and position sizing consistency to produce a bot confidence score. High-confidence bots are auto-tagged. Three tiers:

- **High-Confidence Bot** — regular intervals + uniform sizing + multi-coin speed
- **Likely Bot** — two or more strong signals present
- **Bot Activity** — borderline patterns flagged for review

### 👤 User Tags
Label any wallet with a preset or custom tag. Tags persist across sessions and surface everywhere that username appears on the site.

Built-in presets: `💻 Dev` · `👑 VIP` · `🤝 Friend` · `🚩 Rugpuller` · `🐋 Whale` · `⛔ Scammer` · `✅ Trusted` · `🤖 Bot` · `🎰 Degen` · `🔮 Insider`

### 📊 Portfolio Estimator
Reconstructs an estimated portfolio for any user from observed trade history — quantities held, average buy prices, realized P&L, and estimated current value per coin.

### 🔔 Toast Alerts
Configurable non-blocking notifications for:
- Rug risk threshold breaches
- Watchlisted coin activity
- Volume spikes (configurable multiplier, default 3×)
- Buy/sell events from tracked users

### 📋 Community Reports
Submit, browse, and vote on rugpuller/scammer reports directly within the UI. Stores up to 200 reports locally with upvote/downvote per entry.

### ⌨️ Hotkeys

| Key | Action |
|---|---|
| `` ` `` | Toggle center dashboard |
| `F` | Toggle live feed panel |
| `S` | Toggle search |

All hotkeys are rebindable in Settings.

### 🛠️ Additional Tools

- **Watchlist** — track specific coins with instant alerts
- **Coin Notes** — attach private notes to any coin
- **Ad blocker** — removes rugplay.com ads
- **Appear offline** — mask your online presence
- **Compact mode** — tighter layout for smaller screens
- **Dark enhance** — deeper dark mode styling
- **Sticky portfolio** — keeps your portfolio visible while scrolling
- **Quick buy presets** — configurable 1-click buy amounts (default: $5 / $10 / $50 / $100)
- **URL shortcuts** — `/@username` → `/user/username` and `/*SYMBOL` → `/coin/SYMBOL`
- **Sparkline charts** — inline mini trade charts on coin pages

---

## Data & Privacy

All data is stored in your browser's `localStorage`. Nothing is sent to any external server. Blackline+ only connects to `rugplay.com` to read trade data.

You can export or import everything (history, tags, notes, watchlist, settings, reports) as a single JSON file from **Settings → Data**.

---

## Configuration

Open the center panel (`` ` ``) → **Settings**. Key options:

```
liveToasts            true/false   Show real-time trade notifications
rugThreshold          0–100        Rug alert trigger level        (default: 70)
volumeSpikeMultiple   number       Volume spike alert multiplier  (default: 3×)
toastDuration         ms           Toast display duration         (default: 4500ms)
buyPresets            array        Quick-buy amounts              (default: [5, 10, 50, 100])
defaultSlippage       %            Default slippage               (default: 1%)
adBlocker             true/false   Block rugplay ads
appearOffline         true/false   Hide online status
compactMode           true/false   Tighter UI layout
showBotBadges         true/false   Show bot detection badges
showRugpullerBadge    true/false   Show rugpuller badge on profiles
```

---

## Changelog

### v4.0.0 — Current
- Full ground-up rewrite with clean modular architecture
- Persistent session state (open panels survive page refresh)
- Bot detector with three-tier confidence scoring + auto-tagging
- Community reports system with voting
- Volume spike tracker
- Profile and coin page enhancers
- Rugpuller badge injection on user profiles
- Sparkline trade charts on coin pages
- Fully rebindable hotkeys
- Full JSON import/export for all data

---

## Contributing

Issues and PRs are welcome. If you catch a false positive in bot detection, a missed rug pattern, or a UI bug — open an issue with the coin symbol or username and what you observed.

---

## License

MIT — use it, fork it, build on it.

---

<div align="center">

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:0a0a0f,50:0f1923,100:0a0a0f&height=80&section=footer" />

*Blackline+ is not affiliated with rugplay.com. Use at your own risk.*

</div>
