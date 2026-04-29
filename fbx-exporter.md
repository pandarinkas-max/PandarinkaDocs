# Studio FBX Exporter

<div class="video-preview">
  <iframe
    src="https://www.youtube-nocookie.com/embed/S1LyGUQBos4"
    title="Studio FBX Exporter video"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
    allowfullscreen>
  </iframe>
</div>

[**Studio FBX Exporter**](https://www.patreon.com/posts/studio-fbx-1-0-0-154928946) adds a simple FBX export button to the Studio toolbar.

Select one Studio object or character, click the button, and the plugin exports the selected hierarchy as an `.fbx` file with a texture folder next to it.

Use it when you want to move assembled Studio props into Blender, Maya, Unity, or another 3D workflow. It is also useful for turning item maps into normal map assets, exporting [Quick Pick](https://www.patreon.com/collection/2136425?view=expanded) cached map objects, preparing kitbash pieces, or building a zipmod from something already assembled in Studio.

## Quick Start

1. Select exactly one object or character in Studio.
2. Click the **FBX** button on the left toolbar.
3. Wait for the export notification.
4. Open the export folder:

```text
BepInEx\plugins\FBX Exporter\
```

Import the `.fbx` together with its `.fbm` folder. The textures are stored as external files, not embedded inside one single FBX file.

## What It Exports

- Standard Studio objects.
- [Quick Pick](https://www.patreon.com/collection/2136425?view=expanded) extracted or cached map objects that behave like normal Studio objects.
- Whole selected hierarchies made from many separate pieces.
- MeshRenderers and SkinnedMeshRenderers.
- Materials, UVs, texture tiling/offset, scale, and transforms.
- Textures into a `.fbm` folder next to the `.fbx`.
- Characters in their current posed state, but character export is rough and not the main purpose of the plugin.

Red/problematic [Quick Pick](https://www.patreon.com/collection/2136425?view=expanded) objects are not supported reliably.

## Output Files

The exported FBX is named from the selected object plus a timestamp.

Example:

```text
Chair_Set_2026-04-29_15-30-10.fbx
Chair_Set_2026-04-29_15-30-10.fbm\
```

The default export folder is:

```text
BepInEx\plugins\FBX Exporter\
```

You can set a custom export directory in the plugin settings.

## Notes

- This is a direct Studio exporter, not a raw asset extractor. It exports what is currently loaded and visible in Studio.
- Most normal objects should work well in Blender and Unity.
- Older Blender versions may not import this export correctly because the plugin writes ASCII FBX. Blender `5.1.1` was tested and works correctly.
- Some special shaders, plugin-specific material effects, or unusual renderer setups may not look exactly the same after export.
- If the result is missing textures, keep the `.fbx` and its `.fbm` folder together when importing.
- [BepInEx 5](https://github.com/BepInEx/BepInEx/releases) and [HS2API](https://gofile.io/d/VYsLtI) `1.43+` are required.
- Plugin post: [Studio FBX Exporter](https://www.patreon.com/posts/studio-fbx-154930351).

## Common Problems

**Nothing exports.**

Select exactly one Studio item or character. The selected tree node must be backed by a real Studio object and it must contain renderers.

**The FBX imports without textures.**

Import or move the `.fbx` together with the `.fbm` folder created next to it.

**A Quick Pick map object does not export correctly.**

Use extracted or cached [Quick Pick](https://www.patreon.com/collection/2136425?view=expanded) map objects that behave like normal Studio items. Red/problematic Quick Pick objects are not reliable export targets.

**Blender does not import the FBX.**

Older Blender versions can have trouble with ASCII FBX files. Try a newer Blender version. Blender `5.1.1` was tested and imports the exported FBX correctly.

**A character export looks bad.**

Character export is currently secondary. It can export the current posed state, but it is not as clean as normal object export.
