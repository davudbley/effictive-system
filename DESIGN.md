---
name: Autopilot
description: Industrial control-room (Leitstand/HMI) design system for the Autopilot single-file landing page — graphite panels, hairline seams, status lamps, signal green.
colors:
  ground: "#0c0f12"
  panel: "#12161a"
  panel-2: "#161b20"
  panel-3: "#1b2127"
  seam: "#242c33"
  seam-soft: "#1d242a"
  ink: "#e9eeee"
  ink-dim: "#a3b4af"
  ink-faint: "#7a8d84"
  green: "#38e08b"
  green-deep: "#0a2a1a"
  green-ink: "#07130c"
  amber: "#f5b02e"
  amber-deep: "#2a2008"
  line: "#3d4850"
typography:
  display:
    fontFamily: "'Saira Condensed', system-ui, sans-serif"
    fontSize: "clamp(3rem, 8.5vw, 5.9rem)"
    fontWeight: 700
    lineHeight: 1.02
    letterSpacing: "-0.01em"
  headline:
    fontFamily: "'Saira Condensed', system-ui, sans-serif"
    fontSize: "clamp(2rem, 5vw, 3.1rem)"
    fontWeight: 600
    lineHeight: 1.02
    letterSpacing: "-0.01em"
  title:
    fontFamily: "'Saira Condensed', system-ui, sans-serif"
    fontSize: "1.5rem"
    fontWeight: 600
    lineHeight: 1.02
  body:
    fontFamily: "'Saira', system-ui, sans-serif"
    fontSize: "1.04rem"
    fontWeight: 400
    lineHeight: 1.65
  label:
    fontFamily: "'Martian Mono', monospace"
    fontSize: "0.68rem"
    fontWeight: 400
    letterSpacing: "0.09em"
rounded:
  r-panel: "6px"
  r-chip: "3px"
spacing:
  pad: "clamp(1.1rem, 3vw, 2rem)"
components:
  button-primary:
    backgroundColor: "{colors.green}"
    textColor: "{colors.green-ink}"
    rounded: "{rounded.r-chip}"
    padding: "0.85rem 1.5rem"
  button-primary-hover:
    backgroundColor: "#4ceb9a"
  button-ghost:
    textColor: "{colors.ink}"
    rounded: "{rounded.r-chip}"
    padding: "0.85rem 1.5rem"
  chip-auto:
    backgroundColor: "{colors.green-deep}"
    textColor: "{colors.green}"
    rounded: "{rounded.r-chip}"
    padding: "0.34rem 0.6rem"
  chip-hand:
    backgroundColor: "{colors.amber-deep}"
    textColor: "{colors.amber}"
    rounded: "{rounded.r-chip}"
    padding: "0.34rem 0.6rem"
  chip-keep:
    backgroundColor: "{colors.panel-3}"
    textColor: "{colors.ink-dim}"
    rounded: "{rounded.r-chip}"
    padding: "0.34rem 0.6rem"
  panel:
    backgroundColor: "{colors.panel}"
    rounded: "{rounded.r-panel}"
  panel-head:
    backgroundColor: "{colors.panel-2}"
    textColor: "{colors.ink-dim}"
    padding: "0.7rem 1.1rem"
  terminal:
    backgroundColor: "{colors.green-ink}"
    textColor: "{colors.green}"
    rounded: "{rounded.r-panel}"
    padding: "1.3rem 1.4rem"
  terminal-hover:
    backgroundColor: "#0c1d12"
---

# Design System: Autopilot

## Overview

**Creative North Star: "Der Leitstand" (The Control Room)**

The page is the control room of the visitor's own office: paperwork rendered as a running, supervised industrial process. Every surface borrows the grammar of a plant HMI — graphite panels joined by hairline seams, monospaced readouts in panel headers and footers, status lamps that glow green when a process runs and amber when it is on manual, a physical HAND/AUTO mode switch. Signal green is not decoration; it is the committed state of the machine ("in Betrieb") and the primary action. The world explicitly refuses the dark AI-agency aesthetic: no neon glow, no particle networks, no gradient haze.

Density is calm and engineered. One dark ground carries flat panels; structure is drawn with 1px borders, never cast with shadows. Type is industrial signage: condensed uppercase display caps for anything that names a thing, a workmanlike sans for prose, and a small caps-tracked mono strictly for operational readouts (tags like `Mod-01`, `P-101`, clock, panel labels). Motion is process motion — a pulse travelling through pipes, lamps switching on in sequence — always with a settled end state and full `prefers-reduced-motion` fallbacks.

**Key Characteristics:**
- Graphite panel ladder (`ground` → `panel` → `panel-2` → `panel-3`) with 1px hairline seams; zero elevation shadows.
- Two signal hues only: green = running/committed/primary action, amber = manual operation. No third accent.
- Three-font industrial stack: Saira Condensed versal display, Saira body, Martian Mono readouts — all embedded, no external requests.
- 6px panel radius, 3px chip radius; stroke-based line icons at 1.5px.
- One deliberate inversion: the contact section is fully drenched in signal green — the "GO" panel.

## Colors

A near-monochrome graphite field with exactly two signal hues, used the way an HMI uses lamp colors: state, not style.

### Primary
- **Signal Green** (`green`, #38e08b): the running state and the one call to action. Lamps in the on state, active process stations, the AUTO side of the mode switch, `chip-auto`, "ok" values in the datasheet, the primary button, focus outlines, text selection, and the brand mark's screen. Hover brightens to #4ceb9a (buttons only).
- **Green Deep** (`green-deep`, #0a2a1a): dark green well used as chip background behind green text (`chip-auto`).
- **Green Ink** (`green-ink`, #07130c): near-black green. Text color on green surfaces (primary button label, contact-section text) and the background of contact terminal tiles.

### Secondary
- **Amber** (`amber`, #f5b02e): manual operation only — warn lamps, the HAND side of the mode switch, `chip-hand`. Never a decorative highlight.
- **Amber Deep** (`amber-deep`, #2a2008): chip background behind amber text (`chip-hand`).

### Neutral
- **Ground** (`ground`, #0c0f12): the page background; also the sticky header at 88% opacity via `color-mix` with backdrop blur.
- **Panel** (`panel`, #12161a): default panel/card surface (board, datasheet, module list, phase cells).
- **Panel 2** (`panel-2`, #161b20): panel head/foot strips, switch housing, hover state of module rows, de-emphasized "keep" rows.
- **Panel 3** (`panel-3`, #1b2127): innermost inlays — process nodes, `chip-keep`, the darkest step of the inset ladder.
- **Seam** (`seam`, #242c33): primary 1px hairline — section dividers, panel outer borders, header bottom border.
- **Seam Soft** (`seam-soft`, #1d242a): quieter 1px hairline inside panels — row dividers, head/foot separators, and the 28px schematic grid lines of the board canvas.
- **Line** (`line`, #3d4850): stronger structural stroke — ghost button border, idle process nodes and pipes, switch border, scrollbar thumb, brand-mark frame.
- **Ink** (`ink`, #e9eeee): primary text.
- **Ink Dim** (`ink-dim`, #a3b4af): secondary text — body copy in sections, nav links, panel-head labels.
- **Ink Faint** (`ink-faint`, #7a8d84): tertiary text — mono tags, captions, idle node icons, off lamps, footer.

### Named Rules
**The Signal Discipline Rule.** Green means "läuft" (running/committed) or the primary action; amber means "Hand" (manual). Neither hue is ever used as ornament, background wash, or a third-priority highlight — if an element is not a state or the CTA, it stays graphite and ink.

**The One Drench Rule.** Signal green floods exactly one surface on the page: the contact section (`.contact`), where the palette inverts (green ground, `green-ink` text, `green-ink` terminal tiles). Everywhere else green stays a signal on graphite. Do not add a second drenched section.

## Typography

**Display Font:** Saira Condensed (embedded woff2, weights 600 + 700; fallback system-ui, sans-serif)
**Body Font:** Saira (embedded woff2, weights 400 + 500 + 600; fallback system-ui, sans-serif)
**Label/Mono Font:** Martian Mono (embedded woff2, weights 400 + 500; fallback monospace)

**Character:** Industrial signage over engineering log. The condensed uppercase display speaks like stencilled equipment labels; the mono is the plant's telemetry. Saira keeps prose humane between the two. All fonts are embedded as base64 `@font-face` — the page makes no external font requests.

### Hierarchy
- **Display** (700, clamp(3rem, 8.5vw, 5.9rem), 1.02): hero H1 only, uppercase, letter-spacing -0.01em, max-width 14ch. The single green word inside it (`.hl`) is the only colored text in a heading.
- **Headline** (600, clamp(2rem, 5vw, 3.1rem), 1.02): section H2s, uppercase, seated on the `sec-head` baseline row with a mono tag on the right.
- **Title** (600, 1.5rem): H3 in phase cells; module names use the same voice at 1.12rem with 0.04em tracking; station names at 1.02rem with 0.05em tracking. All uppercase Saira Condensed.
- **Body** (400, 1.04rem, 1.65): paragraph prose, capped at 62ch (`p{max-width:62ch}`); leads at 1.12–1.15rem capped at 56ch; secondary copy in `ink-dim`. Emphasis via weight 500–600 and `ink`, not italics.
- **Label** (Martian Mono 400, 0.68rem, 0.09em, uppercase): the `.mono` readout voice — panel heads/foots, section tags, module tags, phase tags, the clock. `.mono-strong` bumps to weight 500. Chips drop to 0.62rem at 0.08em.

### Named Rules
**The Versal Display Rule.** Every heading is Saira Condensed, uppercase, tight-leaded (1.02). There are no sentence-case, serif, or non-condensed headings anywhere in the world.

**The Readout Rule.** Martian Mono appears only as small operational readouts: 0.62–0.72rem, uppercase, wide-tracked, usually in `ink-faint`/`ink-dim`. It is never used for headlines, body prose, or at large sizes.

## Layout

One centered column: `.wrap` at max-width 1180px with `padding-inline: clamp(1.1rem, 3vw, 2rem)` (`--pad`). The page is a vertical stack of full-width sections chained by 1px `seam` bottom borders — the seams, not whitespace alone, articulate the page. Section rhythm: `padding-block: clamp(3.2rem, 7vw, 5.5rem)`; the hero runs slightly tighter.

Recurring section furniture: every section opens with a `sec-head` row — uppercase H2 left, mono tag right (e.g. "Betriebsart", "E/A-Liste"), baseline-aligned, closed by a 1px seam underneath with 1.1rem below and clamp(1.8rem, 4vw, 2.8rem) after.

Grids are asymmetric two-column on desktop and collapse to one column: `ha-grid` 5fr/7fr (≤900px), `ref-grid` 6fr/6fr (≤900px), `phases` 3×1fr fused by 1px seam gaps — `gap:1px` over a `seam` background (≤820px), module rows a 110px/4fr/6fr/auto grid (≤820px). The process board's horizontal flow becomes a vertical flow at ≤760px (pipes rotate from 2px-high to 2px-wide). Header condenses at ≤840px (nav collapses to "Kontakt", clock hides) and ≤560px. Observed breakpoints: 900, 840, 820, 760, 600, 560px.

The sticky header is a 60px status bar: brand left, nav center-right, and a live readout (blinking green lamp, "Anlage in Betrieb", ticking clock) right — the page's frame is itself an instrument.

### Named Rules
**The Grid-in-the-Canvas Rule.** The 28px schematic grid (`background-size: 28px 28px`, `seam-soft` lines) exists only inside the process-board canvas (`.board-body`). The page ground and all other panels stay plain — the grid marks the one drawing surface, not a global texture.

## Elevation & Depth

No shadow elevation anywhere. Depth is drawn, not cast: surfaces sit flat on `ground` and step up through the panel ladder (`panel` → `panel-2` for heads/hovers → `panel-3` for inlays), always separated by 1px hairlines (`seam` outside, `seam-soft` inside, `line` for strong strokes). The sticky header gains presence through translucency (`color-mix(in srgb, var(--ground) 88%, transparent)` + `backdrop-filter: blur(10px)`), not a drop shadow. Hover feedback is a background-tone step or a 1–2px `translateY` lift with no shadow.

### Shadow Vocabulary
- **Lamp glow, green** (`box-shadow: 0 0 8px 1px rgba(56,224,139,.55)`): the emission of an on-state status lamp (`.lamp.on`, active stations).
- **Lamp glow, amber** (`box-shadow: 0 0 8px 1px rgba(245,176,46,.5)`): the emission of a warn-state lamp (`.lamp.warn`).

These are light sources, not elevation; they never appear on panels, buttons, or text.

### Named Rules
**The Seam Rule.** Structure is expressed exclusively through 1px borders and panel tone steps. If a surface needs separation, add a hairline or step the panel tone — never a box-shadow.

## Shapes

Machined, near-rectangular geometry. Panels and everything panel-like (board, datasheet, module list, switch housing, nodes, terminals, about-badge) use a 6px radius (`--r-panel`); chips and buttons use a 3px radius (`--r-chip`); nested elements subtract the inset (switch inner buttons: `calc(var(--r-panel) - 3px)` inside a 4px-padded housing). Status lamps are the only circles: 9px dots. Process pipes are 2px bars with 1px radius. Focus outlines carry a 2px radius.

Borders are the form language: every panel is `1px solid seam` with internal `1px solid seam-soft` dividers; the ghost button and idle nodes use the heavier `line` stroke. Iconography is stroke-only inline SVG at 1.5px stroke (24px viewBox drawn at 26px in nodes, 15–16px in buttons/labels), matching the hairline world; the only filled shape is the green screen rectangle of the brand mark.

## Components

### Buttons
- **Shape:** 3px radius (`--r-chip`), inline-flex with a 0.6rem gap to a 16px stroke icon; Saira 600 at 1rem; padding 0.85rem 1.5rem.
- **Primary:** signal green surface with near-black green text (`green` / `green-ink`) — the single loudest element outside the contact drench.
- **Hover / Focus:** background brightens to #4ceb9a plus `translateY(-1px)`; transitions 0.18s with lift easing `cubic-bezier(.22,1,.36,1)`. Focus: global 2px `green` outline at 3px offset.
- **Ghost:** transparent with `1px solid line` border and `ink` text; hover raises border to `ink-dim` and lifts 1px.

### Chips
- **Style:** Martian Mono 500 at 0.62rem, uppercase, 0.08em tracking, padding 0.34rem 0.6rem, 3px radius; colored well + matching signal text.
- **State:** `chip-auto` (green on `green-deep`) = automated; `chip-hand` (amber on `amber-deep`) = manual; `chip-keep` (dim ink on `panel-3`) = stays human. Chip swaps animate background/color at 0.25s.

### Status Lamp (signature primitive)
9px circle. Off: `ink-faint`. On: `green` with green glow. Warn: `amber` with amber glow. `.blink` pulses opacity 1→0.35 over 1.6s ease-in-out infinite (header "Anlage in Betrieb"). Lamps accompany stations, task rows, and panel heads as state indicators.

### Cards / Containers (panels)
- **Corner Style:** 6px radius, `overflow:hidden` so head/foot strips sit flush.
- **Background:** `panel` body; `panel-2` head/foot strips with mono readout labels left/right, separated by `seam-soft`.
- **Shadow Strategy:** none — see The Seam Rule.
- **Border:** `1px solid seam` outer; `1px solid seam-soft` row dividers.
- **Internal Padding:** heads/foots 0.7rem 1.1rem; rows ~0.95–1.05rem 1.1–1.2rem; the board canvas clamps up to 2.2rem.

### Record / Datasheet (signature)
The "Anlagen-Datenblatt": a panel rendered entirely in Martian Mono 0.72rem / 0.05em tracking; `dt` uppercase `ink-faint`, `dd` `ink-dim`, rows divided by `seam-soft`, status value in `.ok` green. Used to present the one real reference workflow as plant paperwork.

### HAND/AUTO Switch (signature)
A `panel-2` housing (`1px solid line`, 6px radius, 4px padding, 4px gap) holding two uppercase Saira Condensed buttons. Active side gets its signal surface: HAND = `amber`/`amber-deep` text, AUTO = `green`/`green-ink` text; inactive sides stay `ink-faint` on transparent. Toggling restates lamps and chips across the task panel with a 70ms stagger (0ms under reduced motion). Focus outline inset (-2px).

### Process Board (signature)
The hero instrument (`.board`): panel with mono head ("Prozess P-101 · Ausgangsrechnung" + lamp) and foot, canvas with the 28px schematic grid, five stations (64px `panel-3` nodes, `line` borders, stroke icons) joined by 2px pipes. The pulse: pipes fill with a green gradient sweep over `--board-step` (1100ms linear) while stations flip `is-on` (green border, green icon, 9% green-tinted node, lamp on). Cycle starts at 35% visibility via IntersectionObserver, loops after a 3.4s hold; under `prefers-reduced-motion` the board renders fully-on and static. Vertical variant under 760px.

### Contact Terminals (signature)
Inside the green-drenched contact section: tiles of `green-ink` at 6px radius, padding 1.3rem 1.4rem; mono label row in light green #8ff0bd with a 15px stroke icon; value in Saira Condensed 600 (clamp(1.15rem, 2vw, 1.45rem), no uppercase) in near-white green #eafff3. Hover: `translateY(-2px)` and background deepens to #0c1d12. Selection and focus invert to `green-ink`.

### Navigation
Sticky 60px status bar (see Layout). Links: Saira 500 at 0.92rem, `ink-dim`, no underline, hover to `ink` at 0.18s. Right-side readout: blinking green lamp + mono "Anlage in Betrieb" + live JS clock. Mobile: only the "Kontakt" link survives; the clock, then the readout label, drop away.

## Do's and Don'ts

### Do:
- **Do** build every container as a panel: `panel` surface, `1px solid seam` border, 6px radius, and — when it has a title — a `panel-2` head strip with mono readout labels (The Seam Rule).
- **Do** reserve green strictly for running/committed states and the primary action, and amber strictly for manual operation (The Signal Discipline Rule).
- **Do** set all headings in uppercase Saira Condensed (600–700, line-height 1.02) and all operational labels in Martian Mono 0.62–0.72rem uppercase with 0.08–0.09em tracking.
- **Do** give every animation a settled end state and a `prefers-reduced-motion` path (board renders fully-on; staggers collapse to 0ms).
- **Do** draw icons as stroke-only inline SVG at 1.5px stroke width — no icon fonts, no filled glyphs, no external assets.
- **Do** keep hover feedback to tone steps and 1–2px lifts on `cubic-bezier(.22,1,.36,1)` at ~0.18s.

### Don't:
- **Don't** use box-shadows for elevation, neon glow effects, particle networks, or gradient washes — the world's thesis explicitly refuses the dark AI-agency look. The only glow is the 8px lamp emission.
- **Don't** let the 28px schematic grid escape the process-board canvas onto the page ground or other panels (The Grid-in-the-Canvas Rule).
- **Don't** introduce a third signal hue or use green/amber decoratively; graphite and ink carry everything that is not a state or the CTA.
- **Don't** create a second green-drenched section — the contact "GO" panel is the single palette inversion (The One Drench Rule).
- **Don't** load external fonts, scripts, images, or trackers; the page is one self-contained file with embedded woff2 fonts and inline SVG.
- **Don't** exceed the radius vocabulary: 6px panels, 3px chips/buttons, circles only for 9px status lamps.
