# Navigator for Objects

Guide a connected FK bone chain with a few controls. **Classic** uses Middle and End controls and supports hooh's Dick Navigator. **Path** lets a tail, tentacle, cable, or another flexible object follow a curved route as you move it forwards and backwards.

Open **Toolkit > Transform > Navigator for objects**.

[Pandarinka Toolkit on Patreon](https://www.patreon.com/Pandarinka/posts/pandarinka-and-154581882)

## Classic mode

<div class="video-preview" style="margin-left: auto; margin-right: auto;">
  <video controls playsinline preload="metadata" poster="assets/images/navigator-for-objects.jpg" width="1920" height="1080" style="display: block; width: 100%; max-width: 100%; height: auto;" aria-label="Navigator for Objects video guide">
    <source src="assets/videos/navigator-for-objects.mp4?v=original-60fps" type="video/mp4">
    Your browser does not support embedded video. <a href="assets/videos/navigator-for-objects.mp4?v=original-60fps">Open the video</a>.
  </video>
</div>

Classic requires `HS2_Hooah.dll`, usually included in the game bundle.

### Set up Classic

1. Select the object and choose **Classic** under **New chain**.
2. Select its first FK bone and click **Set up** next to **Start**.
3. Select its last FK bone and click **Set up** next to **End**.
4. Click **Connect Navigator**.

The bones between Start and End form one chain, with up to 128 bones. If you already have an [IK for Objects](ik-for-objects.md) chain, enable **Use a chain from IK for Objects (optional)** and select it instead.

Turn on **Enable Navigator** to use the chain.

### Middle and End controls

Move **Middle** to adjust the bend and **End** to position the tip. **Select Middle** and **Select End** select these controls from the menu. **Reset length** restores the default chain length.

To use an existing **Dick Navigator** item, click **Use existing hooh Navigator** and select it from the list. **Use built-in points** switches back to Middle and End.

## Path

<div class="video-preview" style="margin-left: auto; margin-right: auto;">
  <video controls playsinline preload="metadata" poster="assets/images/navigator-path.jpg" width="1920" height="1080" style="display: block; width: 100%; max-width: 100%; height: auto;" aria-label="Navigator Path video guide">
    <source src="assets/videos/navigator-path.mp4" type="video/mp4">
    Your browser does not support embedded video. <a href="assets/videos/navigator-path.mp4">Open the video</a>.
  </video>
</div>

### Set up Path

1. Select the object and choose **Path** under **New chain**.
2. Select its first FK bone and click **Set up** next to **Start**.
3. Select its last FK bone and click **Set up** next to **End**.
4. Click **Connect Navigator**.

The bones between Start and End form one chain, with up to 128 bones. If you already have an [IK for Objects](ik-for-objects.md) chain, enable **Use a chain from IK for Objects (optional)** and select it instead.

On an existing chain, enable **Follow a curved path** to switch to Path mode. Turn on **Enable Navigator** to make the chain follow the route.

### Shape the route

Path creates a separate **Navigator Path** folder in the Studio tree. The purple line shows the entire route, and the colored controls shape it.

| Point | What it controls |
| --- | --- |
| **Entry** (blue) | Where the chain enters the path. Rotate it to set the approach direction. |
| **Bend** (green) | Move it to change where the route bends. Rotate it to change the curve's direction through that point. |
| **End** (red) | Where the route ends. Rotate it to set the direction the chain continues in beyond End. |

Click a point's name in the panel to select it. **Add bend** inserts a point after that row, and **Remove** deletes an intermediate point. A path can have up to 32 points, including Entry and End. Use **Select path folder** to move, rotate, or parent the whole route in Studio.

### Move the chain along the path

Move the **source object** toward Entry along its approach direction. The first bone stays attached to the object, and the rest of the chain feeds along the route. Move the object back to retract the chain. Bend and End shape the part of the route the chain reaches. To see their effect, advance the chain into that part of the path.

**Length** scales the chain. At **1x**, segments keep their original lengths. Use more bones if long segments skip over a tight bend. Clear **Show guide points** to hide the controls and preview while Navigator keeps running.

### Position the tip with Progress

Enable **Control with Progress** to place the tip directly along the path. At **0%** the tip is at Entry, at **50%** it is halfway along the route, and at **100%** it is at End. The slider also lets you place the tip before Entry or beyond End.

Select the **Navigator Path** folder to keyframe **Navigator Path progress**, **Navigator Path control with Progress**, and **Navigator Path enabled** in Timeline. To animate a point, select it and use the selected GuideObject position and rotation tracks. You can also use points as Node Constraints targets.

### Saving and editing

Chain settings, path points, and Progress are saved with the scene, including when Navigator is disabled. Moving points, adding or removing bends, and changing settings support **undo/redo**. Include the separate path folder when saving or exporting the setup. Removing a chain leaves its folder in the tree so it can be removed separately.

If the path folder was deleted, select the source object and click **Connect Navigator** with the same Start/End bones to restore the connection. **Create new path** on the existing chain also creates a replacement folder. Repeated Connect on an intact chain keeps its edited route and control points.

Navigator takes control of its assigned bones while enabled. Disable **Enable Navigator** or use **Remove chain** to return control to [IK for Objects](ik-for-objects.md); other chains keep working.
