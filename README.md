# StrayModdingWiki

### Discord: https://discord.gg/v2e7SbsJTW

TOC:

ModLoader Download Link: https://www.nexusmods.com/stray/mods/77

[Making ModLoader Compatible Mods](#modloader-tutorial-largely-copied-from-the-kh3-modloader-instructions)

[uProject Installation](#uproject-installation)

 
 
 
# ModLoader Tutorial (Largely copied from the KH3 Modloader instructions.)

### Original credit to YuriLewd of KH3 Modding

Making Your Mods Compatible With Stray Modloader

Stray Modloader simply loads map instances, so if you’re designing a logic mod you could place all the logic in an empty level’s blueprint located here:

![image](https://user-images.githubusercontent.com/73571427/180675346-983189ad-406b-4abd-a7f5-5e16dd921ccc.png)


This map should be placed in the correct folder, the full path will be /Content/CustomContent, From a blank uproject all you need to do is make a new folder titled CustomContent and then place or create your map in that folder. 

Making an already made blueprint actor into a Stray Modloader map could be done in numerous ways, easiest being just placing the actor into the map, however that method might crash the game if the user has that map in their load list and they remove you mod, so instead you should just make a very simple blueprint in your level blueprint to spawn your actor instead. This is what the full blueprint should look like:

![image](https://user-images.githubusercontent.com/73571427/180675427-a876e709-0697-45dc-81bf-bc4fc5b80774.png)

Making it is as simple as attaching the node “Spawn Actor From Class” with your actor and a Make Transform node into Event BeginPlay. When you load the actor with this method, the game won’t crash even if the actor doesn't exist.



# uProject Installation


# Prebuilt uProject Installation Instructions
 
 ## Note - the screenshots are taken from my instructions for a different game and therefore don't match the names of the files we are using here.

### See [option 1](#1-github-clone-install---update-with-the-click-of-a-button) for install along with Github desktop to allow for easy updates, or [option 2](#2-standard-install---no-easy-updating) for standard install.  Be sure to install any missing [prerequisites](/uProject%20and%20Engine%20Installation.md#prerequisites) first.

I highly recommend following option 1, as you can update with the click of a button and updates will only download changed files.


## Prerequisites

### Install Visual Studio 2017

Download and install Visual Studio 2017 (2019 or 2022 should also work as this game is built on 4.27).  It can be found here (https://my.visualstudio.com/Downloads?q=visual%20studio%202017&wt.mc_id=o~msft~vscom~older-downloads), and you should download the "Community" version (Visual Studio Community 2017 (version 15.9)).  You may need to log in to a Microsoft account to access this link.

If you are installing for the first time, be sure to include the below options.

### VS - C++ Tools

To add C++ tools to your VS installation, make sure you select Game development with C++ under Workloads, as well as these additional options.


    C++ profiling tools


    C++ AddressSanitizer (optional)


    Nuget Package Manager


    Windows 10 SDK 

### VS - Include the UE Installer
To include the UE installer when installing VS, locate the Summary sidebar on the right, expand Game Development with C++, and under Optional, make sure the checkbox for Unreal Engine installer is checked to enable it. 

![image](https://user-images.githubusercontent.com/73571427/176460487-8654e419-2dc4-4cb3-8e67-314c558492b5.png)



# 1. Github Clone Install - Update with the click of a button


### Prerequisites

Github Desktop: https://desktop.github.com/ (install with defaults, being sure to include any options relating to adding GIT as an environmental variable/path.)

Git CLI: https://git-scm.com/downloads (install with defaults, being sure to include any options relating to adding GIT as an environmental variable/path.)

### uProject

Create a new folder in which you would like to install the uProject.

Open a new powershell window from within this new folder.  Paste the below command into the powershell window

    git clone --branch main https://github.com/narknon/HK_Project.git
    
    
Wait for the download to complete based on the output in the console window.  This should be much quicker than the engine download.

Once complete, find the HK_project.uproject file in this folder.  Right click on this file, and select "Switch Unreal Engine Version" and select "4.27".


![image](https://user-images.githubusercontent.com/73571427/176458008-307cc67f-0122-4a1b-9025-964c3592c8c1.png)


![image](https://user-images.githubusercontent.com/73571427/176459346-7e40b7bd-ab8d-4e81-8866-e6acc9394b79.png)


Following this, the uproject should generate a .sln file.  If this file does not generate, something went wrong.  Try right clicking on the HK_project.uproject again, and this time select "Generate Project Files."  If the .sln still does not generate, something else is happening.  Navigate to your Saved/Logs folder to find a file titled unrealversionselector-2022.06.29-09.16.08.log (the date will be the current date/time, not the one listed here), and check to see what the error was, or post the file in the #kh3-modding channel on the discord for help. 


If the .sln did generate, you should now be able to launch the project by double clicking on the HK_project.uproject.  Proceed to the Github Desktop steps below to allow one-button updates.

### Github Desktop

Open Github Desktop and navigate to File->Add Local Repository; or press CTRL+O.  

![image](https://user-images.githubusercontent.com/73571427/176687516-0dfd3263-16f4-4b3d-aa0c-113b6dfb798d.png)


In the new dialog, press "Choose" and navigate to the folder to which you cloned the uproject (this will be the folder that contains the hidden .git folder, not the folder that is a directory up from that).

![image](https://user-images.githubusercontent.com/73571427/176687457-13a4c1b3-aaeb-48b9-97a4-b9485ed0d3bd.png)

Once inside this folder, press select folder.

![image](https://user-images.githubusercontent.com/73571427/176687920-28b70244-6639-41f5-8900-c125e032a354.png)

The repository should now be added as the current repository.

![image](https://user-images.githubusercontent.com/73571427/176688075-eef2ed9d-3151-4320-b000-f75a67eea494.png)


You should be able to switch between branches easily if you'd like to try out one of the experimental branches.


### Done!


# 2. Standard Install - No easy updating

From this repository, click on the green arrow to the top right, and select download zip.

![image](https://user-images.githubusercontent.com/73571427/176456031-7dd76359-dce9-4ac4-9a10-616bae4552e4.png)


Once the download is complete, extract to a folder (I personally prefer not to use Desktop or Documents for Unreal installs, and instead install on root of my drive, or close to root).

### uProject

Inside the folder to which you extracted the project, find the HK_project.uproject file.  Right click on this file, and select "Switch Unreal Engine Version" and select "4.27".

![image](https://user-images.githubusercontent.com/73571427/176458008-307cc67f-0122-4a1b-9025-964c3592c8c1.png)


![image](https://user-images.githubusercontent.com/73571427/176459346-7e40b7bd-ab8d-4e81-8866-e6acc9394b79.png)



Following this, the uproject should generate a .sln file.  If this file does not generate, something went wrong.  Try right clicking on the HK_project.uproject again, and this time select "Generate Project Files."  If the .sln still does not generate, something else is happening.  Navigate to your Saved/Logs folder to find a file titled unrealversionselector-2022.06.29-09.16.08.log (the date will be the current date/time), and check to see what the error was, or post the file in the #kh3-modding channel on the discord for help. 


If the .sln did generate, you're done!  Double click on the HK_project.uproject to launch the project!

### Done!



# 3. Troubleshooting

If your problem is not solved by the below, then navigate to Saved/Logs for both your uProject folder, your engine folder, and the automation tool (see below paths), and request help in the server by sending the relevant logs from each.

{EngineFolderRoot}\Engine\Saved\Logs

{EngineFolderRoot}\Engine\Programs\AutomationTool\Saved\Logs

{EngineFolderRoot}\Engine\Programs\UnrealHeaderTool\Saved\Logs

{ProjectFolderRoot}\Saved\Logs
