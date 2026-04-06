# Nothing Phone Glyph Composer (13x13)

Web tool for creating glyph animations for the 13x13 matrix (Nothing Phone 4a Pro workflow), including OGG metadata export for ringtones.

## Features

- 13x13 matrix editor with LED mask
- Per-pixel brightness (0-4095)
- Frame timeline: Add, Copy, Delete, navigation
- Frame duration control (set hold time in ms for the current frame-run)
- Preview with device-like 60 FPS timing
- JSON import (`Load JSON`)
- JSON export (`Export JSON`)
- Gallery page (`gallery.html`) with:
  - Shared animations from `gallery/gallery-index.json`
  - Per-animation `Play` preview
  - `Use` button to open an animation in Glyph Composer
- OGG export with metadata:
  - `AUTHOR=<glyph data>`
  - `TITLE=<ringtone title>`
- Automatic animation looping on export when audio is longer than the animation

## Files

- [Glyph Composer](https://itssveennn.github.io/Nothing-Glyph-Composer/index.html) - main app
- `gallery.html` - gallery page with play/use flow
- `gallery/gallery-index.json` - shared gallery manifest
- [Tutorial for .ogg](file:///C:/Users/Sven/Downloads/composer%20new/tutorial.html) - short guide for creating compatible OGG files

## Quick Start

1. Open [Glyph Composer](https://itssveennn.github.io/Nothing-Glyph-Composer/index.html) in your browser.
2. Create your animation on the matrix.
3. Optional: load an existing JSON file.
4. Set a title in `Rintone title / Filename.`.
5. Select your `.ogg`/`.opus` file.
6. Click `Bake & Download OGG`.

## Gallery

`gallery.html` only shows published animations loaded from `gallery/gallery-index.json`.

`Play` previews an animation directly in the gallery card.
`Use` sends the selected animation back to Glyph Composer and loads it automatically.

To publish shared animations, add JSON files into `gallery/` and register them in `gallery/gallery-index.json`:

```json
[
  { "title": "My Animation", "file": "my-animation.json" }
]
```

## JSON Format

JSON import/export uses this schema:

```json
{
  "fps": 60,
  "width": 13,
  "height": 13,
  "frames": [
    {
      "p": [0, 255, 128],
      "d": 33
    }
  ]
}
```

- `p`: active LED values as 8-bit (0-255), in mask order
- `d`: duration in milliseconds

## OGG Preparation (Short Version)

Detailed guide: [Tutorial for .ogg](file:///C:/Users/Sven/Downloads/composer%20new/tutorial.html)

Recommended workflow:

1. Open your MP3 in Audacity
2. Press `Ctrl + A`
3. Go to `File -> Export Audio`
4. Format: `Opus file`
5. Keep all other settings unchanged
6. Export
7. Rename `.opus` to `.ogg`

## Notes

- This tool runs fully client-side in the browser (no server required).
- Not all OGG files are structured the same; unusual streams may fail.
- If you see `Baking failed`, create a fresh OGG file using the workflow above.

## Credits

(c) its.sveennn
