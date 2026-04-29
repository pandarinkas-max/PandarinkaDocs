# Keep Texture Scale

<div class="video-preview">
  <iframe
    src="https://www.youtube-nocookie.com/embed/_Vw4AJ6jK7E"
    title="Keep Texture Scale video"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
    allowfullscreen>
  </iframe>
</div>

**Keep Texture Scale** keeps texture tiling visually consistent when selected Studio objects are scaled.

Use it for walls, floors, panels, rocks, props, or map pieces where scaling the object makes the texture look stretched.

## Quick Start

1. Open **Pandarinka Toolkit**.
2. Go to **Transform**.
3. Open **Keep Texture Scale**.
4. Expand **Objects**.
5. Search or browse the Studio tree.
6. Check the objects or folders you want to track.
7. Scale those objects normally in Studio.

The selected objects keep their texture tiling closer to the original scale.

## How Selection Works

You can check a single object or a parent folder.

If a parent folder is checked, its children are treated as part of that selection. This is useful for grouped walls, floors, furniture sets, or imported map pieces.

The selection is saved with the scene and restored after loading.

## Use It For

- scaled floors
- scaled walls
- resized panels
- large map pieces
- props where material tiling should stay readable

## Notes

- Unchecking an object restores its tracked mesh data.
- Duplicated selected objects can inherit the same texture-scale behavior.
- Some unusual meshes or materials may still need manual material adjustment.
