# Chaos to Categories (Integumentary)

Single-file static web app (`index.html`) deployed on Vercel from GitHub (MrRankdizzle/integumentary-system-chaos-to-categories). No build step, no dependencies besides Google Fonts.

- Board data: the `BOARDS` array in the script. Each board has an `accent` color and 4 `groups` ({ name, terms }). Group order = the 2x2 layout order in Guided Sort (top-left, top-right, bottom-left, bottom-right), matching the original slides.
- Modes: `sort` (Guided Sort) and `chaos` (Chaos Mode, 4 mistakes allowed).
- Progress: localStorage key `c2c-integumentary-v1`.
- Design: Mustang colors (Carolina blue, sky blue, navy, white); light and dark themes via CSS tokens on `:root`.
- Student-facing rules: no emoji in the UI (use SVG icons); button labels must make sense without reading instructions; keep it interactive.
- Settings menu (three-line button in the top corner of every screen, `setBtn()`, `data-settings`, `openSettings`): text size, light/dark, high contrast, Animations (Full/Calm), read aloud + speed, dyslexia-friendly text (Lexend), reading ruler, color-blind friendly, plus Erase my stars and Reset all settings. Saved under its own localStorage key `c2c-integumentary-settings`, so erasing stars never resets a student's accommodations. A small script in `<head>` applies them before the page paints. Same pattern as Mustang Fold Rush.

## Accessibility rules (please follow)

- Motion: never read the device's `prefers-reduced-motion` (many school computers have it on). Calm motion comes only from Settings: `.rm` in CSS, `reducedMotion()` in JS.
- Color-blind friendly (`.cb` on `<html>`): anything that shows right/wrong or done by color also needs a non-color cue (check, X, outline). Use the `--good` and `--bad` tokens, not raw hex, so the blue/orange palette applies.
- Read aloud (`.tts`): `sayBtn(text, label)` makes a speaker button; pass the exact plain text to read. Tapping a term says it, and `toast()` speaks its message.
- Size new text in rem so the Text size setting scales it. Check phone width (390px) with Extra large + Dyslexia-friendly on.
- Any new top bar gets `${setBtn()}` so Settings is always reachable.
