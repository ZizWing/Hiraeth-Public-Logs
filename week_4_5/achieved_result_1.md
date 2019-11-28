Achieved result 1 - Unity upgrade & fixes
===================

## Description
After starting the upgrade proces on monday, I finally had a working version of unity again by the end of wednesday.

There were multiple issues present, which appear to be unique to my machine and for some reason cannot be corrected through version control reverting.

Immediately after performing the installation of the new Unity version I noticed that all of the HD Render Pipeline functionality was gone. No textures were loaded, nothing worked and there were severe compile errors that even included kernel error messages. This was caused due to Unity not being able to load any packages (including the package manager itself). This was partially fixed by resetting all packages to default through _"Help -> Reset Packages to Default"_. This resolved some of the package errors but kept all the kernal errors. Eventually I discovered through trial and error that complete removal and reinstalling of the packages (including the default ones) would solve some errors one-by-one. In the end I had a game that could start but still kept spewing out errors that ran into the hundreds within seconds.

The second batch of issues were coming from the Wwise integration. Now this was an absolute \*\*\*\*\* to fix and is also what caused the significant time investment. My Unity could not play any audio due to the errors and made debugging nearly impossible due to the amount of errors being thrown into the console.

In a futile attempt to restore the audio to a working state I tried to:
- Revert to earlier commits that worked before. 
- Switch to working branches
- Edit Wwise configurations 
- Replace the entire Wwise folder
- Replace DLL files
- Install Wwise and re-generate the soundbanks
- Re-integrate Wwise by re-installing the integration plug-in
- Literally delete the entire project and re-clone it
- Manually delete any temporary files and cache files used by Unity
- Clean the Windows registry
- Removed Wwise project settings from version control to remove the possibility of it being locked by it

In the end nothing could fix my issues and I found myself with no remaining options left other than re-installing Windows. At this point I randomly decided to just hit play again and... well... it worked somehow. I still don't know how, but somehow after nearly 3 days of not being able to do anything useful, it fixed itself. Needless to say I was beyond frutrated about this, but at the same time glad this was finally over.

There's no real media to show for all of this since all that would amount to is debug output; which admittedly was never all that useful considering it never even helped pinpoint the issue.

## Found sources
1. [Wwise Troubleshooting Page](https://www.audiokinetic.com/library/edge/?source=Unity&id=unity__picker.html)
> Helped determine the issue with Wwise references being lost. The _AkWwiseProjectData.asset_ may not be under versioncontrol.

2. [Wwise "Populating Wwise Picker" fix](https://www.audiokinetic.com/qa/5207/inability-to-update-wwise-unity-integration-2018-6762-1211)
> Provided a solution for an infinite loading on start-up of unity, which prevented unity from starting.

## Achieved learning goal(s)
- Learned to never use external tools unless absolutely necessary
- Learned to reserve a lot of time for updates, no matter how small they seem

## Integration 
> (Note, the literal translation was something like "The transfer of" in regards to the team.)

### Within the team
N/A

### Towards other teams
N/A
