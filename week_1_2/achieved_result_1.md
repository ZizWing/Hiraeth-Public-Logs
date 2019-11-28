Achieved result 1 - Editor- and scene-specific code execution
===================

## Description
The absorb event for the firefly AI can be called by pressing spacebar, which will trigger it to transition into the absorb state. This behaviour is only present in the "Firefly example scene" scene when played through the Unity editor. In other words: The code snippet responsible for this behaviour does not affect any other scene nor will it affect the final game.

![Scene-specific code execution](https://github.com/HANICA-GAME/sep2018-stud-lucas-van-swaay/blob/master/Project%20-%20Programming/individual/week_1_2/products/Achieved%201/W1-2_A1_Scene_Specific_Code.gif)

|The commit(s)|The scene(s)|The gameobject(s)|The script(s)|
|---------|--------|--------------|----------|
| [0c08f919118f1adff8a2c7e875e40af7be65ea87](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/26/commits/0c08f919118f1adff8a2c7e875e40af7be65ea87) | World\Dynamic\Firefly\_Scene\Firefly example scene | World\Dynamic\Firefly\Prefab\Firefly Swarm | FireflySwarmController

## Found sources
- [How to get scene name in edit mode without #IF UNITY_EDITOR](https://answers.unity.com/questions/1030527/how-to-get-scene-name-in-edit-mode-without-if-unit.html)
> Provided a starting point of the concept of limiting code execution based on the scene. If scene info can be freely accessed it can be combined with the method of limiting code to run in-editor only.

- [How to check which scene is loaded and write if code for it](https://answers.unity.com/questions/1173303/how-to-check-which-scene-is-loaded-and-write-if-co.html)
> The answer to the question by user "IgorAherne" provided me with a near 1:1 example of what I was looking for. A slight alteration of this example was used in the end.

- [#IF UNITY_EDITOR breaks standalone build](https://forum.unity.com/threads/if-unity_editor-script-breaks-standalone-build-solved.471105/)
> One of the first results I came across, which proved to me that editor-only code execution was possible.

## Achieved learning goal(s)
- Learned how to write code for unity that only executes when ran in the editor.
- Learned how to access Scene data.
- Combined the two to limit code execution in-editor within a specific scene for demo purposes in cases of unimplemented events.

## Integration 
> (Note, the literal translation was something like "The transfer of" in regards to the team.)

### Within the team
Not much to mention here, the code has no effect outside it's own scene and thus can't cause issues within the game itself.

### Towards other teams
If similar scenario's happen again, the code can be easily copied and modified to suit a different scene and needs. It also provides easy examples for designers of "could-be" functionality without the need of implementing (for example) fully working AI just to trigger an event on a world object.
