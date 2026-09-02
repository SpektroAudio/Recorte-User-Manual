# Actions

---

## About

Many of Recorte's features can be controlled using actions, which you can trigger using keyboard shortcuts or the Action Palette.


---

## File

### Auto Trim File

Trim the active file to its audio content. A temporary region spanning the whole file is shrunk based on loudness (threshold), and all samples before and after it are removed.

Parameters:

| Name      | Description     |
|-----------|-----------------|
| Threshold | Threshold in dB |

### Close Active File

Close the active file in the workspace.

### Close All Files

Close all files in the workspace.

### Duplicate File

Duplicate the active file.

### New File From Selected Region

Create a new file from each selected region in the active file.

### New Files From All Regions

Create new files from each region available in the active file.

### Open File

Open a file from disk into the workspace (opens the file dialog).

### Slice File

Split the file into equal slices / regions.

Parameters:

| Name     | Description         |
|----------|---------------------|
| Slices   | Number of slices / regions    |

### Trim File to Selected Regions

Trim the active file based on the selected regions' start and end.



---

## Playback

### Play

Start playback of the active file, or the current selection / selected regions, with custom pitch and gain.

Parameters:

| Name     | Description                          |
|----------|--------------------------------------|
| Pitch    | Playback rate (1.0 = original speed), bipolar slider (-10.0 to 10.0) |
| Gain     | Gain level (0.0 to 1.0)              |
| Loopable | Loop playback (boolean toggle)       |

### Play Note

Start playback with the pitch and gain set by an incoming MIDI note (Base note: C4). Plays the current selection or selected regions at that pitch; without a selection, each note from C4 up plays a different region.

Parameters:

| Name     | Description         |
|----------|---------------------|
| Note     | Note number / pitch (0-127) |
| Velocity | Note velocity (0-127), sets the playback gain |

### Stop Playback

Immediately stop any ongoing playback.

### Toggle Playback Loop

Enable or disable loop playback.

---

## Editing

### Cut Selection

Cut the current selection from the active file and store it in the clipboard.

### Copy Selection

Copy the current selection from the active file and store it in the clipboard.


### Paste

Paste the content of the clipboard into the active file based on a specified position and mode.

Parameters:

| Name     | Description                                   |
|----------|-----------------------------------------------|
| Position | `Prepend`: Paste to the beginning of the file. <br> `Append`: Paste to the end of the file. <br>`Position`: Paste at a specific position (0–100% of the file length). |
| Mode     | `Insert`: Inserts the new clipboard content at position.<br>`Replace`: Replace existing audio with the clipboard content. <br> `Mix`: Mixes existing audio with clipboard content (blend controlled by the mix ratio, 0.0 to 1.0). <br> `Add`: Overlay existing audio with clipboard content.|

### Convert Bit-Depth

Convert the active file bit-depth and apply dithering when you reduce the bit depth.

Parameters:

| Name      | Description                                  |
|-----------|----------------------------------------------|
| Bit Depth | Target bit depth (1 to 24)                   |
| Dither    | Apply dithering during conversion (boolean toggle) |

### Convert Sample Rate

Convert the active file's sample-rate via re-sampling.

Parameters:

| Name          | Description                                        |
|---------------|----------------------------------------------------|
| Sample Rate   | Target sample rate in Hz (1 to 192000)             |
| Interpolation | Resampling interpolation: Nearest, Linear, or Cubic |

### Duplicate Channel

Duplicate one of the available channels in the active file based on its channel number.

### Remove Channel

Remove a channel from the active file based on its channel number. The last remaining channel cannot be removed.

---

## Region Actions

### Auto Trim Selected Regions

Shrink the selected regions' start and end based on the audio loudness.

Parameters:

| Name      | Description     |
|-----------|-----------------|
| Threshold | Threshold in dB |

### Auto Trim All Regions

Shrink all regions' start and end based on the audio loudness.

Parameters:

| Name      | Description     |
|-----------|-----------------|
| Threshold | Threshold in dB |


### Zero-Cross Selected Region

Snap the selected region to the nearest zero-crossing point.

### Zero-Cross Transients

Snap all transients to the nearest zero-crossing points.

### Create Region From Selection

Create a new region from the current selection.

### Create Region From Transients

Create a region at each detected transient. Transients must be detected first.

Parameters:

| Name      | Description                              |
|-----------|------------------------------------------|
| Pad Start | Padding added before each region start (ms) |
| Pad End   | Padding added after each region end (ms)   |

### Remove Region

Remove a region in the active file based on the region index.

### Remove Selected Region

Remove the currently selected region.

### Remove All Regions

Remove all regions in the active file.

### Duplicate Selected Region

Make a copy of the selected region.

### Expand

Expand the current selection or selected regions to the next or previous region or transient boundary.

Parameters:

| Name       | Description                                                        |
|------------|--------------------------------------------------------------------|
| Destination | `Auto`: Expand automatically based on the current context. <br> `All Regions`: Expand all selected regions. <br>`Selected Regions`: Expand the selected region(s). <br>`Selection`: Expand the current selection. |  
| Location   | `Start`: Expand towards the start. <br> `End`: Expand towards the end. <br>`Both`: Expand both directions. |
| Expand To   | `Region`: Expand to the next region boundary. <br>`Transient`: Expand to the next transient point. |

### Extend (All / Selected) Region Start

Extend the start of all / selected regions backwards until the previous region or transient.


### Extend (All / Selected) Region End

Extend the end of all / selected regions forwards until the next region or transient.

### Join All Regions

Consolidate the audio from all regions in the active file to a new file.
It is also possible to add some separation and crossfading between regions.

Parameters:

| Name           | Description                    |
|----------------|--------------------------------|
| Separation | Gap between segments in ms     |
| Crossfade   | Crossfade duration in ms       |

### Join Selected Regions

Consolidate the audio from the selected regions in the active file to a new file.
It is also possible to add some separation and crossfading between regions.

Parameters:

| Name           | Description                    |
|----------------|--------------------------------|
| Separation | Gap between segments in ms     |
| Crossfade   | Crossfade duration in ms       |


### Slice Selected Region

Split the selected region into equal regions.

Parameters:

| Name     | Description         |
|----------|---------------------|
| Slices   | Number of slices / regions    |

### Resize Region

Open the dialog to resize the current region.

### Resize Region By

Resize region by a specific size preset.

Parameters:

| Name     | Description                          |
|----------|--------------------------------------|
| Size     | Size unit: Millis, Samples, Beats, Bars, SizeKbs, or Factor |
| Millis   | Time in milliseconds (optional, positive integer) |
| Samples  | Number of samples (optional, positive integer) |
| Beats    | Number of beats (optional, positive integer) |
| Bars     | Number of bars (optional, positive integer) |
| SizeKbs  | Size in kilobytes (optional, positive integer) |
| Factor   | Multiplication factor (optional, positive float, default: 1.0) |

### Sort Regions

Reorder the regions of the active file by Name, Position, Start, End, or Length. Only the region order and numbering change — the audio itself is not moved.

Parameters:

| Name   | Description                      |
|--------|----------------------------------|
| Sorting Mode | `Name`<br>`Position`<br>`Start`<br>`End`<br>`Length`  |

### Select Region

Select a specific region based on the chosen selection mode.

Parameters:

| Name     | Description                               |
|----------|-------------------------------------------|
| Selection | `First`: Select the first region. <br> `Last`: Select the last region. <br>`Shortest`: Select the shortest region. <br>`Longest`: Select the longest region. |

### Move Regions

Shift selected regions by a time period.

Parameters:

| Name     | Description                           |
|----------|---------------------------------------|
| Period   | Shift amount in samples, milliseconds, or percentage (positive moves later in the file, negative earlier) |

---

## Export

### Export File

Export the active file to its path (overwrite if the file already exists).

### Export All Regions

Export all regions in the active file as separate audio files to the file path using the Export settings.

### Export Selected Regions

Export the selected regions in the active file as separate audio files to the file path using the Export settings.

### Export All Files

Export all files in the workspace.

---

## Transients & Detection

### Clear Transients

Remove all detected transients.

### Detect Regions

Analyze the active file and create regions from detected audio segments.

Parameters:

| Name            | Description                                   |
|-----------------|-----------------------------------------------|
| Threshold       | Detection threshold in dB                     |
| Min. Length     | Minimum region length in ms                   |
| Min. Separation | Minimum silence between regions in ms         |
| Pad Start       | Padding added before each region start (ms)   |
| Pad End         | Padding added after each region end (ms)      |

### Detect Transients

Analyze and mark transients in the current file.

Parameters:

| Name        | Description              |
|-------------|--------------------------|
| Threshold   | Detection Threshold      |
| Zero-Cross Transients | Toggle zero-crossing for all detected transients  |

### Detect Pitch for All Regions

Run pitch detection on every region.

---

## Recording

### Start Recording

Begin audio recording using the settings defined in the [Audio Recorder](tools/audiorecorder.md).

### Stop Recording

Stop the active recording and create a new file in the workspace from the recording.

### Set Recording Length

Configure the recording duration in seconds.

Parameters:

| Name      | Description           |
|-----------|-----------------------|
| Seconds   | Length in seconds     |

### Load Audio Recorder Preset

Load a saved recorder configuration.

Parameters:

| Name     | Description       |
|----------|-------------------|
| Preset   | Preset file path (.json)       |

### Save Audio Recorder Preset

Export the current recorder settings as a JSON file.

---

## Effects & Processing

### Process

Apply a single audio effect to the active file, all regions, selected regions, or the current selection. See [Effects](effects.md) for available effects.

Parameters:

| Name     | Description                                       |
|----------|---------------------------------------------------|
| Apply To | File / All Regions / Selected Regions / Selection |
| Effect   | Effect to Apply                                   |

### Apply Effect Chains

Apply the current effect chain to the specified destination.

Parameters:

| Name          | Description                                       |
|---------------|---------------------------------------------------|
| Apply To      | File / All Regions / Selected Regions / Selection |
| Clear Effects | Clear the effect chain after applying (boolean toggle) |

### Load Effect Preset

Load a saved effect preset.

Parameters:

| Name     | Description           |
|----------|-----------------------|
| Preset   | Preset file path      |

### Copy Effect Chain

Copy the current effect chain to the clipboard.

### Paste Effect Chain

Paste an effect chain from the clipboard.

### Clear Effect Chain

Remove all effects from the chain.

### Save Effect Preset

Save the current effect chain as a preset.

### Save Effects as Default

Save the active file's current effect chain as the default preset. New files use this chain when they are created.

### Reveal Effect Preset Folder

Open the effect preset folder in Finder.

### Send to Sampler

Send audio to a sampler with custom parameters.

Parameters:

| Name             | Description                               |
|------------------|-------------------------------------------|
| Source           | Source type: File, All Regions, Selected Region, or Selection |
| Output Channel   | Output device channel (1 to output_channels) |
| Gain dB          | Output gain in dB (-96.0 to 0.0, step 3.0 dB) |
| Convert to Volca | Enable Volca Syro stream conversion (optional, boolean toggle) |
| Sample Slot      | Sample slot for Volca (optional, 1 to 100) |
| Quality          | Conversion quality (optional, 8 to 16) |

### Apply Effects To Selected Regions

Apply the file's current effect chain to the selected regions.

Parameters:

| Name          | Description                            |
|---------------|----------------------------------------|
| Clear Effects | Clear the effect chain after applying (boolean toggle) |

### Apply Effects To Regions

Apply the file's current effect chain to specific regions by index.

Parameters:

| Name          | Description                            |
|---------------|----------------------------------------|
| Regions       | List of region indices                 |
| Clear Effects | Clear the effect chain after applying (boolean toggle) |

---

## Batch Processor

### Load Batch Editor Preset

Load a batch processor preset.

Parameters:

| Name     | Description       |
|----------|-------------------|
| Preset   | Preset name or file path (.json) |

### Save Batch Editor Preset

Save the current batch processor settings.

---

## UI & Navigation

### Select Next File

Activate the next file in the workspace.

### Select Previous File

Activate the previous file in the workspace.

### Select Next Region

Move selection to the next region.

### Select Previous Region

Move selection to the previous region.

### Zoom All

Fit the entire file in view.

### Zoom Region

Zoom to the current region.

### Zoom Selection

Zoom to the current selection.

### Zoom

Zoom the view to the selected destination (auto, file, all regions, or selection).

Parameters:

| Name        | Description                                                        |
|-------------|--------------------------------------------------------------------|
| Destination | Destination (Auto/File/AllRegions/Selection)                       |

### Center to Selected Region

Pan view to center on the selected region.

### Toggle Waveform Mode

Switch the waveform view between line and bar display modes.


---

## Selection


### Set Selection to Playback Position

Mark the current playback position as the selection start. If a selection start is already marked, it sets the selection end instead.

### Clear Selection

Deselect everything.

### Extend Selection to Region

Expand selection to the next region boundary.

### Extend Selection to Transient

Expand selection to the next transient.

---

## Workspace

### Save Workspace

Save the current workspace layout and state as a JSON file (opens a save dialog).

### Open Workspace

Load a saved workspace from a JSON file (opens a file dialog).

### Export Theme

Export the current UI theme as a JSON file to the themes folder (opens a save dialog).

---

## Lua Scripting


### Run Lua Script

Execute a Lua script file. See [Lua Scripting / Editor](tools/luaeditor.md) for scripting details.

Parameters:

| Name     | Description          |
|----------|----------------------|
| Script   | Script file path     |

### Run Lua Editor Script

Run the script in the Lua editor panel.

---

## Tools & Windows


### Open Action Palette

Open the Action Palette modal.

### Open Audio Recorder

Open the audio recorder modal.

### Open Lua Editor

Open the Lua scripting editor.

### Open Sample Chain

Open the Sample Chain tool modal.

### Open Batch Editor

Open the Batch Editor tool modal.

### Open Export Settings

Open the export settings dialog.

### Open Keyboard Shortcuts

Open the keyboard shortcuts configuration.

### Open Settings

Open the application settings.


---
