# Design Language

A small visual system for hand-drawn diagrams and spot illustrations used inside the DataForest replica and any future content. The intent is to feel **drawn, not engineered** — warm, imperfect, and human, while still communicating structure clearly.

This is the design book. New sketches should follow these rules so the visual language stays consistent.

---

## 1. Philosophy

| Principle | Meaning |
|---|---|
| **Hand-drawn over geometric** | Lines wobble. Circles are not perfect. A diagram should look like it could have been sketched on a napkin. |
| **Illustrative over schematic** | Prefer a tree, a hand, a profile silhouette over a box-and-arrow flowchart. Iconographic, not architectural. |
| **Sparse over busy** | Each sketch should communicate exactly one idea. If a viewer needs a legend, the sketch is doing too much. |
| **Warm over cold** | Always work in the earth palette. Never pure black on pure white. Always cream-and-ink. |
| **One accent, max** | At most one terracotta spot per sketch. It is the punchline — spend it wisely. |
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

Terracotta       #9E4F2E   THE accent — one spot per sketch
Sage             #5C6B50   success, "trustworthy"
Sand             #B5956A   warmth, growth, honey
Capstone brown   #6B4A2A   deepest earth
```

**How to use the accent:** Terracotta is reserved. It marks the answer, the crown, the punchline — wherever the eye should end up. Do not use it for structural lines. Do not use it for more than one element in a sketch.

---

## 3. Stroke Rules

Hand-drawn feel comes from the strokes, not from filters.

```css
stroke-width: 5–8 (primary lines)
stroke-width: 3–4 (secondary detail)
stroke-linecap: round
stroke-linejoin: round
fill: none (most paths are outlined, not filled)
```

- **No straight horizontal or vertical lines.** Add a small wobble (Bezier control points 2–6 px off the axis).
- **No perfect circles for large shapes.** Use `<circle>` only for solid dots ≤ 14 px. Anything larger is drawn as a closed Bezier path with imperfect curves.
- **Endpoints matter.** Always `stroke-linecap: round`. Lines should look brushed, not laser-cut.
- **No drop shadows. No gradients. No filters.** Flat ink only.
- **Thick over thin.** A 6 px stroke on a 400 px sketch reads as confident. 2 px reads as cautious engineering.

---

## 4. Typography

- **Family:** Georgia, serif (matches the rest of the DataForest aesthetic)
- **Labels:** 14–18 px, used sparingly, italic for flow words ("trust →", "the gap")
- **Headings inside a sketch:** 20–26 px, all-caps when used as a layer name
- **Alignment:** centered under the thing they label, never floating in white space

Never mix serif and sans inside a single sketch.

---

## 5. The Motif Vocabulary

A small set of recurring shapes. **Mix and match from this list** rather than inventing new ones. Consistency across sketches is what makes them feel like a system.

| Motif | Used for |
|---|---|
| **Ball-tipped branching tree** (trunk + branches, each branch ends in a dot) | *The hero motif.* Organized data, structured insight, "a question with an answer", growth. Trees of different sizes represent progressions. |
| **Scattered dots** | Raw data, chaos, "data that exists" but can't be used |
| **Tangled scribble loop** | Confusion, the "before" state, unresolved questions |
| **Connected clusters** (dots joined by short lines) | Cleaned / deduplicated / processed data |
| **Profile silhouette** | The human — a domain expert, a stakeholder, the person who knows what a number means |
| **Hand reaching up / holding** | Asking a question, presenting, offering a finding |
| **Single ball on a stem** | A finding, "the thing at the top of the chain" — often the accent spot |
| **Ground line** (wobbly horizontal) | Shared base for multiple trees/figures growing side by side |
| **Dashed line / arrow** | Flow, time, progression, the gap between two states |

### The ball-tipped tree — anatomy

This is the signature motif. Every time you draw one, it follows this rule:

1. A trunk: one wobbly path from the ground upward.
2. Branches: 4–8 short curves coming off the trunk at staggered heights, alternating left and right.
3. **Every branch ends in a solid dot.** No open ends. No leaves. Just a ball at the tip.
4. Optionally a single crown dot at the top of the trunk.
5. Bigger tree = more branches = more structure = more "trust".

A sparse 3-branch tree is the seed of understanding. A full 8-branch tree is the finished answer.

---

## 6. Composition Rules

- **Read left to right, or bottom to top.** Use this to imply progression.
- **Anchor with one accent dot.** Each sketch should have at most 1 spot of terracotta. The rest is ink on cream. The accent draws the eye to the punchline.
- **Negative space is part of the drawing.** Don't fill the canvas. A sketch on an 800×400 canvas should occupy roughly 60% of it.
- **Repetition with variation.** When showing multiples (3 trees, 5 dots), let each one wobble differently. Identical copies break the hand-drawn feel.
- **Ground it.** Figures should sit on a ground line or inside an organic frame, not float.

---

## 7. Do / Don't

| ✅ Do | ❌ Don't |
|---|---|
| Wobbly Bezier curves | Perfect lines from `<line>` |
| Cream `#F5F0E8` background | Pure white `#fff` |
| One terracotta accent dot | Three competing accent colors |
| Georgia serif labels | Sans-serif system fonts |
| `stroke-linecap: round` | Default square caps |
| Ball-tipped trees, scattered dots, hands | Stacked rectangles, flowchart shapes |
| Two or three word labels | Sentences inside the diagram |
| Thick confident strokes (5–8 px) | Thin technical strokes (1–2 px) |
| Closed Bezier paths for frames | `<rect>` elements |

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

Each sketch is a single self-contained `.svg`. Inline the styles. No external dependencies. Optimized to under 6 KB so they can be committed without bloat.

---

## 9. Sample Sketches (the reference set)

The two reference sketches live in `design/sketches/`:

- **`module-3-slide-1.svg`** — *"The gap between data and insight"* — a tangled scribble with scattered dots on the left, a dashed gap in the middle, and a confident ball-tipped tree on the right. Terracotta accent: the single dot crowning the tree.

- **`module-3-slide-2.svg`** — *"Bronze, Silver, Gold as a progression"* — three ball-tipped trees of increasing size and branch count, sharing a common ground line. Bronze is small and sparse. Silver is medium. Gold is the largest and most branched, crowned with the single terracotta accent. A dashed "progression of trust →" line runs along the ground.

Use these as the starting reference for any new sketch.
