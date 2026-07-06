# Toolkit Options

<div class="video-preview">
  <iframe
    src="https://www.youtube-nocookie.com/embed/_Vw4AJ6jK7E"
    title="Toolkit Options video"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
    allowfullscreen>
  </iframe>
</div>

**Options** is the built-in settings section inside **Pandarinka Toolkit**.

Open it with the gear button in the top-left corner of the Toolkit window.

## What You Can Change

- Hotkeys.
- Window size.
- Window position.
- Window opacity.
- Soft Body selection opacity.
- Performance Monitor visibility.
- Language: English, Japanese, or Chinese.

Window size and position are saved automatically.

## Default Shortcuts

```text
Shift + K: Toolkit window
Shift + P: Pose Match
Keypad1: Pose Match IK
Keypad3: Pose Match FK
U: Drop to Surface
V: Soft Body selection visibility
B: Soft Body paint selection
N: Soft Body erase mode
O: Jiggle contact areas
Snow Field Footprint: set it here before placing footprints
Performance Monitor: not assigned by default
```

You can change these shortcuts in **Options**. Press **Set** near the shortcut you want to change, then press the new key combination. Use **Default** to restore one shortcut, or **Off** to disable it.

## Performance

<div class="guide-image">
  <img src="assets/images/performance-monitor.png" alt="Performance Monitor window">
</div>

The **Performance Monitor** is a small separate window for checking how much time Toolkit features spend each frame.

It shows **Jiggle Dynamics**, **Soft Body**, FPS, and timing information. Recent versions show more accurate FPS and timing numbers, so it is easier to see what is actually adding cost.

**Performance Mode** reduces Soft Body overlay detail and reuses static painted shapes when possible. It is enabled by default, and it is always better to keep it enabled.

## Toolbar Icons

Pandarinka Toolkit adds a Toolkit icon to the Studio toolbar.

It also adds a Pose Match icon that opens the Toolkit directly on the **Pose Match** page.

## Tooltips

Tooltips are available throughout the Toolkit window.

Hover over a setting to see a short explanation of what it does. This is useful in sections with many sliders, such as **Environment**, **Soft Body**, and **Jiggle Dynamics**.
