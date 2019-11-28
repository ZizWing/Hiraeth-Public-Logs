Achieved Bugfixes
=================

## List of Bugfixes
- [Added firefly sprite animation to original particlesystem](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/235)
  - _Assets/World/Dynamic/Firefly/Materials/SpriteSheet_ (Added spritesheet and material)
  - _Assets/World/Dynamic/Firefly/Prefab_ (Changed particle system component settings)
- [Updated firefly spritesheet to new sprites](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/268)
  - _Assets/World/Dynamic/Firefly/Materials/SpriteSheet_ (Updated spritesheet and material)
- [Re-tuned firefly values for smaller scale](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/247)
  - _Assets/World/Dynamic/Firefly/Prefab_ (Changed particle system component settings)
- [Fix/world scaling](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/244)
  - A bit tricky to point to, but every scene has an empty game object named "area #" where # is the number of said area. This area object was rescaled along with the terrain. Everything else is a child object and thus automatically scales along with it. Some minor things were corrected in the fix stated below. The Scenes are located in _\_Scenes/Level 1_ In order to actually play the game, you need to unload all scenes except the _Master_ scene though. The Sceneloader takes care of the rest. If viewing the scene in the editor is enough then simply open whatever scene you need.
- [Fix/level 1 small plant placement](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/256)
  - Literally every plant with a lightsource has had their transform adjusted. Some were underground, some floated and some of their light was blocked by objects. The prefabs were not changed in any significant way, only the range and intensity of their lightsources slightly. All other changes are in-scene positions. Therefore no real path is available here. See the scene paths from the fix above to find the relevant scenes.
