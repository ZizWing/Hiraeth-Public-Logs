# Logbook

## Week 4

### Monday
On this day it was required to upgrade to a new unity version to fix a bug with the terrain collision. For some reason specifically my laptop did not like this Unity installation. On my laptop exclusively the package manager was missing which caused many errors with packages and even started giving out kernel errors. The entire day was spent trying to find solutions for the missing package manager and attempting re-installations and such.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 6 | Upgrading Unity to version 2018.3.0b12 | N/A | A still broken Unity but with a partially restored package manager | N/A |


### Tuesday
Since I installed the new Unity version in parallel I was able to perform some much needed cleanup of the development file hierarchy. A large change in assets was coming this week so I took this chance to remove any unnecessary files (such as duplicates) from the hierarchy and correctly ordened things to prevent clutter in the root. Things became quite a mess rather quickly so I decided to make a small activity diagram to indicate the proper file structure in order to keep things clean and organized. Any remaining time went towards fixing the Unity package manager.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 2.5 | Cleaning up the file hierarchy & documenting the structure | Maurice & Leroy (deciding on what can be removed etc.) | A clean root directory in development | ![Diagram](https://github.com/HANICA-GAME/sep2018-stud-lucas-van-swaay/blob/master/Project%20-%20Programming/individual/week_4_5/products/Week%204%20File%20Hierarchy/Unity%20File%20Hierarchy%20Diagram.png) |
| 3 | Fixing the Unity package manager | N/A | Resotred packages and Unity is capable of running again | N/A |

### Wednesday
After having fixed Unity's package manager, the Wwise integration appeared to be broken as well. No audio was being played and it started spewing out hundreds of nullreferences on it's own scripts. Besides a small change to exclude the project file from version control (which is recommended by Wwise due to locking), I did not manage to find any fix for this issue. In the end I was able to rectify the issue by completely removing the local clone of the repository and re-cloning it. According to git there were no changes in the project, so it had to be something local to my machine. I still have no idea what caused Wwise to break so I hope it doesn't return in the future.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 6 | Fixing Wwise integration | N/A | Excluded Wwise project file (for caching) from git | [Commit](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/145/commits/ab196555255ef65ca236a3a8ec1d82f62b0fb0de) |

### Thursday
The fog in level 1 that was shown off at the last terrible thursday was just a placeholder cloud used as fake fog. On this day I started to look into a proper implementation of fog to make it look less obviously placeholder.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 3 | Creating columetric fog with adjustable placeable volumes | N/A | Fog capabilities across the entire scene with a single large fog volume in area 2 of level 1 | [Commit](https://github.com/HANICA-GAME/sep2018-game-hireath/commit/5eba1bb3df33da9c7788aeeaac4ae0733793be63) |
| 2 | Experimented with 3D textures to create fog clouds | N/A | Spherical clouds of fog that move slowly across the terrain | [Commit](https://github.com/HANICA-GAME/sep2018-game-hireath/commit/36e31b6cdafa2d1e5e02a706ab6fd3f53d4b2865) |
| 0.5 | Investigated performance dip around area 3 | N/A | Nothing yet, but area 3 appears to drop performance significantly |  |

### Friday
This day was mostly spent monitoring performance in hopes of finding a solution for the sudden performance drops in certain areas.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 4 | Investigated performance of level 1 with the profiler | N/A | Determined the performance cause of area 3 being either terrain or lighting. Also noticed a process "Gfx.WaitForPresent" taking up significant processing time. It is unclear what exactly this proces does, but it looks like it's waiting for GPU response (a.k.a. GPU bottleneck) | N/A |
| 1 | Experimented with removing various objects form the scenes in order to minimize the performance impact | N/A | Other than removing terrain or lighting, no significant performance gains were found. | N/A |

## Week 5

### Monday
Further research into performance improvements. I managed to find an updated tutorial that covers combining meshes and it's textures. I also discovered that we may be able to use git's Large File Storage (LFS) to reduce some long wait times. This was put on hold due to the coming terrible thursday and a fear of breaking things.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 4.5 | Researched performance optimization techniques | N/A | Found multiple potential improvements that could apply to our project. | Research is described [here](https://github.com/HANICA-GAME/sep2018-stud-lucas-van-swaay/blob/master/Project%20-%20Programming/individual/week_4_5/_intended_result_3.md) as of now. Results will follow later. |
| 0.5 | Looked into Git Large File Storage (LFS) | N/A | Configuration may be missing, could lead to faster git functionality of fixed. (No priority until after Terrible Thursday) | N/A |


### Tuesday
A rather slow day of working on pullrequests and fixing issues together with other members of the team.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 1 | Helped with the reviewing of some PR's | N/A | Succesfully added features | [Filtered list of PR's from tuesday](https://github.com/HANICA-GAME/sep2018-game-hireath/pulls?utf8=%E2%9C%93&q=is%3Apr+is%3Aclosed+involves%3AZizWing+merged%3A2018-12-11+) |
| 3 | Further research into performance and mesh combining | N/A | Found an updated tutorial for creating custom combine implementations including materials this time. | Research is described [here](https://github.com/HANICA-GAME/sep2018-stud-lucas-van-swaay/blob/master/Project%20-%20Programming/individual/week_4_5/_intended_result_3.md) as of now. Results will follow later. |

### Wednesday
I spent all day working on reviewing pull requests, helping people fix issues I found and in general assist where possible.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 6.5 | Reviewing PR's and assisting in fixing issues I encountered. | Programming & Art teams (anyone who put up a PR I reviewed) | Updated assets were added and lots of fixes went in. The player was not yet integrated unfortunately. | [Filtered list of PR's from wednesday](https://github.com/HANICA-GAME/sep2018-game-hireath/pulls?utf8=%E2%9C%93&q=is%3Apr+is%3Aclosed+involves%3AZizWing+merged%3A2018-12-12) |

### Thursday
Terrible thursday. Implemented and fixed a lot of assets from the days before and fixed various issues that appeared. The biggest problem was the player being integrated from a very old development build, which caused old files to be re-inserted. We ended up reverting to an earlier commit and removed the new player in order to add it later in a more stable state.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 4.5 | Integrating and fixing assets for terrible thursday | Programming & Audio teams | animated bleddyn, updated tree/plat prefabs and improved audio implemented. (and some smaller fixes) | [Filtered list of PR's from thursday](https://github.com/HANICA-GAME/sep2018-game-hireath/pulls?utf8=%E2%9C%93&q=is%3Apr+is%3Aclosed+involves%3AZizWing+merged%3A2018-12-13+) |


### Friday
Optional informative generic comment about this day.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 1 | Updated some missing logs in the personal files | N/A | Roughly up-to-date logs | _This document_ and [intended result 3](https://github.com/HANICA-GAME/sep2018-game-hireath/pulls?utf8=%E2%9C%93&q=is%3Apr+is%3Aclosed+involves%3AZizWing+merged%3A2018-12-12) |
|  |  |  |  |  |
