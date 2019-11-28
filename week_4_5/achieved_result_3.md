Achieved result 3 - Performance Research
===================

## Description
As described in intended result 3, no prototyping was done this week and since the logs are broken up in weeks, this means there is nothing to show for it here.

That said... What I did manage to do is learn a lot about performance in Unity, most of which is irrelevant for the project due to time limitations and such. But at the very least I managed to find some info for later in other projects. The one thing that seemed promising was the draw call optimisation considering our batches (and thus draw calls) are rather high. This would be in the form of a MeshCombiner on which I'll start next week.

## Found sources
1. [Draw Call Optimization](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=video&cd=1&ved=0ahUKEwjLxpC8sZffAhUIElAKHYgMDTMQtwIIKTAA&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DeTWw6guy3lI&usg=AOvVaw1BigiECThlnUnz30DDz1fE)
> A partial tutorial about merging similar meshes to reduce draw calls. Part 2 does not seem to exist.

2. [Unite 2017 - Performance for beginners](https://www.youtube.com/watch?v=1e5WY2qf600)
> Basic performance and profiling talk and tips

3. [Unite 2017 - Squeezing Unity: Tips for raising performance](https://www.youtube.com/watch?v=_wxitgdx-UI)
> A more advanced talk about Unity performance. Some good information to take into account, but most likely not relevant for our project (yet).

4. [Git Large File Storage (LFS)](https://robots.thoughtbot.com/how-to-git-with-unity)
> Unity git integration LFS & auto collapse generated files. Came across this and it seemed promising considering git can take a long time to do actions with large files. This may be worth looking into if we run into problems with it.

## Achieved learning goal(s)
- I did not get the chance to profile the game outside the editor yet, so this is still something to look into in the future.
- Determining bottlenecks is something I started on with the profiler, but I'm not confident yet in my ability to detect them efficiently.
- GPU instancing is usable as long as there is nog GPU bottleneck and the objects are all using the same material without too much complexity. For our game it would probably be best to skip this considering we cannot clearly determine how much headroom our GPU's will have in the end.
- LOD and culling was already being worked on, so it was no longer neccesary to research this. The short answer is: Yes it works through a built-in system that is tweakable.
- The MeshCombiner is a viable option of which I will make a prototype next week.

## Integration 
> (Note, the literal translation was something like "The transfer of" in regards to the team.)

### Within the team
N/A

### Towards other teams
N/A
