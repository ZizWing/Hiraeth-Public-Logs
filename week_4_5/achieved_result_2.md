Achieved result 2 - Volumetric Fog
===================

## Description
Volumetric fog works and is easy to set up thanks to the built-in support in the new HD Render Pipeline. As of writing there is an implementation of moving low-hanging fog that takes the shape of an ellipse for the sake of testing. There are some drawbacks though:
- Shapes in fog are created using 3D textures. These 3D textures can only be created through scripts, which becomes very complicated and time consuming the more complex of a shape is required.
- Volumetrics take up approximately 30% of CPU instructions on my machine (which is far from the best), which means usage should be severly limited for the sake of performance, or perhaps volumetrics should not be used at all.

Besides these drawbacks, setting up the fog is as simple as enabling the support in the render pipline, setting a global value and then adding volumes wherever you want. To make them move and use shapes a 3D Texture is required though.

An example of the current fog effect in action:
![Volumetric Fog](https://github.com/ZizWing/Hiraeth-Public-Logs/blob/master/week_4_5/products/Achieved%202/Volumetric%20Fog.gif)

Afterwards I started to look into performance, just to make sure the fog wasn't too heavy on the game. What I found instead was that Area 3 and the lighting caused my machine to suffer far more than the fog I implemented. The way I managed to find this is through a CPU process in the profiler. The process named "Gfx.WaitForPresent" was being called whenever the framerate got below 60 FPS. From what I can tell this indicates a GPU bottleneck since the CPU is waiting for a response here. The actual cause is somewhat unclear considering many people run into this issue on the Unity forums, all with various causes.

An example of the process in question:
![Gfx.WaitForPresent Graph](https://github.com/ZizWing/Hiraeth-Public-Logs/blob/master/week_4_5/products/Achieved%202/Gfx.WaitForPresent.png)

Here you can see the difference in frametime clearly. Before the spikes of Gfx.WaitForPresent (lightgreen) I am looking away from area 3, while I am look at area 3 when the spikes occur.

There also appears to be some kind of issue related to the Unity editor, where it doesn't update the interface properly. I noticed this when letting the game run for a few minutes after launching the editor. At some point the fps drops regardless of what I'm looking at and doesn't go back up again unless I restart the editor. It even persists bewteen play tests in the editor. The weird thing here is that updating something in the editor speeds it up again. An example of this is hovering over items in the scene hierarchy. This creates a hover-effect which somehow increases Unity's update rate which then also improves the framerate in play mode. This is so bizarre to me that I honestly don't know what to look for online to get this resolved. For now I will ignore this since the built version of the game seems to be mostly unaffected by this. I'll keep it in the back of my mind either way.

As for the performance dip I found... This is something we will look into at a later date once we have more time to do so. We're still not sure how reliable results from my machine are considering the issues it had with the current Unity installation.

Volumetric fog on the other hand seems like a good possibility if we can get proper 3D textures going for it.

|The commit(s)|The scene(s)|The gameobject(s)|The script(s)|
|---------|--------|--------------|----------|
|[Link to the commits](https://github.com/link-to-the-animatie)| Name of the scene(s) | Path to the GameObject that uses the script(s) | Name of the scripts

## Found sources
[Volumetric Fog Settings Tips](https://forum.unity.com/threads/using-the-new-volumetric-fog-features-in-2018-2-hdrp.541085/#post-3567940)
> A Unity dev explaining a basic setup for a textured fog volume.

[Fog tutorial in unity](https://unity3d.com/learn/tutorials/topics/unity-artists/volumetric-fog-fog-volume-3)
> Halfway through the tutorial I noticed this was using assets from the asset store, but the result is similar to what I'm looking for. It at the very least provided a working example of the desired result to work towards.

[Profiler RenderTexture.SetActive](https://answers.unity.com/questions/210896/rendertexturesetactive-huge-profiler-spikes.html)
> Some info on a specific process that seemlingly took up a lot of performance (turned out to be Gfx.WaitForPresent later on).

[Profiler Gfx.WaitForPresent](https://forum.unity.com/threads/gfx-waitforpresent.211166/)
> A whole thread full of people having a similar symptom of performance issues caused by (potentially) the same process.

[GPU Instancing](https://www.youtube.com/watch?v=l3Unh6FE1-s)
> A video I came across with a potential performance increase depending on what the source of my issue was.

[Unity documentation CombineMeshes](https://docs.unity3d.com/ScriptReference/Mesh.CombineMeshes.html)
> The Unity documentation for Mesh.CombineMeshes which helps with performance when used to batch static objects. Could be worth looking into for fixing the noticed performance dips.

[Unity documentation Draw call batching](https://docs.unity3d.com/Manual/DrawCallBatching.html)
> The Unity documentation explaining performance gains by batching dynamic and static objects.

[Unity documentation Optimizing graphics performance](https://docs.unity3d.com/Manual/OptimizingGraphicsPerformance.html)
> Documentation explaining some common pitfalls in terms of performance.

## Achieved learning goal(s)
- Learned how to read and use the built-in profiler
- Learned how to create decent looking (and moving) volumetric fog

My personal skills regarding the detection of performance-heavy items in the world is far from over. The intended result document mentioned this, but this is mostly just a starting point for something I want to improve slowly over time. No real results have been achieved yet. This is mostly achieved through debugging and general experience.

## Integration 
> (Note, the literal translation was something like "The transfer of" in regards to the team.)

### Within the team
Nothing has been communicated yet, but it comes down to changing a few project settings and adding a prefab. There shouldn't be anything affecting others in any meaningful way.

### Towards other teams
Nothing yet, fog is not yet ready to be integrated.
