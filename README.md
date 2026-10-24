# Vector Front — v126

This is now a folder instead of one giant HTML file. Structure:

```
index.html          - all the game code (HTML/CSS/JS), ~630KB
assets/
  base/              - home base damage-stage artwork (4 images)
  buildings/
    standard/        - the normal 10-building set + damage states (40 images)
    industrial/      - Industrial Hell's 12-building set + damage states (48 images)
    legacy/          - old shape-based building sprites, kept for loading very old saves (8 images)
  terrain/
    mountains/       - the 12 mountain images
    roads/           - road tile textures
    compounds/       - decorative ground pads
    craters/         - permanent battle-damage crater sprites
    trees/           - tree sprite variants
    grassland_tiles/ - grassland + farmland ground textures
    ice_tiles/       - ice biome ground textures
    urban_tiles/     - Industrial Hell ground textures
  units/
    body/            - unit sprites
    wreck/           - destroyed-unit wreck sprites
  ui/
    title_artwork.jpg - title screen background
```

## Why this changed

Previously every image was embedded directly inside the HTML file as base64 text,
which made the single file ~25MB and meant any small change (like swapping one
image) touched the whole file. Now the code and the art are separate: `index.html`
references images by normal relative paths (e.g. `assets/units/body/tank.png`),
exactly like a normal website.

## Running it

**Must be served over HTTP** — same as before (GitHub Pages, or a local server
like a-Shell's). Opening `index.html` directly by double-clicking it (`file://`)
will NOT load the images, because browsers block that kind of local file access
for security reasons. Keep the whole folder together — `index.html` needs
`assets/` to sit right next to it.

For GitHub: commit the whole folder (`index.html` + `assets/`) to your repo.
GitHub Pages will serve `index.html` at your site's root automatically.

## For future changes

When asking Claude to add or replace art going forward, the same folder can be
handed back and forth — only the specific image files that changed need to be
touched, not the whole codebase.
