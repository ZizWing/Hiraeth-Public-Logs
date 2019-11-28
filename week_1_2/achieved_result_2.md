Achieved result 2 - Firefly Particle System Implementation
===================

## Description
The fireflies flock smoothly within a specified range. Once they leave the range they immediately move back towards the swarm range. If the player is in range the swarm radius increases to allow the fireflies to flock around the player. They also try to avoid the player if he gets too close. Once in range the player can absorb the fireflies by calling an event, which in turn moves all the fireflies towards the player and destroys them. If the player decides to cancel the ability, the swarm repositions itself on the player and re-forms itself. The re-forming of the swarm is still very sudden and could be smoothed out in the future. The fireflies also don't give off any light yet, which could be added in the future.

Below are some gifs of the behaviour with the new particle system.

Flocking:
![Flocking](https://github.com/HANICA-GAME/sep2018-stud-lucas-van-swaay/blob/master/Project%20-%20Programming/individual/week_1_2/products/Achieved%202/Particle%20Flocking.gif)

Player Evasion:
![Player Evasion](https://github.com/HANICA-GAME/sep2018-stud-lucas-van-swaay/blob/master/Project%20-%20Programming/individual/week_1_2/products/Achieved%202/Particle%20Evade%20Player.gif)

Absorb and Reposition:
![Absorb and Reposition](https://github.com/HANICA-GAME/sep2018-stud-lucas-van-swaay/blob/master/Project%20-%20Programming/individual/week_1_2/products/Achieved%202/Particle%20Absorb%20%26%20Reposition.gif)

Regarding the performance of the particle system... Here is a comparison between the two implementations. Please note that the recording software reduces the performance in both versions by a fair amount, but this should not make a huge difference for the results. Both scenes are roughly targeting a framerate of 60 FPS, but neither has been configured to perfectly match this value. The idea is that the difference in particle/object count shows the significance of the particle system, while roughly keeping within reason of the target framerate.

GameObject implementation (2500 objects):
![Performance Object Implementation](https://github.com/HANICA-GAME/sep2018-stud-lucas-van-swaay/blob/master/Project%20-%20Programming/individual/week_1_2/products/Achieved%202/Performance%20Object%20Implementation%20(2.5k).gif)

Particle implementation (15000 particles):
![Performance Particle Implementation](https://github.com/HANICA-GAME/sep2018-stud-lucas-van-swaay/blob/master/Project%20-%20Programming/individual/week_1_2/products/Achieved%202/Performance%20Particle%20Implementation%20(15k).gif)

As demonstrated by the gifs, the particlesystem can have many more particles on-screen than it can with objects. It is also visible in the gif that non-scripted behaviour (flocking without player interferance) is much faster. The object implementation only gains a minimal performance boost when the player is not in range due to them running completely on scripts.

> Also provide a link to all commits (or the last commit related to the result). Make sure it is clear which scene(s), objects(s) and scripts are relevant in order to view the results in Unity. To do so, use the table below.

|The commit(s)|The scene(s)|The gameobject(s)|The script(s)|
|---------|--------|--------------|----------|
| [PR #63](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/63) |  Hiraeth/Assets/World/Dynamic/Firefly/\_Scene/Firefly example scene | Hiraeth/Assets/World/Dynamic/Firefly/Prefabs/Firefly Swarm | Hiraeth/Assets/World/Dynamic/Firefly/Scripts/ _Everything In This Folder and Subfolders_ |
| [PR #64](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/64) | Hiraeth/Assets/World/Dynamic/Firefly/\_Scene/Firefly example scene | Hiraeth/Assets/World/Dynamic/Firefly/Prefabs/Firefly Swarm | Hiraeth/Assets/World/Dynamic/Firefly/Scripts/FireflyEventListener |
  | [PR #66](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/66) | Hiraeth/Assets/World/Dynamic/Firefly/\_Scene/Firefly example scene | Hiraeth/Assets/World/Dynamic/Firefly/Prefabs/Firefly Swarm | Hiraeth/Assets/World/Dynamic/Firefly/Scripts/FireflySwarmController |

## Found sources

1. [Everything to know about the PARTICLE SYSTEM](https://www.youtube.com/watch?v=FEA1wTMJAR0) 
> Provides a quick overview of the common in-editor modules and their settings you can edit to create a particle system.

2. [Unity Live Training Session - Visual Effects with Particles](https://unity3d.com/learn/tutorials/topics/graphics/introduction-and-goals?playlist=17102) 
> An 8-part tutorial/demonstration of the creation of a fire effect using the Unity particle system. This provides a good example of the impact of different settings within the system and what you can do with them.

3. [Particle system move to player](https://forum.unity.com/threads/solved-particle-system-move-to-player.436507/)
> A bunch of examples are given in this forum to solve the problem of moving particles towards a single point. In the end this did not work for me since this would require a singular effect and cannot be directly applied to existing particles. In the end I used my own script to create the desired behavior.

4. [ScriptReference ParticleSystem.GetParticles](https://docs.unity3d.com/ScriptReference/ParticleSystem.GetParticles.html)
> Since the particle system uses structs underwater, this particular documentation provided an example of the correct usage of the particle system within scripts. In particular the initialization of the particle array and applying them again through SetParticles was out of the ordinary.

5. [Possible to change position of individual particles?](https://forum.unity.com/threads/possible-to-change-position-of-individual-particles-shuriken.139156/)
> Replies in this forum explained the inner workings of the particle system which, together with point 4, helped me understand the basics of controlling the particle array of a particle system.

6. [Restrict particles inside a Mesh](https://answers.unity.com/questions/224967/particles-restrict-particles-inside-a-mesh.html)
> One of multiple forum/question pages asking about constraining particles within a mesh. Since particle collision is possible and editable easily through the editor, one of my first ideas was to create an inverted mesh of a sphere and have the particles bounce around inside it. This turned out not to work very well and had very little good info to back up this method. (There were more sources for this but I forgot to save them.)

7. [Unity - Displaying Particles Via Script](https://unity3d.com/learn/tutorials/topics/scripting/displaying-particles-script)
> A tutorial that explains some basic functionality for manually emitting particles with a script. I used this briefly before deciding to switch to using bursts instead. The bursts can be called at set intervals and provide an easy way to instantly spawn the required amount of particles on relocation of the swarm. This way I can keep the lifetime of the particles infinite and don't need to worry about the lifetime or spawnrates of particles.

## Achieved learning goal(s)
- I now have a basic understanding of the capabilities of the particlesystem and am confident in my ability to create some basic effects without too much trouble.
- I can succesfully modify individual particles (or all at once) through scripts. Behviour does conflict with particle system controlled movement and such, but this is a matter of finding a balance between controlling particles through scripts or the system only where needded.
- As shown in the gifs above, I have learned that the particle system is many magnitudes more performant than using regular objects (as expected) and that I should use it whenever possible. I am curious how the Entity Component System would factor into this, but that is something for another time.

## Integration (Note, the literal translation was something like "The transfer of" in regards to the team.)

### Within the team
Nothing to note here. Working on the fireflies was a mostly individual job without any dependencies in our team (so far).

### Towards other teams
Considering there already was a firefly swarm fully functioning at this point, my main goal was to implement a new version which has the exact same outgoing events. This ensures other teams won't notice a difference in implementation, only in visual display. There was 1 downside though, which was the fact that the new swarm was it's own new prefab. This means that the old prefab would be removed and replaced, requiring the re-placement of said prefab in the scenes. Since we're still very early in the project and before the first main integration push, this was easily worked around by communicating the upcoming change with the integration team. In the future it may be better to strip the old prefab down to it's base and manually add the new components to it so it automatically updates through git. This way there is no need to redo anything (other than adjust new variables in the interface).
