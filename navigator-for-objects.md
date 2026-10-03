# Navigator for Objects

<div class="video-preview" style="margin-left: auto; margin-right: auto;">
  <video controls playsinline preload="metadata" poster="assets/images/navigator-for-objects.jpg" width="1920" height="1080" style="display: block; width: 100%; max-width: 100%; height: auto;" aria-label="Navigator for Objects video guide">
    <source src="assets/videos/navigator-for-objects.mp4?v=original-60fps" type="video/mp4">
    Your browser does not support embedded video. <a href="assets/videos/navigator-for-objects.mp4?v=original-60fps">Open the video</a>.
  </video>
</div>

Use **Navigator for objects** with other objects that have a connected FK bone chain. Move two control points to bend the chain, or connect the **Dick Navigator** item from Hooh.

The plugin works with all penis models and many other objects.

Open **Transform > Navigator for objects**. It requires `HS2_Hooah.dll`, which is most likely already included in your standard game bundle.

## Setup

1. Select your object. Select its first FK bone and click **Set up** next to **Start**.
2. Select the last FK bone and click **Set up** next to **End**.
3. Click **Connect Navigator**.

The bones between Start and End become one chain. Move **Middle** to adjust the bend and **End** to position the tip. **Length** adjusts the chain's length; **Reset length** restores it.

Use **Select Middle** or **Select End** to select a control from the menu. **Show guide points** hides or shows them without disabling Navigator.

## Using Dick Navigator

Add the **Dick Navigator** item to the scene. In your chain's settings, click **Use existing hooh Navigator** and select it from the list. Its controls now drive your object.

**Use built-in points** switches back to Middle and End.

## With IK for Objects

If you've already set up a chain with [**IK for Objects**](ik-for-objects.md), enable **Use a chain from IK for Objects (optional)** and select that chain instead of assigning its bones again.

Navigator controls that chain while enabled. Disable **Enable Navigator** or use **Remove chain** to return control to IK. Other IK chains keep working.

The setup is saved with the scene, and setup changes and control movements support **undo/redo**.
