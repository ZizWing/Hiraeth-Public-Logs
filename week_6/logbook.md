# Logbook

## Monday
This full day was spent on getting the first prototype for the MeshCombiner working.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 6 | Created MeshCombiner prototype | N/A | Functioning prototype, but it only works correctly with meshes that have only 1 material. | [MeshCombiner commit history](https://github.com/HANICA-GAME/sep2018-game-hireath/commits/enhancement/optimized-mesh-combine-and-occlusion) and [the most representative commit](https://github.com/HANICA-GAME/sep2018-game-hireath/commit/ce3f852044cf347c84f42d825dfcfefac53d831c) |


## Tuesday
Spent most of the day improving the MeshCombiner to make sure it works correctly with submeshes and multiple materials per mesh.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 6.5 | Adding multi-material support to the MeshCombiner | N/A | Multi-material meshes now combine correctly, but exceeding 65535 vertices breaks meshes and vertices are multiplied by the amount of materials somehow. | [MeshCombiner commit history](https://github.com/HANICA-GAME/sep2018-game-hireath/commits/enhancement/optimized-mesh-combine-and-occlusion) and [the fix commit](https://github.com/HANICA-GAME/sep2018-game-hireath/commit/202d41b5787e96fc6bd2edf82f6d31145f2e4183) |

## Wednesday
Most of the day was spent on preparing things for terrible thursday, but Marco came  by to take a look at the MeshCombiner in order to figure out what was going wrong with the vertices. We figured it out eventually but also decided to leave the combiner for later since performance gains would be minimal compared to the time investment. I still plan on finishing it for personal use outside of the project at some point.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 1.5 | Investigating MeshCombiner vertices issue and performance impact | Marco | Decided to leave it as-is for now and return to it when needed due to required time investment versus performance gains. | N/A |
| 2 | Added sprite animation to firefly particles | Robin | Animated fireflies based on their movementspeed | [PR #235](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/235) |
| 2.5 | Scaled down level 1 (area 1-3) | N/A | Properly scaled level 1 in relation to level 2 and the player prefab. Some minor tweaks required for dynamic objects (shrine, fireflies, vines, etc.) | [PR #244](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/244) |

## Thursday
The entirety of this day was spent fixing and integrating things for terrible thursday. Many things happened while working together with different programmers (and on their devices), which means a lot will be hard to log here.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 4.5 | Implementing things for release 0.4 (terrible thursday) | I honestly didn't keep track... about half the programming team. | Despite some minor last minute bugs, everything that was planned was implemented and worked correctly. | [Filtered list of PRs](https://github.com/HANICA-GAME/sep2018-game-hireath/pulls?utf8=%E2%9C%93&q=is%3Apr+is%3Aclosed+involves%3AZizWing+merged%3A2018-12-20+) |


## Friday
The day before the Christmas vacation. A slow day with a lot of people leaving early or working from home. I spent most of my time working on these peronal files of this week to ensure everything is up-to-date. Other than that I worked on fixing the remaining bugs from the terrible thrusday with those who were here.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 1 | Logged week 6 | N/A | Up-to-date logs of everything before the vacation | _These documents_ |
| 3 | Stuff and things | No idea | Something | I forgot to log at the end of the day and noticed after the vacation (2 weeks later). No clue what I did the rest of the day. |
