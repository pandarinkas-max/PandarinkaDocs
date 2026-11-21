# Character Baker

Character Baker turns each posed character into a separate Studio object. Use it for background characters and crowds when you want to keep their clothes, hair and expression while reducing the work Studio spends on animation and physics. By default, the object keeps FK bones so you can still adjust its pose.

[Pandarinka Toolkit on Patreon](https://www.patreon.com/Pandarinka/posts/pandarinka-and-154581882)

## Getting Started

1. Set the character's pose, expression, outfit and clothing state as you want them to appear.
2. Select one or more characters in the Workspace. Open **Toolkit → Characters → Character Baker**, above **Uncensor Search**.
3. For a fixed pose, open **Advanced** and clear **Keep FK bones** before baking. Leave it enabled if you plan to pose the object later.
4. Click **Bake Selected Characters**. When the bake finishes, each selected character has been replaced by an object in the Workspace. You can move, rotate, scale, hide or duplicate it like other Studio objects.

## Restore a character

Select one or more baked objects and click **Restore Selected Characters**. Each original character returns with the pose, clothes and expression it had when baked, at the object's current position, rotation and scale. Use Restore when you want to edit character features again. Pose or material edits made to the baked object stay with that object.

**Each bake also writes a recovery PNG to `UserData/CharacterBaker/Originals`.** These files take up disk space and stay there until you delete them yourself, even after you restore or delete the object. A saved scene containing the baked object embeds the original character data. Once you have that scene saved and verified, you can remove extra recovery PNGs if you no longer want the separate backups. Keep the character's mods and shaders installed for loading and restoration.

## FK and IK on a baked object

**Advanced → Keep FK bones** applies to new bakes and starts enabled. Clothing follows the retained bones. You can pose them with FK and animate them in Timeline. Hair and clothing simulations stop at bake time, and the facial expression stays fixed.

**Set up IK for Objects** also starts enabled. It automatically enables IK for Objects on the new object and creates targets for the limbs it detects. Select the object and open **Toolkit → Transform → IK for Objects** to adjust the targets. Clear only **Set up IK for Objects** for an FK-only bake. Clearing **Keep FK bones** clears both options. To change a fully static object back to a poseable one, restore the character and bake it again with FK enabled. [IK for Objects guide](ik-for-objects.md)

## Materials and shadows

Under **All baked characters**, a change applies to existing baked characters and becomes the default for future bakes. To adjust one object, expand its row under **Baked characters**. Clicking its name selects it in the Workspace.

| Setting | When to use it |
| --- | --- |
| **Bake materials (extra performance)** | Enabled by default. Combines supported skin and clothing layers to reduce rendering work. Hair and eyes keep their original materials. Turn this off for a close-up if you prefer the original skin lighting, fabric detail or gloss. Preparing maps takes time and uses memory. |
| **Character shadows** | Enabled by default. Keep shadows on for characters whose shadows matter to the shot. Turning them off on background characters can reduce shadow rendering work. |

## Render resolution and Automatic LOD

Open **Advanced** under the global settings or inside an individual baked character's row. **Render resolution** defaults to **100%**. The other choices are **75%, 50% and 25%**. They reduce the pixels used to draw the character. The mesh, pose and material settings stay the same.

- **Automatic LOD** adjusts resolution according to how much of the camera view the character occupies. The slider becomes **Minimum render resolution**. A smaller figure can use fewer pixels while a nearby face stays sharper.
- While the camera moves, Baker returns to full resolution. Stop the camera to see the lower setting take effect. With Graphics SSS active, Baker uses the original rendering path.
- **Cache stationary view at 100%** is off by default. Use it for a locked camera looking at unselected, stationary extras with **Character shadows** off. Baker can reuse their last image between edits. **Orbiting can lower FPS** with this option enabled.

## Unbaked characters

You can use these two options on ordinary characters before baking anything.

- **Performance Mode for Characters** pauses pose updates for eligible, unselected characters once their pose settles. Select a character to edit it again. **Poses held** counts the characters currently paused. Zero means this option is saving no pose work at that moment.
- **Skip hidden FK and IK handle updates** skips work on hidden controls belonging to unselected characters. Selecting the character wakes its controls. This can save CPU time in a scene with many handles.

## Crowds and performance

On scene load, Baker can use one temporary source character to rebuild several baked objects with matching appearances, even when they have different poses. If a source cannot supply the materials an object needs, Baker loads that object's own snapshot. Each object keeps its own pose, name, transform and render settings.

In a scene with eight characters, baking raised the frame rate from **35 to 120 FPS**. The gain depends on what takes time in your shot. If lighting and scene effects already take most of the frame, baking characters can make a smaller difference. To compare settings, keep the same camera, visible objects and lighting.
