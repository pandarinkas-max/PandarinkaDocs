# SliceWorks

<div class="video-preview">
  <iframe
    src="https://www.youtube-nocookie.com/embed/aVFX2tA0Y34"
    title="SliceWorks video"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
    allowfullscreen>
  </iframe>
</div>

Cut characters and objects into separate parts, create holes, and add animated blood effects. Cut surfaces have their own materials, which you can edit in **Material Editor**.

Use SliceWorks for:

- **Gore and injury scenes**, with textured cut surfaces and animated blood.
- **Cyborgs and robotic inserts**, making room for mechanical parts inside a character.
- **Supernatural body effects**, such as floating limbs, body separation, or staged regeneration.
- **Animating individual body parts**: detach an arm and animate it on its own. Working with only the part you need simplifies setup and can reduce scene load.
- **Creative object effects**: stage a sword cutting through a prop, split scenery into pieces, or create cutaway views.

Open Toolkit, then select **SliceWorks**, below **Pose Match**.

## Quick Start

1. Choose **Characters** or **Objects**, then select the character, object, or existing SliceWorks part in the Studio workspace.
2. Choose **Straight**, **Jagged**, **Hole**, **Jagged Hole**, or **Fist**.
3. Click **Place cutter** and move the cursor over the target. Use the mouse wheel to change the tilt. For **Hole** and **Jagged Hole**, the wheel changes the diameter instead.
4. Press the **middle mouse button** to fix the cutter. Left and right mouse buttons remain available for moving the camera.
5. Adjust **Tilt X / Y / Z**, **Position X / Y / Z**, and the cut size, then click **Cut**.

**Keep cut-out part** is enabled by default and creates a separate part in the workspace. Disable it to remove the cut-out area instead.

The cut preview is visible through the model, with an outline and translucent fill.

Enable **All characters** or **All objects** to apply the same cutter to every character or object it intersects. The whole operation can be undone together.

Placement button: **Options > Hotkeys > SliceWorks — fix cutter**.

## Cut Shapes

- **Straight** creates a flat cut.
- **Jagged** creates an uneven cut surface. **Jagged depth** controls its relief, and **Jagged detail** controls the amount of detail.
- **Hole** makes a circular opening. Adjust its **Diameter**.
- **Jagged Hole** makes an opening with an irregular edge. Use **Diameter**, **Jagged depth**, and **Jagged detail** to shape it.
- **Fist** makes a fist-shaped opening. Adjust **Fist width** and use **Mirror horizontally** after fixing the cutter to flip its outline.

For Straight and Jagged cuts, **Cut size** limits the blade width. Make it small enough to avoid neighbouring parts, but wide enough to cover the full cross-section of the part you want to detach.

## Detached Parts and Undo

Each detached part gets its own workspace entry and a pivot centred on the piece. You can move, rename, and cut it again.

Character parts keep FK/IK and character animations. Object parts keep the object's existing FK bones and animation, when present. Detached parts work with **Timeline**, **NodesConstraints**, other Studio plugins, and **Toolkit's own tools**.

The **Cuts** list shows previous cuts. **Undo Cut** rejoins the removed area with its parent. Later cuts that depend on that piece or cross the same seam are restored with it; separate cuts remain in place.

Cuts, adjustments, **Refit cut surfaces**, and **Undo Cut** support Studio **undo/redo**. Everything is saved with the scene.

## Refit Cut Surfaces

If a cut surface stretches or shifts after changing a pose, select the affected part and click **Refit cut surfaces**. This rebuilds the surface to fit the current pose while keeping its materials.

With **All characters** or **All objects** enabled, refit applies to all cut parts in that mode.

## Cut Surface Materials

Select the character, object, or detached part and open **Material Editor**. Find the material whose name starts with **SliceWorks Cut**, followed by the cut number and the affected part, such as **Head**, **Body**, **Top**, or **Object**. Hair cut materials use labels such as **Front hair**, **Back hair**, and **Hair extension**.

Import your cut texture into **MainTex**. Use the **Offset X / Y** and **Scale X / Y** fields directly below MainTex to centre and resize it. This is also where you can align the bone in a texture with the middle of the cut. New cut materials start with **Glossiness** at **0**.

### Included Textures

The plugin comes with a **ZIP containing five gore textures**:

- **Muscle Tissue**
- **Muscle Tissue with Bone** — a bone in the centre.
- **Connective Tissue**
- **Deep Red Tissue**
- **Deep Red Tissue with Bone** — a bone in the centre.

Extract the ZIP and import a texture into the cut material's **MainTex**.

I can't show graphic preview images here, but these textures and the blood effect can create realistic cut or severed-limb effects.

## Blood Effect

Click **Spawn blood** at the bottom of SliceWorks. It creates a red entry in the workspace. Select that entry to edit the effect, and use Studio controls to move, rotate, scale, or parent it.

- **Drops** creates falling droplets.
- **Trickle** sends separate droplets along a curved path.
- **Stream** creates a continuous, narrowing flow.
- **Dripping** creates hanging strands with drops at their tips.

**Animation speed** controls playback; set it to **0** to pause. Edit colour, textures, and glossiness in **Material Editor**:

- **SliceWorks Blood - Strands** controls the hanging strands and their connections.
- **SliceWorks Blood - Strand Tips** controls the rounded tips, with separate **Glossiness** and a smooth transition into the strands.
- **SliceWorks Blood - Stream** controls the flowing stream and linked arcs.
- **SliceWorks Blood - Drops** controls falling droplets.

Use each renderer's **Enabled** setting in Material Editor to show or hide **Blood strands**, **Blood stream**, or **Blood drops** independently.

### Effect Zone

Enable **Show zone while Toolkit is open** to see the effect's area. **Zone width X**, **Zone height Y**, and **Zone depth Z** set its size. The source sits at the top of the box. You can also resize it by scaling the workspace item.

**Keep falling drops inside zone** removes droplets when they leave the box. Linked arcs can extend outside it.

### Hanging Strands

In **Dripping** mode, adjust **Strand count**, **Strand thickness**, **Irregularity**, and **Tip fullness**. **Top connections** adds links between nearby strands. Change **Pattern seed** for another arrangement.

Enable **Interweave strands**, then adjust **Weave amount** and **Weave turns** to intertwine them. Open **Falling drops** to control drop size, emission rate, lifetime, gravity, and initial fall speed.

### Linked Arcs

Spawn two blood items. Select the first, click **Connect arc to another blood item**, and choose the second from the list. Move either item to adjust the endpoints; use **Arc sag**, **Arc bend X**, and **Arc bend Z** to shape the connection. **Disconnect arc** removes the link.

Blood effects, their settings, and connections are saved with the scene and support **undo/redo**. Their workspace transforms can be controlled through **Timeline** and **NodesConstraints**.
