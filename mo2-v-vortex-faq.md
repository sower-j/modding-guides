# Mod Organizer 2 Vs Vortex - FAQ

The goal of this document is not to bash one mod manager or the other. Instead it is meant to clear up some misconceptions about MO2 and Vortex. Keep in mind that MO2 and Vortex have different design goals. Vortex is designed to handle modding any game on Nexus, so it needs to be slightly more complex/robust. MO2 was designed to handle Bethesda games and is optimized for that modding structure. It has since had compatibility added for other games, but still doesn't require the same level of robustness Vortex does. 

## Questions and Answers

---

### Isn't Vortex best for beginners? Nexus says it was specifically designed for new modders while MO2 is for advanced modders.

<details>

  <summary><u><b>expand answer</u></b></summary>

In my opinion no. I'm not saying Vortex doesn't work for beginners, but it doesn't help you build any skills or understanding either.

Vortex works great if you never plan on exceeding 20 mods or so. Once you pass that number, user intervention is required to manage conflicts and load order. Now you have a problem. You have lots of mods you want to use, but have no knowledge of how to handle conflicts and load order because Vortex has been doing it for you.

These are skills and knowledge you acquire immediately while using MO2 because it doesn't do anything in the background for you. Your knowledge will grow at a steady rate as you continue to add mods instead of the large spike of knowledge required for Vortex once it can no longer properly handle the number of mods you want to use. 

</details>

---

### Isn't Vortex's UI easier to understand/use than MO2's? 

<details>

  <summary><u><b>expand answer</u></b></summary>

In some cases yes. If you have a small mod list Vortex can be simpler to use. However, once you start using custom rules it becomes quite complex. Meanwhile, MO2 has the same level of complexity regardless of how many mods you have installed.

Vortex has all its information split up onto different screens. Installed/enabled mods, file overwrite rules, plugin order, plugin groups (LOOT groups), and plugin-to-plugin specific load order rules all have their own screen. It becomes quite difficult to remember what you have done previously which can lead to creating cyclical rules that can be quite difficult to troubleshot. (Yes, I have done this and it was a nightmare figuring out where I made the mistake) 

In contrast, you can see all file overwrites and plugin order at the same time in MO2. There is no switching from screen to screen, or trying to remember what other rules/groups you have created to manage things. In addition you use the same methods for managing file conflicts and plugin load order: drag and drop. Whichever mod/plugin is lower in the list wins.

</details>

---

### Doesn't Vortex's LOOT handle everything for me? Why would I want to use MO2 where I have to manually sort everything?

<details>

  <summary><u><b>expand answer</u></b></summary>

LOOT isn't perfect, at some point user intervention is required to properly handle conflicts. With Vortex you have to start working around LOOT's default sorting rules, which requires advanced knowledge of LOOT groups and plugin conflict resolution.

MO2 can run a basic version of LOOT, which will ensure plugins will be loaded after any plugins it has tagged as a master. Outside of that you are not confined to any specific sorting schema and can sort things in a way that makes sense for you.


</details>


---

### What's the difference between how Vortex and MO2 handle files? I thought they did the same thing.

<details>

  <summary><u><b>expand answer</b></u></summary>

The end result of how each manager handles files feels the same to the user, but when you look into it, they are completely different. 

Note: The following is a very simplified explanation, if you would like a more in-depth answer feel free to contact me on Discord or Nexus.

Vortex uses what are essentially advanced shortcuts (hard links) to make files available in the Fallout 4 folder. This method has several disadvantages:

  1. Hard-links can only be used to link files to the same drive letter (C:). This means you cannot have your mods and game on two separate drives.

  1. The system used to manage these links is vulnerable to errors, which can lead to files being deleted, not removed, or not updated when expected. (While this is rare, it can cause major issues)

  1. Using the base Fallout 4 folder means if something goes wrong you could be left with your base game files broken or missing, which would require you to do a full re-install of the game to fix it.

Mod Organizer 2 uses a standalone virtual file system. This system avoids the disadvantages present in Vortex's systems:

  1. The virtual file system is not tied to a single drive, you can have your mods and game on separate drives if you wish.

  1. The virtual file system is regenerated every time the game is launched, so it is highly unlikely to contain errors.

  1. Since MO2 generates its own file system your game folder is never touched so you will never have to reinstall your game again.

</details>

---

### Vortex can install things like F4SE, Why can't MO2?

<details>

  <summary><u><b>expand answer</b></u></summary>

Since Vortex just uses hard links (see question above if you don't know what this means) it's easy to put these files directly in the root (base) Fallout 4 folder. But this comes with the risk of messing up your game files.

Mod organizer 2's virtual file system does not interact with the root Fallout 4 folder by default, it only makes a copy of the Data folder in the virtual file system.

There is a tool to enable MO2 to install things like F4SE called Root Builder. This tool first makes a backup of your root Fallout 4 folder. When the game is launched it copies the required files to the Fallout 4 folder. After the game closes it removes the files it added and checks the contents of your Fallout 4 folder against the backup it made to ensure no files were removed or modified in any way. If anything was changed (extremely unlikely) it will notify you and you can restore your original files from the backup.

If you would like more details about Root Builder I have a guide for installing and using it [here](./mo2-rootbuilder.md)

</details>
