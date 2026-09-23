# IK for Objects

<div class="video-preview" style="margin-left: auto; margin-right: auto;">
  <video controls playsinline preload="metadata" width="820" height="461" style="display: block; width: 100%; max-width: 100%; height: auto;" aria-label="IK for Objects video guide">
    <source src="assets/videos/ik-for-objects.mp4" type="video/mp4">
    Your browser does not support embedded video. <a href="assets/videos/ik-for-objects.mp4">Open the video</a>.
  </video>
</div>

**IK for Objects** adds IK controls to NPCs with FK bones.

Move a hand or foot target, and the connected limb bends to follow it. It also supports the spine, shoulders, and hips. Each part has its own block of settings.

## Getting Started

Open **Toolkit > Transform > IK for objects**:

1. Select an object and click **Auto setup**.
2. Click an IK point on the model.
3. Drag it to move, or use the rotation rings to adjust its orientation.

**Bend points** control where elbows and knees point.

Bones controlled by IK have their FK points hidden. Other bones, including fingers, neck, and ears, keep their FK controls.

## Manual Setup

<div class="video-preview" style="margin-left: auto; margin-right: auto;">
  <video controls playsinline preload="metadata" width="820" height="461" style="display: block; width: 100%; max-width: 100%; height: auto;" aria-label="IK for Objects manual setup video guide">
    <source src="assets/videos/ik-for-objects-manual-setup.mp4" type="video/mp4">
    Your browser does not support embedded video. <a href="assets/videos/ik-for-objects-manual-setup.mp4">Open the video</a>.
  </video>
</div>

If **Auto setup** cannot recognize the bone names, you can assign every joint manually. Open the part's block, select an FK point on the model, and click **Set up** beside its slot:

- **Arms:** upper arm → elbow → hand.
- **Legs:** thigh → knee → foot.
- **Spine:** assign the bones from the lower back toward the chest. Use **Add bone** or **Remove last bone** to match the number of joints.

Once all slots form a connected chain, IK activates automatically. A spine with four assigned bones gets **two controls: an end target and a bend point**, which drive the whole chain.

To change a bone, uncheck **IK** for that part to reveal its FK points, then select the new bone and click **Set up** beside the slot. **Shoulder** and **hip** blocks also have their own **Set up / Replace** buttons.

If IK does not activate, check the message at the bottom of the section. The slots must contain different, connected bones in parent-to-child order. A bone already used by another chain must be freed by removing that chain first. Incomplete or invalid assignments keep the previous working chain in place.

## Compatibility And Saving

The controls support **Move Controller, Node Constraints, Timeline, and pose undo/redo**. IK settings and unfinished manual assignments are saved with the scene. Reassigning bones keeps the existing control references used by other plugins.

[**Joint Follow**](joint-follow.md) is also supported. Enable it to help elbow and knee bend points follow your adjustments when moving hands and feet.

[**Refer to animation (for objects)**](refer-to-animation.md) updates both FK and IK to match the current animation pose.

Studio's axis visibility toggle also hides the IK points without changing the pose.

## Performance

In my tests, this control scheme delivered even higher FPS than native FK. Results depend on the rig and scene.

## Notes

**Manual setup can also make IK work with animals and other rigged creatures or objects.** Assign the appropriate FK bones to each chain; standard bone names are not required. The rig must expose suitable, connected FK bones.

Automatic setup and full-body coupling are designed around humanoid rigs. This feature uses the object's existing skeleton; it does not create a rig for an unrigged object.
