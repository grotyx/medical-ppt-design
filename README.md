# Medical PPT Design System

A production-ready design system for academic medical presentations, built for the **Spine division at Seoul National University Bundang Hospital (SNUBH)**. It pairs a complete written specification with a reference PowerPoint deck so that every slide — cover, section divider, content, conclusion, closing — uses identical zones, type, and color logic.

The system is **Starbucks-inspired** (four-tier green architecture) but adapted for an academic surgical context: warm-neutral canvas, tight typography, evidence-first visualization, and locked layout coordinates measured from the actual production file.

---

## Repository Contents

| File | Purpose |
|---|---|
| [`design.md`](./design.md) | The complete specification — color tokens, type scale, slide skeleton with exact coordinates, body box patterns (A–I), chart palette, do/don't rules, agent prompt guide. |
| [`backbone_slides.pptx`](./backbone_slides.pptx) | Reference PowerPoint deck (16:9, 13.333" × 7.5"). Treat as the ground-truth template for cover, content, divider, and closing slides. |

---

## Design Principles

- **16:9 only** — 13.333" × 7.5" (1920 × 1080 px reference). No other aspect ratios are valid output.
- **Five locked zones** on every content slide: header strip, headline, subtitle, body card, footer. Coordinates do not move between slides.
- **Four-tier green system** — each green has a distinct role, not interchangeable:
  - `#006241` Starbucks Green — headlines, KPI numbers
  - `#00754A` Green Accent — accents, bullets, primary chart series
  - `#1E3932` House Green — cover, dividers, closing
  - `#2B5148` Green Uplift — dark mid-tone overlays
- **Gold (`#cba258`)** is reserved for statistical significance badges and clinical award moments — never a general accent.
- **Pretendard** is the only typeface, with universal `-0.01em` letter-spacing. Hierarchy is carried by weight (700 / 500 / 400) and color, not by size jumps.
- **Visualization-first**: whenever a slide carries data, comparison, process, or relationship — visualize it; do not narrate it in prose.
- **Density rule**: the body card must never be left half-empty. Use side panels, KPI rows, callout strips, or Pattern F (Stacked Insight Layers).

---

## Slide Skeleton (Content Slides)

| Zone | x | y | w | h |
|---|---|---|---|---|
| Header strip | 0.1512" | 0.135" | 6.0" (left) | 0.28" |
| Headline | 0.2752" | 0.4771" | 11.0" | 0.50" |
| Subtitle | 0.2752" | 1.0335" | 12.3" | 0.27" |
| Body card (white) | 0.2752" | 1.4111" | 12.7946" | 5.7167" |
| Footer — page | 0.1512" | 7.24" | 0.6" | 0.25" |
| Footer — source | 7.1822" | 7.2369" | 6.0" | 0.25" |
| SNUBH logo | 12.0447" | 0.0" | 1.2887" | 0.8519" |

Body content lives strictly inside the white card (1.4111"–7.1278").

---

## Body Box Patterns

The spec defines nine reusable body-box patterns:

- **A** — Single Chart (Full Width)
- **B** — KPI Tiles Row + Chart
- **C** — Two-Column (Claim / Evidence)
- **D** — Three KPI Tiles + Chart
- **E** — Full-Width Table
- **F** — Stacked Insight Layers
- **G** — Big Message
- **H** — Pillar Cards
- **I** — Forest Plot / Equivalence Plot

See [`design.md` §5](./design.md) for coordinates and usage rules.

---

## Intended Use

This system is intended for:

- Surgical and clinical research presentations
- Conference talks (domestic and international)
- Grand rounds, journal clubs, and registry updates
- Trial result reporting and equivalence/non-inferiority studies

It is **not** intended for:

- Patient-facing handouts (different typography and density needs)
- Marketing or sales decks (the gold-tier accent rules will be misapplied)

---

## How to Use

1. Open `backbone_slides.pptx` and use it as the template — do not move the five locked zones.
2. Read `design.md` end-to-end once. Re-read §0 (Production Constraints) and §5 (Body Box Patterns) before every new deck.
3. Match every slide's body content to one of Patterns A–I. If none fits, the slide content is probably trying to do too much — split it.
4. When generating slides programmatically (e.g., via an LLM agent), pass `design.md` as the system prompt and reference the pattern by letter.

---

## Brand Assets

- **Logo**: SNUBH (Seoul National University Bundang Hospital) — top-right of every slide. Transparent PNG, original proportions, no recoloring/shadows/borders.
- **Font**: Pretendard (variable). Stack: `Pretendard, "Pretendard Variable", -apple-system, system-ui, sans-serif`.

The logo file itself is not redistributed in this repository.

---

## License

This work is licensed under the **Creative Commons Attribution 4.0 International License (CC BY 4.0)** — see [`LICENSE`](./LICENSE) or <https://creativecommons.org/licenses/by/4.0/>.

You are free to share and adapt the material for any purpose, including commercially, provided you give appropriate credit.

**Exclusion — SNUBH brand assets.** The Seoul National University Bundang Hospital logo, institutional marks, and any related trademarks embedded in `backbone_slides.pptx` are **not** covered by this license. Those assets remain the property of Seoul National University Bundang Hospital and may not be redistributed, sublicensed, or used in derivative works without separate permission from SNUBH. When reusing this template, replace the SNUBH logo and institutional identifiers with your own.

**Suggested attribution:**
> Park S-M. *Medical PPT Design System.* CC BY 4.0. <https://github.com/grotyx/medical-ppt-design>

---

## Maintainer

Sang-Min Park, MD — Department of Orthopedic Surgery, Seoul National University Bundang Hospital.

Feedback, corrections, and pattern proposals welcome via GitHub Issues.
