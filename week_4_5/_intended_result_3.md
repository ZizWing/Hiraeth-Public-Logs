Intended result 3 - Performance research
==================

## Description of the result
The plan is to start working on performance improvements soon. My own laptop is starting to struggle with the game and it isn't even that bad in terms of performance. The most relevant specs are:
- Intel I7 6700HQ
- Nvidia GTX 960M
- 8GB DDR4 RAM

This should be enough to run a game with our visual fidelity at the very least stable above 30 FPS and most likely at 60 FPS as well. Right now it struggles to keep above 30 in certain areas whereas in others it can reach 60 fairly consistently. Lots to optimize it seems.

Considering we're nearing the feature-freeze in week 7, I'd like to get some research done instead of going in blind with only 2-ish weeks until the final deadline. As such, the achieved result may not contain much (if any) results yet and will most likely consist of potential performance gains that I will start working on in the coming weeks.

## Planned tasks
I have seen a couple of settings in the editor that relate to performance. Some examples are GPU instancing, texture sizes, LOD and culling systems and built-in quality settings. These may provide some basic performance gains, but I also intend on minimizing any bottlenecks I can find through the profiler. I will need to figure out how to properly interpret the profiler and how to use it in a built version of the game for more accurate readings. Finally I would like to try and use one of Unity's recommended performance optimizations, which is the combining of meshes. This can reduce draw calls significantly but it seems to require a partially custom implementation based on the assets used. This could be a big performance increase if done properly though.

## Intended learning goal(s)
- Learn how to read Unity's profiler and determine bottlenecks in our game.
- Learn how to profile outside the editor to exclude the editor from influencing the performance.
- Investigate whether GPU instancing is viable and if so, how to use it.
- Learn how to properly combine meshes to reduce draw calls.
- Learn how to manage LOD and culling distances within the editor.

## Intended integration 
> (Note, the literal translation was something like "The transfer of" in regards to the team.)

### Within the team
None for the moment.

### Towards other teams
None for the moment.
