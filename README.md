# Pooria Shahbazi – Interactive CV

**Live:** [pooriashahbazi.com](https://pooriashahbazi.com)

An interactive CV website themed around embedded systems: the page boots like a Linux board, the background is a live PCB, and my career is shown as logic-analyzer channels. Bilingual (English / German), built with plain HTML, CSS and JavaScript – no frameworks, no build step, no dependencies.

> Information Engineering student at HAW Hamburg · Embedded Systems & Software
> Embedded Linux · ESP32 firmware in C · FPGA / VHDL · PCB design in Altium · Java & Python

---

## Features

| Section | What it does |
|---|---|
| **Boot sequence** | U-Boot / kernel-style serial log on first visit (skippable, shown once per session) |
| **PCB background** | Canvas-rendered copper traces with signal pulses that react to the mouse cursor |
| **Signal timeline** | Education and experience as logic-analyzer channels – hover to probe a point in time, click a channel to decode its details |
| **Projects** | Project cards incl. an interactive **CyPi block diagram** (power chain, I²C, GPIO, DSI, audio, Bluetooth, USB CDC modules) and an animated FPGA traffic-light state machine |
| **Skills** | Laid out like a peripheral register map – click any skill to highlight the projects and roles where it was used |
| **Languages** | Proficiency rendered as PWM duty cycle |
| **Serial console** | A small in-browser shell: `help`, `whoami`, `projects`, `cat cypi`, `i2cdetect`, `lsusb`, `skills`, `contact`, `cv`, `lang de` … and a few hidden commands |
| **EN / DE** | Language toggle, auto-detected from the browser; CV download matches the selected language |

Also: responsive down to phone width, keyboard accessible, respects `prefers-reduced-motion`, print-friendly.

## Project structure

```
index.html                    # the whole site: markup, styles and scripts in one file
photo.jpg                     # profile photo
CV_Pooria_Shahbazi_EN.pdf     # downloadable CV (English)
CV_Pooria_Shahbazi_DE.pdf     # downloadable CV (German)
```

All CV content lives in data objects at the top of the `<script>` block in `index.html` (`TIMELINE`, `PROJECTS`, `SKILLS`, `LANGS`, `UI`), so updating the CV means editing data, not markup.

## Run locally

No build needed – open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
```

then visit `http://localhost:8000`.

## Deployment

Hosted on **GitHub Pages** from the `main` branch (root) with a custom domain registered at one.com. Pushing to `main` updates the live site within about a minute.

## Tech

HTML5 · CSS3 (custom properties, grid, animations) · vanilla JavaScript (Canvas 2D, inline SVG, IntersectionObserver) · Google Fonts (Space Grotesk, JetBrains Mono)

## Contact

- GitHub: [@PooriaShahbazi](https://github.com/PooriaShahbazi)
- LinkedIn: [linkedin.com/in/pooriashahbazi](https://www.linkedin.com/in/pooriashahbazi)
- Website: [pooriashahbazi.com](https://pooriashahbazi.com)

---

© 2026 Pooria Shahbazi. All rights reserved.
