# Soft Body

**Soft Body** is used for manual body, head, and clothing mesh shaping in Studio.

Use it when you want to push, pull, expand, tighten, or smooth a painted area on a character body, head, or clothing mesh.

<div class="guide-video-block">
  <video controls preload="metadata" poster="assets/images/soft-body-jiggle-dynamics-preview.png">
    <source src="assets/videos/soft-body-jiggle-dynamics-guide.mp4" type="video/mp4">
  </video>
  <div class="video-chapters" aria-label="Video timecodes">
    <button class="video-chapter-link" type="button" data-video-time="0">0:00 Preview</button>
    <button class="video-chapter-link" type="button" data-video-time="117">1:57 Soft Body guide</button>
    <button class="video-chapter-link" type="button" data-video-time="468">7:48 Jiggle Dynamics guide</button>
    <button class="video-chapter-link" type="button" data-video-time="690">11:30 Performance</button>
  </div>
</div>

## Quick Start

1. Open **Pandarinka Toolkit**.
2. Go to **Soft Body**.
3. In **Characters**, choose the character you want to edit.
4. Turn on **Enable Plugin**.
5. Choose a page: **1**, **2**, **3**, and so on.
6. Open **Painted Selection & Shape**.
7. Open **Brush Selection**.
8. Turn on these options:
   - **Use painted selection**
   - **Show painted selection** (**V**)
   - **Paint selection in viewport** (**B**)
9. Paint the area directly on the character in the viewport.
10. Choose a direction, then adjust **Brush Amount**.

The basic idea is simple: first paint where the edit should happen, then choose how that painted area should move.

## Pages

Pages let you keep different edits separate.

Use **page 1** for one deformation, **page 2** for another, **page 3** for another, and so on. This is useful when you want one area shaped one way and another area shaped differently.

Example:

1. Use **page 1** for a belly edit.
2. Use **page 2** for a breast edit.
3. Use **page 3** for a clothing-only edit.

Each page keeps its own painted selection and shape settings.

**Active page** controls only the current page. If you turn it off, that page keeps its settings, but stops affecting the mesh.

## Painted Selection & Shape

Open **Painted Selection & Shape**, then open **Brush Selection** to paint the area you want to edit.

Turn on:

- **Use painted selection**: tells Soft Body to use the painted mask for editing.
- **Show painted selection** (**V**): shows the painted area in the viewport.
- **Paint selection in viewport** (**B**): lets you paint directly on the character.

You can also use hotkeys:

```text
V: show or hide the painted selection
B: turn viewport painting on or off
N: switch between paint mode and erase mode
```

## Brush Controls

**Brush Radius** controls how wide the paint brush is.

Use a smaller radius for tight areas, edges, fingers, seams, or small clothing details.

Use a larger radius for big soft areas, like belly, breast, butt, thigh, or broad clothing shapes.

If the painted area is too hard to control, lower the radius first.

**Brush Strength** controls how quickly painting changes the selection.

Higher strength fills the selection faster.

Lower strength gives softer control and is better when you want to build the selection slowly.

If the selection becomes too strong or too wide, switch to **Erase Mode** or press **N**, then erase the extra area.

## Edit Painted Selection

After you paint a selection, choose how it should move.

- **Out**: pushes the painted area outward from the surface.
- **In**: pushes the painted area inward.
- **Up** / **Down**: moves the painted area vertically.
- **Left** / **Right**: moves the painted area sideways.
- Rounded shape controls:
  - **Expand**: spreads the area outward from its center. This is best for rounded forms, for example around an arm or leg, but it can be used anywhere it gives the right shape.
  - **Tighten**: pulls the area inward toward its center. This is best for rounded forms, for example around an arm or leg, but it can be used anywhere it gives the right shape.

For most body shaping, start with **Out** or **In**.

Turn on **Apply painted shape** to keep the painted area deformed.

Then use:

- **Brush Amount** for how far the body or skin moves.
- **Edge Smoothing** for how smooth the deformation is inside the painted area.
- **Neighbor Feather** for how much nearby mesh is softly included around the painted selection.

Start with **Brush Amount**. This is the main slider.

If the shape looks too sharp, raise **Edge Smoothing**.

If the edge of the painted area looks too sudden, raise **Neighbor Feather** a little.

**Brush Amount** is the main strength of the manual shape.

Raise it slowly. A small change is often enough.

The direction buttons decide where the painted area moves. **Brush Amount** decides how far it moves.

**Edge Smoothing** smooths the deformation inside the painted selection.

It does not make the painted area bigger. It makes the shape less sharp and less lumpy.

Use it when the result has visible bumps or uneven parts inside the selected area.

**Neighbor Feather** softly includes nearby vertices around the painted selection.

At **0**, the deformation stays inside the painted selection.

Raise it when the edge of the deformation looks too harsh or when the shape needs to blend into the surrounding body.

Do not raise it too much if you need a tight, precise edit.

## Linked Meshes (Clothes)

Use **Linked Meshes** when the edit should affect clothing or nearby linked mesh parts.

For normal body edits, **Stitch linked meshes** makes clothing follow the skin changes.

For clothing-only edits, turn on **Clothing only (this page)**. In this mode, the painted body area is used as a guide, but the page deforms clothing instead of the body.

Main controls:

- **Clothing Follow**: how strongly clothing follows the current Soft Body deformation.
- **Seam Fix Strength**: fixes the character mesh borders. If this is lower than **1**, holes can appear where the uncensor mesh connects.
- **Follow Distance**: how far from the body a linked clothing or seam vertex can be and still follow the deformation.
- **Brush Amount (Clothes)**: the main strength for clothing-only deformation. This slider works only for clothing, not skin.
- **Edge Smoothing** under **Clothing Shape**: smooths the clothing deformation inside the selected clothing area.
- **Neighbor Feather** under **Clothing Shape**: softly extends the clothing deformation to neighboring triangles.

If clothing does not react, make sure **Clothing only (this page)** is on, the page has a painted area, and the needed layer is enabled under **Linked Layers**.

## Presets

**Presets** are used to save and copy the full Soft Body page set.

When you click **Create / Update**, the plugin saves all Soft Body pages: painted selections, directions, shape sliders, clothing-only states, and linked mesh settings.

When you select a preset and click **Apply**, the saved page set is copied back into Soft Body.

Use presets when you want to reuse the same Soft Body setup on another character or another scene.

Main buttons:

- **Create / Update**: saves the current Soft Body page set into the preset name field.
- **Apply**: copies the selected preset back into Soft Body.
- **Open Folder**: opens the folder where preset files are stored.
- **Rename**: renames the selected preset.
- **Delete**: removes the selected preset.

Soft Body presets are stored here:

```text
BepInEx/plugins/PandarinkaToolkit/Presets/mesh_soft_body_page
```

A new chat called **presets** was recently created in my [Discord channel](https://discord.com/invite/Ndzqjv8awk). You can use it to share your Soft Body presets with other users.

## Common Problems

**Nothing changes**

Check that a character is selected, **Enable Plugin** is on, the current page is active, **Use painted selection** is on, and **Apply painted shape** is on.

**I can paint, but I cannot see the selection**

Turn on **Show painted selection** or press **V**.

**Painting does not work in the viewport**

Turn on **Paint selection in viewport** or press **B**.

## Notes

- **Reset** clears only the current page.
- If **Reset** does not visually clear the result, click **Enable Plugin** twice: off, then on.
- Almost all Soft Body actions can be undone or redone with **Ctrl + Z** and **Ctrl + Shift + Z**.
- Works with the **Pregnancy Plus** plugin.
- [Scene Browser Pro separate import](https://www.patreon.com/posts/152468460?collection=2042055) does not work with Soft Body edits yet.
- [Recycle Bin (Stash)](https://www.patreon.com/posts/153538889?collection=2042055) does not work with Soft Body edits yet.
