# Pattern Search spec package (docs only, no app code)

This turn produces documentation and image assets in the repo root. No UI is built yet.

## Files to create

```text
assets/01-pattern-search/
  01-pattern-search-main.png      (uploaded image 1: Pattern Region selected)
  02-detection-conditions.png     (uploaded image 2: Angle/Sensitivity/Accuracy/Min Match%)
  03-search-region-mask.png       (uploaded image 3: Search Region + Mask Region 0-3)
prompts/01-prompts/
  01-pattern-search-spec.md       (the single, complete spec to hand to an AI)
02-conversation/
  01-pattern-search-briefing.md   (verbatim capture of your two briefing messages)
```

Order of work: conversation capture first, then images, then the spec.

## What the spec file contains

One self-contained MD file, nothing split out:

1. **Context** — the app has a Modern UI (existing, flexible) and a Standard UI (this machine-style screen, replicating the vision-controller look). A per-case UI switch selects between them; the Modern UI must remain untouched and functional. Target route pattern follows the existing rules screen (e.g. `/setup/rules/:id`) with a Standard/Modern toggle.
2. **Hard DRY rule** — pattern types (Rectangle, Circle, future types), mask/region types, and all option lists come from one shared source of truth consumed by both UIs. Adding a pattern type in one place makes it appear in both. No duplicated option arrays, no forked components for shared logic; only presentation differs.
3. **Screen 1 anatomy (image 1)** — header readouts: Unit Time (`8.8ms`, meaning TBD, marked with an open question), Counts, Judged Label with Pos. X / Pos. Y / Angle / Match %; the `123.4` numeric-format icon; the `?` help button; the `1/2` page indicator with prev/next arrows. Image toolbar: source dropdown (Reference Image), rendering dropdown (Raw 2 / Filtered), refresh, zoom in / zoom out / fit, `40%` zoom readout (meaning of the percentage flagged as an open question), and the three view-mode icons. Right panel: tool title `T106 Pattern Search`, tree entry, `Reference Image 1 - 000` selector (meaning flagged as an open question), and the four tabs — Search Region, Pattern Region (selected/highlighted state described), Extract Colors, Image Enhance (contents deferred to a later screen). Edit Pattern Region body text, Pattern Region shape dropdown, and second Reference Image selector.
4. **Screen 2 anatomy (image 2)** — Detection Conditions panel after a pattern is set: Angle Range `+/- 030`, Detection Count `01`, Search Sensitivity slider (Normal), Accuracy slider (Normal), Min. Match% `40` with slider; the `>>` expander; canvas overlays (yellow image frame, blue search region, green pattern region, green orientation marker).
5. **Screen 3 anatomy (image 3)** — Search Region shape dropdown; Mask Region 0-3 as exactly four fixed slots, each a dropdown of region shapes (None + shared shape list); Image Region block with `Use Image Region` checkbox, Reference Tool selector, Detection Color White/Black radio, Preview button, all disabled until enabled (purpose flagged as an open question).
6. **Regions and layers model** — masks are layers: Standard UI = exactly 4 fixed mask layers; Modern UI = unlimited layers with draw tools and full flexibility. Both read the same region/shape definitions. On-canvas regions are draggable and resizable via corner and edge handles, with the colour coding above, live coordinate feedback into the header readouts, and clamping inside the image bounds.
7. **Bottom action bar** — Origin/Point, Display, OK, Cancel, the `...` / keypad button, Register Image, Run (primary highlighted blue), and the settings icon at far right: position, icon, label, colour, enabled/disabled behaviour, and expected action for each.
8. **Visual system** — dark chrome, thin light borders, small monospace-ish numeric fields with boxed values, green active-tab accent, blue primary action, exact colour/spacing guidance expressed as semantic design tokens rather than hardcoded colours.
9. **Open questions section** — Unit Time meaning, zoom `40%` semantics, `Reference Image 1 - 000` numbering, Image Enhance contents, Image Region purpose. Each marked so the AI asks rather than invents.
10. **Embedded images** — each of the three screenshots inline as base64 data URIs, plus cropped detail callouts (header strip, toolbar, tab row, detection conditions, mask region list, bottom bar) so the AI can zoom into each region it is asked to reproduce.

## Technical notes

- Crops are generated from the uploads with Pillow and embedded as base64 alongside the full screenshots.
- Full-size base64 embedding makes the MD file large (roughly 2-3 MB). If you would rather keep it lean, the alternative is embedding only the crops as base64 and referencing full images by repo path.
- Images are committed as real files under `assets/01-pattern-search/` as you asked, not CDN asset pointers, since they are spec source material.
