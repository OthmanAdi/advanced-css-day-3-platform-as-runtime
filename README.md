# Platform as Runtime — Advanced CSS Day 3

> Vier Pages. Ein Token-System. Kein Framework.
> Heute lassen wir die Browser-Plattform für uns arbeiten.

## Was hier läuft

Ein kleiner Multi-Page-Site mit vier Seiten — Home, Pricing, Profile, Login.
Eine geteilte Navigation, ein 3-Layer-Token-System aus dem Day 2,
saubere Komponenten, deployt auf Vercel und GitHub Pages.

Drei Browser-Features kommen heute neu dazu:

| Feature | Wofür | Issue |
|---------|-------|-------|
| **View Transitions API** | Nahtlose Page-Wechsel ohne JS-Framework | [#1](../../issues/1), [#4](../../issues/4) |
| **Subgrid** | Zeilen über mehrere Cards hinweg aligned | [#2](../../issues/2) |
| **Anchor Positioning** | Tooltips ohne Floating-UI-Library | [#3](../../issues/3) |
| **`@supports`** | Fallback für nicht-Chromium-Browser | [#5](../../issues/5) |

## Live

- Vercel: _wird in Block A nachgetragen_
- GitHub Pages: _wird in Block A nachgetragen_

## Stack

Vanilla HTML + CSS. Kein Build-Step. Kein Framework. Modern CSS Features
brauchen Chrome 120+, Edge 120+, Safari 26+. Firefox sieht einen Fallback
(siehe Issue #5).

## File-Struktur

```
.
├── index.html         Home — Hero + 3 Feature-Cards
├── pricing.html       Pricing — 3 Plan-Cards mit unterschiedlich langen Listen
├── profile.html       Profile — Avatar + 3 Stat-Cards (Tooltip-Anker)
├── login.html         Login — Form mit :has-Validation
├── tokens.css         3-Layer Token-System (Primitives → Semantic → Component)
├── base.css           Reset + Body + Nav + Buttons + Footer
├── pages.css          Page-spezifische Styles (vier Sektionen, eine pro Page)
├── transitions.css    Stub — wird in Block A + D befüllt
└── tooltips.css       Stub — wird in Block C + E befüllt
```

## Lokal laufen lassen

```bash
# Variante 1 — Python (vorinstalliert auf Mac, Windows mit Python)
python -m http.server 8000

# Variante 2 — Node
npx serve .

# Dann: http://localhost:8000
```

Direkter Doppelklick auf `index.html` funktioniert auch, aber View Transitions
brauchen einen echten HTTP-Server, sonst feuern sie nicht.

## Today's Engineering Laws

| Law | Wo es heute zuschlägt |
|-----|------------------------|
| **Hyrum's Law** | Issue #4 — sobald `view-transition-name` deployed ist, ist es ein Vertrag |
| **Postel's Law** | Issue #1 — sei großzügig in dem was der Browser ignoriert |
| **Worse Is Better** | Module-spine — `:has()` statt useState, View Transitions statt Framer |
| **Law of Demeter** | Issue #3 — Tooltip kennt nur seinen Anker, nicht das ganze Layout |

## Author

OthmanAdi (Ahmad Adi) — Morphos Advanced CSS Cohort, Mai 2026
