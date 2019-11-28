Intended result 2 - Firefly Particle System Implementation
==================

## Description of the result
The plan is to implement the fireflies using the particle system in order to increase performance (and at the same time learn how to use the particle system). Based on some limited knowledge beforehand, the noise module could be used as a substitute for the manual flocking behaviour, assuming particles can be easily kept within a defined space. Further changes such as absorbing them would have to be done through state changes, adjusting the particle system at runtime or both.

## Planned tasks
- Implement flocking through the particle system.
- Prevent particles from leaving the swarm radius.
- Change particle behaviour when the player gets close (flock around him).
  - Potentially the same as preventing the particles to leave the swarm radius, but with a different target.
- Implement absorb behaviour.
- Implement reposition behaviour (when player cancels the ability).
- Adjust particle settings based on scriptable object (Stats).

The tasks are mostly planned to be performed alone, but René also needs to research the particle system for his own tasks and we plan on helping each other out with issues when needed.

## Intended learning goal(s)
- Learning how to properly set up a (semi-)complex particle system through the Unity editor.
- Learning how to include custom behaviour to the particles through scripts.
- Learning the (rough) performance differences between using a particle system and using regular objects.

## Intended integration 
> (Note, the literal translation was something like "The transfer of" in regards to the team.)

### Within the team
Nothing worth mentioning, we briefly discussed whether using the particle system was worth investing time into. Given the early state of the project and the fact that no major integration has happened yet. A large change in object functionality is deemed possible as long as it happens before the integration team starts.

### Towards other teams
#### Programming (Player & UI) Team:
To make sure my efforts towards the particle system wouldn't be in vain, I discussed with the player programming team whether it would be viable to implement a new firefly version before the end of the first sprint. Since we decided to use events to indicate different states of objects and the player's abilities, the change in implementation should have no impact on the functionalities of either team. As long as the correct events are called at the corresponding time, neither of the teams need to care what each other's objects look like or how they react.
