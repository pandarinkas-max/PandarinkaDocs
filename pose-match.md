# Pose Match

<div class="video-preview">
  <iframe
    src="https://www.youtube-nocookie.com/embed/_Vw4AJ6jK7E"
    title="Pose Match video"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
    allowfullscreen>
  </iframe>
</div>

[**Pose Match**](https://www.patreon.com/posts/posematch-and-154581882?utm_medium=clipboard_copy&utm_source=copyLink&utm_campaign=postshare_creator&utm_content=join_link) takes a pose from a reference image and transfers it into **NeoStudioV2**.

Pose Match is now part of **Pandarinka Toolkit**.

The workflow is:

1. Load a reference image in **PoseMatch Program**.
2. Let the program detect the body pose.
3. Adjust the preview if needed.
4. Export a draft.
5. Apply that draft to a selected character in Studio through **Pandarinka Toolkit**.

## Install

1. If you used the old standalone **PoseMatch** Studio plugin, delete it from `BepInEx\Plugins`.
2. Put `PandarinkaToolkit.dll` into `BepInEx\Plugins`.
3. Put **PoseMatch Program** anywhere on your PC.
4. Keep the PoseMatch Program folders next to the `.exe`.

## Quick Start

1. Start `PoseMatch Program.exe`.
2. In **Settings**, choose your exact `BepInEx\Plugins` folder.
3. Load a reference image.
4. Click **Estimate Pose**.
5. Adjust the preview if needed.
6. Click **Export Draft**.
7. In Studio, select a character.
8. Open **Pandarinka Toolkit**.
9. Go to **Pose Match**.
10. Click **Refresh**.
11. Select the draft.
12. Click **Apply Pose**.

## Toolkit Buttons

**Refresh** reloads the list of available pose drafts from the PoseMatch drafts folder.

**Apply Pose** applies the selected draft to the selected Studio character.

**FK** switches the selected character to FK mode.

**IK** switches the selected character to IK mode.

**Mirror Pose** mirrors the current pose of the selected character.

## PoseMatch Program 2.0.0

This version includes:

- Jeff v2 3D preview with movable bones.
- FK / IK export modes.
- **Flip Torso** fixes many poses where the Studio result does not match the Jeff preview.
- `Ctrl + Z` and `Ctrl + Shift + Z`.
- Solve, preview, and stability fixes.
- Japanese language support.

## Reference Quality

Best results usually come from clear full-body references.

Extreme profile poses, heavy occlusion, strong foreshortening, deep backbends, or complex hand-to-foot contact may still need manual correction.

Use drafts in the plugin with the standard T-pose.

If the pose looks correct on Jeff but comes out wrong in Studio, use **Flip Torso** in PoseMatch Program and export the draft again.

## Notes

- Pose detection and pose transfer work locally on your PC.
- No internet connection is required.
- Supported OS: **Windows 10/11 64-bit**.
- Neck, feet, wrists, and fingers are planned for future support.

## Credits

PoseMatch uses RTMPose models from [OpenMMLab MMPose](https://github.com/open-mmlab/mmpose), licensed under Apache License 2.0.

Jeff model: [Mannequin on Sketchfab](https://sketchfab.com/3d-models/mannequin-d2a062e37cd042599f58b2c3d2ebd4b3).
