---
name: soul-to-soul-design
description: Use this skill to generate well-branded interfaces and assets for Soul to Soul Travel (a Colombian boutique experiential-travel company — warm, grounded, unhurried), either for production or throwaway prototypes/mocks/etc. Contains essential design guidelines, colors, type, fonts, assets, and UI kit components for prototyping.
user-invocable: true
---

Read the `readme.md` file within this skill, and explore the other available files (`tokens/`, `components/`, `templates/`, `guidelines/`, `assets/`).

If creating visual artifacts (slides, mocks, throwaway prototypes, etc), copy assets out and create static HTML files for the user to view. If working on production code, you can copy assets and read the rules here to become an expert in designing with this brand.

Core rules to honor every time:
- **Palette:** Coffee `#503421` (text), Light `#F7F4F0` (long text), Coconut `#F0E8D5` (background), Terracotta `#A35940` (primary CTA — a warm moment, never constant noise), Palm `#D3C381` (secondary CTA). The weathered pastels are for the Windows of Colombia component ONLY.
- **Background rhythm:** Coconut ↔ Light alternation; Coffee for deep moments; Palm for the single decisive moment.
- **Type:** Milanesa Serif Light / Playfair Display (display, editorial only) + Avenir / Inter (body). Italic is semantic, not decorative. Headings are regular weight.
- **Adaptive button rule:** a filled button whose color matches the background inverts to Coconut + Coffee text.
- **Voice:** warm, honest, concrete, unhurried — a friend who lives in the place. Specificity over vagueness. Tagline: *Keep Seeking.*
- **Never:** stock photography, FOMO/countdowns, wellness clichés ("transformative"/"life-changing"), purple AI gradients, decorative emoji, generic fonts as primary.

## Layout & usage rules (Homepage-established)

- **Rhythm:** one section padding everywhere (`--section-pad-y` 104px); content aligns to `--content-max` 1280px + 56px gutter; 72px heading→content gap.
- **Readable contrast:** sentences meant to be read use `--coffee` / `--coffee-90` on light — never the faint `--coffee-70/55` (those are for labels/metadata only).
- **Text over photos:** `--light` at full opacity + a bottom scrim gradient (text-shadow alone isn't enough).
- **Icon / arrow buttons:** flip the glyph to `--light` on hover — never hover to a fill equal to the glyph colour.
- **Carousels:** show position with clickable dots (active = 22px pill, inactive = 7px @ 0.3) beside the ‹ › arrows, and size cards so the next one peeks. Dot colour follows the surface (Coffee on light, Palm on deep).
- **Alignment:** inside a left-aligned lockup every part shares one left edge — never re-center a child with `margin:auto`/`text-align` inside it; beside media, align column **tops** (`align-items:flex-start`), not centers.
- **Botanical illustrations have gravity:** a plant that reads as growing (banana, palm) **stands on a section edge as if it were the floor** (`bottom: 0`), never floating. Exception: a **seam botanical** (the monstera) straddling the boundary between two sections, half in each, to tie them together.
- **Eyebrows are Medium Terracotta** (12px / 600 / 0.18em, Terracotta; Palm on deep) — the `Eyebrow` component handles it.
- **Value-prop → symbol:** Balance → `piedras-zen`, Connection → `mano-espiral`, Firsthand → `vasija-flores` (retired "Craft").

## Creative direction — the layer that keeps this from looking like a template

**Start from the objective — design is thinking, not decoration.** Before any treatment, answer: *what am I communicating, and what is this piece / section / call-out for?* Three questions gate every choice: (1) the single message, stated before any layout; (2) how the viewer clicks with the idea *and* the brand in one gesture; (3) how this differs from everyone else (the final test below). Structure the message *before* the layout with the **Pyramid Principle** (Minto) — answer-first / BLUF (lead with the conclusion; the hero *is* the answer), MECE support (3–4 non-overlapping points, no gaps), SCQA for longer pieces (Situation·Complication·Question·Answer). This feeds the rules: the objective decides the *one bold bet* (rule 1), and MECE is what makes structure *real* (rule 3). Only once the objective is set do the two layers below apply.

The palette is *not* what makes this brand distinctive. Cream + serif + terracotta is the same ground every "boho" studio — and every AI default — stands on. That's fine; it *is* the brand. The distinctiveness is spent elsewhere: **structure, the signature element, and photography** — never the palette. Hold two layers apart:
- **System layer — repeat with discipline.** Palette, the adaptive button, header, grid, spacing, the Coconut↔Light rhythm. Never improvised, never "varied for variety." Consistency lives here.
- **Expression layer — vary on purpose.** How a headline is emphasized, which hero treatment, which graphic resource leads. This is where the boldness and the variation are spent.

Five rules for the **expression layer**:
1. **One bold bet per piece.** One memorable element; everything else simple and disciplined. Before you finish, take one ornament *away*. If everything shouts, nothing is heard.
2. **Vary the gesture — never repeat it.** Our own blessed device — one accent word in italic — is lovely once and a formula across twenty slides. It's one tool among several: scale, whitespace, a single handwritten word, a photo that carries the moment. Rotate them. Emphasis is a decision per piece, not a mold. Experiment; if it misses, fix it. It should read as made by someone with soul, not by a machine.
3. **Structure only when it encodes something real.** Numbers, eyebrows, rules, dividers earn their place only when they map a true sequence, hierarchy or order the reader needs. Numbering things that aren't a sequence is decoration — cut it. Same for fonts, colors, illustrations, textures, organic shapes: each enters when it both communicates *and* builds brand identity.
4. **Dose for balance.** Loaded up on illustrations? Let it breathe with space, color or texture. Used terracotta for force already? Let it rest before repeating. Used eyebrows? Rest them. Playing with elements is not saturating them.
5. **The voice doesn't soften into template either.** Banned commercial-tourism filler — EN: *all-inclusive · all sorted · escape the stress · unforgettable experience · magical places*; ES: *todo resuelto · todo incluido · escápate del estrés · experiencia inolvidable · lugares mágicos*. Short sentences. Leave room for the reader to complete the feeling. Every message carries a purpose, not just a sell.

**Named tells — the small AI reflexes to catch in review.** The five rules govern the big moves; these are the little decorative reflexes that slip in *even when the five rules pass*, because they aren't brand-specific — just what a model reaches for by default:
- **No scroll cues** (*"Scroll ↓" · "Scroll to explore"* · a bouncing chevron). Composition invites the scroll; a label announcing it is filler.
- **No decorative status dots** (the pulsing *"● Live" / "● Available"* dot) unless it reports real state.
- **No locale / time / weather strips** (*"Bogotá · 24°" · "Currently in Medellín, 6:14am"*) — tempting on a travel brand, still filler. A place earns its name in the copy, not a meta-strip.
- **No fake product UI** — a trip-planner app / booking dashboard / itinerary screen mocked from styled `<div>`s is a Tell. Lead with real photography or a real component.
- **No invented precision** (*"98% would return" · "4.1× more restful"*) unless real or labelled as example. Faked precision the brand doesn't claim is data-slop.
- **Copy self-audit before ship:** re-read every visible string (headings, eyebrows, buttons, captions, alt text, footer) and rewrite anything broken, with an unclear referent, or that reads like a model trying to sound thoughtful (forced metaphor, mock-poetic micro-copy). Unsure? Replace it with a plain functional sentence.
- Two caps that make rule 2 checkable: **max 2 image+text split sections in a row** (the third is the zig-zag reflex — break it), and **N items = N cells** (no empty middle/trailing tile to "balance" a grid).

**Run the final test before delivering anything:** *Could this only be Soul to Soul?* If the same piece could belong to any other travel brand, it isn't done — back to rules 1–4. **North star: less noise, more intention.** *(Pending: Raíz's signature element isn't defined yet; once it is, it becomes the default answer to rule 1 and the divider of rule 3. Until then the "bold bet" defaults to a strong photograph or a structural move.)*

If the user invokes this skill without any other guidance, ask them what they want to build or design, ask some questions, and act as an expert designer who outputs HTML artifacts _or_ production code, depending on the need.
