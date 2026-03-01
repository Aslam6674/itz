# Scroll-Driven Hero Section Animation
### Assignment Submission — ItzFizz

---

## Live Demo
🔗 [View Live](https://Aslam6674.github.io/itzfizz-hero/)

---

## Overview

This project is my implementation of the scroll-driven hero section animation assignment. I built the entire thing as a **single HTML file** so it can be deployed to GitHub Pages without any build tools — just upload and run.

The design is inspired by the reference demo but I made it my own with a dark luxury automotive aesthetic, gold accents, and a custom SVG car illustration that I drew directly in code.

---

## What I Built

### Hero Section Layout
The hero uses a **3-column CSS grid** layout:
- **Left column** — vertical letter-by-letter headline (`W E L C O M E I T Z F I Z Z`)
- **Center column** — the car SVG that animates on scroll
- **Right column** — impact statistics panel

### Load Animations (on page open)
I used GSAP to animate everything in on load:
- **Headline letters** stagger in from the left one by one (45ms delay each)
- **Stats** fade up with a small offset delay
- **Scroll hint** fades in last, after everything else settles

### Scroll Animation (core feature)
This was the most interesting part to figure out. I used **GSAP ScrollTrigger with `pin: true`** to keep the hero section fixed while the user scrolls through 2.2x the viewport height.

As the user scrolls, the car goes through 3 phases:
1. Sweeps to the right + tilts clockwise (`rotateZ: 9deg`)
2. Crosses to the left + tilts the other way (`rotateZ: -6deg`)
3. Snaps back to center perfectly

The `scrub: 1.5` setting ties the animation directly to scroll position so it feels fluid and natural — not time-based.

I also added:
- Letter parallax (drift upward and fade as you scroll)
- Stats slide out to the right as the car takes over
- Gold scroll progress bar at the top of the page

---

## Tech Stack

| Technology | How I Used It |
|---|---|
| **HTML5** | Structure and markup |
| **CSS3** | Custom layout, variables, keyframe animations |
| **Tailwind CSS** | Utility classes for quick spacing/sizing |
| **JavaScript (ES6+)** | Logic, refs, scroll calculations |
| **React 18** | Component structure (via CDN, no build step) |
| **GSAP 3** | Intro animations (stagger, fade, slide) |
| **GSAP ScrollTrigger** | Scroll-pinning and scrub-based animation |

---

## Project Structure

```
itzfizz-hero/
├── index.html      ← everything lives here (self-contained)
└── README.md       ← this file
```

I kept it as a single file intentionally — no bundler, no `npm install`, nothing to configure. Just open it and it works.

---

## How to Run Locally

1. Clone or download this repo
2. Open `index.html` in VS Code
3. Install the **Live Server** extension
4. Click **"Go Live"** in the bottom-right corner
5. Visit `http://127.0.0.1:5500/index.html`

> ⚠️ Don't open the file directly in the browser (`file://`) — some scripts may not load correctly. Use Live Server instead.

---

## Key Things I Learned

- **GSAP `scrub`** is the key to scroll-tied animations. Setting `scrub: 1.5` instead of `true` adds a small lag that makes the motion feel more physical and weighted
- **`will-change: transform`** on the car element helps the browser optimize the animation and keeps it at 60fps
- **Pinning with ScrollTrigger** (`pin: true`) was tricky at first — you need to give the trigger element extra scroll space via `end: "+=220%"` or the animation finishes too quickly
- Using **CSS `transform`-only properties** (translate, rotate, scale) for all animations avoids layout reflows completely

---

## Design Decisions

- **Dark luxury theme** — felt right for an automotive/mobility brand like ItzFizz
- **Gold accents (`#c9a84c`)** — single accent color keeps it premium without being busy
- **Bebas Neue** for the headline — bold condensed font reads well vertically
- **Space Mono** for stats/body — monospace gives a technical/data feel
- **SVG car drawn in code** — wanted everything self-contained, no image dependencies

---

## Browser Support

Tested and working in:
- ✅ Chrome 120+
- ✅ Firefox 121+
- ✅ Safari 17+
- ✅ Edge 120+

---

*Assignment submitted as part of the frontend development evaluation.*
