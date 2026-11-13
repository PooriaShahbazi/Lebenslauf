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
| **Projects** | Project cards incl. an interactive **CyPi block diagram** – hover any block to trace its connections: LiPo → 5 A fuse → on/off switch → charge/discharge module → 5 V PDU (Pi, amplifier, Bluetooth keyboard), MAX17048 fuel gauge over I²C, DSI display, rotary encoder, amplifier → stereo speakers, and planned TM4C1294 / MCX N236 modules over USB CDC. Plus an animated FPGA traffic-light state machine |
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
CNAME                         # custom domain for GitHub Pages
README.md
```

## Updating the content

All CV content lives in data objects in the `<script>` block of `index.html`, so updating the CV means editing data, not markup:

| Object | Contents |
|---|---|
| `TIMELINE` | Education and work entries (`k: "edu"` / `"work"`, `from` / `to` as `MM/YYYY`, `to: null` = ongoing) |
| `PROJECTS` | Project cards, bullet points and tags |
| `SKILLS` | Skill groups for the register map |
| `LANGS` | Spoken languages and levels |
| `DIAG` | Descriptions for each block of the CyPi diagram |
| `UI` | Interface strings |

Every text is either a plain string or an `["English", "Deutsch"]` pair. When the CV changes, update the two PDFs as well so the download matches the page.

## Run locally

No build needed – open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
```

then visit `http://localhost:8000`.

## Deployment

Hosted on **GitHub Pages** from the `main` branch (root), with HTTPS enforced. The domain is registered at one.com and points to GitHub Pages (A records for the apex domain, CNAME for `www`). Pushing to `main` updates the live site within about a minute.

## Download the CV

- [English (PDF)](https://pooriashahbazi.com/CV_Pooria_Shahbazi_EN.pdf)
- [Deutsch (PDF)](https://pooriashahbazi.com/CV_Pooria_Shahbazi_DE.pdf)

## Tech

HTML5 · CSS3 (custom properties, grid, animations) · vanilla JavaScript (Canvas 2D, inline SVG, IntersectionObserver) · Google Fonts (Space Grotesk, JetBrains Mono)

## Contact

- GitHub: [@PooriaShahbazi](https://github.com/PooriaShahbazi)
- LinkedIn: [linkedin.com/in/pooriashahbazi](https://www.linkedin.com/in/pooriashahbazi)
- Website: [pooriashahbazi.com](https://pooriashahbazi.com)

---

© 2026 Pooria Shahbazi. All rights reserved.
