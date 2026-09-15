# IK for Objects

<div class="video-preview">
  <video controls playsinline preload="metadata" width="820" height="461" style="display: block; width: 100%; max-width: 100%; height: auto;" aria-label="IK for Objects video guide">
    <source src="assets/videos/ik-for-objects.mp4" type="video/mp4">
    Your browser does not support embedded video. <a href="assets/videos/ik-for-objects.mp4">Open the video</a>.
  </video>
</div>

**IK for Objects** adds IK controls to NPCs with FK bones.

Move a hand or foot target, and the connected limb follows. It also supports the spine, shoulders, and hips.

## Getting Started

Open **Toolkit > Transform > IK for objects**:

1. Select an object and click **Auto setup**.
2. Click an IK point on the model.
3. Drag it to move, or use the rotation rings to adjust its orientation.

**Bend points** control where elbows and knees point.

If automatic setup misses a supported bone, select its FK point and click **Set up** to assign it to the corresponding IK slot. Use **Replace** to change an assignment and the checkboxes to enable or disable controls. Empty shoulder slots let you assign shoulders manually.

The controls follow a fixed human bone structure, with connected chains for arms, legs, and the other supported body parts. You cannot add extra IK points or freely assign any bone to any control.

Bones controlled by IK have their FK points hidden. Other bones - including fingers, neck, ears, and tail - keep their FK controls.

## Compatibility And Saving

The controls support **Move Controller, Node Constraints, Timeline, and undo/redo**. IK settings are saved with the scene.

[**Joint Follow**](joint-follow.md) is also supported. Enable it to help elbow and knee bend points follow your adjustments when moving hands and feet.

[**Refer to animation (for objects)**](refer-to-animation.md) updates both FK and IK to match the current animation pose.

Studio's axis visibility toggle also hides the IK points without changing the pose.

## Performance

In my tests, this control scheme delivered even higher FPS than native FK, so performance should not be a concern.

## Notes

IK for Objects is designed for human anatomy. Other rigged creatures, such as animals and monster girls, are not supported yet. If you are interested in support for them, we can discuss it separately.
