Achieved Features
==================

## Feature 1 - Adding lighting to the firefly swarms
A firefly swarm naturally gives off a weak light. The light was not implemented yet in sprint 1, thus it had to be done now. Instead of using the particlesystem to create a lightsource on one (or more) of the particles, I opted for a manual approach to allow for better control. I added a single lightsource that moves with the swarm based on the average position (center). The size and intensity of the light can then be controlled through a script. I've set it up in such a way that it can scale with the amount of particles if desired.

In the gif below you can see the implementation of the firefly lighting. It stays centered in the swarm and it's range/intensity can be adjusted through settings.
![Firefly Lighting](https://github.com/HANICA-GAME/sep2018-stud-lucas-van-swaay/blob/master/Project%20-%20Programming/individual/week_3/products/Achieved%20Features/Firefly%20Lighting.gif)

|The commit(s)|The scene(s)|The gameobject(s)|The script(s)|
|---------|--------|--------------|----------|
|[PR #109](https://github.com/HANICA-GAME/sep2018-game-hireath/pull/109)| _World/Dynamic/Firefly/\_Scene/Firefly example scene_ | _World/Dynamic/Firefly/Prefab/Firefly Swarm_ | _World/Dynamic/Firefly/Scripts/Controllers/FireflyLightController_

## Feature 2 - Destructible Trees
Work in progress of destructbale trees. The functionality is finished, but it needs to be fine tuned to suit gameplay needs. Art is also still missing, but this is a minor change to be made.

The main idea of the destructable trees is to have them fall over on collsion with the Gwilym to keep art work to a minimum. The destruction is created by simply enabling physics once a collision occurs. Particle systems are spawned on collision as well.

In the gif below you can see the basic systems in place. Particles on collision and when something gets in range of the leaf volume (invisible sphere on top of the blocks). Furthermore the trees properly enable physics upon collision.
![Falling Trees](https://github.com/HANICA-GAME/sep2018-stud-lucas-van-swaay/blob/master/Project%20-%20Programming/individual/week_3/products/Achieved%20Features/Falling%20Trees%20(No%20Art).gif)

In order to prevent confusion when configuring the destructable trees, the configurations I added make use of a custom propertydrawer which was created from a tutorial found [here](http://www.brechtos.com/hiding-or-disabling-inspector-properties-using-propertydrawers-within-unity-5/). This allows me to hide variables in the inspector based on the value of others. (E.g. "Spawn Treestumps: True" shows additional settings for the treestumps).

|The commit(s)|The scene(s)|The gameobject(s)|The script(s)|
|---------|--------|--------------|----------|
| [Basic setup](https://github.com/HANICA-GAME/sep2018-game-hireath/commit/895a40254617877984497d83b18939d7ff290237)| _World/Dynamic/FallingTree/\_Scene/Falling Tree Demo.unity_ | _World/Dynamic/FallingTree/Prefabs/Dummies/Dummy Tree_ | _Hiraeth/Assets/World/Dynamic/FallingTree/Scripts/FallingTreeController.cs_ _Hiraeth/Assets/World/Dynamic/FallingTree/Scripts/FallingTreeStats.cs_ |
| [Added basic particle system and dummy treestumps](https://github.com/HANICA-GAME/sep2018-game-hireath/commit/cc9f903ba814b3a5990339e805b6a2fecb6031be) | _World/Dynamic/FallingTree/\_Scene/Falling Tree Demo.unity_ | _World/Dynamic/FallingTree/Prefabs/Dummies/Dummy Tree_ | _Hiraeth/Assets/World/Dynamic/FallingTree/Scripts/FallingTreeController.cs_ |
| [Fixed collision physics](https://github.com/HANICA-GAME/sep2018-game-hireath/commit/8258890646849e302a1c7df16ba174ae646b6230) | _World/Dynamic/FallingTree/\_Scene/Falling Tree Demo.unity_ | _World/Dynamic/FallingTree/Prefabs/Dummies/Dummy Tree_ | _ Hiraeth/Assets/World/Dynamic/FallingTree/Scripts/FallingTreeController.cs_ |
| [Adjusted prefabs for proper positioning](https://github.com/HANICA-GAME/sep2018-game-hireath/commit/9bdce307cdd3a011fd6f46a8818f8732f89bbb50) | _World/Dynamic/FallingTree/\_Scene/Falling Tree Demo.unity_ | _Hiraeth/Assets/World/Dynamic/FallingTree/Prefabs/Dummies/Dummy Tree_ _Hiraeth/Assets/World/Dynamic/FallingTree/Prefabs/Dummies/Dummy Stump_ | _Hiraeth/Assets/World/Dynamic/FallingTree/Scripts/FallingTreeController.cs_ |
| [Experimented with leaf particles](https://github.com/HANICA-GAME/sep2018-game-hireath/commit/ef6a2226b91e374c733665d6f20d501eb51f579a) | _World/Dynamic/FallingTree/\_Scene/Falling Tree Demo.unity_ | _Hiraeth/Assets/World/Dynamic/FallingTree/Prefabs/Dummies/Dummy Tree_ _Hiraeth/Assets/World/Dynamic/FallingTree/Prefabs/LeafParticles_ | _Hiraeth/Assets/World/Dynamic/FallingTree/Scripts/FallingTreeLeafController.cs_ |
| [Added toggleable settings for particles](https://github.com/HANICA-GAME/sep2018-game-hireath/commit/2aec81f2fa734261ab7e41369e762feb1316dee3) | _World/Dynamic/FallingTree/\_Scene/Falling Tree Demo.unity_ | _Hiraeth/Assets/World/Dynamic/FallingTree/Prefabs/Dummies/Dummy Tree_ | _Hiraeth/Assets/World/Dynamic/FallingTree/Scripts/FallingTreeStats.cs_ _Hiraeth/Assets/World/Dynamic/FallingTree/Scripts/FallingTreeLeafController.cs_ _Hiraeth/Assets/World/Dynamic/FallingTree/Scripts/FallingTreeController.cs_ |
