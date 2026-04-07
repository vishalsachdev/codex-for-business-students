# Business Model Canvas — Visual Design Specification

> **Purpose:** This file describes the exact visual layout of the Alexander Osterwalder / Strategyzer Business Model Canvas so that an AI agent can generate a pixel-accurate HTML/CSS, SVG, or React rendering of it. Use this as a knowledge source alongside `business-model-canvas.md` (content template).

---

## Canvas Grid Layout

The canvas is a single rectangular card divided into **5 columns × 3 rows**. The top two rows hold 9 content blocks; the bottom row spans the full width split into two halves.

```
┌──────────────┬──────────────────────────┬──────────────────┬──────────────────────────┬──────────────┐
│              │                          │                  │                          │              │
│              │      KEY ACTIVITIES      │                  │  CUSTOMER RELATIONSHIPS  │              │
│     KEY      │         (2A)             │      VALUE       │          (4A)            │   CUSTOMER   │
│  PARTNERS    ├──────────────────────────┤   PROPOSITIONS   ├──────────────────────────┤   SEGMENTS   │
│     (8)      │                          │       (2)        │                          │     (1)      │
│              │      KEY RESOURCES       │                  │        CHANNELS          │              │
│              │         (6A)             │                  │          (3A)            │              │
├──────────────┴──────────────────────────┴────────┬─────────┴──────────────────────────┴──────────────┤
│                                                  │                                                  │
│               COST STRUCTURE (9)                 │              REVENUE STREAMS (5)                  │
│                                                  │                                                  │
└──────────────────────────────────────────────────┴──────────────────────────────────────────────────┘
```

### Precise Column / Row Spans

| Block                  | Grid Column   | Grid Row | Approximate Width | Approximate Height |
|------------------------|---------------|----------|-------------------|--------------------|
| Key Partners (8)       | col 1         | row 1–2  | 20%               | 66%                |
| Key Activities (7)     | col 2         | row 1    | 20%               | 33%                |
| Key Resources (6)      | col 2         | row 2    | 20%               | 33%                |
| Value Propositions (2) | col 3         | row 1–2  | 20%               | 66%                |
| Customer Rel. (4)      | col 4         | row 1    | 20%               | 33%                |
| Channels (3)           | col 4         | row 2    | 20%               | 33%                |
| Customer Segments (1)  | col 5         | row 1–2  | 20%               | 66%                |
| Cost Structure (9)     | col 1–2 + half of 3 | row 3 | 50%          | 33%                |
| Revenue Streams (5)    | half of 3 + col 4–5 | row 3 | 50%          | 33%                |

### CSS Grid Implementation

```css
.bmc-canvas {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
  grid-template-rows: 1fr 1fr 0.7fr;
  grid-template-areas:
    "partners activities  value  relationships  segments"
    "partners resources   value  channels       segments"
    "costs    costs       costs-rev  revenue    revenue";
  gap: 0;
  width: 100%;
  max-width: 1200px;
  aspect-ratio: 1.6 / 1;
  border: 2px solid #333;
  font-family: 'Segoe UI', system-ui, sans-serif;
}

/* Note: costs-rev area is split visually via a centered vertical divider.
   In practice, make Cost Structure span cols 1-3 and Revenue Streams span cols 3-5,
   or use the 10-column approach below for pixel accuracy. */
```

### Alternative: 10-Column Grid (More Precise)

```css
.bmc-canvas {
  display: grid;
  grid-template-columns: repeat(10, 1fr);
  grid-template-rows: 1fr 1fr 0.7fr;
  gap: 0;
}

.partners       { grid-column: 1 / 3;   grid-row: 1 / 3; }
.activities     { grid-column: 3 / 5;   grid-row: 1 / 2; }
.resources      { grid-column: 3 / 5;   grid-row: 2 / 3; }
.value          { grid-column: 5 / 7;   grid-row: 1 / 3; }
.relationships  { grid-column: 7 / 9;   grid-row: 1 / 2; }
.channels       { grid-column: 7 / 9;   grid-row: 2 / 3; }
.segments       { grid-column: 9 / 11;  grid-row: 1 / 3; }
.costs          { grid-column: 1 / 6;   grid-row: 3 / 4; }
.revenue        { grid-column: 6 / 11;  grid-row: 3 / 4; }
```

---

## Visual Styling

### Colors (Strategyzer-inspired palette)

| Element              | Color         | Notes                            |
|----------------------|---------------|----------------------------------|
| Canvas background    | `#FFFFFF`     | White                            |
| Block borders        | `#333333`     | Thin (1–2px) solid lines         |
| Block header text    | `#333333`     | Bold, uppercase, 0.75rem         |
| Block body text      | `#555555`     | Regular weight, 0.85rem          |
| Icon accent color    | `#F5A623`     | Optional — warm yellow/amber     |
| Cost Structure bg    | `#FAFAFA`     | Subtle distinction for bottom row|
| Revenue Streams bg   | `#FAFAFA`     | Subtle distinction for bottom row|

### Typography

- **Block headers:** Bold, uppercase, small (11–13px), letter-spacing 0.5–1px
- **Block content:** Regular weight, 13–15px, line-height 1.4
- **Canvas title:** Placed above the grid — bold, 18–24px

### Icons (Optional — Strategyzer Style)

Each block traditionally has a small icon in the header area:

| Block                | Icon Description                         |
|----------------------|------------------------------------------|
| Key Partners         | Handshake / linked chain                 |
| Key Activities       | Checkmark in circle / gear               |
| Key Resources        | Factory / building                       |
| Value Propositions   | Gift box / diamond                       |
| Customer Rel.        | Heart / people with heart                |
| Channels             | Delivery truck / arrow path              |
| Customer Segments    | Person silhouette / group                |
| Cost Structure       | Dollar sign / coins                      |
| Revenue Streams      | Cash register / money flow               |

---

## Block Content Layout

Each block follows this internal structure:

```
┌─────────────────────────┐
│ 🎁 VALUE PROPOSITIONS   │  ← icon + header (uppercase, bold)
│─────────────────────────│
│                         │
│ • Bullet point 1        │  ← content area (bulleted list or
│ • Bullet point 2        │     short paragraphs, left-aligned)
│ • Bullet point 3        │
│                         │
└─────────────────────────┘
```

- Header pinned to top of block
- Content area scrollable if overflow (for interactive versions)
- Padding: 12–16px inside each block
- Bullet style: `•` or `–`, not numbered

---

## Responsive Behavior

| Breakpoint      | Layout                                                    |
|-----------------|-----------------------------------------------------------|
| ≥ 1024px        | Full 5-column canvas (landscape)                          |
| 768px – 1023px  | Scale down proportionally, reduce font size               |
| < 768px         | Stack blocks vertically in reading order: Value Prop → Customer Segments → Channels → Customer Rel. → Key Activities → Key Resources → Key Partners → Cost Structure → Revenue Streams |

---

## HTML Structure Reference

```html
<div class="bmc-wrapper">
  <h2 class="bmc-title">Business Model Canvas — [Company Name]</h2>
  <div class="bmc-canvas">
    <div class="bmc-block partners">
      <div class="bmc-block-header">
        <span class="bmc-icon">🤝</span> Key Partners
      </div>
      <div class="bmc-block-content">
        <ul>
          <li>Partner 1</li>
          <li>Partner 2</li>
        </ul>
      </div>
    </div>
    <!-- ... repeat for all 9 blocks ... -->
  </div>
</div>
```

---

## SVG Alternative (For Static / Print Output)

When generating an SVG version:

- Canvas dimensions: `viewBox="0 0 1200 750"`
- Use `<rect>` for each block with `stroke="#333"` and `fill="#fff"`
- Use `<text>` with `font-weight="bold"` and `text-transform="uppercase"` for headers
- Use `<foreignObject>` for rich text / bullet lists inside blocks
- Bottom row splits at x=600 (midpoint)

### SVG Block Coordinates

| Block              | x    | y    | width | height |
|--------------------|------|------|-------|--------|
| Key Partners       | 0    | 0    | 240   | 500    |
| Key Activities     | 240  | 0    | 240   | 250    |
| Key Resources      | 240  | 250  | 240   | 250    |
| Value Propositions | 480  | 0    | 240   | 500    |
| Customer Rel.      | 720  | 0    | 240   | 250    |
| Channels           | 720  | 250  | 240   | 250    |
| Customer Segments  | 960  | 0    | 240   | 500    |
| Cost Structure     | 0    | 500  | 600   | 250    |
| Revenue Streams    | 600  | 500  | 600   | 250    |

---

## Usage Instructions

### For AI Agents (Codex / Claude Code)

When asked to create a Business Model Canvas visualization:

1. **Read this file** for the visual layout specification
2. **Read `business-model-canvas.md`** for content structure / filled data
3. **Generate HTML + CSS** using the 10-column grid approach (most reliable)
4. **Populate** each block with the student's business data
5. **Output** as either:
   - An HTML file the student can open in a browser
   - A React/Next.js component for the student's app
   - An SVG for embedding or printing

### Prompt Example

> "Read the business model canvas design spec and the filled-out BMC for NovaBrew. Generate a single HTML page that displays the canvas as a visual grid matching the Strategyzer layout."

---

*Based on the Business Model Canvas by Alexander Osterwalder & Yves Pigneur (Strategyzer). This design specification is for educational use in generating visual representations.*
