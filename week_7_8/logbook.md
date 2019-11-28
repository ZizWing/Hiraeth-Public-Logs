# Logbook

## Week 7

### Monday
Slow start after the vacation with a bit of waiting until the lead meeting was done. Got time to update some personal documents, followed by tasks resulting from the lead meeting.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 2 | Updating all reflections up until now | N/A | Updated reflections (ready for feedback) | _See reflection of each week_ |
| 2.5 | Started working on the destructible bridge. | N/A | Bridge was given better collision, but the way LOD is implemented prevented proper collapsing. Collapse is non-functional. | [Commit](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/300/commits/e5cc248a8b2c81e51cfa50d8acb636ae3631c485) |


### Tuesday
Further work towards implementing the bridge collapse. Almost got it all working, just need to implement the trigger and Bleddyn interactions.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 6 | Implementing a new bridge variant and its collapse functionality | Robin & Rose (Art) | Replace old bridge with new objects that can be controlled separately and added collapse mechanic (no trigger yet). Also made the bridge navigable by AI. | [Commit 1](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/300/commits/c69fe4b9c0f0a25fbbee2ecd655bd4518700aae1) & [Commit 2](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/300/commits/caa3e7a0785ee935af9a5fff79e78c2f9571847a) |

### Wednesday
Finalizing the collapsing bridge and the start of my second attempt at increasing performance.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 1.5 | Added trigger to bridge collapse and made Bleddyn fall properly with physics. | N/A | Fully functional bridge collapse. | [Commit](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/300/commits/a0c34ccfebd69339888746beb630b5f0775bef65) |
| 1.5 | Making a development build to profile | _patience and boredom_ | A working dev build and working build cache on my machine (reduces build times to reasonable times (~15 minutes at most) | N/A |
| 1 | Profiling the first dev build for signs of performance heavy workloads | N/A | Approximately a third of the frametime is lost to terrain rendering (heightmap mostly) and another sizeable chunk to shadows. | N/A |

### Thursday
Final day of performance research. The art team was busy modifying most scenes so changing performance across the board would prove difficult without conflicts. Therefore more time was put into prototyping performance changes locally to ensure quick implementation on friday.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 5 | Prototyping (and a little research) of performance optimizations | N/A | Got all improvements working before the end of the day and made notes to ensure quick implementation the next day with the updated scenes. | N/A |


### Friday
This day I was almost pulled away from performance optimizations due to being required to build the game twice for testing. This came up last minute and my laptop was the only one with a build history (that saves time with shader compilation being cahced). The first half of the day was lost due to this. The rest of it was dedicated to implementing the performance changes.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 3 | Last-minute builds for requested testing | N/A | I was unable to continue working due to the heavy load on my laptop from building. I attmepted to help as pair programmer with bugfixes around me. | N/A |
| 2.5 | Implementing performance optimizations in the updated scenes. | N/A | Succesfull implementation and an increase of at least 20 frames per second on my own laptop. General improvements across the board for everyone. | [PR #340](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/340) |

## Week 8

### Monday
A day of bugfixing, integrating and fine-tuning before the final deadline. I was busy with fixing the vinedoor animation which did not work in built versions of the game. After that I was mostly doing pullrequest reviews to make sure as many fixes and integrations made it through before the deadline of the day after. I helped out looking at fixes on demand though.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 2.5 | Fixing the vinedoor animation in built versions of the game | Maurice & Robin (art) | Working animations in all game versions (editor & built) | [PR #348](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/348) |
| 3.5 | Reviewing PR's and helping out where possible. | Mostly World & AI programming team members | most changes got approved and integrated excluding some final audio and art changes. | [Filtered list of PR's involving myself](https://github.com/HANICA-GAME/sep2018-game-hireath/pulls?utf8=%E2%9C%93&q=is%3Apr+involves%3AZizWing+is%3Aclosed+merged%3A2019-01-14) |

### Tuesday
The day of the final presentation. Last minute bugfixes and adjustments were being made across the board. Myself and many others no longer had any official tasks left besides "help fix things". As such we were all over the place and things did not get logged all that well. The best I can do is show a list of PR's involving myself and mentioning that I helped out solving issues in pair-porgramming style multiple times, though there is no evidence for this.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 4 | Final PR reviews and fixes being applied | Anyone that asked me for help (I never kept track) | In the end all changes were integrated except we forgot to re-bake the navmehs on the destrcutable bridge. A lot of bugs also appeared in the demo in the end. | [Filtered list of PR's involving myself](https://github.com/HANICA-GAME/sep2018-game-hireath/pulls?utf8=%E2%9C%93&q=is%3Apr+involves%3AZizWing+is%3Aclosed+merged%3A2019-01-15+) |

### Wednesday through Sunday
The remaining time this week was used for everyone to finish these personal documentation files. As such I have skipped logging this since the project is technically over. If you want to see the history of these files just look at this repo's commit history from january 16th 2019 and onwards.

## Week 9
The week of ICA-Presents, the final demo. During this week we plan on fixing as many bugs as we can and really polishing up everything we can. Myself and (most likely) René will look into lighting actually being able to bake lightmaps in less than 40 hours per scene. Everything else is up for debate at this point. This falls outside the official project hours and as such cannot be logged anyway.
