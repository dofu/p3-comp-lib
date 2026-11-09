# Instructions for coding agents

This folder is the P3 component library: `pds-*` web components, plain
JavaScript, no build step. When you build or change any screen in a
project that includes this library, these rules apply.

Non-negotiables, before anything else (README section "Non-negotiables"):

- One screen per `<pds-preview>`; a flow is several previews.
- Two surfaces: the screen is `--pds-surface-1`, a container on it is
  `--pds-surface-2`, and nothing on surface-2 has a fill of its own.
- A card never holds a card. Containers are placed by the screen, never
  inside each other; sub-items indent under their parent row.
- `chevron_right` ends a row that opens another screen; `chevron_down`
  and `chevron_up` a row that expands in place. Never both meanings on
  one icon.
- Money is `SGD 10,000.00`: code, one space, two decimals. Never `$`,
  never the code after, never bare. Prices carry no code and the
  market's tick decimals; quantities are whole.

1. Read `README.md`, sections "Non-negotiables" and "Rules for every
   screen", and follow them.
2. Build from this library only. Never write your own button, input, tab,
   chip, switch, list, dialog or navigation, never style a raw `<button>`
   or `<input>` to look like one, and never copy from another UI kit or
   from the current POEMS app. If a component is missing, say so and use
   the closest one.
3. `custom-elements.json` is the contract: use only the attributes it
   lists. Per-component guidance (when to use, do and don't) is in
   `src/<component>.md`. Colours come from `tokens/tokens.css` only; type,
   spacing and radius from `foundations/` (a `pds-type-*` class on every
   hand-built text, `--pds-space-*` for every gap, `--pds-radius-*` for
   every corner; nothing off those scales).
4. Add `pds-navigation-bar` only on root screens; the preview frame
   already carries the status bar and the home line.
5. Wrap every screen you render for review in `<pds-preview>` from
   `preview/pds-preview.js`, and end with only what the reviewer must decide
   (README rule 7): no build notes, no component list. The deliverable is
   the live page. If a picture is asked for anyway, render it with
   `corners="square"` and no toggles: rounded corners are for the live
   page only.
6. A screen you build is a high-fidelity concept to show an idea: not a
   URS, not settled requirements, not a build to hand to developers. Say
   so if asked.
7. Copy is short and complete, no fillers, and every string is given in
   English, modern Chinese (Simplified) and Japanese with the `data-zh`,
   `data-ja` and `data-<attr>-zh/ja` conventions in `preview/pds-preview.md`.
   Chinese and Japanese copy is your suggestion, the shortest wording
   possible, not taken from POEMS translation files; say so if asked.
8. Follow README section "Content rules from the design system": a
   financial value never truncates or rounds; a money action never reads
   OK, Yes or Submit; one choice from a few is a segmented button or radio,
   several at once are chips or checkboxes; nothing shrinks or truncates at
   larger text sizes. Each `src/<component>.md` ends with that component's
   own rules; read it before using the component.
