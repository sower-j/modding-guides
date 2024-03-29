# Horizon Framework - Custom Groups 

This guide will give a more in-depth explanation for using the custom groups that come with the Horizon Framework collection on Nexus.


TLDR: Put ESM plugins in the `Master Plugins (ESMs)` group, put ESL plugins in the `ESLs` group, patches for Horizon (standalone or replacer ESPs) in the `Horizon Patches` group. **Do not make changes to any of the other groups unless you know what you are doing**

---

### **For those who don't know the distinction between "standalone patches" and "(ESP) replacer patches":**
  - Standalone patches are a new plugin that uses the original mod and Horizon as a master.
  - (ESP) Replacer patches edit the original mod's plugin to make it compatible with Horizon. They should have Horizon as a master as a result.

---

Since there is no way to manually order plugins in Vortex I had to get creative with groups to get Horizon's plugins into the order recommended by the author, Zawinul.

## New Groups

Lets start by looking at the groups I've added and their purpose.

<img src="./images/hz-vortex-groups.png" width="50%">

| Group Name | Purpose |
| :--------- | :------ |
|Master ESMs | This group is where all other plugins with the ESM extensions should go. Their order within this group is not terribly important but we need all non-Horizon ESMs in this group to ensure Architect is the final loaded ESM. ***With the exception of official FO4 plugins*** **Users should add ESM plugins to this group** |
|Architect | This group is designated to a single plugin, `Architect.ESM`. This ensures it is the final ESM loaded which is important because the rest of Horizon relies on the changes made here. If other mods were to overwrite it, Horizon may not function as expected. **Nothing should be added to this group** | 
| ESLs | This group serves the same purpose as Master ESMs. ***With the exception of official Creation Club Content*** **Users should add ESLs to this group** |
|Architect Addons | This group contains two plugins that edit global loot respawns and should need to be the first ESP type plugins. This group ensures they maintain this position. **Nothing should be added to this group** |
| Horizon Patches | This group ensures patches for horizon load after official Horizon plugins, but before some that need to be loaded last for compatibility reasons. **Users should add standalone and/or esp replacer patches to this group** |
| Horizon Last | This group ensures a set of plugins from the Horizon installer load last. These plugins are very sensitive to being overwritten so they must load last. **Nothing should be added to this group unless the mod author says it needs to go below Horion's plugins** |

---

## Requirements for adding plugins to groups

There are only three groups the user should be editing: `Master ESMs`, `ESLs`, and `Horizon Patches`. Below are the requirements for adding plugins to each group.

  - Master ESMs - **With the exception of official Fallout 4 Plugins** Any plugin that ends in `.esm`
  - ESLs - **With the exception of official Creation Club content** Any plugin that ends in `.esl`
  - Horizon Patches - Any type of patch for Horizon, standalone or (ESP) replacer.

## Adding Plugins to New Groups

I will demonstrate adding plugins to groups using a patch as an example, but the process is similar for the other two groups. To start with, go to the plugins tab in Vortex. Double click the plugin to open the sidebar.

In this example I am going to add `VCMT Expansion patch - PROJECT VARIANCE.esp` to the `Horizon Patches` group because it is a **(ESP) replacer patch** that has `Z_Horizon.esp` as a master as seen below. 

  - Note: Not all patches are guaranteed to have `Z_Horizon.esp` as a master. Sometimes people forget to assign it during patch creation so try to pay special attention to ESP origins

<img src="./images/hz-patch-group01.png" width="50%">

Once you have confirmed your plugin is a patch for Horizon open the groups drop down menu and select `HZ Patches`

<img src="./images/hz-patch-group02.png" width="50%">

At this point I suggest manually triggering a resort by pressing the sort button near the top of the page to confirm correct load order position.
