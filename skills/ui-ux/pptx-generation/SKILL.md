---
name: gdt-pptx
description: "Use this skill whenever creating, editing, or reviewing a PowerPoint deck for Geodata (GDT) — including GDT-branded pitch decks, service/capability decks, client-facing presentations, internal training or onboarding decks, or any pptx for GDT's clients/portfolio companies that doesn't have its own separate brand (e.g. GSM Outdoors uses its own terracotta brand — do not apply GDT purple to GSM work). Trigger this any time the user mentions 'GDT deck', 'Geodata deck', 'Geodata presentation', 'GeoDataTek presentation' (legacy spelling), 'company standard formatting/branding' for a slide deck, or references the GDT reference/sample pptx, even if they don't say 'branding' explicitly — e.g. 'make me a slide deck for our new service' from a GDT context should still use this skill. Always consult this before writing pptxgenjs code or editing slide XML for a GDT-branded deck, so colors, fonts, spacing, and layout patterns match the established GDT visual identity instead of generic defaults."
---
 
# GDT (Geodata) PowerPoint Branding
 
Encodes Geodata's official slide-deck design system, reverse-engineered measurement-by-measurement from GDT's reference deck (`GeoData - IT Security & Cybersecurity Services`), so new GDT decks reproduce the same visual language instead of generic AI-deck defaults. Every rule below is either measured directly from that file or an explicit GDT brand rule — nothing here is invented.
 
**This skill governs brand/design-system only.** For all mechanics of actually building or editing the `.pptx` file (pptxgenjs gotchas, template editing workflow, QA, converting to images, validation), use the `pptx` skill together with this one — read both before writing code.
 
## When to use this vs. plain `pptx`
 
- Building/editing a deck **for GDT itself** (GDT corporate decks, GDT service/capability decks, GDT sales/pre-sales pitch decks, GDT internal decks like onboarding/training) → use this skill's design system in full.
- Building a deck for a **GDT client or portfolio company that has its own brand** (e.g. GSM Outdoors — terracotta/red `C00000`, its own type system) → use that brand instead, not this one. Ask if it's unclear which brand applies.
## Visual Design Principles
 
This is the philosophy behind every rule further down — apply it as a lens whenever a situation isn't explicitly covered:
 
1. **Executive, not decorative.** The deck reads like a boardroom document, not a startup pitch. Flat fills, hairline borders, generous whitespace — never gradients, bevels, WordArt, or *outer* shadows. "Flat" here means nothing floats off the page; it does **not** mean zero effects. Every lavender card carries one subtle inner shadow (11pt blur, `3F248C`, 6% alpha) — see Depth & effects in `references/gdt-brand.md`.
2. **One accent color, used with restraint.** Purple (`3F248C`) is the single dominant brand color. It marks titles, icon fills, and emphasis — it is not sprinkled everywhere. Everything else is white, lavender tint, or steel-blue text.
3. **Structure over decoration.** Content is organized into a strict grid of square-cornered cards, tables, and one process-flow pattern — never plain unstructured bullet paragraphs, never decorative accent bars or edge stripes.
4. **Circles mean "icon," squares mean "content."** Rounding is reserved entirely for icon badges and short pill tags. Every content container — card, panel, table — has sharp 90° corners with a thin border. Mixing these up is the most common way a new deck stops looking on-brand.
5. **Consistent header/footer scaffolding, every slide, no exceptions.** Same logo positions, same title/subtitle treatment, same footer strip — the repetition across all 7 reference slides is itself the brand cue, not incidental.
6. **Concise, sentence-case, scannable text.** Titles and card headers are sentence case (not Title Case, not ALL CAPS). Body copy stays to 1–2 short lines per card — this is a system for skimming, not reading dense paragraphs.
7. **Aptos, full stop.** One typeface family for every element on every slide — titles, cards, tables, footers, even connector glyphs. No secondary or "accent" font is ever introduced.
## Typography — Aptos everywhere, with zero exceptions
 
Every piece of text on a GDT slide is **Aptos**. This is not limited to titles and body copy — it applies to every text-bearing element PowerPoint can produce, including ones that are easy to forget because they aren't hand-typed:
 
- Titles and subtitles
- Body text and bullet lists
- Card titles and card body copy
- Table headers and table body cells
- Header/logo-adjacent text (if any is ever added)
- Footer text (the static "Geodata - Confidential" string)
- Slide-number fields and date fields
- Chart titles, data labels, axis labels, and legends (if a chart is ever added — see Chart Styling below)
- Callouts and connector/separator glyphs (e.g. the "›" chevrons in a process flow)
- Placeholder/prompt text in any template placeholder
- SmartArt text, if content is ever converted to or through SmartArt
- Any other automatically-generated PowerPoint text (e.g. default chart series names)
**Why this needs to be explicit rather than assumed:** the reference deck's own slide master sets the *default* style for the footer, date, and slide-number placeholders to **Segoe UI**, not Aptos. Every actual instance of those fields in the deck overrides that default with an explicit `Aptos` typeface on the run — the deck never relies on inheritance for this. That means if a new slide inserts a date, slide-number, or footer field without explicitly setting the font, **PowerPoint will silently fall back to Segoe UI**, not Aptos, and not Calibri either — but the failure mode is the same: an unintended font sneaking in. Always set the font explicitly on every run, including field runs, rather than trusting placeholder inheritance.
 
There is no secondary or "accent" typeface anywhere in the reference deck. Calibri appears exactly once, on a single decorative chevron glyph — treat that as the one flaw to fix, never as precedent.
 
### Italic is part of the system — not decoration
 
The reference deck has **48 italic runs**, applied to one consistent tier of text. The test: **supporting copy is italic, content copy is roman.**
 
- **Italic:** slide subtitles (every content slide), cover subtitle, cover byline, cover pill tag, all full-width purple strips, the contact line.
- **Roman:** cover title, slide titles, card titles, card body, table headers and cells, tag chips, process-step numerals and titles, footer/date/slide-number.
Leaving subtitles roman is the most common way a new deck misses this — it's easy to overlook because the size and color are already correct.
 
## Quick reference
 
- **Canvas:** 16:9 widescreen, 13.333in × 7.5in (`pres.layout = "LAYOUT_WIDE"` in pptxgenjs)
- **Margins:** 0.6in symmetric left/right; content zone starts at y = 2.0in, below the title/subtitle block
- **Primary color:** purple `3F248C` (titles, icon fills, table headers, emphasis cards)
- **Backgrounds:** lavender tint `F5F3FB`, lavender-accent hairline border `D8D0EE`, white `FFFFFF`
- **Secondary text color:** steel blue `4A6080`
- **Font:** **Aptos, everywhere, with zero exceptions** — see the dedicated Typography section below for the full list of elements this covers.
- **Type scale:** 44pt bold cover title · 24pt bold slide titles · 16pt bold card titles · 14pt regular body/subtitle · 13–14pt bold pill/tag text · ~10.5pt footer (13pt is the practical floor for real content text — see Accessibility)
- **Shapes:** square-cornered rectangles with a uniform **0.5pt `D8D0EE` hairline border on every card, regardless of fill color** (neutral or purple-emphasis cards use the identical border — fill changes, border never does); perfect circles (never soft-rounded squares) for icon badges; pill/stadium shapes only for short standalone tags
- **Style:** flat design — zero gradients, zero *outer* shadows, zero bevels, zero WordArt, zero SmartArt-style decoration, zero accent stripes or underlines under titles
- **Depth:** every lavender `F5F3FB` container carries an `innerShdw` — 11pt blur, `3F248C`, **6% alpha**. Purple-filled shapes never do.
- **Dividers:** card title/body rules are 0.5pt `3F248C` at **24% alpha** — never solid
- **Italic:** subtitles, cover byline, cover pill, purple strips, and the contact line are italic; titles, card titles, card body, tables, and footers are roman (see Typography)
- **Name:** the company is **`Geodata`** — never `GeoDataTek`/`GeoData`; the domain stays `geodatatek.com`
Full palette, exact measurements, typographic scale, shape geometry, header/footer field behavior, table styling, and slide-pattern library: **read `references/gdt-brand.md` before designing slides** — treat every number in it as the standard, not a suggestion.
 
## Explicit design rules (apply literally, don't reinterpret)
 
- Maintain a **0.6in** left/right outer margin on every slide.
- Never start slide content above **y = 2.0in** — that space belongs to the title/subtitle header block.
- Use **0.2in** gutters between cards in a 2-column grid, **0.15in** in a 3+ column grid.
- Give every content card a **0.5pt hairline border in `D8D0EE`** — this color never changes, even on a purple-filled emphasis card — never a thicker border, never no border, never a shadow instead of a border.
- Give every card **square 90° corners** — corner radius is only for icon badges and pill tags, never for a content card, table, or panel.
- Make every icon badge a **perfect circle** (equal width/height, `adj=50000` roundRect or a true circle/ellipse) filled solid `3F248C` with a single-color white glyph centered inside, sized to roughly half the badge diameter.
- Use **sentence case** for all titles and card headers ("Why continuous threat exposure assessment?" not "Why Continuous Threat Exposure Assessment?") unless the reference deck's proper nouns require capitalization.
- Keep card body copy to **1–2 short lines** — if it runs longer, shorten the copy or split into two cards; never shrink the font to force a fit.
- Never use a decorative color bar, edge stripe, or underline beneath a title — use whitespace or a filled background panel instead.
- Apply the **purple full-width strip** pattern (solid `3F248C` fill, white bold centered text) only for a single closing takeaway line per slide — not as a recurring section divider.
- Reuse the **same header/footer scaffolding on every slide**: logos from the master (never re-pasted per slide), title at y=0.765in, subtitle at y≈1.28in, footer divider line at y=7.06in.
- For the footer, always include: dynamic slide-number field, dynamic date field, and the static text **"Geodata - Confidential"** in the footer placeholder — see `references/gdt-brand.md` for which of these are true PowerPoint fields versus manually-typed text.
- Give every lavender `F5F3FB` container an **`innerShdw`: 11pt blur, `3F248C`, 6% alpha** — cards, chips, and lavender pills alike. Never put it on a purple-filled shape, a badge, a strip, or a table.
- Set every card divider rule to **0.5pt `3F248C` at 24% alpha** — never solid, and never a different alpha on different slides. Inconsistent divider opacity across slides is a real and easily-missed defect.
- Italicize **subtitles, the cover byline, the cover pill tag, purple strips, and the contact line** — and nothing else. See Typography above.
- Spell the company **`Geodata`** everywhere, including the footer (`Geodata - Confidential`) and `docProps`. Leave the `geodatatek.com` domain lowercase and intact — any find/replace must be case-sensitive.
- Never introduce a brand color, gradient, outer shadow, or bevel that isn't in the palette table in `references/gdt-brand.md` without asking first.
## Reference deck
 
`assets/gdt_reference_deck.pptx` is the actual GDT sample this skill was built from. When starting a new GDT deck:
 
1. Thumbnail it for a quick visual refresher: `python /mnt/skills/public/pptx/scripts/thumbnail.py assets/gdt_reference_deck.pptx gdt_ref_thumbs`
2. Cross-check any color, font, size, or spacing value you're about to use against `references/gdt-brand.md` rather than recalling it from memory — the measurements there are exact, not approximate.
3. If the new deck should literally reuse layouts/icons from this file (not just the design system), edit it directly following the `pptx` skill's "Editing existing decks and templates" workflow instead of writing pptxgenjs from scratch.
## Slide-pattern library
 
Pick from these patterns (detailed in `references/gdt-brand.md`) rather than defaulting to plain title+bullets:
 
1. **Cover slide** — follow this exact vertical hierarchy, top to bottom, matching the reference deck's structure:
   - Logo (from the master, top corners — never re-placed inside the body of the cover)
   - Title (44pt bold, lavender title block)
   - Subtitle (14pt, directly beneath the title)
   - Business pillars / supporting statement (the centered byline, e.g. "delivered by X in partnership with Y", plus the pill tag)
   - Bottom highlight strip (full-width purple strip listing 2–3 service pillars separated by `|`)
   - Footer (date, confidentiality text, slide number — same scaffolding as every other slide)
2. **Comparison slide** — two square cards side by side (neutral vs. purple-emphasis), each with a title, divider rule, and 5-item bullet list. Same 0.5pt `D8D0EE` border on both cards regardless of fill.
3. **Feature/benefit grid** — 2×3 or 3×2 grid of square cards with circular icon badges, bold titles, 1–2 line descriptions.
4. **Process flow** — 5-step horizontal chevron-connected flow with icon badges and faded ghost numerals (not a hub-and-spoke diagram). Every step must use: **equal card widths** (don't replicate the reference deck's one 2.252in outlier). For a **5-step** flow that width is **2.349in**, which is simply what fills the content zone at five steps. For any other step count, hold the invariants — 0.6in margins, equal widths, equal gaps — and divide the 12.133in content width accordingly, rather than reusing 2.349in literally and leaving the row under-filled. A 4-step flow works out to 2.808in cards with 0.30in gaps., **equal icon-badge sizes**, **equal chevron-connector sizes**, **consistent vertical alignment** across all steps, and **sequential, consistently-styled numbering** (e.g. 01–05, same size/color/alpha throughout).
5. **Pricing/comparison table** — purple header row, manually-banded body rows, content-driven (not equal) column widths.
6. **Closing/contact slide** — 3-card feature grid + purple takeaway strip + centered contact line.
Not every deck needs all six — choose the subset that fits the content, but keep the same visual grammar throughout: flat cards, purple/lavender/steel-blue palette, Aptos everywhere, no gradients/shadows/stripes.
 
## Design Don'ts
 
- Never use gradients — zero gradient fills exist anywhere in the reference deck.
- Never use drop shadows — `outerShdw` count is 0 across all 7 reference slides. **But this does not extend to inner shadows:** the deck contains 56 `innerShdw` elements, and every lavender `F5F3FB` container is *required* to carry one (11pt blur, `3F248C`, 6% alpha). Omitting it makes cards look flat and unfinished against a real GDT deck. Purple-filled shapes never take it.
- Never use bevel effects.
- Never use WordArt.
- Never use decorative ribbons, banners, or edge stripes.
- Never apply SmartArt's built-in decorative styling (3D, gradient, shadowed SmartArt looks) — if content must go through SmartArt, restyle it flat to match this system afterward.
- Never use more than one accent color per deck — purple (`3F248C`) is the single accent; everything else is white, lavender, or steel-blue text.
- Never stretch or distort an icon's aspect ratio to fill a badge — resize proportionally.
- Never distort, skew, or non-uniformly scale the GDT or partner logo.
- Never overcrowd a slide — if content doesn't fit within the established margins/grid/type scale, cut content or split across two slides; don't shrink margins or gutters to force a fit.
- Never justify text — the reference deck uses only left- and center-alignment, never justified paragraphs.
- Never shrink body/content text below **13pt** (the smallest real content size measured in the deck) to force a fit.
- Never invent a new layout, shape treatment, or color that isn't documented in `references/gdt-brand.md` — if a request needs something this spec doesn't cover, say so and ask, rather than improvising something that merely looks plausible.
## Image usage
 
*(The reference deck contains no photographic imagery — only small icon glyphs and the two header logos. The rules below are a reasonable extrapolation from the deck's overall flat, uncluttered style, not a directly measured precedent. Flagging this so it isn't mistaken for a verified rule.)*
 
- If a photo or illustration is ever needed, prefer a clean cut-out (transparent or white background) over a busy rectangular photo — this matches the deck's icon treatment (isolated glyph, no background clutter).
- Avoid generic, colorful stock photography — it clashes with the deck's restrained single-accent-color palette.
- Images should support a specific point being made, not decorate the slide or dominate its layout.
- Maintain generous white space around any image — don't let it touch card borders or the slide's outer margin.
- Keep image treatment consistent across a deck — don't mix cut-out icons on one slide with full-bleed photos on another.
## Logo usage rules
 
- **Use the vector `.svg` logo, never a rasterized PNG.** Both logos live in the reference deck as SVG (`ppt/media/image1.svg` = Geodata, `image2.svg` = WATI) — copy those parts directly. Rasterizing softens the mark at projection size and is the most visible avoidable quality loss in an otherwise correct deck.
- Never recolor the Geodata or partner (e.g. WATI) logo — use it exactly as provided.
- **Only place a partner logo that actually applies to the engagement.** WATI is the reference deck's partner, not a permanent fixture. For a deck with a different partner or none, leave the top-left slot empty rather than carrying WATI over, and don't recreate a third party's mark from memory — ask for the approved asset.
- Maintain consistent placement: GDT logo top-right, partner logo top-left, at the master-level positions in `references/gdt-brand.md` — don't move logos slide-to-slide.
- Preserve the logo's native aspect ratio at all times; never stretch or squash it.
- Maintain clear space around the logo — don't let card content, titles, or other elements crowd into the logo's header zone.
- Never place a logo inside a content card, table, or process-flow step — logos belong in the header only.
## Chart styling guidelines
 
*(No native charts exist anywhere in the reference deck, so none of this is directly measured — it's inferred from the deck's overall flat, single-accent-color design language. Treat it as a reasonable default, and flag to the user that it's untested against an actual GDT chart if the distinction matters for their use case.)*
 
- Flat design only — no 3D chart types, no gradients, no shadows on chart elements.
- Primary data series in purple `3F248C`; secondary series in lavender tint `F5F3FB` or the lavender-accent `D8D0EE`, keeping to the same restrained, single-accent-plus-neutrals palette used everywhere else in the deck.
- Minimal gridlines — light, low-contrast, or omitted entirely rather than heavy default gridlines.
- Chart titles, axis labels, data labels, and legends all set in Aptos (per the Typography section above).
- Aim for the same clean, executive appearance as the rest of the deck — no default PowerPoint chart styling (drop shadows, gradient fills, bright multi-color palettes).
## Accessibility guidelines
 
- **Minimum body/content font size: 13pt** — the smallest actual content text measured in the reference deck. Footer/meta text (date, page number, confidentiality line) can go as small as ~10.5pt, but that's reserved for non-critical metadata, never for content someone needs to read from across a room.
- Maintain high contrast: dark text (purple `3F248C` or steel blue `4A6080`) on light backgrounds (white or lavender tint `F5F3FB`), or white text on the solid purple `3F248C` fill — never light-on-light or dark-on-dark combinations.
- Never place text directly over a busy or high-contrast-variation image — if imagery is used, keep text off of it or on a solid card background instead.
- Maintain the measured spacing standards (0.6in margins, 0.2in/0.15in gutters, y=2.0in content start) rather than compressing them — cramped spacing hurts readability at a distance as much as small text does.
- Check every slide at normal projection/screen-share scale, not just at 100% zoom on a laptop, before calling a deck finished — this is a presentation system, and slides need to hold up when projected or shared on a call.
## Building a new deck from scratch (pptxgenjs)
 
1. Read the `pptx` skill's pptxgenjs gotchas section first (hex color format, shadow rules, chart quirks, etc.).
2. Set `pres.layout = "LAYOUT_WIDE"`.
3. Pick slide types from the pattern library above that fit the content.
4. Apply the Quick Reference and Explicit Design Rules above; consult `references/gdt-brand.md` for exact positions before placing any shape.
5. Add the standard footer: dynamic slide number + dynamic date + static `"Geodata - Confidential"` (house spelling — the reference deck's `GeoData` casing is superseded).
6. QA per the `pptx` skill (content QA, `validate.py`, visual QA via rendered images) — plus the GDT-specific checks below.
### pptxgenjs gotchas specific to this design system
 
These cost real time on a prior build; none are in the `pptx` skill's generic list:
 
- **`pres.defineSlideMaster` writes the slide-number field's `rPr` with no typeface**, relying on the shape's `lstStyle` to supply Aptos. The brand rule is to never trust inheritance on field runs — post-process the generated layout XML and pin `<a:latin/ea/cs typeface="Aptos"/>` directly on the `<a:fld type="slidenum">` run.
- **pptxgenjs cannot emit a date field.** Write a sentinel string (e.g. `__DATEFLD__`) into the master's footer text, then post-process it into `<a:fld type="datetime1">` carrying the same `rPr`. Without this the date is static text that never updates.
- **Never back a table with a bordered rectangle to fake its outer hairline.** PowerPoint recalculates table row heights on open, so the table grows and desyncs from the rect; the rect then either pokes out or hides entirely under the opaque cell fills. Instead place the rect **after** the table in `<p:spTree>` with `<a:noFill/>` and the `D8D0EE` 0.5pt stroke, sized to the table's real bounds — it then draws the frame over the table edges.
- **Text-run transparency:** `transparency: 20` on `addText` correctly emits `<a:alpha val="80000"/>`, which is what the process-flow ghost numerals need.
- **Aptos has no metric-compatible substitute in LibreOffice**, so the QA render mis-measures text width. Leave ~10% slack in every text container and don't trust the preview's apparent fit — this directly contradicts the base `pptx` skill's "never default to Aptos" advice, which is overridden here by the brand rule.
### GDT-specific QA checks
 
Run these before delivering — each corresponds to a defect that has actually shipped:
 
```bash
# Aptos only (buFont Arial in latent master scaffolding is fine — it never renders)
grep -oh 'typeface="[^"]*"' unpacked/ppt/slides/*.xml | sort | uniq -c
# palette only: 3F248C 4A6080 D8D0EE F5F3FB FFFFFF 0D0D0D
grep -oh 'srgbClr val="[0-9A-F]\{6\}"' unpacked/ppt/slides/*.xml | sort | uniq -c
# corner radii: expect ONLY val 50000 (circles/pills) or val 0 (chips) — never an intermediate radius
grep -oh 'fmla="val [0-9]*"' unpacked/ppt/slides/*.xml | sort | uniq -c
# effects: outerShdw must be 0; innerShdw must equal the lavender-container count
grep -oh 'outerShdw\|innerShdw\|gradFill' unpacked/ppt/slides/*.xml | sort | uniq -c
# divider opacity: every rule must read 24000
grep -oh '<a:alpha val="[0-9]*"/>' unpacked/ppt/slides/*.xml | sort | uniq -c
# name: must return nothing
grep -rn 'GeoDataTek\|GeoData[^t]' unpacked/ppt unpacked/docProps
```
 
**Do not diff two decks on geometry and colour alone.** A prior review compared position, size, fill, stroke, font, size, bold, and colour — and missed three real changes because it never read the **alpha channel**, the **`<a:effectLst>`**, or the **italic flag**. Any comparison must cover all three.