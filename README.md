# Drug Box Insert Designer

A browser-based tool for laying out drug boxes and vials into a container, then exporting the result as an SVG file for LightBurn (laser cutter software).

## Features

- Add drugs from presets (TXA, Cefazolin, Ket/Cef, Ondansetron, 1ml vial, 2ml vial, Methoxy/Fent lolly) or create custom boxes
- Automatic layout with configurable minimum gap between boxes and walls
- Rounded or concave container corners
- Multiple containers with automatic or manual box assignment
- Drag boxes to reposition — other boxes shove out of the way
- Keyboard shortcuts:
  - **Q** / **W** — rotate selected drug left / right (1° per press; Shift = 15°, Alt = 5°)
  - **P** — pin selected drug so it won't move
  - **Arrow keys** — nudge selected drug (Shift = 10mm, Alt = 0.1mm)
  - **Escape** — deselect
- **Reorganize** button — repack unpinned drugs while keeping pinned ones in place
- **Mirror** checkbox per drug — generates a backing-layer container with those drugs at identical positions
- SVG export ready for import into LightBurn


That's it. Any edits you push to the branch will redeploy automatically.

## Working offline

You don't need GitHub Pages to use this — `index.html` is fully self-contained. Just open it directly in a browser. All packing, dragging, and SVG export runs client-side; no server or network access needed.

## Tech notes

- One-file HTML/CSS/JavaScript. No build step, no dependencies.
- Uses `<canvas>` for the layout preview and shelf packing + MaxRects algorithms for the layout.
- SVG export uses stroke colors LightBurn recognizes: red (`#FF0000`) for drug outlines, blue (`#0000FF`) for the container outline (imports as separate cut layers).
