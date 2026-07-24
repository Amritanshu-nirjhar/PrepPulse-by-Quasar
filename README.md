# PrepPulse — by Quasar

**Mess intelligence that tells your kitchen exactly how much to cook.**

PrepPulse is a concept website for an AI-powered food management system aimed at hostel/college messes and institutional kitchens. It analyzes consumption history, seasonality, the academic calendar and weather to forecast how much of each dish should be prepared — cutting food waste and saving money — and puts that forecast in the hands of kitchen staff through a simple AI chatbot.

This repo contains a single self-contained front-end file: a landing page plus a login screen, no build step required.

---

## File

| File | Description |
|---|---|
| `preppulse.html` | The entire site — landing page + login view — in one file. |

Just open `preppulse.html` in any modern browser. There's nothing to install or build.

---

## What's inside

**Landing page**
- Hero section with an animated "pulse" visual (the Quasar brand mark, radiating rings + waveform)
- **The idea** — why mess waste happens and how PrepPulse fixes it (season, academic calendar, weather, dish-level history)
- **Sample dashboard** — an illustrative telemetry readout showing waste-before/after, monthly savings, and forecast accuracy
- **How it works** — the 5-stage pipeline: Log → Learn → Predict → Pulse → Ask
- **Chatbot demo** — a mocked conversation showing the AI assistant recommending prep quantities with reasoning
- **Impact section** — why less waste matters (money, food quality, calmer kitchens)
- Footer with nav links

**Login view**
- Split-screen layout with the animated brand panel on the left and a sign-in form on the right
- Role selector: Mess Manager / Kitchen Staff / Admin
- Email + password fields, "keep me signed in," "forgot password," and a campus SSO button (all UI only — see [Limitations](#limitations))

The two views live in the same HTML file and are swapped with a bit of JavaScript based on the URL hash — clicking **Log in** anywhere takes you to `#login`, and **← Back to PrepPulse** returns you to the landing page. No page reload, no separate files.

---

## Tech stack

- Plain HTML, CSS, and vanilla JavaScript — no frameworks, no dependencies, no build tools
- Google Fonts: [Space Grotesk](https://fonts.google.com/specimen/Space+Grotesk) (headings), [Inter](https://fonts.google.com/specimen/Inter) (body), [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) (data/telemetry labels)
- All visuals (the Quasar logo mark, pulse rings, waveform, icons) are hand-coded inline SVG — no image assets to host

Because everything is inline in one file, you can host it anywhere: drop it on GitHub Pages, Netlify, Vercel, or just double-click it locally.

---

## Design system

| Token | Value | Use |
|---|---|---|
| `--void` | `#050914` | Background |
| `--panel` / `--panel-2` | `#0b1530` / `#0f1c3d` | Cards, panels |
| `--quasar` | `#2f6bff` | Primary blue accent |
| `--pulse` | `#3ee8ff` | Cyan accent, glow effects |
| `--ice` | `#e8edfb` | Primary text |
| `--muted` | `#8391b8` | Secondary text |
| `--good` | `#4ee6a8` | Positive stats (savings, waste reduction) |

All colors are defined as CSS custom properties at the top of the `<style>` block, so re-theming the whole site is a matter of editing one `:root` section.

---

## Customizing

- **Logo/branding**: the Quasar mark is inline SVG in the `<nav>`, footer, and login panel. Swap it for a real logo file by replacing the `<svg>...</svg>` blocks with an `<img>` tag.
- **Copy & stats**: all text lives directly in the HTML — search for the section by its `id` (`#about`, `#how`, `#chatbot`, `#impact`) to edit.
- **Dashboard numbers**: the figures in the "Sample dashboard" section are clearly labeled as **illustrative example data**, not verified real-world statistics. Replace them with real numbers once connected to actual mess data.
- **Login logic**: the form currently has no backend — `onsubmit="return false;"` just prevents the page from reloading. Wire it up to your auth provider or API of choice.

---

## Limitations ##

This is a **front-end concept/demo only**:
- No backend, database, or authentication is implemented — the login form and SSO button are UI mockups
- The chatbot conversation is scripted/static, not a live AI integration
- Dashboard figures are sample data for illustration, not real statistics

To make this production-ready, you'd want to add: a backend + database for logging consumption/leftovers, a forecasting model, real authentication, and a live LLM-backed chatbot endpoint....

---

## Credit

Designed and built as **PrepPulse**, a project by ***Quasar***
...
..
