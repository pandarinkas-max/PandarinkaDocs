# Pandarinka Toolkit

[**Pandarinka Toolkit**](pandarinka-toolkit.md) is the main Studio plugin for Pandarinka tools.

It includes **Soft Body**, **Jiggle Dynamics**, **Pose Match**, **Characters**, **Transform**, **Environment**, **Clothing Lab**, and **Options** in one window.

The Toolkit package also includes **PoseMatch Program**, the desktop program used to create pose drafts from reference images.

Pose Match is built into Pandarinka Toolkit now. Do not keep the old standalone `PoseMatch.dll` together with `PandarinkaToolkit.dll`.

Install:

1. Put `PandarinkaToolkit.dll` into `BepInEx\Plugins`.
2. Put **PoseMatch Program** anywhere on your PC.
3. Keep the whole PoseMatch Program folder together.

Default shortcuts:

```text
Shift + K: Toolkit window
V: Show / hide Soft Body painted selection
B: Paint Soft Body selection in the viewport
N: Soft Body erase mode
Shift + P: Pose Match
Keypad1: Pose Match IK
Keypad3: Pose Match FK
U: Drop to Surface
Snow Field Footprint: set in Options
```

## Latest Update Highlights

- **Clothing Lab** was added for using female clothing on male characters, with Surface Fit, Top Surface Mask Editor, and Grid Warp controls.
- **Environment** was added as a large new Toolkit section for snow and rain scenes.
- **Soft Body** can now edit simple object meshes, including snow fields.
- **Soft Body** now has manual gizmo mode, Mirror Brush, more pages, mouse-wheel brush radius control, and clearer layer highlighting.
- **Jiggle Dynamics** can use the same character as both source and receiver, and Character Sources are much faster now.
- **Uncensor Search** now shows the zipmod name, the current uncensor, and can open the related source folder.
- **Transform** now includes folder scale support.
- **Performance Monitor** now shows more accurate FPS and timing information.
- Unnecessary log spam was reduced.
- Tooltips were added throughout the plugin. Hover over a setting to see a quick explanation.

Notes:

- Pandarinka Toolkit is made for **StudioNEOV2**.
- PoseMatch Program and the Toolkit plugin work locally on your PC.
- Pandarinka Toolkit is translated into **Japanese** and **Chinese**.
- Requires **BepInEx 5.4.23**. Slightly earlier versions may also work, but I have not tested them.
- Requires **HS2API 1.43+**.
- Supported OS: **Windows 10/11 64-bit**.

<div class="guide-warning-large">
  <strong>Known Incompatibility: ObjectMap Plugin</strong>
  <p><b>ObjectMap plugin</b> can conflict with <b>Pandarinka Toolkit</b>. This is especially visible on the <b>Hooh School</b> map. I do not plan to fix this.</p>
</div>
