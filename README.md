# AllTameable

![Banner](https://raw.githubusercontent.com/meldurson/AllTameable/main/Banner.png)

This update to the AllTameable from buzz so if they want it removed I will oblige. I'm fairly new to coding in unity so there may be some issues.

The original mod can be found at [AllTameable](https://www.nexusmods.com/valheim/mods/478?tab=description)

A detailed changelog can also be found on the [Nexus Page](https://www.nexusmods.com/valheim/mods/1571?tab=description)

I made this so I could use it on a dedicated server and ended up adding features that I wanted to have.

__By default, the config file does not add taming to any additional creatures. Each creature has to be manually added to the config or use one of the provided config files__


__The current state of the mod includes the following features:__

* Ability to tame any creature specified in the config including added by RRRM (Others may work I just haven't tested)
* Works in singleplayer, multiplayer, and dedicated server as long as all parties have the mod installed
* Added a craftable item that when hovering over a creature and wielding the item it will show taming time and acceptable consumables
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
* Can tame passive creatures such as Deer (or others added my mods such as Horems Wildlife)


__Current features that do not work:__
* Ability to tame Bosses (they have special AI that is not conducive with taming)
* Ability to tame Birds (also have a special AI)

## Installation Instructions:

* Download the main file with a mod manager or manually place the DLL file in the plugins folder
* Download one of the TameList in the optional files section and place in the config folder
  * [TameList Vanilla](https://github.com/meldurson/AllTameable/blob/main/TameList%20Vanilla.zip)
  * [TameList DoD](https://github.com/meldurson/AllTameable/blob/main/TameList%20DoD.zip)
* Open the TameList file and modify to your hearts content, including adding creatures that are added by mods as long as it follows the correct format
* If wanting to modify tame of RRRNPC then I recommend using my [RRRCore Taming Patch](https://github.com/meldurson/AllTameable/raw/main/RRRCoreTamingPatch_0.0.1.zip)

__Note:__ The new TameList is optional, if you already have the original config file you do not need to download any extra files. The TameList file with override if it is found when loaded, otherwise the "meldurson.valheim.AllTameable.cfg" is used.


## Configuration

The descriptions of the options in the config are as follows:
* __name:__ This is where you put the IDs of the creatures you are adding separated by a : (colon)
* __commandable:__ This sets the ability to order them to follow you or not
* __tamingTime:__ This is the time it will take to tame the creature (in seconds)
* __fedDuration:__ This is how long a creature will be full for after it eats (in seconds)
* __consumeRange:__ This is the max range the creature can be at to eat food
* __consumeSearchInterval:__ This is how often the creature checks to see if food is in range to decides whether it needs it (in seconds)
* __consumeHeal:__ This is how much health each food provides
* __consumeSearchRange:__ This is the range the creature can detect food from
* __consumeItems:__ This is where you put the ID's of the items you want the creature to eat, put a : symbol in between each food (doesn't need to be a food item)
* __changeFaction:__ This is whether the creature will change faction when tamed (If set to on it will attack/get attacked by anything that attacks you)
* __procretion:__ This is whether the creature can breed to produce offspring
* __maxCreatures:__ This is the max amount of creatures within 30m you can have of the creature ID typed in, if it exceeds this they will stop breeding
* __pregnancyChance:__ This is the chance the creature has of becoming pregnant, Lower number = higher chance (scales from 0.00 to 1.00)
* __pregnancyDuration:__ This is how long the creature is pregnant for (In seconds)
* __growTime:__ This is how long it takes for offspring to grow into an adult (In seconds)

__Example:__
Deer,true,900,150,2,10,30,20,Raspberry:Blueberries:Carrot:Turnip:Mushroom:Cloudberry:OnionSoup:Onion,true,true,10,0.66,150,300

__To make two different prefabs able to breed with each other separate their ID with a colon such as:__
RRRN_HumanMale:RRRN_HumanFemale,true,900,150,2,10,30,20,CookedMeat,true,true,10,0.66,150,500

This will allow for both humans to breed with each other

__To make a creature not tameable you set the line to the creature name plus a -1 such as:__

Wolf,-1

This will not allow for wolves to be tamed

__Note:__ This should be used on servers to set creatures you don't want tamed


