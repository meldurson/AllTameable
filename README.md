
![Title](https://raw.githubusercontent.com/meldurson/AllTameable/main/Pics/Title.png)
##  

![Banner](https://raw.githubusercontent.com/meldurson/AllTameable/main/Pics/DeerHover_5to1Zoom.png)
This is an overhaul and rewrite of [AllTameable](https://www.nexusmods.com/valheim/mods/478?tab=description) from Buzz.

### Latest Update
    Version 1.5.1
    * Fixed mass command localization
    * Now shows adjusted taming time with buffs
    * Implemented stricter network version allowance
	
### Feral Creatures
* With __update 1.4.7__ you can now have creatures that you are not yet able to tame.
* These creatures will be notated as __"Feral"__ instead of Wild when looking at them.
* The two circumstances this can happen is:
    * In the _meldurson.valheim.AllTameable.cfg_ file you can set the maximum level you can tame wild creatures. So if set to __1__ then any two star (or higher with CLLC) would be feral and cannot be tamed. 
    * In the _AllTameable\_TameList*.yml_ files you can specify a custom option of __requiredWorldKeys=__ such as _defeated_dragon_ which will mean unless you have defeated Modor they will be _Feral_.
* You can read more on how to modify the tamelist for required keys [HERE](https://thunderstore.io/c/valheim/p/Meldurson/AllTameableTamingOverhaul/wiki/572-1-how-to-format-the-tamelist/)
####

## DNA
* All tameable creates can now have random colour and traits.
* You can toggle both if you just want colour or just want traits.
* Same as everything else, when breeding will inherit with variance from parents 
* New equipment to show you a creature's DNA.
* The lower other physical stats, the easier it is to get higher in another stat.  
####
 
<details>
   <summary>Strength of Stat Effects</summary>
  
  | Main Stat    | Strong Effect (30%) | Medium Effect (20%) | Weak Effect (10%)|
  | ----------- | ----------- | ----------- |----------- |
  | Speed      | Armor     |Size | Health
  | Armor     | Speed     |Health | Size
  | Health     | Size     |Armor | Speed
  | Size    | Health     |Speed | Armor
  
  
  
  __Examples:__  
  *We will use a variance (configurable ) of 10%*
  *  If you two creatures with all traits at 100%, the range of the trait will +-10%.
  *  If you have two creatures with 50% Speed and 100% Armor, Health, and Size, since Speed has a Strong effect on Armor and Speed is low, the range of the Armor trait will +13%,-7.7%, for Size the range would be +12%,-8.3%, for Health the range would be +11%,-9%, and for Speed it would stay +-10%
  *  Oppositely, if you have a 150% Speed, 100% all others, the ranges will be, +7.7%,-13% for Armor, +8.3%,-12% for Size, -9%,+11% for Health
  *  This compounds will all traits, so if Speed, Armor, and Size are all 50% and Health is 150% the ranges would be:
     *   +17,-5.6 for Health: *(1.3x1.2x1.1=1.7 increase)* , *(0.77x0.83x0.9 = 0.56 decrease)*
     *   +14,-7 for Speed *1.3x1.2x0.9=1.4 increase* , *0.77x0.83x1.1 = 0.7 decrease*
     *   +12,-8.3 for Armor *1.3x0.83x1.1=1.2 increase* , *0.77x1.2x0.9=0.83 decrease*
     *   +10,-9.7 for Size *0.77x1.2x1.1=1 increase* , *1.3x0.83x0.9=0.97 decrease*
  * Detailed calculations for DNA can be found [here](https://valheim.thunderstore.io/package/Meldurson/AllTameableTamingOverhaul/wiki/574-detailed-calculations-for-dna/)
 </details>  
 

* As the new DNA system is a major overhaul and is quite complex, if you have any issues, [let me know](https://github.com/meldurson/AllTameable/blob/main/README_New.md#contact) and I can try and fix them.
* If you have errors or do not want the DNA system you can disable it in the config.
* Also, if you have any suggestions on how the DNA system or the mod can be improved, feel free to make a suggestion [here](https://github.com/meldurson/AllTameable/discussions/2)
  
![DNA](https://raw.githubusercontent.com/meldurson/AllTameable/main/Pics/DragonDNA_5to1Zoom.png)  



## New in 1.3
* Works with Ashlands.
* Complete overhaul of eggs and hatching.
  * Eggs now have levels inherited from parents and determines level once hatched.
  * Dragon eggs now hatch the same as chicken eggs.
  * All genetic functionality that was available with normal offspring now can apply to eggs.
* Changed where taming tools are made, now required to use a crafting table.
* Added an advanced taming tool that can be used to interact with creatures from further away and command multiple creatures at a time.
* Can cycle between different mass commands using the cycle key when looking at a tamed creature.
* Added three tiers of special taming food that reduces taming time, made in the cauldron.
* Mutation chances are now split between levels, infusions, and effects.
* Can now log out and into a different world at it will reload your configs, no longer need to quit and reopen.
##
__The current state of the mod includes the following features:__
![Creatures](https://raw.githubusercontent.com/meldurson/AllTameable/main/Pics/LoxHatchlingUlv_5to1.png)

* Ability to tame any creature specified in the config including added other mods.
* Works in singleplayer, multiplayer, and dedicated server as long as all parties and the server have the mod installed.
* Added craftable items that when hovering over a creature and wielding the item it will show taming time and acceptable consumables.
* Ability to have hatchable dragon eggs.
* New Config solution to manage creature tames more easily.
* CLLC integration (Optional):
  * Levels of hatched dragon egg gets level chance from CLLC.
  * Inheritance of effect and infusion from parents.
  * Mutation chance to get a different effect/infusion.
  * Mutation chance for level to change (+1/-1) eg: two 3 star creatures would have a chance to breed a 4 star and also 2 star.
* __Monster Modifier integration__
* Added ability to remove option for taming.
* Can set a healing amount when a tame consumes an item (this feature was removed in Hearth and Home).
* Can breed Humans added by RRRNPC.
* Can breed different creatures together (mainly useful for humans with male/female variants).
* Can tame passive creatures such as Deer (or others added by mods such as Horems Wildlife).
* Can have specific offspring depending on mates.
* Can set Trades for instant taming.  
* __Can turn on Simple Mode to only change taming and does not include custom procreation.__
  * If do not need complex procreation and are having issues, turn this on in config.
* Special taming food that decreases taming time.
  * Made using the cauldron and uses completed tasty mead.
  * Potion that can be drank that speeds up taming of all creatures in area.
* Increased reach for interaction with creatures when using the taming tool.
* Can have creatures lay eggs.
* Command multiple creatures at once with taming wand.
* DNA that is randomized for every creature and can be breed for specific traits.
* Equipment to help with taming and breeding.
* Can hand feed tamed creatures by using food on them.
* __Can tame all bosses!__

![Modor](https://raw.githubusercontent.com/meldurson/AllTameable/main/Pics/DragonTower5to1.png)

__Current features that do not work:__
* <del>Ability to tame Bosses (they have special AI that is not conducive with taming)</del> fixed in version 1.3.3
* Ability to tame Birds (also have a special AI)


### Items:
![Items](https://raw.githubusercontent.com/meldurson/AllTameable/main/Pics/Items_5to1.png)
There are currently 2 tools, 3 wearables, and 4 consumables added by this mod. The recipes can be modified in the config file.
<details>
  <summary>Default Recipes</summary>
  
| Item      | ID | Required Items | Crafting Station |
| ----------- | ----------- | ----------- |----------- |
| Taming Tool      | el_TamingTool       |1 Raw Meat, 1 Red Mushroom, 1 Carrot, 5 Resin | Workbench lvl 1
| Taming Wand     | el_AdvancedTamingTool       |3 Crystal, 20 Cloudberry,10 FineWood,2 Dragon Tears | Workbench lvl 4
| Basic Taming Food     | el_T1Food       |1 Tasty Mead, 3 Yellow Mushroom, 1 Leather Scraps | Cauldron lvl 1
| Superior Taming Food X 3     | el_T2Food       |6 Medium Health Potion, 10 Barley Flour, 1 Dragon Tear | Prep Table lvl 1
| Excellent Taming Food     | el_T3Food       |4 Minor Eitr Mead, 2 Major Health Potion, 1 Anglerfish, 5 MageCap | Cauldron lvl 5
| Mead Base Speed Tame     | MeadBaseSpeedTame       |3 Wolf Trophy, 5 Barley Flour, 5 Tamed Nearby*, 10 Honey | Mead Cauldron lvl 1
| Taming Potion X 4     | MeadSpeedTame       |1 Mead Base Speed Tame | Fermenter
| Calming Gloves     | CalmingGloves       |6 Linen Thread, 2 Silver, 4 Tamed Nearby*, 5 Wolf Hide | Workbench lvl 4
| Taming Hat     | TamingHat       |10 Linen Thread, 5 Tamed Nearby*, 1 Goblin Totem, 15 Lox Hide | Artisan Table lvl 1
| Bestial Command Robes     | BestialRobes       |10 Wolf Pelt, 10 Linen Thread, 10 Tamed Nearby*, 5 Needle | Workbench lvl 5


\* Must have __X__ number of tamed creatures nearby (10m) when attempting crafting
</details>

##


I made this so I could use it on a dedicated server and ended up adding features that I wanted to have. I can only work on this in my spare time, if you enjoy the mod and want and have the ability to send a few bucks you can on [Ko-fi](https://ko-fi.com/meldurson)

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/B0B3NARM0)


![Soldier Egg](https://raw.githubusercontent.com/meldurson/AllTameable/main/Pics/SeekerSoldierEgg_5to1.png)


## Installation Instructions:

* Download the main file with a mod manager or manually place the DLL file in the plugins folder.
* ### This mod is required to be installed on both client and server in order to function!
* Download one of the TameList in the optional files section and place in the config folder.
  * [TameList Vanilla](https://github.com/meldurson/AllTameable/blob/main/TameList%20Vanilla.zip) curated list with increasing difficulty to tame.
  * [TameList Simple](https://github.com/meldurson/AllTameable/blob/main/TameList%20Simple.zip) sticks to vanilla taming except for what you can feed.
  * [TameList DoD](https://github.com/meldurson/AllTameable/blob/main/TameList%20DoD.zip) (updated Nov 23)
  * [TameList Monsterlabz](https://github.com/meldurson/AllTameable/blob/main/TameList%20MonsterLabz.zip) (updated Nov 23)
  * [TameList Monstrum](https://github.com/meldurson/AllTameable/blob/main/TameList%20Monstrum.zip) (updated Nov 23)
  * [TameList EpicValheim](https://github.com/meldurson/AllTameable/blob/main/Tamelist%20EpicValheim.zip) (updated Feb 23)
  
* Open the TameList file and modify to your hearts content, including adding creatures that are added by mods as long as it follows the correct format.
* If you have a Tamelist that you want to share, feel free to send it to me through Discord.


### [Configuration](https://valheim.thunderstore.io/package/Meldurson/AllTameableTamingOverhaul/wiki/572-how-to-format-the-tamelist/)
Explanation and overview of how to format the TameList can be found on the [wiki](https://valheim.thunderstore.io/package/Meldurson/AllTameableTamingOverhaul/wiki/572-how-to-format-the-tamelist/)
and a more detailed version can be found [here](https://valheim.thunderstore.io/package/Meldurson/AllTameableTamingOverhaul/wiki/573-in-depth-explanations-of-tamelist/)


### Known Incompatibilities:
* Issues with Valheim Plus Invincible Tames (throws an error, not game breaking)
* Tames entering WardIsLove wards can throw an error (Also not game breaking)


## Troubleshooting
__If a creature is not tameable when you think they should be then there are a steps you can take:__
1. When you start the game before the title screen there will be a block of messages saying which creatures have been set to tameable. The start of the message will be __[Info   :AllTameable-Overhaul]__ the name of the creature should be here with successfully added beside it. If it is not you may need to check your TameList
2. If you enable Debug Output in the __meldurson.valheim.AllTameable.cfg__ then when you load into the world it should show what creatures have successfully changed to be tameable and if they are commandable. This will be a block of  
__[Warning:AllTameable-Overhaul]__ Creature is commandable
__[Warning:AllTameable-Overhaul]__ Successfully added Tame and Procreation to Creature
3. If it says that the creature is tameable or commandable but does not show when in game, if you use the Taming Tool when Debug is enabled and hover over the creature it will show the Prefab name and if it is commandable. If the Prefab name is not in your Tamelist then you will have to add it.


__If a creature is not procreating then there are a couple steps you can take:__
1. Enable Debug in the __meldurson.valheim.AllTameable.cfg__
2. When hovering over the creature when they are fed it will bring up a few stats. 
   - The one you may need to look at is the Less than max instance: 
4. If it says Needs Mate then it will let you know the creatures that are around
5. If it says Error then it will post in Bepinex what the error is (Note: For 30s-1m after loading into a world there may be some errors with other mods that affect spawning that should go away)

   If none of that works, then reach out to me on the [Valheim Modding Discord](https://discord.com/invite/GUEBuCuAMz) 

### Contact:
The most reliable way to reach out would be to ping me in the [Valheim Modding Discord](https://discord.com/invite/GUEBuCuAMz) under @Meldurson or dm me on Discord.
