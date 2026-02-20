# Postflow Figma to HTML/CSS Translation

## Background and Motivation

Restart the implementation from a completely clean slate. All previously generated HTML/CSS/JS should be removed so we can rebuild the Postflow billing screen directly from the Figma design (`node-id=0:50`) without legacy constraints. We still target a faithful vanilla HTML/CSS translation with shadcn-inspired interaction polish, but the emphasis is now on a methodical rebuild that double-checks specs at each step.

## Key Challenges and Analysis

1. **Design token fidelity**: Need precise Switzer font weights, stone palette hexes, gradient values, and consistent radii/shadows from the Figma spec.
2. **Hero layout**: Two-column card with layered background (grid lines + glow) that must remain centered and scale gracefully down to tablet widths.
3. **Interactive states**: Payment method toggle, inputs, and CTA gradients require hover/focus states resembling shadcn defaults.
4. **Asset sourcing**: Need vector versions of logo, icons, and background motifs (may require exporting SVGs or recreating with CSS).
5. **Testing**: Visual regression (manual screenshot diff) plus basic DOM assertions to ensure structure renders without console errors.

## High-level Task Breakdown

### Task 0: Clean Slate
- [ ] Remove existing `index.html`, `styles.css`, `app.js`, and any derived assets/configs
- [ ] Create empty scaffolding (fresh HTML/CSS files + optional asset folders)
- **Success Criteria**: Repo contains only minimal starter files with no legacy markup/styles.

### Task 1: Spec Extraction & Token Sheet
- [ ] Capture typography, spacing, radii, shadows, gradients, and assets directly from Figma
- [ ] Document them in `/docs/tokens.md` and wire into `:root` CSS variables
- **Success Criteria**: Token table matches Figma; CSS variables ready for use.

### Task 2: Base Layout & Background Canvas
- [ ] Build semantic HTML skeleton (header, hero title, two-column card)
- [ ] Implement background grid/glow lines per Figma, ensuring proper z-index layering
- **Success Criteria**: Page shell renders with correct canvas before card details.

### Task 3: Left Column (Header + Form)
- [ ] Implement header (logo, close button) and hero copy exactly
- [ ] Build payment form elements with accurate spacing, validations, helper text
- **Success Criteria**: Left card visually matches Figma snapshot with interactive states.

### Task 4: Right Column (Summary + CTA)
- [ ] Implement summary pricing, discount rows, CTA button, footnote copy
- [ ] Add button/interaction states (hover, focus) to match design cues
- **Success Criteria**: Summary column aligns pixel-for-pixel with Figma.

### Task 5: QA & Polish
- [ ] Desktop/tablet responsive checks, cross-browser smoke test
- [ ] Fine-tune typography/spacings; ensure assets optimized
- **Success Criteria**: Manual review shows no divergence; lint/tests pass.

## Project Status Board

- [x] Task 0: Clean Slate
- [x] Task 1: Spec Extraction & Token Sheet
- [x] Task 2: Base Layout & Background Canvas
- [x] Task 3: Left Column (Header + Form)
- [x] Task 4: Right Column (Summary + CTA)
- [ ] Task 5: QA & Polish

## Current Status / Progress Tracking

**Current Status**: Task 4 complete. Right column now features the Postflow Pro pricing summary, discount line, total, subscribe CTA, and terms copy styled per Figma.

**Next Step**: Task 5—QA polish (alignment tweaks, responsive test, final adjustments).

## Executor's Feedback or Assistance Requests

- Placeholder icons currently CSS blocks; will swap to actual SVGs in later pass if needed.

## Lessons

*No new lessons—carry over prior guidance (read files first, include debug info, run npm audit if vulnerabilities appear, ask before using `-force`).*
