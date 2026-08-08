# Axis Exploded Lab

Axis Exploded Lab is a standalone Three.js control surface for an axis-aligned exploded assembly animation of a fixed ball valve.

This repository is not the final online renderer. It intentionally keeps materials lightweight so the public page can load quickly and focus on animation inspection, rig tuning, part-family visibility, and transform export. Final material look development and 240-frame hero rendering should happen offline in Blender or another production renderer.

The demo keeps the ball center fixed, disables self-rotation, and choreographs the explosion by assembly-axis order:

- outer blockers and fasteners clear first;
- shells and brackets move next;
- inner seats, springs, packing, and stem stacks move after their parent blockers have cleared;
- X flow-axis, Y stem-axis, Z depth-offset, spacing, and timeline progress are adjustable in the browser.
- `window.__issue8HeroExplosion` exposes the rig contract for downstream Blender/keyframe export.

## Scope

- Three.js: load the GLB, color part families, operate the animation, inspect timing, and export transform data.
- Blender: render final materials, lighting, camera, and image/video frames.
- No online PBR texture loading is required for the public page.
- The published page uses a sub-1 MB meshopt-compressed rig preview GLB, keeping part/node identity intact for animation.

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
