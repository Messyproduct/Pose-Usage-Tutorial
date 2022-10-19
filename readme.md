# Using Poses Made for Different Skeleton Orientations

When creating poses for use in the [Smash Ultimate Render Setup Google Drive](https://twitter.com/LN_310/status/1560758532546433025?s=20&t=dDclxKbZIDaFh1PgzoGYow) it is the hope that it will make UI creation easier. So, it is a goal to make it as user friendly as possible. However, some poses in the Drive have a different skeleton format (see below)

![Bone Orientation Example](https://i.imgur.com/tKQElP3.png)

This would be fine if the poses still transferred as intended but the different bone orientation causes some strange side effects in the pose (Pose Credit Nano)

![Pose Copied to Differing Skeleton Format](https://i.imgur.com/70rhlk7.png)

This is obviously not desirable. So, it in this short write-up I will show you how to use a pose regardless of the skeleton format that is used. Please note that this will only apply for vanilla skeletons; That means that Exo will not be supported. For info on how to `retarget` poses for use with Exo please check out the [Blender Rokoko Plugin](https://github.com/Rokoko/rokoko-studio-live-blender)

## Setup

For the sake of this write-up, the source pose armature/meshes will be represented by the color *RED* and the destination armature/meshes will be represented by *BLUE*.

### Alignment
First you must align your destination armature to your source armature, this will involve rotating the older format's skeleton 90 degrees forward. The goal is to have both skeletons occupy exactly the same space. Ideally this will be at the scene's origin (Location `x=0 y=0 z=0`) to make the process as simple as possible.

If this is not the case, try lining them up as close as possible; it does not need to be exact, but closer is better.

![Lining Up the Armatures](https://i.imgur.com/jQaI2sv.png)

### Applying Transformations / Reparenting
Once you have lined up your armatures to the best of your ability, apply the transforms. In object mode select all your objects `Shortcut: A Key` And applying the transformations with `Ctrl + A`.

![applying transformations](https://i.imgur.com/rGpAkws.png)

Next you will need to reparent the meshes to the source skeleton:
1.	First select all the meshes you want to make the pose
2.	Select the Source Pose Skeleton
3.	Right click on the viewport and select `Parent>Armature Deform`


![Changing parent](https://i.imgur.com/pLle4ck.png)


Done! as you can see, the Source Armature's Pose (Red Skeleton) is now properly deforming the Destination Mesh (Blue Model). At this point you can freely delete the Destination Armature (Blue Skeleton) as it no longer is needed for the render.


![enter image description here](https://i.imgur.com/xXkSdn5.png)

While this tutorial demonstrates using a newer format's pose on an older format's skeleton the concepts shown in this tutorial will work for the opposite since the armature is being swapped out entirely.
