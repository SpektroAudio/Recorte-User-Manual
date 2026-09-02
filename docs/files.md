# File

---

## File Structure

Each file open in Recorte includes information such as:

- **Audio Buffer**

    - Name

    - Samples *(Multi-channel audio samples)*

    - Info *(Sample rate, bit-depth, bpm, number of bars)*

    - [Regions](regions.md)

    - [Effects](effects.md)

    - Transients

- **Path**

- **Export Settings**

- **View Settings**

- **Undo History**

When you load existing files, Recorte automatically parses the audio data with the original metadata (filename, path, file format, sample rate, and bit-depth). It then converts it to its own file format with the correct path and export settings.

When you record new samples, Recorte uses the recording sample rate / bit-depth and default folder settings.

Recorte uses its file format only internally. Export files through [Export actions](actions.md) to convert them back into an audio format.

To continue a session in the future, use the Save Workspace or Load Workspace action.

---

## Supported Formats (Import / Export)

Recorte currently supports the following formats:

| Format | Import | Export | Limitations   |
|--------|--------|--------|---------------|
| WAV    | ✓      | ✓      | 16 or 24 bits |
| AIFF   | ✓      | ✓      | 16 or 24 bits |
| FLAC   | ✓      | ✗      | -             |
| MP3    | ✓      | ✗      | -             |

---

## Export Settings

Each file has a list of export settings that define how Recorte writes audio files to disk. Each row produces one output file and defines:

- **Format** — WAV or AIFF (integer PCM).
- **Sample Rate** — target sample rate of the exported file.
- **Bit Depth** — target bit depth of the exported file.
- **Suffix** — text appended to the filename before the extension.

All rows share the file's export name and path. Recorte writes each file as `{filename}{suffix}.{extension}` (`.wav` or `.aif`). When a file has more than one row, Recorte appends an index number to keep filenames unique, for example `kick_24_4801.wav` and `kick_16_4402.wav`.

When you open an existing file, Recorte automatically creates an export setting that matches the format, sample rate, and bit depth of the source file. New rows added in the Export view start with the current file's values.

### Exporting files in Recorte

When you export a file or region, Recorte processes the audio for each row:

- **Sample Rate** — If the file's sample rate differs from the target sample rate, Recorte resamples the audio with its built-in (windowed-sinc) resampler.
- **Bit Depth** — If the target bit depth is lower than the file's bit depth, Recorte automatically converts the bit-depth and applies TPDF dither when downscaling.
- **Effects** — When you export a file, Recorte first renders the active (non-bypassed) global effect chain into the audio. When you export regions, Recorte renders each region with its effects before it writes the file.

`Export File` writes to the file's export path. If the target file already exists, Recorte opens a save dialog so you can choose a new name or location. That choice becomes the file's new export setting.

Recorte lists exported files in the *Exported Files* panel of the Export view. From this panel, you can copy a file path or reveal the file in the file manager.

---

## Workspace

The group of currently open files defines the Workspace in Recorte.

Use the `Save Workspace` and `Load Workspace` actions to save and recall the contents of the current workspace.

