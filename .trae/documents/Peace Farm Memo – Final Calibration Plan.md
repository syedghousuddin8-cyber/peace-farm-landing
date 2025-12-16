## Desktop Flow Refinements
- Enforce left alignment and reduce modular segmentation across sections. Remove component-like backgrounds and heavy dividers; keep only hairline rules.
- Reduce hero prominence to printed-memo scale. Decrease `hero-title` size and neutralize accent color to ink for calm gravity.
- Financial band reads as a single term sheet strip: drop per-cell borders, keep a single hairline rule top and bottom; labels lighter/smaller, values darker/anchored.
- Compliance area becomes footnote-like: remove grey panel, increase margins and keep one hairline above; ensure legal line stands alone.
- Gatekeeper CTA moves from fixed bar to a final endpoint section with hairline top, no blur/hover. Procedural tone only.

## Mobile Flow Refinements (Confidential Brief)
- Remove card feeling entirely: no panel backgrounds, no strong dividers; flow as single-column notes.
- Reduce header dominance; tighten `hero-title` and abstract spacing, let content read vertically like a PDF.
- Term sheet collapses into a clean two-column list without cell borders; numbers stay visually dominant.
- CTA becomes a simple footer block at the end, matching memo tone and spacing.

## Typography Micro-Adjustments
- Reduce font-size variance: decrease headings, keep body stable; numbers visually outweigh words.
- Reduce bold usage by ~20%: lower weights on headings and labels; minimize uppercase letter-spacing.
- Neutralize expressiveness: shift most accent color to ink on headings; reserve accent for minimal cues.
- Term sheet: labels lighter/smaller; values darker (ink) and tabular; subtitles non-italic and lighter.

## Spacing & Continuity Tuning
- Normalize vertical rhythm across sections; reduce gaps in multi-column areas to lower visual rhythm.
- Increase margins around legal text for due-diligence signaling; keep one hairline rule above.
- Treat each section as a paragraph: remove block-perimeter borders; rely on spacing and hairlines only.

## Minimal Copy Tightening (IC Language Only)
- Hero abstract (replace lines in `peace_farm.html:498–500`):
  "Clear-title agricultural parcel within RRR impact radius; positioned for land banking and allocation efficiency."
- Investment Logic nodes (`peace_farm.html:569–590`):
  1) Infra-Driven Uplift: "RRR access changes compress travel time; current pricing discounts relative to post-access valuations justify allocation."
  2) Inventory Constraint: "Contiguous clear-title parcels are limited; scarcity supports basis defensibility and exit."
  3) Cost Efficiency: "0% deferred payments lower capital density; staged outflows improve IRR."
- Audit statement (`peace_farm.html:597–600`):
  "Verified delivery of compliant land assets; title integrity and custody documented."
- Legal footer line already present (`peace_farm.html:556–559`): keep as is; increase surrounding margins.
- CTA microcopy already present (`peace_farm.html:613–614`): keep verbatim.

## Component → Document Transitions
- Hero abstract left rule becomes hairline; reduce left padding to integrate with body text column.
- Term sheet grid reads as a single strip; remove inner borders and italic subs; numbers dominate.
- Compliance becomes a footnote paragraph; no panel background.
- CTA rendered as endpoint note with hairline top; no hover transitions, no blur.

## Final CSS Deltas (no execution yet)
```css
/* Typography */
h1, h2, h3 { font-weight: 400; color: var(--pe-ink); }
.hero-title { font-size: 2.2rem; margin: 16px 0 20px; }
.meta-label { font-size: 0.58rem; letter-spacing: 1px; color: #999; }

/* Hero abstract */
.hero-abstract { font-size: 0.9rem; padding-left: 12px; border-left: 1px solid var(--pe-line); color: #111; }

/* Term sheet */
.term-grid { border-top: 1px solid var(--pe-line); border-bottom: 1px solid var(--pe-line); }
.term-cell { padding: 16px 0; border-right: none; }
.term-val { color: var(--pe-ink); font-size: 1.4rem; }
.term-sub { font-size: 0.62rem; color: #888; font-style: normal; }

/* Compliance */
.compliance-block { background: transparent; padding: 48px 0; border-top: 1px solid var(--pe-line); }
.compliance-title { font-size: 0.95rem; font-weight: 500; }
.legal-footer { margin-top: 48px; padding-top: 12px; border-top: 1px solid var(--pe-line); font-size: 0.62rem; color: #777; }

/* Rationale */
.reason-grid { gap: 24px; }
.reason-node { border-top: 1px solid var(--pe-line); padding-top: 12px; }
.reason-title { font-weight: 500; font-size: 0.8rem; color: var(--pe-ink); }
.reason-body { font-size: 0.78rem; color: #333; }

/* Audit */
.audit-statement { font-size: 1rem; color: var(--pe-ink); margin-bottom: 24px; }
.audit-row { gap: 36px; border-top: 1px solid var(--pe-line); }
.audit-item strong { font-weight: 500; }

/* CTA – endpoint, not callout */
.gate-bar { position: static; background: var(--pe-paper); backdrop-filter: none; padding: 24px 0; border-top: 1px solid var(--pe-line); }
.gate-note { font-size: 0.55rem; color: #888; font-style: italic; }
.btn-alloc, .btn-call { height: 30px; padding: 0 16px; letter-spacing: 1px; transition: none; border: 1px solid var(--pe-line); background: transparent; color: var(--pe-ink); }
.btn-alloc:hover, .btn-call:hover { opacity: 0.9; }

/* Mobile */
@media (max-width: 768px) {
  .hero-title { font-size: 1.8rem; margin: 12px 0 16px; }
  .term-grid { grid-template-columns: 1fr 1fr; }
  .term-cell { border-bottom: none; padding: 10px 0; }
  .compliance-grid, .compliance-list { gap: 20px; }
  .gate-flex { gap: 10px; }
  .btn-alloc, .btn-call { width: 100%; }
}
```

## Validation
- Single question: "Would this be appropriate to circulate before a ₹10 Cr allocation discussion?" If yes, calibration passes; if it reads like a landing page, fail.