Achieved Bugfixes
=================

## List of Bugfixes
- [Fixed the vinedoor animation not working in built versions of the game.](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/348)
  - _/Assets/World/Dynamic/VineDoor/Prefab/VineDoor.prefab_ Fixed by removing a duplicate animator component which was located on the model along with one on the main prefab object. I have no idea why the animation works correctly in the editor and not in the build, but removing this one component (after a lot of debugging) seemed to fix the issue in the builds. It was probably conflicting with the other animator since they were both configure to respond to the same input.

Most of my time was spent helping others and reviewing pullrequests these 2 weeks along with "fixing" performance. The performance changes could technically be called fixes, but I decided to include them in the achieved features document instead. Therefore this document may seem more empty than it probably should.
