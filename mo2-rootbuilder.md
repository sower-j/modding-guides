# Using MO2 to Manage F4SE, ENB, and More

Mod Organizer 2 cannot install mods that use the base Fallout 4 folder natively (where the `Fallout4.exe` is located). Luckily there is a MO2 plugin called [Root Builder](https://www.nexusmods.com/skyrimspecialedition/mods/31720) that will enable MO2 to manage these applications.

Based on your settings, Root Builder will temporarily copy, or link mods that need to be in the Fallout 4 folder. This makes it so that your Fallout 4 folder remains untouched and you have everything managed from one location, MO2.

If you would like to jump straight to a specific section here are some jump points:

  - [F4SE](#f4se-installation)
  - [Buffout 4's TBB Redistributables](#buffout-4-tbb-redistributables)
  - [ENB Binaries](#enb-binaries)
  - [ENB Preset](#enb-preset)
  - [xSE Plugin Preloader](#xse-plugin-preloader)
  - [Final Notes and Other Resources](#final-notes-and-other-resources)

---

## Installing Root Builder

Root Builder [(download here)](https://www.nexusmods.com/skyrimspecialedition/mods/31720) needs to be installed manually. Download it to any location you like, the desktop makes it easy to find for the next steps.

1. Once downloaded, unzip the folder. You should now have a `rootbuilder` folder that contains a few files, another rootbuilder folder, and a shared folder.

1. Locate your MO2's installation folder by launching MO2 and opening the settings. Go to the Path tab and take note of the base directory. 

    ![MO2 Base DIR](./images/mo2-base-dir.png)

1. Close MO2 and navigate to that folder in your file explorer. Find the `plugins` folder.

    ![MO2 Plugins](./images/mo2-plugins.png)

1. Now put the ***entire*** `rootbuilder` folder into the `plugins` folder. 

    ![Move Rootbuilder](./images/mv-rootbuilder.png)

    If you have done this correctly, inside `*\Mod Organizer\plugins\rootbuilder\` you should find two folders, `shared` and `rootbuilder` as well as a file called `__init__.py`

1. Launch MO2 and ensure you have installed it correctly by clicking the tools icon.

    ![Rootbuilder Confirm](./images/mo2-rootbuilder-confirm.png)

---

## Installing Mods in Root Builder Format

Root builder uses a slightly modified folder structure when installing mods that need to be in the Fallout 4 folder such as F4SE or ENBs. 

During installation you will need to create a `Root` folder inside of the `Data` directory and place any files that need to be in the Fallout 4 folder (where `Fallout4.exe` is located) into the new `Root` folder.

I will start off with F4SE since it is required for several other mods to function properly.

***NOTE: Many mods installed in this way will have a warning that there is no valid game data. This is expected since this is an unofficial plugin MO2 does not recognize the folder structure.***

### F4SE Installation

1. [Download F4SE](https://f4se.silverlock.org/) and save it to an easy to find location, the desktop works well. Drag the archive into MO2's download tab

    ![Move F4SE](./images/mv-f4se.png)

1. Begin the installation as normal by double clicking the mod in the downloads tab. Expand the drop downs until you see the `Data` folder. Right click the `Data` folder and create a `Root` folder inside of it.

    ![F4SE01](./images/rootbuilder-f4se01.png)

1.  Now put all the files that are required to be in the Fallout 4 directory into the `Root` folder.

    ![F4SE02](./images/rootbuilder-f4se02.png)
    
1. For F4SE to function only `f4se_1_10_163.dll`, `f4se_steam_loader.dll` and `f4se_loader.exe` are required. You can uncheck everything else in the `Root` file.

    ![F4SE03](./images/rootbuilder-f4se03.png)

1. Finally right click the `Data` folder and select `Set as <data> directory`. Your final folder structure should look like the picture below.

    ![F4SE03](./images/rootbuilder-f4se04.png)

1. Click "OK" and your F4SE installation is now complete! I renamed mine to `MO2-F4SE` to make it easier to find later. Don't forget to enable the mod on the left panel.

    ![F4SE03](./images/rootbuilder-f4se05.png)

1. To launch FO4 using F4SE you will need to add it as a launcher. Start by clicking the executable button near the top of MO2.

    ![MO2 Executable 01](./images/mo2-add-executable01.png) 

1. When the executable window opens click the `+` to and select `add from file...`. 

    ![MO2 Executable 02](./images/mo2-add-executable02.png) 
     
1. Navigate to the F4SE mod you created earlier and select the `f4se_loader.exe`. 

    ![MO2 Executable 03](./images/mo2-add-executable03.png)

1. After you have selected your F4SE executable be sure click Apply at the bottom of the window. As you can see I gave mine a different title. This is just my preferred naming scheme, you do not need to rename it.

    ![MO2 Executable 04](./images/mo2-add-executable04.png)

1. Now you can launch F4SE from the dropdown next to the `Run` button in the top right side of MO2.

    ![MO2 Executable 05](./images/mo2-add-executable05.png)

Now F4SE is installed correctly and you can launch your game with all the extra goodies F4SE has to offer.

---

### Buffout 4 TBB Redistributables

1. Begin the installation as normal by double clicking the mod in the downloads tab. Right click the `Data` folder and create a `Root` folder inside of it.

    ![Rootbuilder Buffout01](./images/mo2-rootbuilder-buffout01.png)

1. Move `tbbmalloc.dll` into the new `Root` folder

    ![Rootbuilder Buffout02](./images/mo2-rootbuilder-buffout02.png)

1. Click `OK` and and you're done! Don't worry about MO2 saying the contents aren't valid, that is expected. Press ignore on the warning that comes up.

    ![Rootbuilder Buffout03](./images/mo2-rootbuilder-buffout03.png)

1. Don't forget to enable on the left pane in MO2!

---

### ENB Binaries

This is a basic install of the ENB Wrapper itself that presets on Nexus require. 

1. [Download ENB](http://enbdev.com/download_mod_fallout4.htm) and save it to a temporary location. The desktop is a good location. Extract it and find the `Wrapper` folder. Right click and add it to a compressed folder. You can use whatever tool you would like for this as long as you end up with a ZIP or 7z archive.

    ![ENB Wrapper01](./images/enb-wrapper01.png)

1. Drag your new archive into MO2. I have renamed my archive but you could leave it as "Wrapper" if you like.

    ![ENB Wrapper02](./images/enb-wrapper02.png)

1. In MO2 begin the installation as normal by double clicking the mod in the downloads tab. Right click the `Data` folder and create a `Root` folder inside of it.

    ![Rootbuilder ENB01](./images/mo2-rootbuilder-enb01.png)

1. We only need `d3d11.dll` and `d3dcompiler_46e.dll` for this install. Move them into the new `Root` folder and uncheck everything else.

    ![Rootbuilder ENB02](./images/mo2-rootbuilder-enb02.png)
    
1. Click `OK` and and you're done! Don't worry about MO2 saying the contents aren't valid, that is expected. Press ignore on the warning that comes up.

    ![Rootbuilder ENB03](./images/mo2-rootbuilder-enb03.png)

1. Don't forget to enable on the left pane in MO2!

---

### ENB Preset

Comming Soon

---

### xSE Plugin Preloader
   
1. Begin the installation as normal by double clicking the mod in the downloads tab. Right click the `Data` folder and create a `Root` folder inside of it.

    ![Rootbuilder Preloader01](./images/mo2-rootbuilder-preloader01.png)
   
1. Move `lpHlpAPI.dll` and `xSE PluginPreloader.xml` into the new `Root` folder

    ![Rootbuilder Preloader02](./images/mo2-rootbuilder-preloader02.png)

1. Click `OK` and and you're done! Don't worry about MO2 saying the contents aren't valid, that is expected. Press ignore on the warning that comes up.
   
    ![Rootbuilder Preloader03](./images/mo2-rootbuilder-preloader03.png)

1. Don't forget to enable on the left pane in MO2!

---

## Final Notes and Other Resources

If the red "x" flags in MO2 bother you they will go away if you right click the mod and select "Ignore Missing Data"

![MO2 Flags](./images/mo2-missing-data.png)

---

Bigglesworth has also made a guide for Root Builder with his custom repacks if you are interested. Find it [here](https://docs.google.com/document/d/1G_atn4azIh0JPrvBVAV6PhJ5kkrVnaktbBi_PJRpzV4/edit?usp=sharing) !