# Effects

---

Recorte features 25+ audio effects. These effects can be applied to the entire file, all regions, specific regions, or the waveform selection destructively (through the `Apply` actions) or non-destructively (through the [Effect Chain panel in the Editor](userinterface.md#effect-chain)).

---


## Effect Chains

The effect chains in Recorte let the user add effects to the active file non-destructively through a serial chain of effects. The chain is used when playing or creating files and regions (as new [files](files.md) in Recorte or exported audio files).

Effects can be added to the list through the (:phosphor-plus:) button. Reorder them by dragging and dropping on the effect title.  
Each effect in the list can also be collapsed (▸), disabled (:phosphor-check:) or removed (:phosphor-x:) using the buttons on the effect header.

Each [file](files.md) loaded in Recorte contains two effect chain types:

1. **Global**: A single global chain in the file that is applied to the file (including all regions).
2. **Region**: Individual effect chains that can be added to each region.

### Applying Effect Chains

Effect chains can also be applied (destructively) to an entire file, its regions, or a selection using the `Apply Effect Chains` [action](actions.md).

### Effect Chain Presets

Effect chains can be saved and loaded as presets from the Effect Chain sub-menu (:phosphor-list:) in the section header.

It is also possible to replace the default effects. Overwrite the `default.json` preset file or select the `Save as Default` option from the preset sub-menu.

Presets are stored as JSON files and can be used in any file.

### Managing Effect Chains

The Effect Chain sub-menu (:phosphor-list:) also contains options for copying, pasting and clearing the effect chains.

---

## Available Effects

### Channels

#### Mono to Stereo
Duplicates the mono channel to create a stereo signal.

#### Stereo to Mono
Converts stereo to mono using various modes (Mixed, Left, or Right) and an optional Dual Mono mode.

| Parameter | Description |
|---|---|
| Mode | Selection of downscale method (Mixed, Left, Right) |
| Dual Mono | Copies left to right and keeps both channels |

### Creative

#### Bit Crush
Reduces sample rate and bit depth.

| Parameter | Description |
|---|---|
| Sample Rate Reduction | Percentage (0–100%) |
| Bit Depth | Percentage (0–100%) |

#### Cluster
Creates randomized echoes/delays and mixes them back into the signal.

| Parameter | Description |
|---|---|
| Max Repeats | Number of echo repeats (2–50) |
| Max Delay | Maximum delay in ms (0–1000) |
| Mix | Wet/dry mix in % (0–100) |

#### Frequency Shifter
Shifts all frequency components by a fixed amount (changes pitch).

| Parameter | Description |
|---|---|
| Frequency | Shift amount in Hz (-1000–1000) |
| Mix | Dry/wet mix (0–100%) |

#### Granular
Applies a granular effect by scanning through the audio with a modulated window.

| Parameter | Description |
|---|---|
| Grain Size (ms) | Grain size in ms (1–128) |
| Frequency | Scan rate in Hz (1–100) |
| Factor | Playback speed factor (0.01–10, logarithmic) |
| Window Type | Window type (None, Hanning, Blackman, Tukey, Tukey Wide) |

#### Spectral Gate
Attenuates spectral bins below a threshold using FFT-based processing.

| Parameter | Description |
|---|---|
| Threshold | Fraction of frame peak (0–1) |
| Depth | Attenuation amount (0 = none, 1 = full mute) |
| Fft Size | FFT window size (512, 1024, 2048, 4096) |
| Sliding Window | Enable streaming mode |

#### Transient Shaper
Enhances or reduces transients (attack) and sustain (release).

| Parameter | Description |
|---|---|
| Attack | Transient control (-1–1) |
| Release | Sustain control (-1–1) |

### Edit

#### Pad
Adds silence to the beginning and/or end of the buffer.

| Parameter | Description                                        |
|-----------|----------------------------------------------------|
| Start     | Silence added at the beginning (ms, samples, or %) |
| End       | Silence added at the end (ms, samples, or %)       |

#### Repeat
Repeats the entire selection N times.

| Parameter    | Description                              |
|--------------|------------------------------------------|
| Repeats      | Number of repetitions                    |
| Ratchet Mode | Speeds up the audio by the repeat factor |

#### Reverse
Reverses the audio waveform.

| Parameter | Description         |
|-----------|---------------------|
| Reverse   | Reverses the buffer |

### EQ / Filter

#### Comb Filter
Creates resonant peaks or notches using a delay line (phaser / flanger effect).

| Parameter  | Description                                |
|------------|--------------------------------------------|
| Mode       | Feed Forward (notches) or Feedback (peaks) |
| Delay Time | Delay in ms (0.1–20)                       |
| Gain       | Feedback gain (-0.90–0.90)                 |
| Mix        | Dry/wet mix (0–100%)                       |

#### DC Filter
Removes DC offset using a high-pass filter.

| Parameter | Description |
|---|---|
| Frequency | Cutoff frequency in Hz |

#### DJ EQ
Three-band equalizer with low shelf, mid bell, and high shelf.

| Parameter | Description |
|---|---|
| Low Gain | Boost/cut in dB (-24 to 24) |
| Mid Gain | Boost/cut in dB (-24 to 24) |
| High Gain | Boost/cut in dB (-24 to 24) |
| Mode | EQ mode (Classic, Isolator) |

#### Tone EQ
Passive-tilt EQ that boosts/cuts bass and treble symmetrically around a center frequency.

| Parameter | Description |
|---|---|
| Tone | Tilt amount (-1.0 = bass boost, 1.0 = treble boost) |
| Slope | Slope in dB per octave (6, 12) |
| Center Frequency | Pivot frequency in Hz (200–2000) |
| Q Gain | Resonance control |

### Fade

#### Fade In
Gradually increases volume from silence at the start of the selection.

| Parameter | Description |
|---|---|
| Mode | Unit selector (ms, samples, or %) |
| Curve | Fade curve shape (-1.0–1.0) |
| Duration | Fade length |

#### Fade Out
Gradually decreases volume from silence at the end of the selection.

| Parameter | Description |
|---|---|
| Mode | Unit selector (ms, samples, or %) |
| Curve | Fade curve shape (-1.0–1.0) |
| Duration | Fade length |

### Gain

#### Compressor
Reduces the dynamic range of the audio signal.

| Parameter | Description |
|---|---|
| Ratio | Compression ratio (1–20x) |
| Makeup Gain | Output gain compensation (0–24 dB) |
| Attack | Attack time (1–100 ms) |
| Release | Release time (1–250 ms) |
| Threshold | Level at which compression engages (-60 to 0 dB) |

#### Drive
Adds saturation/distortion using a tanh curve for warm overdrive.

| Parameter | Description |
|---|---|
| Gain | Drive intensity (0–10x) |

#### Gain
Applies a linear gain multiplier to the audio signal.

| Parameter | Description |
|---|---|
| Gain | Multiplier (0–10x) |

#### Normalize
Scales the signal so its peak reaches a target maximum level.

| Parameter | Description |
|---|---|
| Ceiling | Target peak level in dB (-24 to 0) |

### Pitch / Speed

#### Pitch Shift
Changes pitch without affecting duration using FFT-based processing.

| Parameter | Description |
|---|---|
| Amount | Pitch shift in semitones (-64 to 64) |
| Window Size | FFT window size (10–100) |

#### Rate
Changes playback speed. Optionally preserves pitch with anti-aliasing resampling.

| Parameter | Description |
|---|---|
| Rate | Playback speed in % (6.25–1600) |
| Semitones | Pitch offset in semitones (-48 to 48) |
| Anti Aliasing | If true, uses sinc resampling to preserve pitch |

#### Stretch to BPM
Resamples the audio so it fits a target tempo over a given number of bars.

| Parameter | Description |
|---|---|
| BPM | Target tempo (20–300) |
| Bars | Number of bars to fill (1–32) |

#### Integer Speed Up
Speeds up playback by skipping samples (integer factor, pitch changes).

| Parameter | Description |
|---|---|
| Factor | Speed multiplier (1–10) |

#### Integer Stretch
Stretches audio by duplicating samples (integer factor, pitch changes).

| Parameter | Description |
|---|---|
| Factor | Stretch multiplier (1–10) |

#### Time Stretcher
Advanced grain-based time-stretching with formant preservation and stereo spread.

| Parameter | Description |
|---|---|
| Mode | BPM (`From BPM`, `To BPM`) or Ratio (`Multiplier`) |
| Multiplier | Time-stretch ratio (0.01–4x) |
| Grain Size | Grain size in ms (0.1–200) |
| Overlap | Grain overlap in % (0–100) |
| Window Type | Window function (Hanning, Hamming, Blackman, Bartlett, Welch, Rectangular) |
| Formant | If true, preserves vocal formants |
| Reverse | If true, reverses every 4th grain |
| Grain Spread | Stereo spread in ms (0–100) |
| Quality | Processing quality (Lofi, Standard, High) |

### Resample

#### Resample
Changes the sample rate using sinc interpolation (Blackman-Harris window).

| Parameter | Description |
|---|---|
| Sample Rate | Destination rate in Hz (100–192k) |
| Keep size | If true, resamples then stretches back to original length |
