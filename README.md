# 幻 Phantom Search · 探偵

> **Live →** [https://satyam-64136.github.io/erpinfo/](https://satyam-64136.github.io/erpinfo/)

A cinematic, Japanese ink-aesthetic student directory for DIT University. Search any student by **name**, **ERP ID**, or **phone number** — results appear instantly with a polished card UI and a detailed bottom sheet on tap.

---

## Preview

![Dark mode — ink wash background with pagoda silhouette, sakura petals, and glassmorphism search bar]

*Dark mode (default) · Light mode toggle available top-right*

---

## Features

| | |
|---|---|
| **Instant search** | Debounced live search across name, ERP ID, email, and phone as you type |
| **Smart dropdown** | Top 8 suggestions appear in a blurred dropdown while typing |
| **Result cards** | Responsive grid (1 → 2 → 3 col) with glassmorphism cards and hover lift |
| **Detail sheet** | Tap any card for a bottom-sheet modal with full record — ERP, phone, email |
| **Copy to clipboard** | One-tap phone copy button inside the detail sheet |
| **Dark / Light theme** | Respects system preference; persists choice to `localStorage` |
| **Sakura petals** | 10 ambient floating petal elements — CSS keyframe animated |
| **Live clock** | IST clock in the bottom status bar |
| **Keyboard nav** | Arrow keys navigate dropdown; Enter confirms; Escape closes |
| **Swipe to dismiss** | Swipe down 72 px on mobile to close the detail sheet |

---

## Tech Stack

- **Vanilla HTML / CSS / JS** — zero dependencies, zero build step
- **Google Fonts** — Shippori Mincho · Noto Serif JP · Inter · JetBrains Mono
- **CSS custom properties** — full Japanese ink theme token system
- **`fetch` + `data.json`** — flat JSON file as the data source
- **`navigator.clipboard`** — native copy API
- **CSS `backdrop-filter`** — glassmorphism blur on cards, dropdown, and sheet
- **CSS container queries** — card layout adapts independently
- **Inline SVG** — torii gate, pagoda, bamboo grove, moon — all hand-coded vector art

---

## Project Structure

```
erpinfo/
├── index.html      # Entire app — HTML + CSS + JS in one file
└── data.json       # Student records [ { Name, ERP ID, Email, Phone Numbers } ]
```

### `data.json` schema

```json
[
  {
    "Name": "Student Name",
    "ERP ID": "2300000",
    "Email": "student@dituniversity.edu.in",
    "Phone Numbers": "9876543210"
  }
]
```

---

## Design System

The UI uses a **Japanese Ink (幻影)** theme built entirely from CSS variables:

| Token | Value | Role |
|---|---|---|
| `--paper` | `#100e0a` | Page background |
| `--ink` | `#f0ece0` | Primary text |
| `--sakura` | `#e8607a` | Accent / glow |
| `--gold` | `#d4922a` | Secondary accent |
| `--indigo` | `#6b7fe8` | Highlight / phone |
| `--serif` | Shippori Mincho | Display headings |
| `--mono` | JetBrains Mono | ERP IDs, labels |

Light mode flips the palette to a warm parchment base while keeping the same token names.

---

## Running Locally

No build tooling required. Just serve the folder with any static server:

```bash
# Python
python -m http.server 8080

# Node (npx)
npx serve .

# VS Code
# Install "Live Server" extension → right-click index.html → Open with Live Server
```

Then open `http://localhost:8080`.

> **Note:** The app fetches `./data.json` via `fetch()`, so it must be served over HTTP — opening `index.html` directly as a `file://` URL will block the fetch.

---

## Deployment

Hosted on **GitHub Pages** from the `main` branch root.  
Push to `main` → live at `https://satyam-64136.github.io/erpinfo/` automatically.

---

## Author

**Satyam** · BTech CS · DIT University, Dehradun (Batch 2025–2029)  
[GitHub](https://github.com/satyam-64136)

---

*幻影 · Phantom · 探偵 — built with ink and intention.*
