# Scatter Objects

<div class="video-preview">
  <iframe
    src="https://www.youtube-nocookie.com/embed/RVFaDaJvUJE"
    title="Scatter Objects video"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
    allowfullscreen>
  </iframe>
</div>

**Scatter Objects** duplicates selected Studio objects across an area or a mesh surface.

Use it for things like leaves, stones, grass patches, bottles, pens, debris, moss, or small decorations. Your original objects are only used as templates and are not moved.

## Quick Start

1. Open **Pandarinka Toolkit**.
2. Go to **Transform**.
3. Open **Scatter Objects**.
4. Select an object that will be the area or surface.
5. Click **Use Selected As Area** or **Use Selected As Surface**.
6. Select the objects you want to duplicate.
7. Click **Add Selected Sources**.
8. Set **Count**, **Height**, **Scale**, and **Rotation**.
9. Click **Scatter**.

The result is created in a new Studio folder.

## Area Or Surface

Use **Area** for simple flat placement:

- objects on a table
- leaves on flat ground
- stones on a path
- decorations inside a rectangular zone

Use **Surface** for real mesh placement:

- rocks
- uneven terrain
- slopes
- curved objects
- objects that should follow the shape of a mesh

**Max Slope** is used in Surface mode.

It controls how steep the allowed surface can be. `0` means only almost flat upward-facing parts of the mesh. Higher values allow steeper surfaces. `180` allows all sides, including vertical and underside faces.

For rocks or uneven objects, start with:

```text
Use Selected As Surface
Align to Surface: On
Max Slope: 180
Height: 0.01-0.03
```

## Main Settings

**Count** controls how many objects are created.

The current maximum is `1000` objects per scatter operation.

**Seed** controls the random layout.

Use **Random** when the result looks bad and you want a different distribution.

**Height Min / Height Max** moves objects away from the area or surface.

Small positive values like `0.01` / `0.03` help prevent clipping.

**Scale Min / Scale Max** adds size variation.

For natural objects, try `0.7` / `1.3`.

**Rot X / Rot Y / Rot Z** control random rotation on each axis.

Use values between `0` and `360` when objects should rotate freely. You can randomize only one axis, or all three axes depending on the effect.

## Simple Presets

### Leaves Or Stones On Flat Ground

```text
Mode: Use Selected As Area
Count: 100-200
Height: 0.01-0.03
Scale: 0.7-1.3
Rot Y: 0-360
```

### Small Objects On A Table

```text
Mode: Use Selected As Area
Count: 10-40
Height: 0-0.02
Scale: 0.9-1.1
Rot Y: 0-360
```

### Moss Or Leaves On A Rock

```text
Mode: Use Selected As Surface
Count: 200-500
Align to Surface: On
Max Slope: 180
Height: 0.01-0.03
Scale: 0.6-1.4
Rot Y: 0-360
```

### Petals Floating In The Air

```text
Mode: Use Selected As Area
Count: 700
Height: 0-6
Scale: 0.7-1.3
Rot X: 0-360
Rot Y: 0-360
Rot Z: 0-360
```

## Common Problems

**Nothing happens.**

Select an area or surface first, then add at least one source object.

**Objects clip into the surface.**

Increase **Height Min** and **Height Max** a little.

**Objects only appear on top.**

In Surface mode, increase **Max Slope**. Use `180` if all sides should be allowed.

**Too many objects slow Studio down.**

Lower **Count**, scatter in smaller batches, or use **Bake to Mesh** after creating the scatter result.
