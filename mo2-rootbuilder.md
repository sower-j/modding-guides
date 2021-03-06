# Using MO2 to Manage Script Extenders, ENBs, and More

I have found that many mods and tools that require files to be placed in the root `Fallout 4` folder (where `Fallout4.exe` is located) are lacking installation instructions for mod managers. While these installation instructions still work, they can be difficult to follow. In my opinion using a mod manager to handle these installations has several advantages over manual installation:

  1. These mods and tools are easier to install with this method.

  1. Using a mod manager to install these mods / tools makes it easier to track files.

  1. Troubleshooting bad / incorrect installations is much easier because you know exactly what files the mod provides.

  1. The user does not have to make any changes to the root `Fallout 4` folder.

      - This keeps the `Fallout 4` folder in a vanilla state which is always my recommendation. (In the case of Vortex you can now purge back to a vanilla state easily)

This guide is specific for MO2. Check my [Vortex guide](vortex-root-mods.md) for how to accomplish a similar installation method with Vortex.

Mod Organizer 2 cannot install mods that use the base game folders natively (where the `Fallout4.exe`, or `Skyrim.exe` are located for example). Luckily Kezyma has made a plugin called [Root Builder](https://www.nexusmods.com/skyrimspecialedition/mods/31720) that will enable MO2 to manage these applications.

Based on your settings, Root Builder will temporarily copy, or link mods that need to be in the base game folder. This makes it so that your game folder remains untouched and you have everything managed from one location, MO2.
 

**NOTE: Remember to ensure your MO2 INIs are configured for modding (loading loose files). Expand the instructions below for a quick reminder if you are unsure**

<details>

  <summary><u>expand instructions</u></summary>

 #### MO2 INI Configuration Check

  - Open MO2's INI configuration tool.

    <img src="./images/mo2-ini01.png" width="50%"> 

  - Navigate to the fallout4custom.ini tab.

    <img src="./images/mo2-ini02.png" width="50%">

  - Ensure there is an `[Archive]` section with `bInvalidateOlderFiles=1` and `sResourceDataDirsFinal=` below it as seen in the picture above.

  **NOTE: There may be other settings in this file already. This is not a problem as long as `[Archive]` is present and `bInvalidateOlderFiles=1` and `sResourceDataDirsFinal=` are below it and not under another section header. (section headers are surrounded by square brackets)**

[back to top](#mo2-ini-configuration-check)

</details>

---

If you would like to jump straight to a specific section here are some jump points:

  - [Installing Root Builder](#installing-root-builder)
  - [Script Extenders (F4SE, SKSE)](#installing-script-extenders)
  - [ENB Binaries (Fallout 4 or Skyrim)](#installing-enb-binaries)
  - [xSE Plugin Preloader (Fallout 4 only)](#installing-xse-plugin-preloader)
  - [Final Notes and Other Resources](#final-notes-and-other-resources)

---

## Installing Mods in Root Builder Format

Root builder uses a slightly modified folder structure when installing mods that need to be in a game's base folder (where the EXE is located) such as script extenders or ENBs. 

During installation you will need to create a `Root` folder inside of the `Data` directory and place any files that need to be in the base game folder (where EXE is located) into the new `Root` folder.

***NOTE: Many mods installed in this way will have a warning that there is no valid game data. This is expected since this is an unofficial plugin MO2 does not recognize the folder structure.***

---

 ### Installing Root Builder 

<details>

  <summary><u><b>expand instructions</u></b></summary>

Root Builder [(download here)](https://www.nexusmods.com/skyrimspecialedition/mods/31720) needs to be installed manually. Download it to any location you like, the desktop makes it easy to find for the next steps.

1. Once downloaded, unzip the folder. You should now have a `rootbuilder` folder that contains a few files, another rootbuilder folder, and a shared folder.

1. Locate your MO2's installation folder by launching MO2 and opening the settings. Go to the Path tab and take note of the base directory. 

    <img src="./images/mo2-base-dir.png" width="50%"/>

1. Close MO2 and navigate to that folder in your file explorer. Find the `plugins` folder.

    <img src="./images/mo2-plugins.png" width="50%">

1. Now put the ***entire*** `rootbuilder` folder into the `plugins` folder. 

    <img src="./images/mv-rootbuilder.png" width="50%">

    If you have done this correctly, inside `*\Mod Organizer\plugins\rootbuilder\` you should find two folders, `shared` and `rootbuilder` as well as a file called `__init__.py`

1. Launch MO2 and ensure you have installed it correctly by clicking the tools icon.

    <img src="./images/mo2-rootbuilder-confirm.png" width="50%">

[back to top](#using-mo2-to-manage-script-extenders-enbs-and-more)

</details>

---

 ### Installing Script Extenders

<details>

  <summary><u><b>expand instructions</u></b></summary>

For this example I will be installing F4SE but the process is identical for SKSE aside from different file names. I will note them where needed.

1. [Download F4SE](https://f4se.silverlock.org/) and save it to an easy to find location, the desktop works well. Drag the archive into MO2's download tab.

    <img src="./images/mv-f4se.png" width="50%">

1. Begin the installation as normal by double clicking the mod in the downloads tab. Expand the drop downs until you see the `Data` folder. Right click the `Data` folder and create a `Root` folder inside of it.

    <img src="./images/rootbuilder-f4se01.png" width="50%">

1.  Now put all the files that are required to be in the Fallout 4 (or Skyrim) directory into the `Root` folder.

    <img src="./images/rootbuilder-f4se02.png" width="50%">
    
1. For F4SE to function only `f4se_1_10_163.dll`, `f4se_steam_loader.dll` and `f4se_loader.exe` are required. You can uncheck everything else in the `Root` folder.

    - Note: for **Skyrim** SKSE the files you need to have checked in the `Root` folder are `skse_1_9_32.dll`, `skse_loader.exe`, and `skse_steam_loader.dll`

    <img src="./images/rootbuilder-f4se03.png" width="50%">

1. Finally right click the `Data` folder and select `Set as <data> directory`. Your final folder structure should look like the picture below.

    <img src="./images/rootbuilder-f4se04.png" width="50%">

1. Click "OK" and your F4SE installation is now complete! I renamed mine to `MO2-F4SE` to make it easier to find later. Don't forget to enable the mod on the left panel.

    <img src="./images/rootbuilder-f4se05.png" width="50%">

1. To launch FO4 using F4SE you will need to add it as a launcher. Start by clicking the executable button near the top of MO2.

    <img src="./images/mo2-add-executable01.png" width="50%"> 

1. When the executable window opens click the `+` to and select `add from file...`. 

    <img src="./images/mo2-add-executable02.png" width="50%"> 
     
1. Navigate to the F4SE (or SKSE) mod you created earlier and select the `f4se_loader.exe`(or `skse_loader.exe`). 

    <img src="./images/mo2-add-executable03.png" width="50%">

1. After you have selected your F4SE executable be sure click Apply at the bottom of the window. As you can see I gave mine a different title. This is just my preferred naming scheme, you do not need to rename it.

    <img src="./images/mo2-add-executable04.png" width="50%">

1. Now you can launch F4SE from the dropdown next to the `Run` button in the top right side of MO2.

    <img src="./images/mo2-add-executable05.png" width="50%">

Now F4SE is installed correctly and you can launch your game with all the extra goodies F4SE has to offer.

[back to top](#using-mo2-to-manage-script-extenders-enbs-and-more)

</details>

---

### Installing ENB Binaries

<details>

  <summary><u><b>expand instructions</u></b></summary>

This is a basic install of the ENB Wrapper itself that presets on Nexus require. Once again the installation for Fallout 4 and Skyrim are nearly identical, I will note any differences.

1. [Download](http://enbdev.com/download.html) the enb for your game and save it to a temporary location. The desktop is a good location. Extract it and find the `Wrapper` folder (for **Skyrim** the folder is named `WrapperVersion`). Right click and add it to a compressed folder. You can use whatever tool you would like for this as long as you end up with a ZIP or 7z archive.

    <img src="./images/enb-wrapper01.png" width="50%">

1. Drag your new archive into MO2. I have renamed my archive but you could leave it as is if you like.

    <img src="./images/enb-wrapper02.png" width="50%">

1. In MO2 begin the installation as normal by double clicking the mod in the downloads tab. Right click the `Data` folder and create a `Root` folder inside of it.

    <img src="./images/mo2-rootbuilder-enb01.png" width="50%">

1. We only need `d3d11.dll` and `d3dcompiler_46e.dll` for this install (same for Skyrim). Move them into the new `Root` folder and uncheck everything else.

    <img src="./images/mo2-rootbuilder-enb02.png" width="50%">
    
1. Click `OK` and and you're done! Don't worry about MO2 saying the contents aren't valid, that is expected. Press ignore on the warning that comes up.

    <img src="./images/mo2-rootbuilder-enb03.png" width="50%">

1. Don't forget to enable on the left pane in MO2!

[back to top](#using-mo2-to-manage-script-extenders-enbs-and-more)

</details>

---

### Installing xSE Plugin Preloader

<details>

  <summary><u><b>expand instructions</u></b></summary>
   
1. Begin the installation as normal by double clicking the mod in the downloads tab. Right click the `Data` folder and create a `Root` folder inside of it.

    <img src="./images/mo2-rootbuilder-preloader01.png" width="50%">
   
1. Move `lpHlpAPI.dll` and `xSE PluginPreloader.xml` into the new `Root` folder

    <img src="./images/mo2-rootbuilder-preloader02.png" width="50%">

1. Click `OK` and and you're done! Don't worry about MO2 saying the contents aren't valid, that is expected. Press ignore on the warning that comes up.
   
    <img src="./images/mo2-rootbuilder-preloader03.png" width="50%">

1. Don't forget to enable on the left pane in MO2!

[back to top](#using-mo2-to-manage-script-extenders-enbs-and-more)

</details>

---

## Final Notes 

If the red "x" flags in MO2 bother you they will go away if you right click the mod and select "Ignore Missing Data"

<img src="./images/mo2-missing-data.png" width="50%">

[back to top](#using-mo2-to-manage-script-extenders-enbs-and-more)