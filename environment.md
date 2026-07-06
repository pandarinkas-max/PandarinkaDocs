# Environment

<div class="video-preview">
  <iframe
    src="https://www.youtube-nocookie.com/embed/MCAb8FxGH7s"
    title="Environment video"
    allowfullscreen>
  </iframe>
</div>

**Environment** is used to turn normal Studio scenes into snowy or rainy scenes.

Use it when you want falling snow, snow fields, footprints, snow on objects, snow on characters, blizzard effects, or rain.

Rain and wet effects are still early. At the moment, the main rain feature is **Falling Rain**.

## Quick Start: Snow Scene

1. Open your scene.
2. If the map tree is empty, use **[Quick Pick](https://www.patreon.com/collection/2136425?view=expanded)** to extract the map first.
3. Open **Pandarinka Toolkit**.
4. Go to **Environment**.
5. Start with **Snow**.
6. Create **Snow Field** on the ground or object you want covered.
7. Add **Object Snow** to props that should look snowy.
8. Add **Character Snow** to characters, clothes, hair, or accessories.
9. Turn on **Falling Snow**.
10. Use **Blizzard** if you want heavier storm-like weather.

The usual workflow is simple: make the ground snowy first, then cover objects and characters, then add falling snow on top.

## Snow Field

**Snow Field** creates a snow surface mesh fitted to selected Studio objects.

Use it for ground snow, snow platforms, snow piles, or editable snow surfaces.

Quick workflow:

1. Select the object where the snow field should be created.
2. Open **Environment**.
3. Open **Snow**.
4. Open **Snow Field**.
5. Click **Create On Selected**.

If more than one object is selected, the plugin creates a separate snow field for each selected object.

After creation, the snow field appears in the Studio tree. You can select it, move it, scale it, or edit it further.

Snow fields can use two material sources:

- **Procedural**: built-in generated snow material.
- **Texture**: PBR texture packs from the Weather folder.

Use **Open Folder** in the material section to open the Weather texture folder.

Texture packs are loaded from:

```text
BepInEx/Plugins/PandarinkaToolkit/Weather
```

You can replace the snow look with any PBR texture pack you have. Put the texture files into the Weather folder, click **Refresh**, then choose the texture pack in the plugin.

## Footprints

Snow fields can receive footprints.

Turn on **Place Footprints**, hold the **Snow Field Footprint** hotkey (**Caps Lock** by default), then left-click the snow field in the viewport.

Footprints have their own settings, such as foot size, depth, rim, softness, and color. Use these if the footprint is too deep, too wide, or too visible.

Use **Clear Footprints** if you want to reset the current footprint page.

## Object Snow

**Object Snow** wraps selected objects with snow.

Use it when props should look like they belong in the snowy environment.

Quick workflow:

1. Select an object or folder in the Studio tree.
2. Open **Object Snow**.
3. Click **Add Selected**.
4. Select the added target in the Object Snow list.
5. Adjust the snow layers and material settings.

Object Snow has two main layer types:

- **Full Surface**: covers the object with a continuous snow layer.
- **Mounds**: adds separate snow patches or chunks on top of the object.

If the mounds do not look good, change the random seed or try different settings.

## Character Snow

**Character Snow** adds snow to selected characters.

It works per layer, so you can control body, clothes, hair, and accessories separately.

Quick workflow:

1. Select the character.
2. Open **Character Snow**.
3. Click **Add Selected**.
4. Select the character in **Character Snow Targets**.
5. Enable or disable the layers you want.
6. Tune each layer's snow settings.

Example: add more snow to clothes and hair, but keep the skin almost clean.

This helps the character blend into the snowy scene instead of looking pasted on top of it.

## Falling Snow

**Falling Snow** adds snow particles to the scene.

By default, falling snow follows the camera. This keeps snow around your view while you move through the scene.

If you need snow only in a specific part of the scene, use **Snow Sources**:

1. Change **Snow Mode** to **Snow Sources**.
2. Click **Create Snow Source**.
3. Move the created source object in the Studio tree.
4. Turn on **Show Snow Zones** if you want to see the snowfall area.

Use source mode when only one room, corner, cave entrance, or outside area should have snow.

## Blizzard

**Blizzard** adds stronger winter weather on top of Falling Snow.

It adds wind-blown snow, gusts, and whiteout haze.

Use it for stormy winter scenes, mountain scenes, or any setup where the weather should feel heavier and more dramatic.

Start with blowing snow and haze settings. Use **Blizzard Strength** carefully, because high values can push snowflakes upward too strongly, especially in **Follow Camera** mode.

## Rain

**Rain** adds falling rain particles.

Quick workflow:

1. Open **Environment**.
2. Open **Rain**.
3. Open **Falling Rain**.
4. Turn on **Enable Rain**.
5. Adjust amount, speed, size, length, brightness, wind, and color.

Rain can follow the camera, or it can use **Rain Sources**:

1. Change **Rain Mode** to **Rain Sources**.
2. Click **Create Rain Source**.
3. Move the source object in the Studio tree.
4. Turn on **Show Rain Zones** if you want to see the rain area.

Rain collisions can be enabled, but they can cost FPS in heavy scenes.

## Settings Reference

These are the main visible settings in **Environment**. Start with the first few sliders in each section, then fine-tune only what you need.

### Falling Snow

- **Snow Amount**: how many snow particles are visible.
- **Snow Radius**: width of the snow area when using **Follow Camera** mode.
- **Snow Height**: vertical height of the snow area when using **Follow Camera** mode.
- **Snow Speed**: how fast snow falls.
- **Snow Size**: size of each snowflake.
- **Snow Brightness**: how bright or visible the snowflakes are.
- **Snow Drift**: random sideways movement.
- **Snow Wind X / Snow Wind Z**: steady wind direction on the scene axes.
- **Enable Snow Collisions**: lets snow react to colliders.
- **Snow Bounce**: how much snow particles bounce after hitting a collider.
- **Snow Life Loss**: how quickly particles disappear after collision.

In **Snow Sources** mode, **Snow Radius** and **Snow Height** are replaced by the size and position of the created snow source object.

### Blizzard

- **Blizzard Strength**: main intensity of the whole blizzard layer.
- **Gust Strength**: how strong the wind pulses feel.
- **Gust Speed**: how quickly the gusts change.
- **Blowing Amount**: amount of low wind-blown snow.
- **Blowing Speed**: speed of the blowing snow.
- **Blowing Height**: how high the blowing snow layer reaches.
- **Blowing Size**: thickness of the blowing snow particles.
- **Blowing Length**: length of the wind streaks.
- **Snowflake Gust**: extra sideways force added to normal falling snow.
- **Haze Amount**: amount of whiteout haze.
- **Haze Opacity**: visibility of the haze.
- **Haze Size**: size of haze particles.
- **Haze Height**: vertical height of the haze layer.
- **Whiteout Spread**: how wide the haze spreads across the scene.

Tune **Blowing Amount**, **Blowing Speed**, **Gust Strength**, and **Haze Opacity** first. Use **Blizzard Strength** carefully, especially in **Follow Camera** mode, because high values can push snowflakes above the camera.

### Snow Field

- **Field Resolution**: mesh density of the snow field. Usually, leave it at the maximum value for the best surface detail.
- **Field Thickness**: visual thickness of the snow surface.
- **Mound Height**: height of generated snow bumps.
- **Mound Scale**: size of the generated bumps.
- **Surface Roughness**: unevenness of the snow surface.
- **Field Sparkle**: strength of sparkle on the snow field.
- **Sparkle Count**: how many sparkle particles are used.
- **Sparkle Emission**: how bright the sparkle particles are.
- **PBR Tiling**: texture scale when using a texture pack.
- **PBR Normal**: strength of the normal map from the texture pack.
- **PBR Height**: strength of the height map from the texture pack.

Usually, you do not need to touch **Field Resolution**. Leave it at the maximum value, then use **Mound Height**, **Mound Scale**, and **Surface Roughness** for the look.

### Footprints

- **Foot Length**: length of the footprint.
- **Foot Width**: width of the footprint.
- **Foot Depth**: how deep the footprint is pressed into the snow.
- **Foot Radius**: size of the soft area around the footprint.
- **Rim Height**: raised edge around the footprint.
- **Foot Softness**: how smooth the footprint edge is.
- **Foot Rotation**: rotation of the next footprint. You can also rotate it with the mouse wheel while placing footprints.

If a footprint looks too harsh, lower **Foot Depth** or raise **Foot Softness**.

### Object Snow

- **Snow Coverage**: how much of the object gets covered.
- **Snow Thickness**: thickness of the full surface snow layer.
- **Mound Count**: number of separate snow mounds.
- **Mound Size**: width of the mounds.
- **Mound H.**: height of the mounds.
- **Edge Smoothing**: softness of mound edges.
- **Surface Brightness**: brightness of the generated snow material.
- **Snow Sparkle**: sparkle strength on object snow.
- **Texture Tiling**: scale of the snow pattern or texture.

Use **Full Surface** for a continuous snow coat. Use **Mounds** for separate snow patches.

### Character Snow

- **Fine Coverage**: how much of the selected character layer receives snow.
- **Fine Count**: amount of small snow grains.
- **Fine Size**: size of the grains.
- **Fine Height**: raised height of the grains.
- **Fine Smoothing**: softness of grain edges.
- **Fine Brightness**: brightness of the snow on the character.
- **Fine Sparkle**: sparkle strength on character snow.
- **Fine Tiling**: scale of the snow pattern or texture.

Character Snow works per layer. You can keep skin almost clean while adding stronger snow to clothes, hair, or accessories.

### Falling Rain

- **Rain Amount**: how dense the rain is.
- **Rain Radius**: width of the rain area when using **Follow Camera** mode.
- **Rain Height**: vertical height of the rain area when using **Follow Camera** mode.
- **Rain Speed**: how fast rain falls.
- **Rain Size**: thickness of each rain streak.
- **Rain Length**: length of each streak.
- **Rain Brightness**: how visible or bright the rain is.
- **Rain Drift**: random sideways movement.
- **Rain Wind X / Rain Wind Z**: steady wind direction on the scene axes.
- **Rain Collisions**: lets rain react to colliders.
- **Rain Bounce**: how much rain particles bounce after collision.
- **Rain Life Loss**: how quickly particles disappear after collision.

In **Rain Sources** mode, place and scale the source object instead of using **Rain Radius** and **Rain Height**.

### Color Settings

Most snow, rain, field, object snow, character snow, footprint, blizzard, and haze colors can be edited in **HSV** or **RGB** mode.

- **Hue** changes the basic color.
- **Saturation** controls how colorful it is.
- **Value** controls brightness.
- **Transparency** controls opacity.
- **Red / Green / Blue** gives direct RGB color control.

## Useful Notes

- **Show Effects** hides or shows Environment runtime effects without deleting their settings.
- Snow Field, Falling Snow, and Rain source objects are real Studio tree objects, so you can move them like other objects.
- For extracted maps, use **[Quick Pick](https://www.patreon.com/collection/2136425?view=expanded)** first so the map objects appear in the tree.
- **Soft Body Objects** can edit snow fields after they are created. This is useful for dents, bumps, or uneven snow.
- **Transform > Folder Scale** can help scale extracted map folders or groups of environment objects.
- **Follow Camera** snow is lighter on FPS than separate **Snow Sources**. Use **Snow Sources** only when you need snowfall in specific scene zones.
- In **Falling Snow**, FPS may start to drop gradually when **Snow Amount** is higher than about **4000** particles. Keep this in mind when making heavy snowfall.

## Common Problems

**Character Snow does not restore correctly after loading**

Character Snow may not always restore correctly after loading a scene. This is a known issue and will be fixed later.

**Texture packs do not show**

Put the PBR texture pack into:

```text
BepInEx/Plugins/PandarinkaToolkit/Weather
```

Then click **Refresh** in the material section.
