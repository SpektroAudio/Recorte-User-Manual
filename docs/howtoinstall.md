# Installation

---

## System Requirements

| OS      | Minimum Version          | Notes                                      |
|---------|--------------------------|--------------------------------------------|
| macOS   | 11 (Big Sur) or later    | -                                          |
| Windows | Windows 10               | Windows 11 is also supported               |
| Linux   | Any current distribution | FUSE support is required for the AppImage  |

- 4GB RAM: Recorte uses approximately 80MB of RAM at idle but usage may increase depending on audio files and undo history sizes

- Internet connection is only required for initial authorization

- Minimum resolution: 1280 x 720px


---

## macOS

The macOS installer is a DMG file. The DMG contains the PKG installer that installs the app and the factory settings.

To install Recorte on macOS:

1. Separate installers are provided for Intel Macs and Apple Silicon Macs. Make sure you have the installer for your Mac's chip (Intel or Apple Silicon).
2. Open the DMG file (named like `Recorte_v<version>_macOS.dmg`).
3. Double-click the PKG installer inside the mounted volume.
4. Follow the prompts in the installer window.
5. Enter your Mac account password if prompted.
6. When running Recorte for the first time, macOS may ask for microphone permission.

The installer places Recorte.app in `/Applications` and copies the factory settings to `~/Library/Application Support/Spektro Audio/Recorte/settings`.

!!! note
    The app is signed and notarized by Apple. macOS may show a dialog that asks whether you want to open the app on first launch.

---

## Windows

The Windows installer is an executable file (`Recorte_v<version>_Windows.exe`).

To install Recorte on Windows:

1. Run the installer file.
2. Click Yes in the User Account Control window.
3. Follow the prompts in the installer window.

The installer offers three components:

- **Main Application** (required) — installs `Recorte.exe` to `C:\Program Files\Spektro Audio\Recorte`
- **Userdata** (optional) — copies factory settings and presets to `%LOCALAPPDATA%\Spektro Audio\Recorte\settings`
- **Desktop Shortcut** (optional) — creates a shortcut on the desktop

The installer also creates Start Menu shortcuts under `Spektro Audio > Recorte` and adds an entry to Add/Remove Programs.

---

## Linux

The Linux build is an AppImage file (`Recorte.AppImage`).

To run Recorte on Linux:

1. Open a terminal in the folder that contains the AppImage.
2. Run `chmod +x Recorte.AppImage`.
3. Run `./Recorte.AppImage`.

On first launch, Recorte copies the factory settings from the AppImage to `~/.local/share/Spektro Audio/Recorte/settings`.

The AppImage requires FUSE. If the AppImage does not start, install the FUSE package for your distribution (for example, `sudo apt install fuse3`).

!!! note
    The AppImage is signed with GPG. A signature file (`Recorte.AppImage.asc`) and a checksum file (`SHA256SUMS`) are provided alongside the AppImage.

---

## Activating Recorte

When you start Recorte without a valid license, an activation dialog appears before you can use the editor. Enter your serial code to activate Recorte:

1. Start Recorte. The **ACTIVATION NOT FOUND** dialog appears.
2. In the **Enter serial code** field, type your serial code.
3. Click **Activate**.

Recorte checks the serial code online and binds the license to this computer. If the serial code is valid, the dialog closes and Recorte enables all features.

!!! note
    Recorte needs an internet connection for activation. After activation, Recorte saves the license in `settings/license/activation` inside your user data folder (see File Locations). You do not need a connection on later starts.

- If activation fails, Recorte shows an error notification. Check the serial code and your internet connection. Then try again.
- Recorte ties each license to one computer. If you reach the maximum number of activations, contact Spektro Audio support.

---

## File Locations

For the locations where Recorte installs itself and stores your settings, presets, scripts, and license on each platform, see [File Locations](filelocations.md).

---

## Uninstalling

### macOS

1. Quit Recorte.
2. Move `Recorte.app` from `/Applications` to the Trash.
3. To remove your user data, delete `~/Library/Application Support/Spektro Audio/Recorte`.

### Windows

1. Open Settings > Apps > Installed apps (or Control Panel > Programs and Features).
2. Select Recorte.
3. Click Uninstall.
4. When prompted, choose whether to also remove your personal data (settings, presets, scripts).

### Linux

1. Delete the `Recorte.AppImage` file.
2. To remove your user data, delete `~/.local/share/Spektro Audio/Recorte`.
