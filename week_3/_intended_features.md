Intended Features
==================

## List of Features
- Fireflies with added (adjustable) lighting.
- Destructable trees on a basic level where they fall over if certain entities collide with it
  - Includes particle effects and physics

## Planned tasks
### Firefly lighting
- Determine whether particlesystem lighting or regular lighting is more appropriate for a swarm
- Center the light in the swarm
- Dimm/scale the light based on the swarm size

### Destructable trees
- Detect collision with player
- Enable physics on collision
- Add particle effect at point of impact
- Spawn a treestump when the tree breaks
- Make particles, physics and stumps adjustable in the editor
- Add leaf particles with its own collision (e.g. when it falls over and touches the ground)
