# Recycle Bin

<div class="video-preview">
  <iframe
    src="https://www.youtube-nocookie.com/embed/Hx-NJrji8ro"
    title="Recycle Bin video"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
    allowfullscreen>
  </iframe>
</div>

[**Recycle Bin**](https://www.patreon.com/posts/153538889?collection=2042055) adds object trash and stash tools to **NeoStudioV2**.

It has two parts:

- **Recycle Bin** - temporary session history for deleted objects.
- **Stash** - saved scene storage for objects you want to unload and restore later.

## Recycle Bin

Delete objects normally.

Instead of being gone forever, deleted objects go into the Recycle Bin for the current Studio session.

Right click the delete button to open the Recycle Bin window and restore objects.

Recycle Bin is not saved after restarting Studio.

## Stash

Use **Stash** when you want to remove objects from the scene but keep them saved with the scene.

Left click the Stash button to send selected objects to Stash.

Right click the Stash button to open the Stash window.

Stash can be used to temporarily unload heavy props, lights, characters, or scene parts, then bring them back later.

## Windows

Inside Recycle Bin and Stash windows you can:

- see deleted or stashed objects by category
- restore a single object
- select multiple entries
- restore several objects at once

## Why Use It

- Recover accidental deletes without reloading the scene.
- Temporarily unload heavy scene parts.
- Keep large scenes lighter while working.
- Move assets between scene workflows with Stash.
- Store scene parts and restore them later.

## Notes

- [BepInEx 5](https://github.com/BepInEx/BepInEx/releases) and [HS2API](https://gofile.io/d/VYsLtI) are required.
- [Quick Pick](https://www.patreon.com/collection/2136425?view=expanded) extracted map objects are supported.
- First delete or stash can take a moment while the plugin warms up.
- Very large delete or stash operations can take a few seconds.
- Default bin limit is `32` items and can be changed in settings.
- Some special states from exotic plugins may not save correctly.

## Known Issues

- VNGE and Timeline do not restore after deletion yet.
- Character deletion multiple times may not be fully stable.
