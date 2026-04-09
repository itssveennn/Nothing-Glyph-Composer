# Nothing Phone Glyph Composer

Web toolkit to design 13x13 glyph animations, prepare audio, and bake everything into ringtone-ready OGG files.

## Live Pages

- [Glyph Composer](https://itssveennn.github.io/Nothing-Glyph-Composer/index.html)
- [Audio Converter](https://itssveennn.github.io/Nothing-Glyph-Composer/audio-converter.html)
- [Gallery](https://itssveennn.github.io/Nothing-Glyph-Composer/gallery.html)
- [Tutorial](https://itssveennn.github.io/Nothing-Glyph-Composer/tutorial.html)

## Main Features

- 13x13 matrix editor with brightness control and drawing tools
- Frame-by-frame timeline with per-frame duration control
- Audio Sync mode for timing frames against loaded audio
- JSON import/export for animations
- `.glyphproj` import/export for full project restore
- Browser-based Audio Converter:
  - Waveform preview
  - Trim start/end
  - Append silence
  - Volume adjustment
  - Convert to OGG Vorbis
  - Send converted audio directly to Glyph Composer
- OGG bake writes required glyph metadata tags and validates output

## Recommended Workflow

1. Open [Audio Converter](https://itssveennn.github.io/Nothing-Glyph-Composer/audio-converter.html), upload audio, adjust edits, convert to `.ogg`.
2. Click `Use in Glyph Composer` (or load the `.ogg` manually in Composer).
3. Build animation in [Glyph Composer](https://itssveennn.github.io/Nothing-Glyph-Composer/index.html).
4. Fine-tune timing in `Audio Sync` mode.
5. Export with `Bake & Download OGG`.

## Gallery Publishing

Gallery entries are read from:

- `gallery/gallery-index.json`

Each entry should point to a JSON animation file in `gallery/`:

```json
[
  { "title": "My Animation", "file": "my-animation.json" }
]
```

## Notes

- Everything runs client-side in the browser.
- Hard refresh (`Ctrl+F5`) is recommended after updates on GitHub Pages.
- For full usage details, check [Tutorial](https://itssveennn.github.io/Nothing-Glyph-Composer/tutorial.html).

## Credits

© its.sveennn
