
![Title](https://raw.githubusercontent.com/meldurson/AllTameable/main/Pics/Title.png)
##  

![Banner](https://raw.githubusercontent.com/meldurson/AllTameable/main/Pics/DeerHover_5to1Zoom.png)
This is an overhaul and rewrite of [AllTameable](https://www.nexusmods.com/valheim/mods/478?tab=description) from Buzz.

## DNA
* All tameable creates can now have random colour and traits
* You can toggle both if you just want colour or just want traits
* Same as everything else, when breeding will inherit with variance from parents ( *Requires [CLLC](https://valheim.thunderstore.io/package/Smoothbrain/CreatureLevelAndLootControl/)* )
* New equipment to show you a creatures DNA  

![DNA](https://raw.githubusercontent.com/meldurson/AllTameable/main/Pics/DragonDNA_5to1Zoom.png)  



## New in 1.3
* Works with Hildir's Update
* Complete overhaul of eggs and hatching
  * Eggs now have levels inherited from parents and determines level once hatched
  * Dragon eggs now hatch the same as chicken eggs
  * All genetic functionality that was available with normal offspring now can apply to eggs
* Changed where taming tools are made, now required to use a crafting table
* Added an advanced taming tool that can be used to interact with creatures from further away and command multiple creatures at a time
* Can cycle between different mass commands using the cycle key when looking at a tamed creature
* Added three tiers of special taming food that reduces taming time, made in the cauldron
* Mutation chances are now split between levels, infusions, and effects
* Can now log out and into a different world at it will reload your configs, no more need to quit and reopen
##
__The current state of the mod includes the following features:__
![Creatures](https://raw.githubusercontent.com/meldurson/AllTameable/main/Pics/LoxHatchlingUlv_5to1.png)

* Ability to tame any creature specified in the config including added other mods
* Works in singleplayer, multiplayer, and dedicated server as long as all parties and the server have the mod installed
* Added craftable items that when hovering over a creature and wielding the item it will show taming time and acceptable consumables
* Ability to have hatchable dragon eggs
* New Config solution to more easily manage creature tames
* CLLC integration(Optional):
  * Levels of hatched dragon egg gets level chance from CLLC
  * Inheritance of effect and infusion from parents
  * Mutation chance to get a different effect/infusion
  * Mutation chance for level to change (+1/-1) eg: two 3 star would have a chance to breed a 4 star and also 2 star
* Added ability to remove option for taming
* Can set a healing amount when a tame consumes an item (this feature was removed in Hearth and Home)
* Can breed Humans added by RRRNPC
* Can breed different creatures together (mainly useful for humans with male/female variants)
* Can tame passive creatures such as Deer (or others added by mods such as Horems Wildlife)
* Can have specific offspring depending on mates
* Can set Trades for instant taming  
* __Can turn on Simple Mode to only change taming and does not include custom procreation__
  * If do not need complex procreation and are having issues, turn this on in config
* Special taming food that decreases taming time
  * Made using the cauldron and uses completed tasty mead
  * Potion that can be drank that speeds up taming of all creatures in area
* Increased reach for interaction with creatures when using the taming tool
* Can have creatures lay eggs
* Command multiple creatures at once with taming wand
* DNA that is randomized for every creature and can be breed for specific traits
* Equipment to help with taming and breeding
* __Can tame some bosses!__
![Modor](https://raw.githubusercontent.com/meldurson/AllTameable/main/Pics/DragonTower5to1.png)

__Current features that do not work:__
* <del>Ability to tame Bosses (they have special AI that is not conducive with taming)</del> fixed in version 1.3.3
* Ability to tame Birds (also have a special AI)


### Items:
![Items](https://raw.githubusercontent.com/meldurson/AllTameable/main/Pics/Items_5to1.png)
There are currently 2 tools, 2 wearables, and 4 consumables added by this mod.
<details>
  <summary>Recipes</summary>
  
| Item      | ID | Required Items | Crafting Station |
| ----------- | ----------- | ----------- |----------- |
| Taming Tool      | el_TamingTool       |1 Raw Meat, 1 Red Mushroom, 1 Carrot, 1 Resin | Workbench lvl 1
| Taming Wand     | el_AdvancedTamingTool       |3 Crystal, 2 MageCap, 5 Eitr, 10 FineWood, 2 Major Health Potion | Workbench lvl 3
| Basic Taming Food     | el_T1Food       |2 Tasty Mead, 5 Yellow Mushroom, 2 Freeze Gland, 1 Leather Scraps | Cauldron lvl 2
| Superior Taming Food X 3     | el_T2Food       |6 Medium Health Potion, 10 Barley Flour, 1 Dragon Tear | Cauldron lvl 3
| Excellent Taming Food     | el_T3Food       |4 Minor Eitr Mead, 2 Major Health Potion, 1 Anglerfish, 5 MageCap | Cauldron lvl 5
| Mead Base Speed Tame     | MeadBaseSpeedTame       |5 Wolf Trophy, 2 Superior Taming Food, 10 Honey | Cauldron lvl 1
| Taming Potion X 4     | MeadSpeedTame       |1 Mead Base Speed Tame | Fermenter
| Calming Gloves     | CalmingGloves       |6 Linen Thread, 2 Silver, 4 Tamed Nearby*, 5 Scale Hide | Artisan Table lvl 1
| Taming Hat     | TamingHat       |10 Linen Thread, 2 Eitr, 10 Tamed Nearby*, 8 Scale Hide | Galdr Table lvl 1


\* Must have __X__ number of tamed creatures nearby (10m) when attempting crafting
</details>

##


I made this so I could use it on a dedicated server and ended up adding features that I wanted to have. I can only work on this in my spare time, if you enjoy the mod and want and have the ability to send a few bucks you can on [Ko-fi](https://ko-fi.com/meldurson)

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/B0B3NARM0)

## Changelog

<details>

Version 1.3.3
* Added DNA to all creatures modified by AllTameable
* Added Calming Gloves, Taming Hat, and Taming Potion
* Fixed taming of some creatures that are set to hunt player
* Made so tamed bosses will no longer create weather effects or have a boss bar
* Added equipment to children (not weapons)
* Made groups able to be set for creatures that are set to not be tameable
* When trying to reproduce will take into account all possible mates and offspring to determine max amount in area
* Fixed issue with loading eggs when logging out
* Fixed error with children of creatures that talk (Dverger)
* No longer can interact with fire with a Dragon Egg, need to hatch like chicken egg
* Taming Tool uses resin again to craft instead of Dragon Egg
 
Version 1.3.2
* Fixed incompatibility with JewelCrafting
* Adjusted chicken size to scale better with levels
 
Version 1.3.1
* Fixed issue where could not add dragon eggs to Moder altar
* Made dragon eggs default stack to 20 except if special
   
Version 1.3
* Added ability to specify a custom egg as offspring
* Made eggs have level that will carry over when hatched
* Made eggs inherit CLLC infusion/extra effect same as normal offspring  
* Made dragon eggs work the same as chicken eggs to hatch near fire  
* Added advanced taming stick that can command multiple tames in an area  
* Moved increased interact range to only be on advanced taming stick  
* Added Tier 3 taming food  
* Fixed issue with specific offspring not getting changed back to default  
* Made default tamelist taming values closer to vanilla (mostly with growup time)  
* Can now specify child offsping using specificOffspring and will not make a mini version of it  
* Made compatible with Hildir Update  
* Split mutation chances into three separate chances
* Added ability to specify group in config so tamed and wild of different prefabs won't attack eachother
* Fixed issue where logging out did not properly reset config so should be able to change world/servers without quitting game
  
Version 1.2.1
* Fixed incompatibility with Auto_Feed
  
Version 1.2.0
* Increased interact range with tame stick for creatures (can hover over them from further)
* Added taming food that when a creature consumes it will decrease taming time
* Changed sooth effect to be calmer
* Fixed default tamelist carrying over from file to file
  
Version 1.1.5
* Added Simple config option to only allow for simple procreation (use default vanilla)
* Removed the ability to specify creatures for taming in normal config (meldurson.valheim.AllTameable)
* If updating and specifying creatures in meldurson.valheim.AllTameable, will create TameList for you
* If not updating or do not specify creatures in meldurson.valheim.AllTameable then will make a Tamelist (Same as Vanilla TameList)
* Made complex procreation more stable
* Fixed issue where could find closest mate to be same creature even when set to canMateWithSelf=false
* Removed the need for adding a "-1" on a line in TameList that only specifies mates
* Changed ranges to scale with "size" in TameList
* Changed UpdatedInterval to closer to Vanilla
  
Version 1.1.4
* Added ability to set default in Tamelist
* Added ability to specify attributes by name in tamelist to change them
* Added custom attribute canMateWithSelf so creature can only mate with different creature
* Added custom attribute specificOffspring with probability of specific offspring
* Added ability to have multiple Tamelist files making it easier for mods
* Fixed not being able to specify different mates on separate lines
* Fixed maxCreatures allowing double what it should
  
Version 1.1.3
* Changed way procreation works to remove errors
* Fixed error of infinite spawns if error when growing up
* Fixed minor error when chickens lay eggs
* Added more information when using taming tool in debug mode
  
Version 1.1.2
* Added functionality to trade for instant tame
* Changed petting and taming sounds to be specific to tame and not just wolf growl
* Fixed issues with reading Tamelist for accomodating different number formats
* Added funtionality that small errors in tamelist will create notification but not break tame
* Fixed issue with default config file tames not updating change faction and procreation correctly
  
Version 1.1.1
* Updated to Mistlands update
* Added ability to have Seeker Broods as Offspring from Seekers or Seeker Brutes
  
Version 1.1.0
* Added ability to tame passive creatures (That have AnimalAI not MonsterAI)
* Added ability for different creatures to mate with eachother (such as male/female)
* Allowed for procreation of Humans created with RRRNPC
* Fixed issue where offspring would sometimes be untamed and attack everything
* Fixed issue of duplicating Dragon Egg
* Renamed to AllTameable Taming Overhaul
* Made looking at creatures with taming stick be a little more descriptive on what is missing
* Created a small separate optional patch for RRRNPC to help with taming errors
  
Version 1.0.7
* Fixed Deer and MountUp issue
* Added ability for consuming to provide a set heal on top of regen
* Made regen not say "+0" if regenerating a small amount of health (added healing vfx)
  
Version 1.0.6
* Added ability to tame deer
* Added optional CLLC integration
* Added tamelist format to remove ability to tame (useful for servers)
* Added breeding inheritance for CLLC
* Added mutation chance with breeding
* Fixed issue with two creatures of the same breed trying to kill each other if one tames before the other
* Added ability to get random level out of hatched dragon eggs
  
Version 1.0.5
* Fixed issue with dragon egg sometimes teleporting to spawn when interreacting with fire
* Added ability to pick up eggs once set down for hatching
  
Version 1.0.4
* Fixed some people unable to breed any creature
* Fixed raw meat disappearing on cooking rack
* Added more info when hovering over creature with taming tool
* Added a debug option in config that when set to false removes many lines from the debug window
* When debug set to true, taming stick will show exactly why a creature isn't breading
  
Version 1.0.3
* Added an easier way to load and manage creatures using the TameList
* Fixed ability to hatch dragon eggs
* Added built-in server config sync
* Optimized Startup loading
* Fixed closest creature when loading in to have incorrect taming properties
  
Version 1.0.0
* Updated to hearth and home update
* Added support for creatures added by mods
* Added dedicated server support
* Added a taming tool to see each creatures taming requirements
</details>

![Soldier Egg](https://raw.githubusercontent.com/meldurson/AllTameable/main/Pics/SeekerSoldierEgg_5to1.png)


## Installation Instructions:

* Download the main file with a mod manager or manually place the DLL file in the plugins folder
* Download one of the TameList in the optional files section and place in the config folder
  * [TameList Vanilla](https://github.com/meldurson/AllTameable/blob/main/TameList%20Vanilla.zip) currated list with increasing difficulty to tame
  * [TameList Simple](https://github.com/meldurson/AllTameable/blob/main/TameList%20Simple.zip) sticks to vanilla taming except for what you can feed
  * [Tamelist EpicValheim](https://github.com/meldurson/AllTameable/blob/main/Tamelist%20EpicValheim.zip) old
  * [TameList DoD](https://github.com/meldurson/AllTameable/blob/main/TameList%20DoD.zip) old
* Open the TameList file and modify to your hearts content, including adding creatures that are added by mods as long as it follows the correct format
* <del>If wanting to modify tame of RRRNPC then I recommend using my [RRRCore Taming Patch](https://github.com/meldurson/AllTameable/raw/main/RRRCoreTamingPatch_0.0.1.zip)</del> now included in main mod

__Note:__ The new TameList <del>is optional</del> _is now required_, if you already have the original config file you do not need to download any extra files. The TameList file with override if it is found when loaded, otherwise the "meldurson.valheim.AllTameable.cfg" is used to create a new Tamelist.


### [Configuration](https://github.com/meldurson/AllTameable/blob/main/Wiki_Tamelist.md)
Explanation and overview of how to format the Tamelist can be found on the [wiki](https://github.com/meldurson/AllTameable/blob/main/Wiki_Tamelist.md)
and a more detailed version can be found [here](https://github.com/meldurson/AllTameable/blob/main/Wiki_DetailedTameList.md)


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

   If none of that works then reach out to me on the [Valheim Modding Discord](https://discord.com/invite/GUEBuCuAMz) 

