# Quick Pick

<div class="video-preview">
  <iframe
    src="https://www.youtube-nocookie.com/embed/8fqsfr5DKgk"
    title="Quick Pick video"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
    allowfullscreen>
  </iframe>
</div>

**Quick Pick** lets you select Studio objects directly in the viewport instead of searching for them in the workspace tree.

Use it in crowded scenes, large hierarchies, character setups, prop-heavy rooms, and maps where the object you need is visible on screen but hard to find in the tree.

## Quick Start

1. Hold **Alt**.
2. Move the cursor over the object, character, or map object.
3. Use the mouse wheel if several candidates are under the cursor.
4. Left click to select the highlighted candidate.
5. Hold **Ctrl** while clicking to add it to the current selection.
6. Release **Alt** to return to normal camera control.

Quick Pick selects the object in the Studio tree, opens parent folders if needed, and scrolls the tree to the selected node.

## Viewport Picking

When the pick key is held, Quick Pick blocks camera movement so the viewport does not move while you are trying to select something.

The hover preview shows the object area and name. If several objects overlap, the preview shows an index like `1/3`. Scroll the mouse wheel to cycle through the candidates before clicking.

For characters, aim near the head when several characters are close together, overlapping, or playing animations.

For very small objects, objects behind other objects, or objects inside other objects, move the camera closer, change the angle, or use the mouse wheel to choose the exact candidate.

## Tree Controls

Quick Pick can add small checkboxes to the Studio tree.

Unchecked nodes are ignored by viewport picking. This is useful when a large object, folder, or background prop keeps getting selected instead of the thing behind it.

If a parent folder is unchecked, its children are ignored too. A child can still be turned back on manually if you need that specific object to remain pickable.

Checkbox states are saved with the scene and restored after loading.

Right click a tree node to open the Quick Pick node menu. Depending on the selected object, it can include:

- **Rename**
- **Change Color**
- **Clear Color**
- **Reverse Extraction**
- **Add To Item Cache**

## Map Objects

Quick Pick can work with raw map objects, not only normal Studio items.

If you Alt-click a map object, Quick Pick can extract it into the Studio tree. Extracted map objects behave much closer to normal Studio items: they can be selected, copied, deleted, parented, colored in the tree, and edited with Material Editor when supported.

Extracted map objects are saved with the scene. Quick Pick restores them after loading and keeps their source map data so they can be rebuilt later.

**Add To Item Cache** saves an extracted map object into Quick Pick's item cache. After that, it can be used again through the cached item workflow instead of extracting the same source every time.

The cache file is stored here:

```text
BepInEx\Config\Pandarinka.QuickPick.ItemCache.txt
```

**Reverse Extraction** is available when Quick Pick can safely return the extracted item back to its original live map object. It removes the extracted Studio item and enables the original source object again.

Some map objects are marked as problematic. This usually means the source object is built in a way that is hard to move or cache reliably, such as static batching, combined meshes, or other optimized map structures.

## Map Tools

Open **Map Tools** with **Ctrl+M** or the Quick Pick toolbar icon.

**Cache Entire Map** scans the current map and registers extractable map objects in the Quick Pick item cache.

**Extract Entire Map** creates a Studio folder named after the current map and extracts the map objects into that folder.

The window shows how many map objects were found and how many of them are problematic. Large maps can take time to process, so wait until the operation finishes before saving, loading, or changing maps.

For full map workflows, cache the map first, then extract it. This gives Quick Pick more source data to restore objects correctly after scene load or when moving cached objects between maps.

## Settings

The main config options are:

```text
Enabled: On
Hold Key: LeftAlt
Map Tools Hotkey: Ctrl+M
Allow Either Alt: On
Ignore UI: On
Show Hover Preview: On
Enable Checkboxes: On
```

Object type options are off by default for special Studio objects:

```text
Include Lights: Off
Include Cameras: Off
Include Folders: Off
Include Routes: Off
```

Turn them on only if you want Quick Pick to select those object types from the viewport.

Picking sensitivity can also be adjusted in the config:

```text
Pick Padding Pixels
Min Rect Size Pixels
Object Ray Distance Threshold
Character Ray Distance Threshold
Ray Size Penalty
Character Head Pick Width Pixels
Character Head Pick Height Pixels
Character Head Vertical Offset Pixels
```

Increase padding or minimum rectangle size when tiny objects are hard to grab. Lower them if large nearby objects are winning too often.

## Common Problems

**Nothing highlights.**

Make sure **Enabled** is on, hold the configured pick key, and keep the cursor away from UI panels. If you are trying to select lights, cameras, folders, or routes, enable that object type in the config.

**The wrong object is selected.**

Use the mouse wheel while holding **Alt** to cycle through overlapping candidates. Changing the camera angle also helps when objects sit inside each other.

**A folder or large object blocks everything behind it.**

Disable that node with the tree checkbox, then try picking again. Turn the node back on later if you need it.

**A map object extracts, but cannot be moved normally.**

That source object may be a problematic map object. Some maps use static batching, combined meshes, or special engine structures that cannot behave like clean Studio items.

**Cached or extracted map objects load as missing red objects.**

Update Quick Pick, make sure the source map is available, and load the scene with Scene Browser when possible. Scene Browser separate import is supported by the newer Quick Pick and Scene Browser versions.

**Map Tools is slow on a large map.**

That is expected on heavy maps. Let the cache or extraction process finish before doing anything else in Studio.

## Notes

- Current Quick Pick version in this guide: `2.4.0`.
- Quick Pick is made for **StudioNEOV2**.
- **BepInEx 5**, **HS2API**, and **ExtensibleSaveFormat** are required by the plugin.
- **AdvancedItemSearch** is recommended for cached map object workflows.
- Scene Browser separate import is supported with compatible Quick Pick and Scene Browser versions.
- Default Studio loading can be less reliable for scenes that contain cached or extracted map objects.
