Reflection
==========

## Last week

1. What went well last week and to which extent have the planned results been achieved?
> Although more timeconsuming than I initially thought, building the collapsable bridge was fairly straightforward after some teamwork with the art team. Since the original bridge was a single object, I had to work together with Robin from art to split it up in the correct pieces for it to break. We managed to pull it apart into 2 separate pieces without it taking up too much time and then managed to separate the ropes so they could fall independently. Communication was fast and accurate to the point where the neccesary changes were made within an hour. I could then continue working on it until it was finished. With al little help from Leroy concerning the rigidbody hinges, I managed to finish the bridge on time.

2. What did not go well, what annoyed you and what shouldn't happen again?
> The bridge was quite the edge-case if you ask me. I was tasked with the functionality around the feature-freeze. It all worked out in the end but these last-minute requests should not happen again due to the risk of not being able to complete them before a deadline. In this case I accepted since I had a fair understanding of what needed to be done and enough confidence to get it working to a playable state.

> What really became clear to me (mostly this week, but also during the course of the entire project) is how bad the version control is in the art team. Seeing files come by named...

- Bleddyn_AllAnimations_WithScripts
- Bleddyn_AllAnimations_Adjusted
- Bleddyn_AdjustedAnimations
- ALL_Bleddyn_animations_v3
- Bleddyn_WithAnimations
- Bleddyn_Animated
- walk\_+\_search\_animation

> ...probably says enough about that. I had to test the falling bridge by having a Bleddyn walk over it to trigger the collapse and it took me a solid 5 to 10 minutes to find the right person to ask which prefab was the correct one to test with. Even considering it was the CMD students their first time working with large project groups and all the tools, I still stand by my point of view that they should just leanr how to use git or some other version control system in order take stop this from happening. If nobody pays attention it can turn into an absolute hell trying to find the correct models or textures.

> Communication surrounding build requirements were not established beforehand and as such my bridge did not work due to lacking navigation because the final build forgot to bake that along with the terrain. I made sure to inform all relevant people of this requirement, yet last-minute a new build was made with changes to the navmesh and it just so happened to be built by someone who was not aware of this. In the future I need to make sure rules or documentation is set up for release builds to prevent these things from happening again.

> Having the art team work on improving the environment in the scenes made a lot of sense, but doing this all at the same time and effectively locking out any other changes ot scenes was a stupid move on our part. I suffered from this due to not being able to work on performance changes for any scene until art was done. They were not capable of solving complex merge conflicts in scenes and as such this was best left to us. In other words I was stuck waiting on their progress. What I would have liked is more transparency among the teams regarding scenes and who works in what scene in order to prevent this. A live page with an overview would be best, assuming that exists. As mentioned before in another document, a whiteboard could do the trick too. This way you can quickly communicate with the relevant people to see if any conflicts would arise or to plan your integrations.

3. What will you improve next time?
> Force all teammembers to familiarize themzelves with the chosen tools in order to prevent issues such as the version control discrepancies described above. This saves those who use the tools a lot of time in the long run, even if they have to make time to teach others how to use these tools.

> As already mentioned above: I need to make sure there is some kind of build-documentation that needs to be followed for special cases or as a checklist for release builds. This way we can make sure everything is included in the build proces. testing would also go a long way, but for last-minute builds with a small hotfix, that is not always an option.

> One final thing I want to make sure is done properly next time is setting up a build server. I'm not talking about one of those crappy "Krachtcentrale" servers that can barely handle loading anything. I'm talking about a server that can actually build a lightmap or something within less than 2 days of time. Our laptops were mostly in use so that was out of the question. Using our own pc's at home still used up too much time and weren't always available for use. Let alone fast enough. This is something I really would push for to have near the start of the project since it removes a lot of wasted time for those running the builds. As of writing this, we are unable to make our lightmaps due to it taking about a week in total to go through all scenes with our hardware. Building the game is slow but still manageable at around 1-2 hours for a clean build.
