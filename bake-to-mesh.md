# Bake to Mesh

<div class="video-preview">
  <iframe
    src="https://www.youtube-nocookie.com/embed/RVFaDaJvUJE"
    title="Bake to Mesh video"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
    allowfullscreen>
  </iframe>
</div>

**Bake to Mesh** converts a selected Studio folder into a single baked object.

Use it when you have many separate objects and want to combine them into one baked object. This can be a Scatter Objects result, duplicated props, decorations, or any heavy object group.

[Pandarinka Toolkit on Patreon](https://www.patreon.com/Pandarinka/posts/pandarinka-and-154581882)

## Quick Start

1. Create a scatter result or select any folder with objects.
2. Open **Pandarinka Toolkit**.
3. Go to **Transform**.
4. Open **Bake to Mesh**.
5. Select the folder you want to bake.
6. Click **Bake Selected Folder**.

The baked object appears in the Workspace as a normal Studio item. For large folders, wait for the bake to finish before saving.

## Delete Source Clones

Enable **Delete source clones after bake** to remove the source folder and its contents once the bake is ready. Leave it off to keep editing the original objects or to bake the folder again later.

## Saving and sharing a scene

Bake to Mesh rebuilds the combined object from the original game and mod assets when the scene loads. The scene stores where each mesh belongs and which materials it uses. Textures and geometry that differ from the installed assets are saved in the scene itself. Large custom textures can therefore account for most of the file size.

When sharing a scene, include a list of the zipmods used by the baked objects. The recipient needs those mods installed even if you deleted the source folder from the Workspace. If Toolkit reports a missing asset, reinstall the matching mod and reopen the scene.

Older scenes with embedded bake data still load. To use asset references for an old bake, select its original source folder and bake it again. If you deleted that folder, use a copy of the scene that still contains it.

## What To Expect

Combining many props can improve FPS by reducing the number of separate objects Studio manages. Transparent foliage, shadows, and materials still contribute to rendering cost. To compare FPS, use the same camera angle and show only the original folder or only the baked object.

## Notes

- Materials can still be edited.
- Light and shadows behave like normal Studio objects.
- [Scene Browser (Separate Import)](scene-browser-pro.md) is supported.
- [Recycle Bin (Stash)](recycle-bin.md) is not supported yet.
