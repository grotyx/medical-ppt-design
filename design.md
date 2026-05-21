# Design System for SNUBH Spine PPT (16:9)

---

## 0. Production Constraints (Read First)

### Output Format

- **16:9 slides only** — PowerPoint standard **13.333" × 7.5"**, reference resolution **1920 × 1080 px**. No other aspect ratios are valid output.
- All deliverables must conform to this specification before export.

---

### Brand Assets (Mandatory — No Substitution)

**Logo**
SNUBH (Seoul National University Bundang Hospital) logo only. Place at the **top-right of every slide** unless explicitly directed otherwise. Insert the provided logo file exactly as given — see Logo Integrity Rule below.

**Typography**
**Pretendard** is the primary typeface — no exceptions. Do NOT use DM Sans, Outfit, Poppins, Roboto, Noto, system UI fonts, or any other family. Every weight reference maps to Pretendard's scale (Thin 100 → Black 900).

- Fallback string for export: `Pretendard, "Pretendard Variable", -apple-system, system-ui, sans-serif`
- The only family that should actually render is **Pretendard**.
- Apply a universal letter-spacing of **`-0.01em`** across all text.

**Why Pretendard?** SoDoSans (the inspiration typeface from the Starbucks reference system) is proprietary and not publicly available. Pretendard's humanist geometric proportions, wide weight range, and excellent Korean/Latin mixed rendering make it the closest production-ready substitute for an academic medical institution context.

---

### Slide Skeleton — Locked Positions Across the Deck

Every slide must place these **five zones** at identical coordinates. Only the body contents change between slides — never the frame.

> **⚠️ These coordinates are measured from the actual production file (backbone_slides.pptx, slides 1 & 3, user-edited May 2026). Treat as ground truth.**

| Zone | x | y | w | h | Contents | Style |
|---|---|---|---|---|---|---|
| **Header strip** | `0.1512"` | `0.135"` | `6.0"` (left) | `0.28"` | Chapter / section name (left), SNUBH logo (right) | Chapter: Pretendard 600, 11pt, `#8e8e93`, `-0.01em` (no extra tracking). Caps allowed in EN; do NOT apply additional `+0.05em` letter-spacing for caps. Logo: see Logo Integrity Rule |
| **Headline zone** | `0.2752"` | `0.4771"` | `11.0"` | `0.50"` | Slide headline — one-sentence takeaway | Pretendard 700, **32pt**, `#006241` (Starbucks Green), line-height 1.20, letter-spacing `-0.01em` |
| **Subtitle zone** | `0.2752"` | `1.0335"` | `12.3"` | `0.27"` | Subtitle / subhead | Pretendard 500, 12pt, `rgba(0,0,0,0.58)`, line-height 1.45, letter-spacing `-0.01em` |
| **Body box (white card)** | `0.2752"` | `1.4111"` | `12.7946"` | `5.7167"` | All body components — see §5 | White (`#ffffff`) card, 12px radius, whisper shadow |
| **Footer — page number** | `0.1512"` | `7.24"` | `0.6"` | `0.25"` | Page number | Pretendard 500, 9pt, `#8e8e93` |
| **Footer — source** | `7.1822"` | `7.2369"` | `6.0"` | `0.25"` | Source / footnote | Pretendard 400, 8pt, `#8e8e93`, right-aligned |

**Vertical rhythm (measured gaps):**
- Header strip → Headline: ≈0.34" gap (header bottom at ~0.415", headline top at 0.4771")
- Headline → Subtitle: ≈0.056" gap (headline bottom ~0.977", subtitle top 1.0335")
- Subtitle → Body card: ≈0.38" gap (subtitle bottom ~1.303", card top 1.4111")

**Lock rule:** Five zones do not move between slides. Override only for section dividers, full-bleed covers, and closing slides.

**Hard boundary:** Body card runs 1.4111"–7.1278" (card top + height = 1.4111+5.7167). Footer clearance begins at ~7.24". Content must not overflow the white card.

---

### Logo Integrity Rule

**Logo file:** `logo.png` (SNUH — Seoul National University Bundang Hospital). Original size 1536×1024 px, aspect ratio 3:2. Background is fully transparent (RGBA, alpha=0 on all background pixels) — place directly on any slide color without a backing box.

**Placement — unified across ALL slide types (measured from slide 2, May 2026):**
- `x: 12.0447", y: 0.0", w: 1.2887", h: 0.8519"` — identical on cover, section dividers, and content slides
- Aspect ratio ≈ 3:2 preserved. Do not vary size or position between slide types.

**Rules:** Original proportions, original colors, alpha preserved. Do NOT add shadows, glows, borders, frames, recoloring, gradients, or background fills. Do NOT crop, stretch, skew, rotate, or duplicate. Never place an opaque box behind the logo.

---

### Presenter Defaults (Always Apply)

| Field | Value |
|---|---|
| **발표자** | 박상민 |
| **소속** | 분당서울대학교병원 정형외과 |

These values are fixed across all slide decks. Do not substitute other names unless explicitly instructed.

---

### Cover Slide Layout

The cover slide uses a full-bleed **House Green (`#1E3932`)** background with the following fixed zones.

> **⚠️ All coordinates measured from actual production file (backbone_slides.pptx, slide 1, user-edited May 2026). Treat as ground truth.**

| Zone | x | y | w | h | Font | Color |
|---|---|---|---|---|---|---|
| **Logo** | `SW − 1.7887"` (right-anchored) | `0.16"` | `1.2887"` | `0.8519"` | — | transparent PNG |
| **Label pill** | `0.6"` | `1.11"` | `2.7874"` | `0.49"` | Pretendard 700, **14pt** | White `#FFFFFF` on Green Accent fill |
| **Main title** | `0.6"` | `2.0775"` | `9.0"` | `1.8225"` | Pretendard 700, **54pt** | White `#FFFFFF` |
| **Subtitle (study descriptor)** | `0.6"` | `4.3"` | `9.0"` | `0.38"` | Pretendard 700, **20pt** | `#B3D4CB` |
| **Green accent line** | `0.6"` | `5.05"` | `1.8"` | `0.04"` | — | Green Accent `#00754A` |
| **Affiliation (BR, top)** | `7.5093"` | `5.58"` | `5.0"` | `0.34"` | Pretendard 400, **25pt** | `#8BB8AE` |
| **Presenter name (BR, bottom)** | `7.5093"` | `5.9904"` | `5.0"` | `0.38"` | Pretendard 700, **27pt** | White `#FFFFFF` |
| **Conference + date (BL)** | `0.2977"` | `6.9752"` | `6.0"` | `0.42"` | Pretendard 400, **16pt** | `#8BB8AE` |

**Fixed presenter values (always pre-fill):**
- Affiliation: `분당서울대학교병원 정형외과`
- Name: `박상민`

**Conference + date format:** `학회명  |  날짜` — e.g. `대한척추외과학회 춘계학술대회  |  2025.06`

**Subtitle zone usage:** This line is for a one-sentence study descriptor (design, registry name, cohort tag). It is NOT used for the conference name or presenter — those go in the bottom band.

---

### Body Text Structure Rule

본문 bullet 콘텐츠는 **하나의 텍스트프레임** 안에 단락(paragraph)으로 작성한다. 개별 줄마다 별도 텍스트박스를 사용하지 않는다.

| Level | Prefix | Size | Weight | Color |
| --- | --- | --- | --- | --- |
| 0 (대제목) | 없음 | **24pt** | 700 | `#1F1F1F` |
| 1 (서브불릿) | `●` Green Accent (`#00754A`) **11pt** bold | **20pt** | 400 | `#1F1F1F` |
| 2 (세부항목) | `–` | **16pt** | 400 | `#6B6B6B` |

들여쓰기: level 1 → 0.25인치, level 2 → 0.50인치 (`marL` XML 직접 설정).

**행간 / 단락 간격:**

| 항목 | 값 |
| --- | --- |
| Line spacing (행간) | **28pt** fixed |
| Space before — level 0 | **16pt** (첫 단락은 0pt) |
| Space before — level 1 | **18pt** (불릿 항목 간 여백) |
| Space before — level 2 | **10pt** |

---

### Body Density Rule

The lower body box must NOT be left half-empty.

**If a slide has thin content, apply one of these density tactics** — never decorative padding, never zone invasion:
- Pull supporting evidence into a side panel inside the body box
- Add a "Key Takeaway" callout strip at the bottom of the body box (above 6.85")
- Insert a diagram that reinforces the headline
- Split into a 2-column claim / evidence layout
- Use **Pattern F (Stacked Insight Layers)** — three horizontal bands within the body box

---

### Visualization-First Rule

Whenever a slide carries data, comparison, process, or relationship — **visualize it; do not narrate it in prose.**

**Trigger conditions** (slide MUST include a visualization if any apply):
- Two or more numbers being compared → chart or KPI tile row
- A trend over time → line chart or timeline
- Composition / share / distribution → bar, donut, or stacked bar
- A process or sequence → horizontal arrow flow, numbered stages
- A comparison across categories → grouped / stacked bar
- A structural relationship → diagram, matrix, 2×2
- A hierarchy → tree or org chart

**Visualization priority:**
1. Charts — bar, line, area, scatter, donut (use §4 chart palette)
2. KPI tiles with sparklines
3. Diagrams — flow, sequence, funnel, hierarchy
4. Annotated images / screenshots (only when the visual IS the evidence)
5. Tables — last resort

**Constraints:**
- Visualizations live strictly inside the body box (2.39"–6.85")
- Maximum 1–2 visualizations per slide
- Every chart must have: title (Pretendard 600 14pt), axis labels (Pretendard 400 10pt `rgba(0,0,0,0.58)`), source (Pretendard 400 9pt `#8e8e93`)
- If font sizes would drop below 9pt, split the slide

---

## 1. Visual Theme & Atmosphere

SNUBH Spine PPT follows the **Starbucks-inspired four-tier green system** — a warm, authoritative academic medical design built on the same color architecture as Starbucks' design system. The canvas uses **Neutral Warm (`#f2f0eb`)** for content slides. **Starbucks Green (`#006241`)** anchors all headlines. **Green Accent (`#00754A`)** drives accent elements, bullet markers, KPI tile tops, and data highlights. **House Green (`#1E3932`)** provides the deep feature bands for section dividers and closing slides. **Gold (`#cba258`)** appears only for statistical significance badges and special clinical callouts.

Pretendard with universal `-0.01em` tracking reads confident and precise — appropriate for surgical data without feeling clinical or sterile. Weight shifts (700 → 500 → 400) carry hierarchy; size differences are secondary.

**Key Characteristics:**

- Four-tier green system (Starbucks Green · Green Accent · House Green · Green Uplift) each mapped to a distinct slide role — not a single "brand green"
- Gold (`#cba258`) reserved for statistical significance badges and clinical award moments only — never a general accent
- Warm-neutral canvas (`#f2f0eb`) references calm, authoritative academic materials
- Pretendard with tight `-0.01em` letter-spacing as the universal voice
- Full-pill badges (`50px` radius) for callout labels and status indicators
- 12px card/container radius for all box components
- Whisper-soft layered shadows — never a single heavy drop shadow

**Slide color-band rhythm:**

Neutral Warm (#f2f0eb)   ← Standard content slide background
White (#ffffff)           ← Card / container surfaces within the slide
House Green (#1E3932)    ← Section divider slides, closing slide
Neutral Warm (#f2f0eb)   ← Returns for content slides after a divider
House Green (#1E3932)    ← Final closing slide bookend

---

## 2. Color Palette & Roles

### Primary — Four-Tier Green System

| Token | Hex | RGB | Role in PPT |
| --- | --- | --- | --- |
| **Starbucks Green** | `#006241` | R0 G98 B65 | **Slide headlines**, data highlights, KPI numbers — primary brand signal |
| **Green Accent** | `#00754A` | R0 G117 B74 | **Accent bars** (KPI tiles, body box top bar), bullet markers (●), chart primary series |
| **House Green** | `#1E3932` | R30 G57 B50 | Cover, section divider, closing slide backgrounds (full-bleed dark bands) |
| **Green Uplift** | `#2B5148` | R43 G81 B72 | Mid-tone dark accent panels, decorative overlay rectangles on dark backgrounds |

### Secondary & Accent

| Token | Hex | Role in PPT |
|---|---|---|
| **Gold** | `#cba258` | Statistical significance badges, clinical award callouts, "next step" accent — NOT a general accent |
| **Gold Light** | `#dfc49d` | Background wash on gold-tier callout panels, border on "next step" cards |
| **Gold Lightest** | `#faf6ee` | Warm-cream surface under institutional logo zones, "next step" card background |

### Surface & Background

| Token | Hex | Role in PPT |
|---|---|---|
| **White** | `#ffffff` | Card surfaces, container fills, chart plot areas |
| **Neutral Cool** | `#f9f9f9` | Table header fills, secondary container washes |
| **Neutral Warm** | `#f5f4f2` | **Primary slide background** |
| **Ceramic** | `#edebe9` | Alternating table rows, subtle section washes |

### Text

| Token | Value | Role |
|---|---|---|
| **Text Black** | `rgba(0,0,0,0.87)` | Primary body text, table values, axis labels |
| **Text Soft** | `rgba(0,0,0,0.58)` | Secondary text, captions, footnotes, subtitle zone |
| **Text White** | `rgba(255,255,255,1.0)` | Headline / body on SK Dark bands |
| **Text White Soft** | `rgba(255,255,255,0.70)` | Secondary / caption on dark surfaces |

### Semantic

| Token | Value | Role |
|---|---|---|
| **Adverse Red** | `#c82014` | Adverse event callouts and annotations (e.g., complication rate label, AE-count badge). **Do NOT use as a comparator bar/line color** — for that, use Starbucks Green (secondary series). Reserve Red for cases where the slide is explicitly framing a negative event itself, not the comparator group. |
| **Yellow** | `#fbbc05` | Warning / caution annotations |
| **Positive Tint** | `#FFEBEF` | Positive finding wash (SK Red Light) |
| **Adverse Tint** | `hsl(4 82% 43% / 5%)` | Complication / negative finding wash |

---

## 3. Typography Rules

### Font Family

| Role | Stack |
|---|---|
| **Primary (all slides)** | `Pretendard, "Pretendard Variable", -apple-system, system-ui, sans-serif` |
| **Fallback only** | `"Helvetica Neue", Helvetica, Arial, sans-serif` |

No other typefaces. Pretendard is universal across all slide types.

### Type Scale

| Role | Size | Weight | Line Height | Letter Spacing | Color | Notes |
|---|---|---|---|---|---|---|
| **Cover Title** | **54pt** | 700 | 1.20 | `-0.01em` | `#FFFFFF` | Cover slide main title |
| **Display** | **32pt** | 700 | 1.20 | `-0.01em` | `#006241` | Content slide headline zone (H1) |
| **Cover Subtitle** | **20pt** | 700 | 1.45 | `-0.01em` | `#B3D4CB` | Cover study descriptor line |
| **Subtitle** | 12pt | 500 | 1.45 | `-0.01em` | `rgba(0,0,0,0.58)` | Content slide subtitle zone |
| **Body Large** | **24pt** | 700 | 32pt fixed | `-0.01em` | `#1F1F1F` | 본문 대제목 (level 0) — 단일 텍스트프레임 내 첫 번째 계층 |
| **Body** | **20pt** | 400 | 32pt fixed | `-0.01em` | `#1F1F1F` | 서브불릿 (level 1) — `●` 앞에 Green Accent (`#00754A`) **11pt** bold |
| **Body Detail** | **16pt** | 400 | 28pt fixed | `-0.01em` | `#6B6B6B` | 세부항목 (level 2) — `–` prefix, 회색 |
| **Chart Title** | 13pt | 600 | 1.20 | `-0.01em` | `rgba(0,0,0,0.87)` | Above every chart / diagram |
| **Axis Label** | 9–10pt | 400 | 1.20 | `-0.01em` | `rgba(0,0,0,0.58)` | Chart axis text, table column headers |
| **Caption / Source** | 8–9pt | 400 | 1.40 | `-0.01em` | `#8e8e93` | Source lines, footnotes |
| **KPI Number** | 26–32pt | 700 | 1.0 | `-0.01em` | `#006241` | Large number in KPI tile |
| **KPI Label** | 10pt | 500 | 1.30 | `-0.01em` | `rgba(0,0,0,0.58)` | Metric name beneath KPI number |
| **Badge / Tag** | 9pt | 700 | 1.0 | `0.05em` | White or Gold | Pill badge labels (p-value, status) |
| **Chapter Name** | 11pt | 600 | 1.0 | `-0.01em` | `#8e8e93` | Header strip left |
| **Footer / Page** | 9–10pt | 500 | 1.0 | `-0.01em` | `#8e8e93` | Footer strip |

### Principles

- **Tight negative tracking (`-0.01em`)** applied universally — confident without feeling squeezed.
- **Weight shifts carry hierarchy, not size shifts.** Weight (700 vs 600 vs 400) and color (Starbucks Green vs Text Black) separate levels.
- **Body text never goes pure black** — `rgba(0,0,0,0.87)` matches the warm canvas temperature.
- **Headline zone is always Starbucks Green (`#006241`)**. On House Green dark bands, switch to White.

---

## 4. Chart & Data Visualization Palette

### Primary Chart Colors

| Rank | Name | Hex | Use |
|---|---|---|---|
| 1 | Green Accent | `#00754A` | Primary series, bar fills, line strokes |
| 2 | Starbucks Green | `#006241` | Secondary series / comparison group |
| 3 | Green Light | `#d4e9e2` | Baseline / control group |
| 4 | Gold | `#cba258` | Highlight series, statistically significant finding |
| 5 | House Green | `#1E3932` | Dark accent series |
| 6 | Ceramic | `#edebe9` | Grid fill, background fill |
| 7 | Red | `#c82014` | Adverse event rate, complication series |

### Chart Styling Rules

- **Grid lines:** `1px solid #edebe9` — whisper soft
- **Axis lines:** `1px solid rgba(0,0,0,0.14)`
- **Plot area background:** `#ffffff`
- **Slide background behind chart:** `#f2f0eb`
- **Data labels:** Pretendard 10pt 600 — white on dark bars, Text Black on light bars
- **Chart border-radius:** `4px` on bars where renderer supports it
- **Legend:** Pretendard 10pt 400, `rgba(0,0,0,0.58)`, below or right of chart
- **P-value badge:** Gold pill — Pretendard 10pt 700, `#cba258` border, transparent fill, `50px` pill radius

### Two-Arm Comparison — Color Mapping Rule

For clinical comparisons between an *intervention* and a *comparator* (e.g., novel vs standard, treatment vs control), use the following mapping. Do **NOT** default Adverse Red to the comparator group even when its outcome is worse — that misuses the semantic role of red.

| Role | Color | Token |
|---|---|---|
| Intervention / novel arm (often the "good news" group) | `#00754A` | Green Accent (primary series) |
| Comparator / standard arm | `#006241` | Starbucks Green (secondary series) |
| Adverse event annotation only (a small badge labeling a discrete event count or AE rate) | `#c82014` | Adverse Red |
| Statistically significant finding badge | `#cba258` | Gold |

**Visual contrast tip:** when both bars are green tones (intervention green-accent, comparator starbucks-green), distinguish them by *length* and *labels*, not by chromatic opposition. The contrast comes from the magnitude of the data, not from a "good vs bad" color binary. If chromatic differentiation is essential, use House Green (`#1E3932`) as the comparator instead of Starbucks Green.

### Axis Label Size — Context-Dependent

The 9–10pt baseline in the Type Scale (Axis Label) applies to **dense reading documents** (e.g., printed reports viewed up close). For **podium presentation** decks projected to an auditorium, raise axis labels to **at least 12pt**, with key tick values (equivalence margins, primary thresholds) at **13–14pt 700** to read from the back row. The same minimum applies to forest-plot point estimates, p-value pills, and small legend text — none should drop below 12pt in presentation context.

### KPI Tile Spec

Container:      White (#ffffff), shadow
Top accent bar: 0.06" × full width, Green Accent (#00754A)
KPI Number:     **40pt**, Pretendard 700, #006241
KPI Label:      **12pt**, Pretendard 400, #6B6B6B
Delta badge:    **10pt** bold, White on Green Accent (positive) or Red (negative), pill shape w=0.72" h=0.24"
Chart Title:    **16pt** bold, #1F1F1F
Sparkline:      Green Accent stroke, no fill, 1.5px weight

---

## 5. Body Box Component Patterns

All patterns live strictly inside the body box (2.39"–6.85").

### Pattern A — Single Chart (Full Width)
[ Chart Title — Pretendard 600 14pt rgba(0,0,0,0.87)       ]
[ ──────────────────────────────────────────────────────── ]
[                                                            ]
[            Chart / Visualization                           ]
[                                                            ]
[ Source: _____ Pretendard 400 9pt #8e8e93                  ]

### Pattern B — KPI Tiles Row + Chart
[ KPI Tile ]  [ KPI Tile ]  [ KPI Tile ]  [ KPI Tile ]
[ ─────────────────────────────────────────────────── ]
[              Chart / Visualization                   ]
[ Source line                                          ]

### Pattern C — Two-Column (Claim / Evidence)
[ Claim Column 55%               | Evidence Column 45% ]
[ Headline claim, Body Large     | Chart or diagram     ]
[ Supporting bullets, Body       | with source below    ]
[ "Key Takeaway" callout strip   |                      ]

### Pattern D — Three KPI Tiles + Chart
[ KPI Tile A    |   KPI Tile B    |   KPI Tile C    ]
[ ─────────────────────────────────────────────────  ]
[         Supporting chart or comparison table        ]
[ Source                                              ]

### Pattern E — Full-Width Table
[ Table title — Pretendard 600 14pt                               ]
[ Header row: Neutral Cool (#f9f9f9), Pretendard 600 10pt         ]
[ Data rows: White / Ceramic alternating, Pretendard 400 10pt     ]
[ Row hairlines: 1px solid #e7e7e7                                ]
[ Source — Pretendard 400 9pt #8e8e93                             ]

### Pattern F — Stacked Insight Layers
[ Band 1: House Green (#1E3932) — Key Finding, White 700 14pt       ]
[ Band 2: Neutral Warm (#f2f0eb) — Supporting chart or evidence      ]
[ Band 3: Green Light (#d4e9e2) — Takeaway / clinical implication    ]

### Pattern G — Big Message

Single high-impact message slide. Use sparingly: hook slides, transition slides between major sections, or a moment of pause before/after a major result.

```
[ (Standard 5-zone skeleton — header strip + footer remain)         ]
[                                                                    ]
[                                                                    ]
[              <ONE BIG LINE>     ← 54–64pt, weight 700              ]
[              <ONE BIG LINE>        Starbucks Green or Green Accent ]
[              <ONE BIG LINE>        Centered, line-height ~1.15     ]
[                                                                    ]
[      <one short sub-line, italic, soft text>   ← 14–16pt, italic   ]
```

**Specs:**
- Lines: 1–3 short lines, each 1–4 words ideal. No bullets, no body card content otherwise
- Type: Pretendard 700, **54–64pt**, `#006241` (or `#00754A` for the punchline line)
- Anchor: centered both axes within body card region (roughly y = 2.5"–5.5")
- Sub-line (optional): Pretendard 500, **14–16pt italic**, `rgba(0,0,0,0.58)`, below main lines, centered
- Background remains Neutral Warm; do NOT switch to House Green for emphasis — that role belongs to the Closing slide

### Pattern H — Pillar Cards

Three (occasionally two or four) parallel "pillars" summarizing a multi-dimensional message. Used commonly for Conclusion slides (Efficacy / Safety / Value) or summary slides.

```
[ ┌───────────┐  ┌───────────┐  ┌───────────┐                       ]
[ │ [TAG]     │  │ [TAG]     │  │ [TAG]     │   ← top accent bar    ]
[ │           │  │           │  │           │     + tag pill        ]
[ │  BIG WORD │  │  BIG WORD │  │  BIG WORD │   ← 40–48pt headline  ]
[ │  sub word │  │  sub word │  │  sub word │   ← 16–20pt subline   ]
[ │           │  │           │  │           │                       ]
[ │  short    │  │  short    │  │  short    │   ← 12–14pt body      ]
[ │  body     │  │  body     │  │  body     │     (1–3 lines)       ]
[ └───────────┘  └───────────┘  └───────────┘                       ]
[                                                                    ]
[ ▌ Take-home strip — House Green, white text, full width             ]
```

**Specs:**
- Card container: White (`#ffffff`), 12px radius, whisper shadow
- Top accent bar: 0.08–0.10" tall, full card width, **Green Accent (`#00754A`)**
- Tag pill (centered horizontally near top): Green Accent fill, white Pretendard 700 12–14pt, all caps
- Big word: Pretendard 700, **40–48pt**, Starbucks Green (`#006241`), centered, single line
- Sub word: Pretendard 700, 16–20pt, Text Black, centered
- Body text: Pretendard 400, 12–14pt, Text Body, centered, 1–3 lines
- Card spacing: equal gaps between cards (~0.18–0.22")
- Optional: bottom House-Green strip carrying a unified take-home sentence

### Pattern I — Forest Plot / Equivalence Plot

Used for equivalence/non-inferiority RCT primary outcomes and meta-analytic comparisons. Each trial (or subgroup) occupies its own horizontal panel for breathing room; do NOT stack rows in a dense table-style forest plot.

```
[ ┌─────────────────────────────────────────────────────────────┐  ]
[ │▌Left Label Zone │           Plot Zone               │ p-val│  ]
[ │ Trial name      │   [equivalence margin band ]      │  pill│  ]
[ │ Journal · Year  │       ━━━━━●━━━━━                 │      │  ]
[ │ [Pathology pill]│   ↑ point estimate + CI bar       │      │  ]
[ │ n = NN          │   −margin  0  +margin  axis ticks │      │  ]
[ └─────────────────────────────────────────────────────────────┘  ]
[ (one panel per trial — keep at least 0.20" gap between panels)   ]
[                                                                   ]
[      Axis caption: variable difference (intervention − comp.)    ]
[                                                                   ]
[ ▌ Key takeaway strip — House Green or Green Accent fill          ]
```

**Specs:**
- Panel: white or Neutral Cool (`#f9f9f9`) fill, 8–12px radius, ~2.2" tall, full width
- Panel left accent bar: 0.08" wide, full panel height, in the arm-specific accent color
- Equivalence margin band: shaded rectangle from −margin to +margin, fill **Green Light (`#d4e9e2`)**, spanning ~80% of panel height vertically
- Margin boundary lines: thin vertical lines at ±margin, **Starbucks Green (`#006241`)**, 0.012"–0.016" wide
- Zero reference line: thin vertical line at x=0, soft gray (`#7A7A7A`), 0.008"–0.010" wide
- Confidence interval bar: rectangle from CI_low to CI_high, 0.06–0.08" thick, in the arm accent color
- CI end caps: short vertical caps at both ends, same color, 0.18–0.36" tall
- Point estimate marker: filled diamond, 0.20–0.30" wide, in the arm accent color
- Mean difference text (above CI bar): Pretendard 700, **15–17pt**, in arm accent color, format `+X.X (95% CI -Y.Y to +Z.Z)`
- Axis tick labels: Pretendard, **11–13pt** (use 13pt 700 for margin ticks, 11pt 500 for other ticks); margin ticks colored Starbucks Green to call them out
- Axis caption (below all panels): Pretendard 500, 12pt, Text Soft, centered
- P-value badge (right side of each panel): pill in arm accent color, white Pretendard 700 13–14pt, format `p = 0.XX`
- Key takeaway strip (full-width band below): House Green or Green Accent fill, white Pretendard 700 14–17pt, single sentence (e.g., "✓ Both 95% CIs lie within the ±margin")

**When to use:** equivalence/non-inferiority trials where the audience needs to *see* that the CI is inside the margin band, not just read a p-value. The visual proof IS the slide.

---

## 6. Slide Type Specifications

### Cover Slide
- Background: **House Green (`#1E3932`)** full bleed
- Title: Pretendard 700, **54pt**, White, `x:0.6" y:2.0775" w:9.0" h:1.8225"`
- Study descriptor: Pretendard 700, **20pt**, `#B3D4CB`, `x:0.6" y:4.3" w:9.0" h:0.38"`
- Label pill: Pretendard 700, **14pt**, White on Green Accent, `x:0.6" y:1.11" w:2.7874" h:0.49"`
- Green accent line: `x:0.6" y:5.05" w:1.8" h:0.04"`, color `#00754A`
- Affiliation (BR): **25pt**, `#8BB8AE`, `x:7.5093" y:5.58"`; Name (BR): **27pt**, White, `x:7.5093" y:5.9904"`
- Conference + date (BL): **16pt**, `#8BB8AE`, `x:0.2977" y:6.9752"`
- SNUBH logo: `w:1.2887" h:0.8519"`, top-right anchored
- No header strip, no footer strip

### Section Divider Slide
- Background: **House Green (`#1E3932`)** full bleed
- Watermark section number: Pretendard 700, 48pt, `rgba(255,255,255,0.14)`, bottom-right
- Section title: Pretendard 700, 26pt, White, left-aligned, vertically centered
- Section subtitle: Pretendard 400, 14pt, `rgba(255,255,255,0.70)`
- SNUBH logo: white variant, top-right
- No body box content

### Standard Content Slide
- Background: **Neutral Warm (`#f2f0eb`)**
- Five-zone locked skeleton (see §0 — use measured coordinates)
- Headline: Starbucks Green (`#006241`), Pretendard 700, **32pt**, at `x:0.2752" y:0.4771" w:11.0" h:0.50"`
- Body: White card at `x:0.2752" y:1.4111" w:12.7946" h:5.7167"`, 12px radius, whisper shadow
- Header chapter name: `x:0.1512" y:0.135"`, Pretendard 600, 11pt, `#8e8e93`

### Conclusion Content Slide

A **Conclusion slide** that carries actual conclusion content (pillars, summary table, three-bullet take-home) is a **standard content slide**, NOT a Closing / Thank You slide. It uses the Neutral Warm canvas, full 5-zone skeleton, and a body card that holds the conclusion structure.

- Background: **Neutral Warm (`#f2f0eb`)** — not House Green
- 5-zone skeleton: full (header strip, headline, subtitle, body card, footer)
- Header chapter name: `CONCLUSION`
- Headline (Starbucks Green): the conclusion claim itself
- Body card contents: pillar cards (see Pattern H), take-home strip, or summary visualization
- Footer: page number + source line as usual

Switching a Conclusion slide to the House Green full-bleed design (below) reads as "Thank you" to the audience and dilutes the conclusion content. Keep them visually separated.

### Closing / Thank You Slide
- Use **only as the standalone final slide**, after the Conclusion content slide
- Background: **House Green (`#1E3932`)** full bleed
- Headline: White, Pretendard 700, 28pt
- Affiliation / contact: Pretendard 400, 11–12pt, `rgba(255,255,255,0.70)`
- SNUBH logo: white variant, top-right
- If your acknowledgements list is long, prefer a **standard content slide with "Acknowledgements" chapter name + "Thank you" headline** instead of cramming text onto the dark band

---

## 7. Depth & Elevation

| Level | Shadow | Use |
|---|---|---|
| **Card** | `0 0 0.5px rgba(0,0,0,0.14), 0 1px 1px rgba(0,0,0,0.24)` | KPI tiles, body containers, table cards |
| **Float badge** | `0 2px 6px rgba(0,0,0,0.18)` | Floating annotation callouts, pill badges |
| **Chart container** | `0 1px 3px rgba(0,0,0,0.10), 0 0 2px rgba(0,0,0,0.07)` | Chart area lifted off slide canvas |

**Philosophy:** Never a single heavy drop shadow. Stack 2–3 low-alpha shadows with different offsets.

### Border Radius Scale

| Value | Use |
|---|---|
| `12px` | Cards, KPI tiles, container boxes, chart frames |
| `50px` | All pill-shaped badges, callout labels, p-value tags |
| `50%` | Circular icons, step-number circles |
| `4px` | Table cells, axis-aligned rectangles in diagrams |

---

## 8. Do's and Don'ts

### Do ✓
- Use **Neutral Warm (`#f2f0eb`)** as the standard slide canvas
- Map greens correctly: **Starbucks Green for headlines · Green Accent for data highlights · House Green for deep bands**
- Apply **`-0.01em` letter-spacing** universally (including header strip — no extra tracking for caps)
- Reserve **Gold (`#cba258`) for statistical significance and clinical awards only**
- For two-arm comparisons: **intervention = Green Accent**, **comparator = Starbucks Green** (or House Green if higher contrast needed). Reserve Adverse Red for the *event annotation itself*, not the comparator group
- In presentation context, raise axis labels and small chart text to **≥12pt** (the 9–10pt baseline applies to dense reading documents only)
- Layer 2–3 low-alpha shadows on cards
- Keep all body content strictly inside 2.39"–6.85"
- Visualize data as charts first
- Use weight contrast (700 → 600 → 500 → 400) as the primary hierarchy signal
- For Conclusion slides with actual content: use the **standard content slide** layout, not the House-Green Closing layout (which is reserved for the standalone Thank You slide)

### Don't ✗
- Don't use pure white (`#ffffff`) as the slide canvas
- Don't collapse the four-tier green system to a single green
- Don't use Gold as a general-purpose accent
- Don't color the comparator group bar/line in Adverse Red just because its outcome looks worse — that misuses Red as a "good vs bad" binary instead of "event annotation"
- Don't apply extra letter-spacing (e.g., `+0.05em`) to header strip caps — keep it at the universal `-0.01em`
- Don't leave the bottom 30% of the body box empty
- Don't let content invade header strip, subtitle zone, or footer clearance
- Don't introduce gradient fills — color-block throughout
- Don't use pure black for body text — use `rgba(0,0,0,0.87)`
- Don't stack a single heavy shadow
- Don't mix or substitute typefaces
- Don't place more than 2 visualizations on a single slide
- Don't put Conclusion content on a House Green full-bleed slide — that layout is reserved for the standalone Thank You slide
- Don't ship a presentation deck with axis labels < 12pt; they will not read from the back of the room

---

## 9. Agent Prompt Guide

### Quick Color Reference

| Role | Value |
|---|---|
| Slide canvas | `#f2f0eb` (Neutral Warm) |
| Card / container | `#ffffff` (White) |
| Deep band / divider | `#1E3932` (House Green) |
| Headline text | `#006241` (Starbucks Green) |
| Headline text on dark | `rgba(255,255,255,1.0)` |
| Data highlight | `#00754A` (Green Accent) |
| Body text | `rgba(0,0,0,0.87)` |
| Secondary / caption | `rgba(0,0,0,0.58)` |
| Body text on dark | `rgba(255,255,255,0.70)` |
| Gold — significance / award | `#cba258` |
| Chart primary series | `#00754A` |
| Chart secondary series | `#006241` |
| Chart highlight / p-value | `#cba258` |
| Error / adverse event | `#c82014` |
| Footer / source | `#8e8e93` |

### Example Component Prompts

**1. KPI tile row (4 tiles)**
> "Row of 4 KPI tiles, each White (`#ffffff`) 12px radius, shadow `0 0 0.5px rgba(0,0,0,0.14), 0 1px 1px rgba(0,0,0,0.24)`. Each tile: 4px top accent bar Green Accent (`#00754A`), KPI number Pretendard 700 32pt `#006241`, label Pretendard 500 11pt `rgba(0,0,0,0.58)`, delta badge white on Green Accent (positive) or Red (negative) 50px pill. Supporting chart below. Canvas Neutral Warm (`#f2f0eb`)."

**2. Surgical outcome comparison chart**
> "Grouped horizontal bar chart, two surgical cohorts, 4 outcome metrics. Primary series Green Accent (`#00754A`), secondary Starbucks Green (`#006241`). Chart title Pretendard 600 14pt. Axis labels Pretendard 400 10pt `rgba(0,0,0,0.58)`. Grid `1px solid #edebe9`. Plot area White. Significant bars annotated with Gold pill badge (`#cba258` border, 50px radius, 'p < 0.05' Pretendard 700 10pt gold)."

**3. Section divider slide**
> "Full-bleed House Green (`#1E3932`). Watermark number '02' Pretendard 700 48pt `rgba(255,255,255,0.14)` bottom-right. Section title Pretendard 700 26pt White left-aligned vertically centered. Subtitle Pretendard 400 14pt `rgba(255,255,255,0.70)`. SNUBH logo white variant top-right."

**4. Study design timeline — Pattern C**
> "Two-column Pattern C. Left (55%): claim Pretendard 600 13pt, 3 bullets Pretendard 400 11pt, Key Takeaway strip House Green fill White Pretendard 600 11pt. Right (45%): horizontal arrow-flow, 4 phase boxes White 12px-radius Green Accent 4px top bar, arrows Green Accent. Canvas Neutral Warm."

**5. Outcome data table — Pattern E**
> "6-column table. Header: Neutral Cool (`#f9f9f9`) Pretendard 600 10pt. Rows: White/Ceramic alternating Pretendard 400 10pt. Significant p-values: Gold pill (`#cba258` border, transparent fill, 50px). Hairlines `1px solid #e7e7e7`. Title Pretendard 600 14pt above. Source Pretendard 400 9pt `#8e8e93` below."

**6. Pattern F — Stacked Insight Layers**
> "Three bands inside body box. Band 1: House Green (`#1E3932`) fill, White Pretendard 700 14pt. Band 2: Neutral Warm fill, grouped bar chart Green Accent + Starbucks Green. Band 3: Green Light (`#d4e9e2`) fill, Pretendard 500 12pt `rgba(0,0,0,0.87)` clinical implication."

**7. Closing / Thank You slide**
> "Full-bleed House Green (`#1E3932`). 'Thank You' Pretendard 700 40pt White centered. Presenter name/affiliation Pretendard 500 18pt `rgba(255,255,255,0.70)`. Contact Pretendard 400 14pt `rgba(255,255,255,0.58)`. SNUBH logo white variant top-right."

### Iteration Checklist

1. ✅ Headline in Starbucks Green (`#006241`) — or White on House Green slides
2. ✅ Slide canvas is Neutral Warm (`#f2f0eb`) — not pure white
3. ✅ Body card at `x:0.2752" y:1.4111" w:12.7946" h:5.7167"`; footer at `y:7.24"` — card must not overflow
4. ✅ Pretendard `-0.01em` letter-spacing on all text
5. ✅ Gold only for significance badges or awards — not as general accent
6. ✅ Cards on White (`#ffffff`) with 2-layer soft shadow
7. ✅ Chart primary = Green Accent (`#00754A`); secondary = Starbucks Green (`#006241`)
8. ✅ No single heavy shadow — always 2–3 low-alpha layers
9. ✅ Body box density rule observed — not more than 30% empty
10. ✅ Cover / section dividers / closing → House Green full bleed only

---

## 10. Known Gaps & Notes

- **Pretendard availability:** Ensure Pretendard is installed on all presentation machines. Embed font in PPTX export settings.
- **SoDoSans equivalence:** Pretendard substitutes for Starbucks' proprietary SoDoSans. The `-0.01em` tracking reads well in Pretendard; try `-0.005em` at very small sizes (9–10pt) if it looks too tight.
- **Chart renderer limitations:** PowerPoint's native chart engine does not support `border-radius` on bars. For rounded bar aesthetics, use an external renderer (Python matplotlib/seaborn export) and embed as image inside the body box.
- **Gold pill badges on charts:** Use a floating text box with `#cba258` fill and manual pill rounding in PowerPoint.
- **Logo white variant:** Prepare white-recolored SNUBH logo PNG in advance — do not recolor inside PowerPoint.
- **Transitions:** Use PowerPoint "Fade" (0.3s) as the closest equivalent to the web reference's `0.2s ease`. Avoid decorative morph/wipe transitions.
- **Korean/Latin mixed text:** Verify `-0.01em` does not negatively affect Korean glyph spacing at 9–10pt; adjust to `0em` for Korean-only small-body passages if needed.