# Nothing Phone Glyph Composer (13x13)

Web tool for creating glyph animations for the 13x13 matrix (Nothing Phone 4a Pro workflow), including OGG metadata export for ringtones.

## Features

- 13x13 matrix editor with LED mask
- Per-pixel brightness (0-4095)
- Frame timeline: Add, Copy, Delete, navigation
- Preview with device-like 60 FPS timing
- JSON import (`Load JSON`)
- JSON export (`Export JSON`)
- OGG export with metadata:
  - `AUTHOR=<glyph data>`
  - `TITLE=<ringtone title>`
- Automatic animation looping on export when audio is longer than the animation

## Files

- `index.html` - main app
- `tutorial.html` - short guide for creating compatible OGG files

## Quick Start

1. Open `index.html` in your browser.
2. Create your animation on the matrix.
3. Optional: load an existing JSON file.
4. Set a title in `Rintone title / Filename.`.
5. Select your `.ogg`/`.opus` file.
6. Click `Bake & Download OGG`.

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

Detailed guide: `tutorial.html`

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
