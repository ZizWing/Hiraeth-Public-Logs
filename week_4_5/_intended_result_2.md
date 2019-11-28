Intended result 2 - Volumetric Fog
==================

## Description of the result
Ideally we will replace the current placeholder fog effect in level 1 with proper volumetric fog. This will all depend on how it performs since fog can be very demanding. If this is not possible, there are a couple of options:
1. Improve the current fog effect
2. Replace the effect with a new one that doesn't act like an odd 2D texture at certain angles
3. Remove the fog entirely

## Planned tasks
- Investigate volumetric fog in the HD Render Pipeline
- Implement basic volumetric fog on the level
- Improve implementation by adding fog zones/volumes to specific areas
- Add movement to the fog for realism
- Create a "noise" effect in the fog to make it look more like mist clouds
- Investigate performance impact
- Determine whether volumetric fog is a viable option

## Intended learning goal(s)
- Learning how to monitor performance in Unity
- Improve personal recognition of performance-heavy areas/items through tools
  - This may sound the same as the first point, but what I mean here is being able to recognize the causes of performance and improving my own skills at detecting them before they become an issue in the future.
- Learning how to work with volumes (light and fog in this case) and by extension 3D Textures

## Intended integration (Note, the literal translation was something like "The transfer of" in regards to the team.)

### Within the team
Nothing, this becomes a topic of discussion once it has been determined what kind of fog implementation we are going to use.

### Towards other teams
Same as above: This will depend on the results of this task before integration becomes an topic of discussion.
