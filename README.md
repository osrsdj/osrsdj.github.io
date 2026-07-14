# Drug Box Insert Designer

A browser-based tool for laying out drug boxes and vials into a container, then exporting the result as an SVG file for LightBurn (laser cutter software).

## Live site

Once you've set up GitHub Pages (see below), the site will be at:
`https://<your-username>.github.io/<repo-name>/`

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

## Setting up GitHub Pages

1. Create a new repository on GitHub (public if you have a free account)
2. Upload `index.html` to the root of the repo (either via the GitHub website's "Add file → Upload files", or via `git`)
3. Go to the repo's **Settings** → **Pages** in the left sidebar
4. Under **Source**, select **Deploy from a branch**
5. Choose the `main` (or `master`) branch and the `/ (root)` folder
6. Click **Save**
7. Wait a minute or two, then reload the Pages settings page — the URL of your live site will appear at the top

That's it. Any edits you push to the branch will redeploy automatically.

## Working offline

You don't need GitHub Pages to use this — `index.html` is fully self-contained. Just open it directly in a browser. All packing, dragging, and SVG export runs client-side; no server or network access needed.

## Tech notes

- One-file HTML/CSS/JavaScript. No build step, no dependencies.
- Uses `<canvas>` for the layout preview and shelf packing + MaxRects algorithms for the layout.
- SVG export uses stroke colors LightBurn recognizes: red (`#FF0000`) for drug outlines, blue (`#0000FF`) for the container outline (imports as separate cut layers).
