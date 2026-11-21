# Voice Practice

A simple, ad-free **vocal tuner** and **metronome** for singers, built for daily practice on a phone or tablet. It runs in the browser, works offline once installed, and needs no account.

It is made of two separate screens, switched with the toggle at the bottom:

- **Tuner:** shows the notes you sing as a scrolling line over a piano-style note grid.
- **Metronome:** a clean metronome with a dial, per-beat emphasis, subdivisions and saved settings.

---

## Getting started

1. Open the app link in **Chrome** (recommended).
2. Choose **Add to Home screen** from Chrome's menu to install it like an app.
3. On the Tuner screen, press **▶** and **allow microphone access** when asked.

> The microphone is only used live, on your device. Nothing is recorded, uploaded or shared.

---

## Tuner

### What you see

| Area | What it shows |
|---|---|
| **Top bar** | A deviation meter: how far the note you are singing is from the nearest note (green when close). Below it: the **cents** off, the **note name**, and the **frequency in Hz**. |
| **Loudness meter** | A mirrored waveform of how loud you are singing, with a dB value. The dB figure is relative to your device's microphone, not a real room-loudness measurement. |
| **Pitch monitor** | Your voice drawn as a line over time. Piano keys sit on the left, note names next to them, and the grid lines run across. |

### The pitch line colours

- **Green:** very close to the note
- **Yellow:** slightly off
- **Orange:** noticeably off

In Arab mode the thresholds are tighter, because the targets are closer together.

### Starting, freezing and reviewing

- **▶ / ❚❚** starts and freezes listening.
- The line stops scrolling about **one second after you stop singing**, so you can look back at what you sang.
- When frozen (or after you have stopped singing for a moment), **drag with your finger** to move back through the last ~30 seconds of singing. Drag sideways to go back in time, and up or down to change the pitch range.
- As soon as you sing again, the view returns to live.

### Buttons on the right

| Button | What it does |
|---|---|
| **▶ / ❚❚** | Start or freeze. |
| **C / Do** | Shows the current note-naming style: letters (C, D, E…) or solfège (do, re, mi…). Tap to switch. |
| **West / Arab** | Switches between Western (semitone) and Arab (quarter-tone) mode. |
| **Drone** | Plays a sustained tone to sing against: off → **Root** → **Root + fifth** (tanpura-style). It follows the selected root note. Use headphones, otherwise the microphone will hear the drone. |

### Scales and root note

Two dropdowns at the top right of the pitch monitor choose a **root note** and a **scale** (Major, Minor, the modes, pentatonics, Chromatic, and your own).

- Notes **in the scale** get bright, labelled lines. Notes outside it are grey.
- The **root note** is shown in bold with a thicker line.
- Flats or sharps in the labels follow the key.

### Arab mode and quarter tones

In Arab mode a dashed line appears **between every semitone** for the quarter tones. Quarter tones are written with the standard symbols:

- **half-flat** (a flat sign with a slash)
- **half-sharp** (a sharp sign with a single vertical stroke)

The note readout snaps to the nearest quarter tone, and the deviation bar covers ±25 cents.

### Custom scales

Choose **＋ New custom scale…** at the bottom of the scale dropdown.

1. Type a name (for example, a maqam).
2. Tap the notes that belong to your scale. The 24 buttons cover one octave in quarter tones and are named after the notes of the root you selected. Where one pitch has two names, both are shown with a slash, for example `C♯ / D♭`.
3. Tap **Save**. The scale appears in the dropdown and works with any root note.

To change or delete a custom scale, select it and tap the **✎** button next to the dropdown.

### Tap a note to hear it

Tap quickly anywhere on the pitch grid to hear the nearest note. The line flashes briefly. In Arab mode it snaps to quarter tones.

---

## Metronome

### The dial and tempo

- **Turn the dial** with your finger to change the tempo. The range is **20 to 400 BPM**.
- The two thin **arrows** above the dial change the tempo by exactly **1 BPM**: the right arrow speeds up and the left arrow slows down. Hold to keep stepping.
- The tempo name (Andante, Allegro…) updates automatically.

### Beat circles

Each circle is one beat of the bar. The circles flash in time with the click.

**Tap a circle to change its emphasis.** Each beat cycles through three states:

| State | Look | Sound |
|---|---|---|
| **Emphasised beat** | Teal ring | Higher click |
| **Normal beat** | Plain circle | Normal click |
| **Silent beat** | Dashed, dimmed | No click |

The first beat is emphasised by default. Change it to a normal beat if you don't want an accent on beat one.

### The five buttons

| Button | What it does |
|---|---|
| **Time signature** | Cycles through 1/4, 2/4, 3/4, 4/4, 5/4 and 6/8. |
| **Subdivision** | Opens a sheet to divide each beat into **1 to 7** clicks: eighths, triplets, sixteenths, quintuplets, sextuplets, septuplets. The tempo stays the same, so each beat is simply divided. Confirm with ✓. |
| **Tap** | Tap in time to set the tempo. |
| **▶ / ❚❚** | Start or stop. |
| **Save** | Save and load your settings (see below). |

Each circle gets a thin outline split into as many sections as your subdivision. The sections light up one after another in time, then it moves on to the next circle.

### Saving settings

Tap **Save** to store the current tempo, time signature, subdivision and beat emphasis under a name. Tap a saved entry to load it, or ✕ to delete it.

### Landscape mode

When the device is held sideways, the beat circles and buttons are stacked vertically on the left, and the tempo and dial are on the right.

---

## Your data and privacy

- Custom scales and saved metronome settings are stored **only in your browser, on your device**.
- They are not sent anywhere. Clearing Chrome's site data will erase them.
- The app asks the browser to keep this storage permanently, so it won't be cleared automatically when space is low.
- Audio from the microphone is processed live and is never stored.

---

## Tips

- **Use headphones** when running the drone or tapping notes to hear them, so the tuner doesn't pick up the speaker.
- Sing in a **quiet place** for the most stable pitch line.
- Keep the screen on while practising. The app asks the device to stay awake while it is running.
- On some Xiaomi devices, set the browser's battery option to **No restrictions** so audio isn't cut off in the background.

## Troubleshooting

| Problem | What to try |
|---|---|
| "Mic error" or no pitch line | Allow microphone access for the site in Chrome's settings, then reload and press ▶. |
| An old version still shows | Reload the page, or add `?v=2` to the end of the web address. If you installed it to the home screen, remove the icon and add it again. |
| The line looks jumpy | Move closer to the microphone and avoid background noise. |

---

## For developers

The whole app is a single file (`index.html`) with no build step and no dependencies, using the Web Audio API for pitch detection (YIN algorithm) and the metronome clock. To update it, replace the file in this repository. The page is served with GitHub Pages.
