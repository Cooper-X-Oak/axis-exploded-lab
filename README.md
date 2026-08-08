# Axis Exploded Lab

Axis Exploded Lab is a standalone Three.js preview for an axis-aligned commercial exploded assembly animation of a fixed ball valve.

The demo keeps the ball center fixed, disables self-rotation, and choreographs the explosion by assembly-axis order:

- outer blockers and fasteners clear first;
- shells and brackets move next;
- inner seats, springs, packing, and stem stacks move after their parent blockers have cleared;
- X, Y, Z-offset, spacing, and timeline progress are adjustable in the browser.

## Run Locally

Serve the repository root with any static file server:

```powershell
python -m http.server 8020
```

Then open:

```text
http://127.0.0.1:8020/?view=hero-exploded&explode=1&axisX=1&axisZ=0.75&axisY=0.12&spacing=1
```

## GitHub Pages

This repository is designed to publish directly from the `main` branch root with GitHub Pages.
