# Collected-FN-Game-Servers (🚧 Soon update!! )
Collected FN Game Servers from other archives and sources. Open sources, free to use!



***Ill list all features if some of them have features :)***
Here now you can see SOME GS features as list

[Readme here (moved to a 2nd md)](https://github.com/Ducki67/FN-Gameserver-Center/blob/main/Features.md)



## Suggesting Game-Servers 
Feel free to open a issue ticket and upload the file and ill add it to the list + I might test it

## Clarification :exclamation: 
Some lil' info what this repo will be used for / quick notes

> - **1** This repo will NOT be used for leaking anyone's GS or so  this is gonna be used for a Huge GS Folder that contains the GameServer source codes.
> - **2** I will NOT provide any additional chapters above *C3S4* AKA i won't provide any Chapter 5 or Chapter 4 gameserver source code here ( for good resons and many devs may not want this)
> - **3** The gameservers that are already listed here are:  **open src**, **known**,  **public / published**

# Text tut
speciall thx for 27 stars on this repo, ty yall ❤️

**Requirements:**
  - VS2022 or VS2026 
  - Any gs source from above
  - C++ and problem solving knowledge

**Building the dll**


   **1.** Open the .sln or .vcxproj file of your selected gs in Visualstudio:

   Then after that on the side u should drop down the Solution/Project to see all folders and files.
   
   **2.** Change the gameserver configs:
   
   These are usually in files like `Config.h`, `Configuration.h`, `Globals.h` etc.
   
   If you dont find any file that is dedicated for configs then do  **`Ctrl+f`** and search up namespace names like *Globals*, *Configuration*, *Config(s)* Or even Class and Struct names like *struct FCofiguration* stuff like that.


   **3.** Compiling the dll:

   At the very top of visualstudio set the *Debug* to *Release* Or **Client** (depending which yoz wanna build / if the gs has its own Client) and make sure its on **X64**.

   After that do `Ctrl+Shift+B` to build it.

   And once its done check the folder: **/x64/Release/ExampleGs.dll** and there you go.



<!--# 🚧 Currently being made / Under some construction 🚧 Very soon ill add more info about these + what it tested! -->
