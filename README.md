# AutoHMI — Automotive Human-Machine Interface Prototype

A browser-based interactive HMI dashboard prototype, built to demonstrate interface design principles for in-vehicle digital systems.

**[→ Live Demo](jnagrur.github.io/autohmi)**
**[→ Repo Link](https://github.com/JNagrur/autohmi)**

---

## What This Is

This project simulates the primary display panel of an automotive HMI system — the kind of interface a driver interacts with in real time, under cognitive load, while managing a vehicle.

It is not a production system. It is a design and interaction prototype, built to explore and demonstrate key HMI design questions:

- How do you surface critical information (speed, warnings, temperature) without demanding attention?
- How should controls behave when the user's primary focus is elsewhere?
- What feedback loops reassure the user that the system is responding correctly?

---

## Features & Interaction Design Decisions

### Speedometer Arc
The central arc fills dynamically as the user drags the speed slider. The arc colour shifts from amber → orange → red as speed increases — using a learned visual convention (traffic light logic) that requires no instruction. At speeds above 180 km/h the arc pulses red and the engine temperature alert activates. This models a progressive disclosure pattern: the interface only escalates when escalation is warranted.

### Drive Mode Selector
Four modes (Eco, Comfort, Sport, Sport+) with distinct active states. The selected mode persists visually and would, in a real system, affect throttle response, suspension, and climate behaviour. The design keeps all four options permanently visible — no hidden menus — because mode switching is a high-frequency action that should never require more than one tap.

### Dual-Zone Climate Control
Driver and passenger zones are independently adjustable in 0.5° increments. The fan speed control uses a stepped selector rather than a continuous slider — a deliberate choice based on how drivers actually use climate controls: they want discrete levels, not infinite granularity they have to re-find every time.

### Alert System
System alerts are displayed as persistent chips rather than modal interruptions. Warnings do not block the interface. Critical alerts (engine overheat) use a pulsing red border animation to draw attention without removing driver control. This reflects a core HMI principle: the system informs, the driver decides.

### Media Panel
Track progress, playback controls, and volume are grouped in a single panel on the right. The seek bar is tap-interactive. Track information updates on next/previous without animation delay — snappy feedback for a control that may be used briefly.

---

## Background

This prototype is informed by professional experience developing frontend interfaces for automotive and technology platforms, including:

- HMI development using Unity and C# scripting at Tata Elxsi
- Frontend engineering for internal tooling at Mercedes-Benz R&D India (Vue 3, TypeScript)
- AR/VR proof-of-concept prototyping for spatial interaction design

The design intentionally references automotive instrument cluster conventions — the amber colour scheme, arc-based gauges, and grouped zone layout — rather than applying generic UI patterns to a vehicle context.

---

## Tech Stack

- Vanilla HTML, CSS, JavaScript — no framework dependencies
- SVG-based arc rendering with dynamic path calculation
- CSS custom properties for theming
- Google Fonts: Space Grotesk + Space Mono

Kept dependency-free intentionally: HMI environments often run on constrained embedded systems where framework overhead matters.

---

## What I Would Build Next

- Keyboard and gamepad input support (relevant for actual in-car hardware)
- A navigation panel with route progress and turn-by-turn indicators
- Dark/light ambient mode switching tied to time of day
- Accessibility audit: WCAG contrast ratios for all text/background combinations at all states
- User testing protocol: measuring glance time and error rate for critical controls

---

## Author

Jadeshwari Nagarur — Frontend Engineer & Interaction Designer  
[LinkedIn](https://linkedin.com/in/jadeshwari-nagarur) · [GitHub](https://github.com/JNagrur)
