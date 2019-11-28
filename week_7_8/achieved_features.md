Achieved Features
==================

## Feature 1 - Collapsing Bridge
The bridge in level 2 needs to collapse once the Chaserbleddyn runs across the bridge after the player. The initial model for this was a single object with multiple childobjects in the LOD system. This caused issues when attempting to collapse the bridge since adjusting a single LOD object means the others don't move along. Moving the entire object is not an option either since that would look completely out of place.

To get around this I worked with the art team to separate the object into multiple different objects. One for each side of the bridge so we can break it up in the middle, one for the rocks which the bridge is attached to and one for the ropes on the side. This way the ropes and bridge parts can break and/or swing independently and don't require finnicky searching through LOD objects to dynamically match the sides of the bridge together.

As for the final implementation... The bridge snaps in half in the middle when the Bleddyn enters the trigger (also placed in the middle for now). This causes the collisions of the bridge to disappear and everything on it to fall down. Below is a gif showing off this functionality by using the player to trigger the collapse (for ease of use, just imagine a Bleddyn walking there instead).

![BridgeCollapse](https://github.com/ZizWing/Hiraeth-Public-Logs/blob/master/week_7_8/products/BridgeCollapse.gif)

|The commit(s)|The scene(s)|The gameobject(s)|The script(s)|
|---------|--------|--------------|----------|
|[PR #300](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/300)| _Assets/\_Scenes/Level2/Level2Area3.unity_ | _Assets/World/Dynamic/FallingBridge/Prefabs/FallingBridge.prefab_ | _Assets/World/Dynamic/FallingBridge/Scripts/CollapseBridge.cs_ |

## Feature 2 - Adding back Occlusion Culling
Thanks to Leroy we had Occlusion Culling working in an earlier test version of the game. We had some issues with this as objects would pop in and out of view occasionally. The camera also caused some freaky behaviour due to it sometimes clipping through objects and completely hiding anything behind that (in essence hiding most of the game). With a little help from René later on we adjusted the occlusion culling values to prevent most of this behaviour. Some edge cases may still exist. Having Occlusion culling enabled now speeds up scene loading a fair amount due to it only having to render visible chunks of terrain and not an entire area at once.

A short gif of the final version can be seen here:

![occlusion culling](https://github.com/ZizWing/Hiraeth-Public-Logs/blob/master/week_7_8/products/OcclusionCulling.gif)

|The commit(s)|The scene(s)|The gameobject(s)|The script(s)|
|---------|--------|--------------|----------|
| [My commit](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/340/commits/c010f56de9b430ffab7dc2fff961acb744554d58) | _Everything from level 1 & 2_ | _All Scene and Occlusion files_  | _N/A - All changes were made through the editor_ |
| [René's PR #377 with occlusion commits](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/377) | _Everything from level 1 & 2_ | _All Scene and Occlusion files_  | _N/A - All changes were made through the editor_ |

## Feature 3 - Performance optimizations
Technically the occlusion culling was part of this too. Either way: The final performance changes I managed to add were as follows:

- Disabled planar reflections on reflecting water (biggest FPS boost)
- Added back occlusion culling (see above)
- Changed shadow resolution to 512 from 4096 (shadows from dynamic lights were very heavy too)
- Changed terrain heightmap sizes to 513 from 4097 (minimal changes in terrain an a big FPS boost)
- Changed all plant/mushroom lighting to baked instead of realtime (speaks for itself)
- Made a lot of different objects static such as plants, rocks and trees (should have been static but weren't)

Along with these changes I fixed some small scaling issues caused by the integration from the previous scene changes.
All of these changes make it possbile to run the game easily at 60 fps or above should you have a powerful enough graphics card. My own laptop runs it at around 50 fps on a 1920x1080 resolution. It is severely limited by it's 1GB VRAM. Lowering the resolution of the game to 1600x900 runs the game at a (mostly) stable 60-80 fps depending on the scene, with some small dips here and there. This is running on an Nvidia GTX 960M (close to a GTX 750Ti in terms of desktop GPU's). Slightly more powerful GPU's should have no trouble running the game at 60 FPS or more. My GTX 1080 at home runs it somewhere bewteen 120 and 180 fps depending on the scene.

Unfortunately I do not have any accurate readings from before this change since a lot of changes were being made to all scenes. But the build I was on ran at around 20-40 fps on my laptop at 1920x1080 before any changes were made. A significant boost in performance if you ask me.

Due to the nature of these changes I have not included a gif. I could show a before and after of an fps counter, but that's just extra work for very little in return. Besides, there's no easy way for me to prove what hardware and game version it runs on all in the same gif, so this would make it even less obvious.

|The commit(s)|The scene(s)|The gameobject(s)|The script(s)|
|---------|--------|--------------|----------|
| [PR #340](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/340) | _Everything from level 1 & 2_ | Reflective water, shadow map, occlusion map, terrain heightmap, almost all plants/rocks | _N/A - All changes were made through the editor_ |

Note: this pullrequest contains all performance tweaks except for the final occlusion culling changes made by René at a later date.
