# Jiggle Dynamics

**Jiggle Dynamics** makes selected character bones react to character contact or object contact.

Use it when you want precise, polished jiggle in animations, with control over which bones react and how they move.

The video guide is available on my [Discord server](https://discord.com/invite/Ndzqjv8awk).

<div class="guide-gif-gallery">
  <img src="assets/images/toolkit-preview-03.gif" alt="Pandarinka Toolkit preview 3">
</div>

## Quick Start

1. Open **Pandarinka Toolkit**.
2. Go to **Jiggle Dynamics**.
3. In **Characters**, choose the character that should react.
4. Turn on **Enable Jiggle Dynamics**.
5. Scroll down to **Full Body Bones**.
6. Open the body group you want to move.
7. At the bottom of that group, open **Bones**.
8. Click **Core** for that group. **All** enables every bone; **Core** enables the main bones and is usually the better starting point.
9. Turn on **Show contact areas** or press **O**.
10. Adjust **Impact Area** until the visible zones cover the area you want.
11. Go back up and choose what should push the bones.
12. Use **Character Sources** if another character should push the target.
13. Use **Object Sources** if a scene object should push the target.
14. Test the contact, then adjust settings to your taste.

## Full Body Bones

Start here.

**Full Body Bones** is where you choose which bones on the target character are allowed to react.

Open the group you need, for example **Breast**, **Butt**, **Torso**, **Arm**, **Leg**, or **Head**.

Inside the group, open **Bones** at the bottom. I recommend starting with **Core**. It enables the main useful bones without turning on every small detail bone, which also helps save FPS.

Use:

- **Core**: good starting point for the selected group.
- **All**: enables every bone in the group.
- **Off**: disables the group bones.

After that, turn on **Show contact areas** or press **O**.

Visible contact areas show where the target character can react. If the area is too small, contact will be hard to trigger. If it is too large, the reaction may happen too early or too broadly.

## Per-Bone Editing

If one part of the group needs a different area, edit that exact bone.

Open **Bones**, find the bone you need, then adjust:

- **Impact Area**: contact area for that exact bone.
- **Bone Movement**: how far that exact bone is allowed to move.

When you hover a bone row, the bone is shown on the character. Use this to find the correct bone before changing it.

Use per-bone editing only after the group settings are close. It is easier to tune the group first, then fix small problem spots.

## Character Sources

Use **Character Sources** when another character should push the target character.

1. Go back up to **Runtime**.
2. Open **Character Sources**.
3. Turn on **Enable character sources**.
4. Select the character that should act as the source.
5. Choose which source body parts should cause contact.

The source body parts are the areas from the other character that can push the target, for example **Hands**, **Arms**, **Torso**, **Breast**, **Butt**, **Thighs**, or **Feet**.

After selecting source parts, you can turn on **Show source contact areas** to see their zones.

If the source zones are too small or too large, adjust **Source Collider Size**. If you need more detailed control, open **Source bone areas** and tune the source areas separately.

## Object Sources

Use **Object Sources** when a scene object should push the target character.

Only objects with colliders can work as object sources. I used [these colliders](https://gofile.io/d/sXiv7E) for testing. They should be available by default, but if you do not have them, download and load them first.

1. Select the Studio item or folder in the Studio tree.
2. Open **Object Sources**.
3. Turn on **Enable object sources**.
4. Click **Add Selected Object**.
5. Turn on **Show source contact areas** if you want to see the object source zones.

Use **Object Collider Size** to make object contact easier or stricter.

For individual object sources, use **Area** on that object row.

## Presets

Jiggle Dynamics has presets for two things:

- **Jiggle receiver presets**: save the target character's enabled bones, group settings, contact areas, movement settings, and object source areas.
- **Contact source presets**: save character source settings, enabled source body parts, and source contact area settings.

Use **Create / Update** to save the current setup, and **Apply** to load the selected preset back into the current Jiggle Dynamics setup.

Preset folders:

```text
BepInEx/plugins/PandarinkaToolkit/Presets/jiggle_receiver
BepInEx/plugins/PandarinkaToolkit/Presets/jiggle_contact_sources
```

A new chat called **presets** was recently created in my [Discord channel](https://discord.com/invite/Ndzqjv8awk). You can use it to share your Jiggle Dynamics presets with other users.

## Tuning Settings

After the target bones and sources are set, test the contact.

Use these first:

- **Impact Area**: size of the reaction zone around the enabled bones. This changes where contact is detected; it does not make movement stronger by itself.
- **Base Contact Force**: main contact strength from objects and characters.
- **Extra Character Force**: extra strength only for character sources.
- **Bone Movement (Global)**: how far the whole group is allowed to move.
- **Push Speed**: how quickly the bones react to contact.
- **Return Speed**: how quickly the bones return after contact.
- **Jelly Bounce**: how much after-jiggle remains after contact.

For most setups, adjust in this order:

1. **Impact Area** so the contact starts in the right place and the visible zones cover the area you want.
2. **Base Contact Force** so the reaction is visible.
3. **Bone Movement (Global)** so the movement is not too small or too large.
4. **Push Speed** and **Return Speed** for timing.
5. **Jelly Bounce** only if you want more or less spring after the push.

## Common Problems

**Nothing moves**

Check that **Enable Jiggle Dynamics** is on, the target character is selected, and at least one bone or group is enabled in **Full Body Bones**.

**The contact does not trigger**

Turn on **Show contact areas** and check **Impact Area**. The visible target area must overlap the source contact area.

**Another character does not affect the target**

Check **Character Sources**, **Enable character sources**, selected source character, and selected source body parts.

**An object does not affect the target**

Check **Object Sources**, **Enable object sources**, and make sure the object was added with **Add Selected Object**.

## Notes

- **Reset** resets the current Jiggle Dynamics target state.
- Use **Core** first. Use **All** only when you really want every bone in the group to react.
- **Advanced Global Controls** are better left alone for now. These sliders were not tested much yet, but you can still experiment with them if you want to play around and check the result.
- [Scene Browser Pro separate import](https://www.patreon.com/posts/152468460?collection=2042055) works with Jiggle Dynamics.
- [Recycle Bin (Stash)](https://www.patreon.com/posts/153538889?collection=2042055) does not work with Jiggle Dynamics at the moment.
