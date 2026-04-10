# Design Language

A small visual system for hand-drawn diagrams and spot illustrations used inside the DataForest replica and any future content. The intent is to feel **drawn, not engineered** — warm, imperfect, and human, while still communicating structure clearly.

This is the design book. New sketches should follow these rules so the visual language stays consistent.

---

## 1. Philosophy

| Principle | Meaning |
|---|---|
| **Hand-drawn over geometric** | Lines wobble. Circles are not perfect. A diagram should look like it could have been sketched on a napkin. |
| **Organic over technical** | Avoid grids, gradients, and corporate-clean iconography. Prefer branching, growing, scattered, tangled motifs. |
| **Sparse over busy** | Each sketch should communicate exactly one idea. If a viewer needs a legend, the sketch is doing too much. |
| **Warm over cold** | Always work in the earth palette. Never pure black on pure white. Always cream-and-ink. |
| **Show, don't label** | Prefer one visual word over a paragraph of caption. Two or three words of label maximum. |

---

## 2. Color Palette

The DataForest earth palette. These are the only colors a sketch should use.

```
Background       #F5F0E8   cream / paper
Surface          #FAF6EF   warm card
Ink (primary)    #2C2520   primary stroke / text
Ink (soft)       #5C4F45   secondary text
Ink (muted)      #8C7E6E   captions, dashed guides

Terracotta       #9E4F2E   primary accent — Bronze, danger, focus
Sage             #5C6B50   success, "trustworthy", Silver-equivalent
Sand             #B5956A   warmth, growth, Gold-equivalent
Capstone brown   #6B4A2A   deepest earth
```

**Layer mappings (medallion architecture):**
- **Bronze** → Terracotta `#9E4F2E`
- **Silver** → Stone `#8C7E6E`
- **Gold** → Sand `#B5956A`

We use earthy proxies, not literal metallic colors. Literal silver and gold clash with the warm palette.

---

## 3. Stroke Rules

Hand-drawn feel comes from the strokes, not from filters.

```css
stroke-width: 5–7 (primary lines)
stroke-width: 3–4 (secondary detail)
stroke-linecap: round
stroke-linejoin: round
fill: none (most paths are outlined, not filled)
```

- **No straight horizontal or vertical lines.** Add a small wobble (Bezier control points 2–6 px off the axis).
- **No perfect circles.** Use a `<circle>` only for solid dots ≤ 12 px. Larger circles should be drawn as paths with imperfect curves.
- **Endpoints matter.** Always `stroke-linecap: round`. Lines should look brushed, not laser-cut.
- **No drop shadows. No gradients. No filters.** Flat ink only.

---

## 4. Typography

- **Family:** Georgia, serif (matches the rest of the DataForest replica)
- **Labels:** 14–18 px, used sparingly
- **Headings inside a sketch:** 20–24 px, all-caps when used as a layer name
- **Italics** for trust/flow indicators ("trust →", "raw → usable")
- **Alignment:** centered under the thing they label, never floating in white space

---

## 5. Motifs

A small vocabulary of recurring shapes. Mix and match from this list rather than inventing new ones.

| Motif | Used for |
|---|---|
| **Branching tree** (trunk + dot-tipped branches) | Organized data, taxonomies, growth, "structured insight" |
| **Scattered dots** | Raw data, chaos, "data that exists" |
| **Connected clusters** (dots joined by short lines) | Cleaned / deduplicated data, intermediate layers |
| **Tangled scribble** | Confusion, the "before" state, unresolved questions |
| **Profile silhouette** | The human / domain expert who knows what a number means |
| **Hand reaching up** | Asking a question, presenting, holding a finding |
| **Rounded container** (rx 16–24, thick stroke) | A layer, a stage, a discrete concept being framed |
| **Dashed line / arrow** | Flow, time, progression, the gap between two states |
| **Single solid dot** | A node, a fact, a single record |
| **Small circle on a stick** | A flower, a finding, "the thing at the top of the chain" |

---

## 6. Composition Rules

- **Read left to right, or bottom to top.** Western reading order. Use it to imply progression.
- **Anchor with one accent dot.** Each sketch should have at most 1–2 spots of terracotta. The rest is ink on cream. The accent draws the eye to the punchline.
- **Negative space is part of the drawing.** Don't fill the canvas. A sketch on a 800×400 canvas should occupy roughly 60% of it.
- **Repetition with variation.** When showing multiples (3 layers, 5 dots), let each one wobble slightly differently. Identical copies break the hand-drawn feel.

---

## 7. Do / Don't

| ✅ Do | ❌ Don't |
|---|---|
| Wobbly Bezier curves | Perfect lines from `<line>` |
| Cream `#F5F0E8` background | Pure white `#fff` |
| One terracotta accent dot | Three competing accent colors |
| Georgia serif labels | Sans-serif system fonts |
| `stroke-linecap: round` | Default square caps |
| Branching trees, scattered dots | Stacked rectangles, flowchart shapes |
| Two or three word labels | Sentences inside the diagram |

---

## 8. File Structure

```
design/
├── DESIGN.md            ← this file
└── sketches/            ← all hand-drawn SVGs live here
    ├── module-3-slide-1.svg
    ├── module-3-slide-2.svg
    └── ...
```

Each sketch is a single self-contained `.svg`. Inline the styles. No external dependencies. Optimized to under 4 KB so they can be committed without bloat.

---

## 9. Sample Sketches

The first two reference sketches live in `design/sketches/`:

- `module-3-slide-1.svg` — *"The gap between data and insight"* — uses scattered-dots → arrow → branching-tree composition.
- `module-3-slide-2.svg` — *"Bronze, Silver, Gold"* — three rounded containers stacked, each holding a different data state, with a "trust →" indicator climbing up the side.

Use these as the starting reference for any new sketch.
