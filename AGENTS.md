# AGENTS.md — Soul to Soul website (handoff package)

Instructions for coding agents (Codex, Claude Code, Cursor). Humans: start at `00-LEEME.md`.

## Where the spec lives
The spec is in `docs/handoff/` (Markdown copy of the handoff package). Prototypes, design-system components, photos, fonts and logos live in the full package on the company Google Drive (see `docs/handoff/LEEME-REPO.md`).
Read in this order:
1. `docs/handoff/00-LEEME.md`
2. `docs/handoff/02-design-system/readme.md`
3. `docs/handoff/02-design-system/design-decisions.md`
4. The `NOTAS-*.md` / `BRIEF-*.md` of the page you are building, in `docs/handoff/03-paginas/`

## Source of truth (when things disagree)
1. Decisions dated 2026-10-26 in `docs/handoff/03-paginas/NOTAS-*.md` and `docs/handoff/PENDIENTES.md`. These override the prototypes.
2. `docs/handoff/02-design-system/readme.md` + `design-decisions.md` + `docs/handoff/02-design-system/tokens/`.
3. The prototypes (`*.dc.html`, `sections.jsx`, `02-design-system/components/*.jsx` in the Drive package). They are reference implementations that run inside Claude Design; do not copy their runtime (`support.js`, `ds-base.js`, `image-slot.js`, `tweaks-panel.jsx`, `_ds_bundle.js`).
4. Anything in Notion older than the above (e.g. the May–June "Design System" page) is superseded.
Never resolve a conflict silently: if a page note marks something `[PENDIENTE]`, ask the team.

## Stack (decided)
- Next.js 15 (App Router), TypeScript, Tailwind CSS.
- next-intl with EN and ES at launch.
- Sanity as CMS; content is never hardcoded.
- Vercel hosting; GitHub repo in the company org.
- Resend for transactional email; Brevo for newsletter.
- PostHog + Vercel Analytics + Meta Pixel, all behind cookie consent.
- Tokens: port `docs/handoff/02-design-system/tokens/*.css` (CSS custom properties) as-is and map them in the Tailwind theme. `docs/handoff/02-design-system/tokens/tokens.json` has the same values in machine-readable form.

## Locked conventions
- Animation: import from `motion/react`, never `framer-motion`. GSAP/ScrollTrigger only where `motion` cannot do it.
- Use `min-h-[100dvh]`, never `h-screen`.
- "Raíz" is an internal codename. It never appears in public copy, URLs or metadata.
- Never use the word "pivot" in copy.
- Testimonials: max 3 lines, always with full attribution (name, location, source).
- Safety messaging comes first in trust content. The Colombia safety FAQ is always the first FAQ.
- Every animation respects `prefers-reduced-motion`.
- Elevation is flat: 1px warm hairline (`--border-card`), no box-shadows (sole exception: the Window shutters).
- Buttons: pill radius; primary/secondary colors are fixed per surface (see `02-design-system/components/actions/Button.jsx` in the Drive package and the readme "Button colors per surface").
- Weathered pastel colors are used ONLY by the Window (Windows of Colombia) component.
- Banned copy: all-inclusive, all sorted, escape the stress, unforgettable experience, magical places (and the Spanish equivalents). Use "journey" (not tour) and "host" (not guide).

## Performance
- Never ship original asset files to the browser. `docs/handoff/02-design-system/assets/illustrations/*.png` are 10–17 MB each. Generate WebP/AVIF responsive variants (≤1400px for illustrations) and use `next/image`.
- Self-host fonts as WOFF2 (`docs/handoff/01-marca/fuentes/`). Avenir LT Std only exists as `.otf`; convert it, but the web license is unconfirmed (see `docs/handoff/PENDIENTES.md`).
- Hero video: muted, looping autoplay with a poster image and a lighter mobile encode.
