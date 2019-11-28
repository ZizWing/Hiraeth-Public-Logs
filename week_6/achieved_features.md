Achieved Features
==================

## Feature 1 - MeshCombiner
I managed to find an updated tutorial for the mesh combining. This one included some basics on applying materials to the generated meshes. This helped me significantly when merging meshes with multiple materials.

The sources I used for this were the following:
1. [CombineMeshes in Unity](https://www.youtube.com/watch?v=wYAlky1aZn4)
> Tutorial for Unity's built-in CombineMeshes.

2. [Including materials with CombineMeshes](https://www.youtube.com/watch?v=6APzUgckV7U)
> Tutorial for including materials on combined meshes.

3. [Custom Editor buttons](https://unity3d.com/learn/tutorials/topics/interface-essentials/adding-buttons-custom-inspector)
> Quick tutorial on custom editor UI (buttons) for the MeshCombiner script I made

The final version as of the end of this week is a fully working MeshCombiner script that correctly combines any meshes you throw at it and applies the materials accordingly. 

It does suffer from a significant bug though, which is the fact that a combined mesh's vertices are multiplied by the amount of materials used. After some help from Marco from the MediaLab, we discovered that this happened because materials are applied to a submesh (part of a mesh, not a whole mesh). Once I combine a submesh to the correct CombineInstance, it does not differentiate between submeshes and the main mesh. This causes the entire mesh to be added per material it uses instead of just the part of the submesh. We found a solution for this by directly copying the triangles, vertices and UVs, but this will cost a lot of time to implement for the amount of performance gained.

Another issue I discovered is Unity's vertex limit for meshes. The maximum amount is 65535, which I easily pass due to the multiplying vertices. This limits the usage a little, but can be easily averted by splitting the combined mesh into multiple meshes once this occurs. This still reduces the total amount of meshes significantly and you would end up with 2 or 3 meshes in total. This isn't implemented yet, but it shouldn't take too long to do so, however I will not do so until we need this performance boost.

In general this performance script has been given low priority due to the fact that it only increased my FPS by at most 5 at any given time. Considering the amount of work still to be done, this would be a risky time investment given the amount of open tasks. I may pick this up later if I can. In case anyone is wondering... The combined meshes on the trees and ferns saved up to 1000 batches depending on where you looked and what was being rendered, so there is definitely something to gain here.

Below is a quick demonstration of the script. The actual performance gains are hard to capture in a gif without bloating the filesize to extreme amounts due to video length. As such I only show the combining in action in the editor. In the gif you can see the script disables the renderer of the individual meshes and only has its own renderer enabled with a new (nameless) mesh that consists of all child meshes. The green outlines you see after combining are the original meshes. This is something Unity shows when the renderer is disabled but the objects (or their parent) are selected. The combined mesh's materials are still visible through it though.

![MeshCombiner gif](https://github.com/HANICA-GAME/sep2018-stud-lucas-van-swaay/blob/master/Project%20-%20Programming/individual/week_6/products/MeshCombiner.gif)

The commits for this feature still live on their own branch, these can be found here:

|The commit(s)|The scene(s)|The gameobject(s)|The script(s)|
|---------|--------|--------------|----------|
|[Branch: optimized-mesh-combine-and-occlusion](https://github.com/HANICA-GAME/sep2018-game-hireath/commits/enhancement/optimized-mesh-combine-and-occlusion)| _Assets/Global/Scripts/MeshCombiner/\_Scenes/MeshCombinertest_ (It's a copy of Level 1 Area 2)
 | Multiple objects in the scene use it, there are no prefabs with it attached. These are empty gameobjects with my script attached. The examples are: _Area2/Trees_, _Area2/vegatation/Ferns/BleddynArea_, _Area2/vegatation/Ferns/TreeArea_, _Area2/vegatation/Ferns/JumpArea_, _Area2/vegatation/Bushes/FirstArea_ and _Area2/vegatation/Bushes/SecondArea_ | MeshCombiner (_Global/Scripts/MeshCombiner/Scripts/MeshCombiner.cs_) and MeshCombinerEditor (_Assets/Editor/MeshCombinerEditor.cs_)
