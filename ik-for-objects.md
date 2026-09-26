# IK for Objects

<div class="video-preview" style="margin-left: auto; margin-right: auto;">
  <video controls playsinline preload="metadata" width="820" height="461" style="display: block; width: 100%; max-width: 100%; height: auto;" aria-label="IK for Objects video guide">
    <source src="assets/videos/ik-for-objects.mp4" type="video/mp4">
    Your browser does not support embedded video. <a href="assets/videos/ik-for-objects.mp4">Open the video</a>.
  </video>
</div>

**IK for Objects** adds IK controls to NPCs with FK bones.

Move a hand or foot target, and the connected limb bends to follow it. It also supports the spine, shoulders, hips, and manually assigned tails or tentacles. Each part has its own block of settings.

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

Manually assigned shoulders and hips work with their arm or leg chain, including on an incomplete rig. Assign that chain's bones first; a shoulder or hip slot alone stays pending. Moving the joint affects the connected limb, and pulling a hand or foot beyond its reach involves the shared ancestors. Replacing a clavicle with a twist/helper bone keeps the connection to the same limb.

If IK does not activate, check the message at the bottom of the section. The slots must contain different, connected bones in parent-to-child order. A bone already used by another chain must be freed by removing that chain first. Incomplete or invalid assignments keep the previous working chain in place.

## Tail / Tentacles

<div class="video-preview" style="margin-left: auto; margin-right: auto;">
  <video controls playsinline preload="metadata" width="820" height="461" style="display: block; width: 100%; max-width: 100%; height: auto;" aria-label="Tail and tentacle IK video guide">
    <source src="assets/videos/ik-tail-tentacles.mp4" type="video/mp4">
    Your browser does not support embedded video. <a href="assets/videos/ik-tail-tentacles.mp4">Open the video</a>.
  </video>
</div>

1. Click **Add tail / tentacle**.
2. Select the first FK bone and click **Set up** next to **Start**.
3. Select the last FK bone and click **Set up** next to **End**.

All FK bones between them become one IK chain. Move and rotate its points to pose the tail. Bone names do not matter.

By default, each FK bone gets an IK point. For fewer points, turn **Auto** off, choose **IK points**, and click **Apply chain settings**. The base and tip are always included.

- **Joint Follow for tails** makes other points follow your movement. It is off by default. **2 neighboring points only** limits it to the points on either side; turn that limit off to move the rest of the tail along with them.
- **Refer to animation** restores just this tail to the current animation pose.
- **Remove chain** returns the tail to FK.

Both buttons support **undo/redo**. Body and tail settings can be saved together in **Presets** below.

## Presets

Open **Presets** near the top of **IK for objects**. Enter a name and click **Create / Update** to save the object's complete IK setup: body chains, shoulders and hips, tails, manual bone assignments, point counts, enabled parts, and both tail Joint Follow switches.

Select another object, choose the preset and click **Apply**. Its matching bones receive the saved IK setup in their current pose. The preset stores settings, not a pose; it requires compatible bone names and hierarchy. If a saved bone is missing, the existing setup is kept.

Use **Rename**, **Delete**, or **Open Folder** to manage and share the JSON files. They are stored in `BepInEx/plugins/PandarinkaToolkit/Presets/object_ik`. Deleted presets are kept in its `_Deleted` subfolder.

## Compatibility And Saving

The controls support **Move Controller, Node Constraints, Timeline, and pose undo/redo**. IK settings and unfinished manual assignments are saved with the scene. Reassigning bones keeps the existing control references used by other plugins.

[**Joint Follow**](joint-follow.md) is also supported. Enable it to help elbow and knee bend points follow your adjustments when moving hands and feet.

[**Refer to animation (for objects)**](refer-to-animation.md) updates both FK and IK to match the current animation pose.

Studio's axis visibility toggle also hides the IK points without changing the pose.

## Performance

In my tests, this control scheme delivered even higher FPS than native FK. Results depend on the rig and scene.

## Notes

**Manual setup can also make IK work with animals and other rigged creatures or objects.** Assign the appropriate FK bones to each chain; standard bone names are not required. The rig must expose suitable, connected FK bones.

Automatic setup and the full-body solver are designed around humanoid rigs. Manual shoulder/hip coupling also works when only part of the rig is assigned. This feature uses the object's existing skeleton; it does not create a rig for an unrigged object.
