Achieved Bugfixes
=================

## List of Bugfixes
See [this commit](https://github.com/HANICA-GAME/sep2018-game-hireath/commit/7462a12764caf84cf157831d0f28dc88cbf7a18c) for the code that got changed from all the bugfixes after terrible thursday.

The list of fixes included in the commit:
- Fixed Bledyn AI seeing the player as an obstacle to avoid.
  - _Hiraeth/Assets/NPC/Bleddyn/Scripts/BleddynController.cs_
  - _Hiraeth/Assets/NPC/Bleddyn/Scripts/FieldOfView/FieldOfView.cs_
  - _changes in the editor (obstacle layermask and player tags) on Bleddyn 2 of Area2_
- Fixed Player bodyparts all containing a "Player" layer, confusing and breaking the Bledyn AI.
  - _Made changes in the editor to set the player in it's entirety back to the default layer and only include the highest object in the hierarchy into the player layer._
- Fixed LineRenderer OutOfBounds error
  - _Hiraeth/Assets/Player/Scripts/Ability system/Scripts/RayCastShootTriggable.cs_
- Removed player velocity debug log spamming constantly
  - _Hiraeth/Assets/Player/Scripts/Player movement/CharacterController.cs_
- Fixed linerenderer using worldspace instead of local space
  - _(Changes in the editor) See "testModel (29-11-2018)" Line Renderer component_
- Set line renderer size to 1 (paritally fixes weird scaling issue)
  - _(Changes in the editor) See "testModel (29-11-2018)" Line Renderer component_

There are still glaring issues with the player, which include the positioning of the model and the collisions with the terrain. These issues are not up to me to fix; this is left to the player- and ui-team. The fixes I applied allow us to continue working with what we've got so we can test things in an integrated state properly.

To view the fixes in the editor, please load the scene at _Assets/\_Scenes/Level 1/Level 1.unity_ and make sure _Area1_, _Area2_ and _Area3_ are included in the scene and loaded.
