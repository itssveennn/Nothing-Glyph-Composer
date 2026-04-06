# Nothing Phone Glyph Composer (13x13)

Web-Tool zum Erstellen von Glyph-Animationen fuer die 13x13-Matrix (Nothing Phone 4a Pro Workflow), inklusive OGG-Metadaten-Export fuer Klingeltoene.

## Features

- 13x13 Matrix-Editor mit LED-Maske
- Helligkeit pro Pixel (0-4095)
- Frame-Timeline: Add, Copy, Delete, Navigation
- Preview mit device-nahem 60-FPS-Timing
- JSON Import (`Load JSON`)
- JSON Export (`Export JSON`)
- OGG Export mit Metadaten:
  - `AUTHOR=<glyph data>`
  - `TITLE=<Ringtone title>`
- Automatisches Loopen der Animation beim Export, falls der Sound laenger ist

## Dateien

- `index.html` - Hauptanwendung
- `tutorial.html` - Kurzanleitung fuer kompatible OGG-Dateien

## Schnellstart

1. `index.html` im Browser oeffnen.
2. Animation auf der Matrix erstellen.
3. Optional: bestehende JSON-Datei laden.
4. Im Feld `Rintone title / Filename.` einen Titel setzen.
5. `.ogg`/`.opus` Datei auswaehlen.
6. `Bake & Download OGG` klicken.

## JSON-Format

Der JSON-Import/Export nutzt dieses Schema:

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

- `p`: aktive LED-Werte als 8-bit (0-255), in Masken-Reihenfolge
- `d`: Dauer in Millisekunden

## OGG vorbereiten (Kurzfassung)

Detailliert: `tutorial.html`

Empfohlener Workflow:

1. MP3 in Audacity oeffnen
2. `Ctrl + A`
3. `File -> Export Audio`
4. Format: `Opus file`
5. Rest unveraendert lassen
6. Exportieren
7. `.opus` in `.ogg` umbenennen

## Hinweise

- Dieses Tool arbeitet clientseitig im Browser (kein Server notwendig).
- Nicht jede OGG-Datei ist identisch aufgebaut; exotische Streams koennen fehlschlagen.
- Bei Problemen mit "Baking failed" am besten eine neue OGG-Datei nach obigem Workflow erzeugen.

## Credits

(c) its.sveennn
