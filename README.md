<div align="center">

# ⌨️ TYPING DNA
### *Discover Your Keystroke Personality*

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Chart.js](https://img.shields.io/badge/Chart.js-FF6384?style=for-the-badge&logo=chartdotjs&logoColor=white)

**A browser-based typing speed mini game that generates a unique DNA strand from your keystroke timing patterns — with a full Power BI-style analytics dashboard.**

[▶ Play Now](#how-to-run) · [📊 See Dashboard](#the-analytics-dashboard) · [🧬 How DNA Works](#the-dna-visualiser)

---

| ⚡ 7 Archetypes | 📊 4 Chart Types | 🧬 DNA Visualiser | 📁 1 File | 🔌 0 Dependencies |
|:-:|:-:|:-:|:-:|:-:|
| Discover your typing personality | Full session analytics | Unique to every session | Just open in browser | No install needed |

</div>

---

## 📖 The Story — How This Started

> *"Every typing test tells you your WPM and accuracy. But that felt like only half the story."*

I was going down a rabbit hole one evening reading about **biometric keystroke dynamics** — the idea that the exact timing between your keypresses is as unique as a fingerprint. Researchers use it to identify individuals. That idea stuck with me.

What if I built something that captured that — not for surveillance, but for **self-discovery**? After you finish typing a sentence, you'd see a visual representation of your timing patterns drawn as a DNA strand, unique to you in that moment. And a dashboard that breaks down exactly what kind of typist you are.

I also wanted to prove something to myself: **you can build a professional, visually impressive project with zero external dependencies, zero backend, and a single HTML file.** No React. No Python. No database. Just the browser.

> 🎯 **The challenge I set myself:** Build a typing game + analytics dashboard that looks like something from a corporate BI tool, runs entirely in the browser with one file, and generates a visual fingerprint from keystroke timing — in pure HTML, CSS, and JavaScript.

---

## 🎯 Project Objective

Most typing tools treat users as a speed metric. **Typing DNA treats users as individuals.**

| Goal | Description |
|------|-------------|
| **Primary** | Capture speed, accuracy, *and* rhythm — not just WPM |
| **Secondary** | Visualise typing patterns as a unique DNA double helix |
| **Tertiary** | Present a Power BI-style dashboard with KPIs and charts |

**Tech at a glance:**

| Property | Detail |
|----------|--------|
| Type | Mini Game + Analytics Dashboard |
| Technology | HTML5, CSS3, Vanilla JavaScript, Chart.js |
| Platform | Any modern browser (Chrome, Firefox, Safari, Edge) |
| Dependencies | Zero — one file, double-click to run |
| Deliverable | Single `index.html` |

---

## 🖼️ Wireframe & Design

### Design Philosophy

The design follows a **dark-terminal aesthetic** — think Bloomberg Terminal meets modern SaaS dashboard.

- **Dark backgrounds** make the coloured DNA strand pop — the contrast is essential to the visual payoff
- **Monospace fonts** (Courier New) reinforce the technical feel without being intimidating
- **Purple accent** was chosen for its associations with creativity and precision — fitting for a personality tool
- **Dashboard layout** mirrors Power BI: KPI cards at top, charts in the middle, insights at the bottom

### Game Screen Wireframe



```
┌─────────────────────────────────────────────┐
│  TYPING DNA  — discover your personality    │
│  [ Easy ]  [ Medium ]  [ Hard ]             │
├─────────────────────────────────────────────┤
│                                             │
│   the quick brown fox jumps over the...     │  ← Sentence display
│                                             │
├─────────────────────────────────────────────┤
│  [ start typing here...                 ]   │  ← Input field
├────────┬────────┬────────┬────────┐         │
│  WPM   │  ACC   │  TIME  │ RHYTHM │         │  ← Live stats
│   68   │  91%   │  12.3s │  74%   │         │
├────────┴────────┴────────┴────────┘         │
│  ≋≋≋≋≋≋≋≋≋≋≋≋≋≋≋≋≋≋≋≋≋≋≋≋≋≋≋≋≋≋≋≋         │  ← DNA strand
│  🌊 The Flow Rider — smooth and steady...   │  ← Archetype
│  [ ▶ Start ]  [ ↺ Reset ]  [ 📊 Dashboard ]│
└─────────────────────────────────────────────┘
```

The layout hierarchy was deliberately chosen top-to-bottom:
1. **Header** — brand identity, first impression
2. **Difficulty selector** — first decision the user makes
3. **Sentence display** — primary focus zone, largest element
4. **Input field** — directly below what you're reading, natural eye flow
5. **Live stats** — peripheral vision zone, glanceable without breaking focus
6. **DNA strand** — reward zone, appears on completion
7. **Archetype bar** — the emotional payoff, the result users came for
8. **Action buttons** — always at the bottom, never interrupts the flow

### Dashboard Screen Wireframe

![Game Screen Wireframe](https://github.com/kriti613/Typing-DNA/blob/main/typingdna_UI.png)

---

## 🔄 Application Flowchart

### Full Flow — Game Screen

```
┌─────────────┐
│  Page Loads │
│ Input locked│
└──────┬──────┘
       │
       ▼
┌─────────────┐
│Set Difficulty│
│Easy/Med/Hard│
└──────┬──────┘
       │
       ▼
┌─────────────┐
│ Press Start │
│Sentence load│
│  Timer arms │
└──────┬──────┘
       │
       ▼
┌─────────────┐      ┌──────────────────┐
│  User Types  │─────▶│   Backspace?     │
│ Live updates │      │ Penalises accuracy│
└──────┬──────┘      └──────────────────┘
       │
       ▼
┌─────────────┐
│  Sentence   │
│  Complete?  │
└──────┬──────┘
       │  Yes
       ▼
┌─────────────┐
│ DNA Strand  │
│  Generated  │
│from timings │
└──────┬──────┘
       │
       ▼
┌─────────────┐
│  Archetype  │
│  Revealed   │
└──────┬──────┘
       │
       ▼
┌─────────────┐
│   Dashboard │
│   Unlocked  │
└─────────────┘
```

### Accuracy Penalty Logic

```
Accuracy = (sentence length) ÷ (total keystrokes including backspaces) × 100
```

Every backspace press counts as a keystroke. A perfect run with zero corrections = **100%**. Each unnecessary backspace reduces your score proportionally — you cannot cheat your way to 100% by retyping everything.

---

## 🎮 Features

### The Game

- **3 difficulty levels** — Easy (common phrases), Medium (programming quotes), Hard (pangrams)
- **Real-time character highlighting** — 🟢 green for correct, 🔴 red for wrong, purple cursor for current position
- **Live stats every 150ms** — WPM, Accuracy, and Time update as you type
- **Backspace-penalised accuracy** — the more you correct, the lower your score
- **Instant completion detection** — game ends the moment your text exactly matches the target

### The DNA Visualiser 🧬

The DNA strand is the centrepiece — and what makes this project unlike anything else.

| Step | What Happens |
|------|-------------|
| 1 | Inter-keystroke timing intervals are captured during typing |
| 2 | Intervals normalised between fastest and slowest keypress |
| 3 | Each interval maps to the **amplitude** of the DNA double helix |
| 4 | Slow intervals = wide helix, fast intervals = narrow helix |
| 5 | Hue shifts based on WPM (blue for slower → green for faster) |
| 6 | Bridge rungs coloured by individual key speed |
| 7 | Every strand is mathematically unique to that session |

![DNA Strand Example](https://github.com/kriti613/Typing-DNA/blob/main/typingdnaafterround1.png)

### Typing Archetypes 🏷️

| Icon | Archetype | Classification |
|:----:|-----------|----------------|
| ⚡ | **The Thunderbolt** | WPM > 80 AND Accuracy > 95% |
| 🎯 | **The Marksman** | WPM > 60 AND Accuracy > 90% |
| 🔥 | **The Berserker** | WPM > 50 AND Accuracy < 85% |
| 🧙 | **The Perfectionist** | WPM < 40 AND Accuracy > 95% |
| 🤖 | **The Metronome** | Rhythm Score > 85% |
| 🌊 | **The Flow Rider** | WPM > 45, balanced |
| 🌱 | **The Apprentice** | Default — still growing |

---

## 📊 The Analytics Dashboard

After completing rounds, click **View Dashboard** to access the full session analytics — modelled on a Power BI report layout.

![Dashboard Full View](https://github.com/kriti613/Typing-DNA/blob/main/typingDNafullanalysis.png)
### KPI Cards

| KPI | Calculation |
|-----|-------------|
| **Best WPM** | Maximum WPM across all rounds |
| **Avg Accuracy** | Mean accuracy % — penalised by backspace count |
| **Avg Rhythm** | Mean keystroke consistency score (0–100%) |
| **Rounds Played** | Count of completed rounds in the session |

### Charts

| Chart | What It Shows |
|-------|--------------|
| 📈 **WPM & Accuracy Line Chart** | Both metrics across rounds — reveals improvement trends |
| 🍩 **Accuracy Distribution Donut** | Excellent / Good / Needs Work breakdown |
| 🔵 **Speed vs Accuracy Scatter** | Each round as a dot — reveals speed vs accuracy trade-off |
| 📊 **Per-Round Progress Bars** | Granular WPM, Accuracy, and Rhythm for each round |

### Insights Panel

Six auto-generated cards at the bottom:
- **Best round** — highest WPM round and by how much
- **Most accurate** — cleanest typing round
- **Your archetype** — session personality classification
- **WPM consistency** — how stable your speed was (lower variance = higher score)
- **Average WPM** — mean speed across the session
- **Average rhythm** — mean keystroke timing consistency

---

## 🏗️ Technical Architecture

### Stack

| Layer | Technology |
|-------|-----------|
| Structure | HTML5 — semantic markup, Canvas API for DNA |
| Styling | CSS3 — custom properties, CSS Grid, transitions |
| Logic | Vanilla JavaScript (ES6+) — no frameworks |
| Charts | Chart.js 4.4.1 via CDN |
| Storage | In-memory JS arrays — session-scoped, privacy-respecting |
| Hosting | GitHub Pages / any static host / local file |

### File Structure

```
typing-dna/
└── index.html      ← the entire application (HTML + CSS + JS)
└── README.md       ← this file
```

No build step. No `package.json`. No `node_modules`. No server. Just open `index.html`.

### Key Technical Decisions

**`performance.now()` over `Date.now()`**
Used for sub-millisecond precision on keystroke timing — critical for accurate rhythm scoring and DNA generation. `Date.now()` rounds to milliseconds; `performance.now()` gives microsecond resolution.

**Canvas API for DNA rendering**
The HTML5 Canvas API gives pixel-level control over the DNA strand visualisation. Each session's strand is drawn procedurally from the keystroke interval data — no two strands are identical.

**Single-file architecture**
Chosen deliberately to prove that complexity of output does not require complexity of setup. The entire application — UI, game logic, chart rendering, DNA generation — lives in one file you can double-click.

**No localStorage**
All data is session-scoped and cleared on page refresh. Keeps the app stateless and privacy-respecting — nothing persists without your consent.

---

## 🚀 How to Run

> No installation. No terminal. No Python. If you have a browser, you can run it.

1. Download or clone this repository
2. Open the `typing-dna/` folder
3. **Double-click `index.html`**
4. Select a difficulty level
5. Click **Start** and type the sentence
6. Complete a round → click **View Dashboard** for your analytics

| Requirement | Detail |
|-------------|--------|
| Browser | Chrome, Firefox, Safari, or Edge |
| Internet | Required once to load Chart.js from CDN |
| Installation | None |
| OS | Windows / macOS / Linux |

### Live Version

[View Live Demo](https://kritigupta.github.io/typing-dna)
> *(Enable GitHub Pages: Settings → Pages → Deploy from main branch)*

---

## 🔮 Future Scope

- [ ] **Persistent leaderboard** — save best scores in `localStorage` across sessions
- [ ] **Shareable DNA image** — export your unique strand as a PNG for social media
- [ ] **Custom text mode** — paste your own text to practise specific content
- [ ] **Mistake heatmap** — visualise which letters you consistently mistype
- [ ] **Sound design** — subtle audio feedback for correct/incorrect keystrokes
- [ ] **Offline mode** — bundle Chart.js locally so it works without internet
- [ ] **Multi-language support** — sentences in languages other than English

---

## 📚 References

- [Chart.js](https://www.chartjs.org/) — MIT License, used for all dashboard charts
- [MDN Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API) — DNA strand rendering reference
- [Monkeytype](https://monkeytype.com/) — inspiration for typing test UX
- [Keystroke Dynamics Research](https://en.wikipedia.org/wiki/Keystroke_dynamics) — academic foundation for the DNA concept

---

<div align="center">

**Built with curiosity and zero npm installs.**

*Kriti Gupta — 2026*

⌨️ → 🧬 → 📊

</div>
