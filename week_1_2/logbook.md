# Logbook

# Week 1

## Monday
Maurice's statemachine was ready for use and thus I started to implement my firefly AI into the statemachine. Maurice taught me how the statemachine worked during the proces. Note: the logbook was not yet available on this day so a rough estimation of the time was made.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 5 | Integrating firefly AI with the statemachine | Maurice Berentsen | Learned how to use the statemachine and successfuly implemented firefly AI into statemachine minus player-related states (absorb) | [Implemented statemachine into firefly AI](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/21) |


## Tuesday
The individual file structure was sent to us today, therefore any logs before this point were recreated based on rough estimates.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 1 | Setting up and translating the individual assignment files | N/A | These files | N/A |
| 2.5 | Implementing Firefly absorb state and teaching statemachine workings through pair programming | Davey Jochems | Successful implementation of absorb state, but lacking a way to trigger it | [PR - Implemented absorb state](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/26) |
| 0.5 | Adding a photo & personal description for the website | N/A | Text & photo | [Text](https://docs.google.com/document/d/1WIomCnjm7wHlWz0a9s0BPYjcCkQH6GJOKEV0cHPlPMk) & [Photo](https://drive.google.com/drive/folders/1-4w0JUhAhpfJ_18yROo4BHi-BcTxSsUE) |
| 1 | Refactoring firefly settings and code clean-up | N/A | Improved firefly behaviour from setting changes and reduced load on statemachine | [PR - Implemented absorb state](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/26) |

## Wednesday
Due changes to our file structure, the rebase of the firefly branch took a lot of time to resolve conflicts.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 2 | Rebase and merge of firefly branch into development | Leroy Hermans | Successful merge | [PR - Implemented absorb state](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/26) |
| 1 | Implemented event system for firefly absorb state | N/A | Firefly now transitions to absorbs state when the appropriate event is called | [Commit - Implemented CastFirefly event behaviour](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/26/commits/0c08f919118f1adff8a2c7e875e40af7be65ea87) |
| 2 | Started research of particle system for leaves (foliage interactions) | René | Tested some basic particle system functionality and searched around for tutorials | N/A |
| 1 | Wrote the first research of week 1-2 and configured gif tool | N/A | First intended and achieved result documented | [intended](https://github.com/HANICA-GAME/sep2018-stud-lucas-van-swaay/blob/master/Project%20-%20Programming/individual/week_1_2/_intended_result_1.md) & [achieved](https://github.com/HANICA-GAME/sep2018-stud-lucas-van-swaay/blob/master/Project%20-%20Programming/individual/week_1_2/achieved_result_1.md) |

## Thursday
Started messing around with my own implementation of the particle system for fireflies. Initial results show a lot of promise.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 0.5 | Messed around with the skybox to try and fix the cubic appearance | Maurice | Got a cylindrical effect working but it requires a different texture | N/A (I showed it to Maurice and he did a proper implementation himself) |
| 4 | Implemented firefly flocking with particle system | N/A | similar behaviour with around 4x the performance and slightly less smooth transitions | [Commit - Added alternate firefly swarm based on particle system](https://github.com/HANICA-GAME/sep2018-game-hireath/commit/f796d133656b790ecf61d69118e24fb525eb68b3) |

## Friday
Further implemented particle system for fireflies. I'm now confident the entire behaviour can be implemented through a mix of the particle system and small scripts.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 6 | Implemented player avoidance and improved flocking for fireflies | Leroy Hermans | Approximately 10-15 times performance increase compared to initial implementation | [Added alternate firefly swarm based on particle system (flock & return only](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/63/commits/ab04de634c72e6497c23bb16e35acfbd36bb6405) |

# Week 2

## Monday
Implemented the remaining changes of the firefly behaviour with the particle system. This includes absorb, repositioning and refactoring/updating off editable settings.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 5 | Implementing absorb and reposition functionality for fireflies | N/A | Successful implementation with the particle system | [PR #63 - Changed firefly implementation to particlesystem](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/63/commits/cd3102a5128b210b47a56862fc4abced711b9eaf) |
| 1 | Refactoring and finalizing of editable settings | N/A | Reduced amount of settings needed to modify behaviour and added some missing details like color | [PR #63 - Changed firefly implementation to particlesystem](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/63/commits/cd3102a5128b210b47a56862fc4abced711b9eaf) |

## Tuesday
This dat integration officially started in full force. Most of my time was spent fixing bugs that appeared through integration. Any remaining time was spent working on the individual assignments.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 2 | Fixed a bug with firefly repositioning auto-calling after absorb | N/A | Reposition event now only calls 1 time instead of multiple in some cases. | [PR #64](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/64) |
| 1 | Fixed a bug with firefly particle count not saving properly between runs | N/A | Eventlisteners are now enabled and disabled together to prevent issues with them being overwritten elsewhere | [PR #66](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/66) |
| 1 | Experimented with some lighting on the particlesystem | N/A | Nothing worth mentioning, got interrupted with fixing bugs | N/A |
| 1 | Logged research of particle system | N/A | Fully logged the intended result and added sources to achieved result | [W2 - Intended Result 2](https://github.com/HANICA-GAME/sep2018-stud-lucas-van-swaay/blob/master/Project%20-%20Programming/individual/week_1_2/_intended_result_2.md) & [W2 - Achieved Result 2](https://github.com/HANICA-GAME/sep2018-stud-lucas-van-swaay/blob/master/Project%20-%20Programming/individual/week_1_2/achieved_result_2.md) |


## Wednesday
A little over half the day I spent my time working on writing down my findings of the particle system. Once new potential tasks for the next sprint started becoming clear I spent some time on researching destructible objects for that.

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 3 | Logging intended and achieved result 2 of week 1-2 (make gifs, link commits, link sources, describe everything...) | N/A | Fully logged achieved and intended results 2 of week 1-2 | [Intended](https://github.com/HANICA-GAME/sep2018-stud-lucas-van-swaay/blob/master/Project%20-%20Programming/individual/week_1_2/_intended_result_2.md) & [Achieved](https://github.com/HANICA-GAME/sep2018-stud-lucas-van-swaay/blob/master/Project%20-%20Programming/individual/week_1_2/achieved_result_2.md) |
| 1.5 | Researching destructable object implementations | N/A | Found multiple sources of a couple different approaches. No perfect solution yet. | N/A |

## Thursday

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 3 | Testing SimpleMeshExploder implementation for destructible objects | N/A | Works on relatively simple meshes but looks bad and causes inconsistent performance dips | [SimpleMeshExploder Test commit](https://github.com/HANICA-GAME/sep2018-game-hireath/commit/65ca5cd65761dcea2683692a76e400b10ba6405e) |
| 3 | Testing a particle implementation similar to SimpleMeshExploder | N/A | Works without performance issues but may look weird without physical objects being included | [Semi-dynamic particle explosion commit](https://github.com/HANICA-GAME/sep2018-game-hireath/commit/cb41ab4f48d802776e077fcde93a8c571c76e274) |

## Friday

| Hours | Task | With Who | Result | Link |
|-------|------|----------|--------|------|
| 2 | Helped Maurice search for the cause of reflective terrain in the new render pipeline | Maurice | Tried pretty much every setting we could find with minor changes as a result. No solution found yet. | N/A |
| 1 | Added a single lightsource to the fireflies and tested performance impact | N/A | Performance impact was unnoticable. Proper implementation will follow. | N/A (will follow with proper implementation) |
| 0.5 | Fixed firefly positioning from terrible thursday | N/A | Fireflies are no longer stuck to the ground and can't navigate themselves with the navmesh | [PR #97](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/98) |
| 1 | Researched some more alternatives for destructable objects. | N/A | No viable alternative found. | N/A | 
