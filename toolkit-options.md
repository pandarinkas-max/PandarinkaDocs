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

[Pandarinka Toolkit on Patreon](https://www.patreon.com/Pandarinka/posts/pandarinka-and-154581882)

## What You Can Change

- Hotkeys.
- Window size.
- Window position.
- Window opacity.
- Soft Body selection opacity.
- Performance Monitor visibility.
- Language: English, Japanese, or Chinese.

Window size and position are saved automatically.

## Exclusive Fullscreen

In **Pandarinka Toolkit** and **Toolkit Lite**, open the gear in the top-left corner and enable **Exclusive fullscreen**. By default, Studio uses the desktop resolution and refresh rate of the monitor its window is on. If you use several monitors, move Studio to the one you want before enabling the setting.

Exclusive fullscreen is off by default. Studio applies it when its window gains focus and remembers it for the next launch. The status line shows the active resolution and refresh rate. Clear the checkbox to restore your previous display mode. If the status says exclusive fullscreen is inactive while the checkbox is ticked, turn it off and back on. If you use Configuration Manager, press **F1**, open the entry for your edition of Toolkit, and select **Display**.

**FPS gains vary by scene.** In one test, switching to exclusive fullscreen raised the frame rate from **60 to 120 FPS**. A heavier scene gained **about 10 FPS**. To check the difference in your own scene, compare the same camera view with the setting off and on, keeping Studio in focus for both readings.

### Studio resolution

To run Studio at a different resolution, enter the width and height under **Studio resolution** and press **Enter**. For example, on a 3840×2400 desktop you can run Studio at 2560×1600 if your monitor supports it. This keeps the same 16:10 proportions and gives Studio fewer pixels to render. Your Windows desktop setting stays at 3840×2400. To use the desktop resolution again, clear both fields and press **Enter**.

If Studio needs to enable a display format such as 16:10 or ultrawide for the first time, Toolkit prepares it automatically and shows a restart message. **Restart Studio once when prompted.** After that, you can switch between supported resolutions of that format while Studio is running.

### Keep 16:9 (black bars)

**Keep 16:9 (black bars)** is on by default in exclusive fullscreen. It centers the scene without stretching it. On a 16:10 display the bars appear above and below the scene. On an ultrawide display they appear on the left and right. Studio’s menus stay inside the frame. Clear the checkbox to use the entire display area.

**F11 renders** use the resolution set in Screenshot Manager. For example, a 3840×2160 render uses the full 4K frame even when Studio shows black bars on your monitor. The bars return to the Studio view after capture.

## Default Shortcuts

```text
T: Toolkit window
Shift + P: Pose Match
Keypad1: Pose Match IK
Keypad3: Pose Match FK
U: Drop to Surface
V: Soft Body selection visibility
V: RigFlow Recalibrate IKs
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
