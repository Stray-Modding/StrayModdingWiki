# StrayModdingWiki
 
## ModLoader Tutorial (Largely copied from the KH3 Modloader instructions.

### Original credit to YuriLewd of KH3 Modding

Making Your Mods Compatible With Stray Modloader

Stray Modloader simply loads map instances, so if you’re designing a logic mod you could place all the logic in an empty level’s blueprint located here:

![image](https://user-images.githubusercontent.com/73571427/180675346-983189ad-406b-4abd-a7f5-5e16dd921ccc.png)


This map should be placed in the correct folder, the full path will be /Content/CustomContent, From a blank uproject all you need to do is make a new folder titled CustomContent and then place or create your map in that folder. 

Making an already made blueprint actor into a Stray Modloader map could be done in numerous ways, easiest being just placing the actor into the map, however that method might crash the game if the user has that map in their load list and they remove you mod, so instead you should just make a very simple blueprint in your level blueprint to spawn your actor instead. This is what the full blueprint should look like:

![image](https://user-images.githubusercontent.com/73571427/180675427-a876e709-0697-45dc-81bf-bc4fc5b80774.png)

Making it is as simple as attaching the node “Spawn Actor From Class” with your actor and a Make Transform node into Event BeginPlay. When you load the actor with this method, the game won’t crash even if the actor doesn't exist.
