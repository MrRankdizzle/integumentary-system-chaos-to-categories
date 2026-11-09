# Chaos to Categories (Integumentary)

Single-file static web app (`index.html`) deployed on Vercel from GitHub (MrRankdizzle/integumentary-system-chaos-to-categories). No build step, no dependencies besides Google Fonts.

- Board data: the `BOARDS` array in the script. Each board has an `accent` color and 4 `groups` ({ name, terms }). Group order = the 2x2 layout order in Guided Sort (top-left, top-right, bottom-left, bottom-right), matching the original slides.
- Modes: `sort` (Guided Sort) and `chaos` (Chaos Mode, 4 mistakes allowed).
- Progress: localStorage key `c2c-integumentary-v1`.
- Design: Mustang colors (Carolina blue, sky blue, navy, white); light and dark themes via CSS tokens on `:root`.
- Student-facing rules: no emoji in the UI (use SVG icons); button labels must make sense without reading instructions; keep it interactive.
