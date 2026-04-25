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

## Quick Start

1. Create a scatter result or select any folder with objects.
2. Open **Pandarinka Toolkit**.
3. Go to **Transform**.
4. Open **Bake to Mesh**.
5. Select the folder you want to bake.
6. Click **Bake Selected Folder**.

The baked object appears in the Studio tree as a normal item.

## Delete Source Clones

Enable **Delete source clones after bake** if you want to remove the original scattered objects after the baked object is created.

Leave it off if you want to compare the original scatter folder and the baked result.

## What To Expect

Bake to Mesh can improve FPS because Studio has fewer separate objects to manage.

It is not the same as a full Blender atlas or UV bake. Heavy transparent leaves, cutout materials, shadows, and many materials can still cost performance.

If FPS does not improve immediately, move the camera away from the baked object and then look back at it.

## Notes

- Materials can still be edited.
- Light and shadows behave like normal Studio objects.
- After saving and loading the scene, the baked object returns.
- [Scene Browser (Separate Import)](https://www.patreon.com/posts/152468460?collection=2042055) is supported.
- [Recycle Bin (Stash)](https://www.patreon.com/posts/153538889?collection=2042055) is not supported yet.
