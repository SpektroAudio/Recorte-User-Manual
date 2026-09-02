# File Locations

Recorte stores your settings, presets, scripts, and logs in a user data folder. Recorte creates it on first launch.

| OS      | User Data Folder                                          |
|---------|-----------------------------------------------------------|
| macOS   | `~/Library/Application Support/Spektro Audio/Recorte`     |
| Windows | `%LOCALAPPDATA%\Spektro Audio\Recorte`                    |
| Linux   | `~/.local/share/Spektro Audio/Recorte`                    |

!!! note
    On Windows, `%LOCALAPPDATA%` is usually `C:\Users\<username>\AppData\Local`.  

## Folder Structure

```text
Recorte/
├── logs/                   Log files
└── settings/
    ├── settings.toml       Application settings
    ├── shortcuts.json      Keyboard shortcut assignments
    ├── license/activation  License file (created after activation)
    ├── scripts/            Lua scripts (.lua)
    └── presets/
        ├── effects/        Effect presets
        ├── batch/          Batch Editor presets
        ├── audiorecorder/  Audio Recorder presets
        └── themes/         UI themes
```

To move Recorte to another computer, copy the whole folder to the same location before first launch. This keeps your settings, presets, scripts, and license.
