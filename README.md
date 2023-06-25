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
* Can tame passive creatures such as Deer (or others added by mods such as Horems Wildlife)
* Can have specific offspring depending on mates
* Can set Trades for instant taming


__Current features that do not work:__
* Ability to tame Bosses (they have special AI that is not conducive with taming)
* Ability to tame Birds (also have a special AI)

__Known Incompatibilities:__
* Issues with Valheim Plus Invincible Tames (throws an error, not game breaking)
* Tames entering WardIsLove wards can throw an error (Also not game breaking)

## Installation Instructions:

* Download the main file with a mod manager or manually place the DLL file in the plugins folder
* Download one of the TameList in the optional files section and place in the config folder
  * [TameList Vanilla](https://github.com/meldurson/AllTameable/blob/main/TameList%20Vanilla.zip) currated list with increasing difficulty to tame
  * [TameList Simple](https://github.com/meldurson/AllTameable/blob/main/AllTameable_TameList_Simple.zip) sticks to vanilla taming except for what you can feed
  * [Tamelist EpicValheim](https://github.com/meldurson/AllTameable/blob/main/Tamelist%20EpicValheim.zip) old
  * [TameList DoD](https://github.com/meldurson/AllTameable/blob/main/TameList%20DoD.zip) old
* Open the TameList file and modify to your hearts content, including adding creatures that are added by mods as long as it follows the correct format
* <del>If wanting to modify tame of RRRNPC then I recommend using my [RRRCore Taming Patch](https://github.com/meldurson/AllTameable/raw/main/RRRCoreTamingPatch_0.0.1.zip)</del> now included in main mod

__Note:__ The new TameList <del>is optional</del> _is now required_, if you already have the original config file you do not need to download any extra files. The TameList file with override if it is found when loaded, otherwise the "meldurson.valheim.AllTameable.cfg" is used to create a new Tamelist.


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

__To make a creature tameable by trading set commandable to "trade" and then format trades as Tradeitem=TradeAmount:__
Dverger,trade,BlackCore=5:Coins=999

This will allow to tame a Dverger with either 5 Black Cores or 999 Coins (Note: if wanting to tame by feeding and trade then place trade line after feed line)


__To make a creature not tameable you set the line to the creature name plus a -1 such as:__

Wolf,-1

This will not allow for wolves to be tamed

__Note:__ This should be used on servers to set creatures you don't want tamed

Any line starting with a # in AllTameable_Tamelist will be skipped from calculating into the tamelist  
You can multiple AllTameable_Tamelist\*.cfg files where \* can be anything such as AllTameable_Tamelist_RRR.cfg  

Starting a line with a '\*' will then set all atributes in that as the default going forward allowing to only specify attributes you change,  
You can specify a new default at any time by starting a new line with '\*' as shown below the Boar will have the same attributes as Default and Deer with have the same attributes as Tier_1 the Greyling and Neck will have the same attributes as Tier_1 with dfferent consumeItems  
You can specify any attribute by "name=value"  
__example:__ Surtling,consumeItems=Coal:ElderBark  
This will use all the default values except for consumeItems

## Custom Options:

__canMateWithSelf:__ default=true, options:true,false  
Makes it so can only mate with other creatures that have been specified and not creatures with the same prefab  

__specificOffspring:__ default=none, specify in the form __Mate(offspring1:chance1/offspring2:chance2/...)__  
The following will make it so can only breed Goblins when breeding GoblinShaman and GoblinBrute with an 80% chance and when breeding two GoblinShaman there is a 70% chance to get a GoblinBrute and 30% to get a GoblinShaman

Goblin,-1  
\*GoblinElites,true,2300,250,2,10,90,20,SerpentMeatCooked:CookedLoxMeat:CarrotSoup:BloodPudding:FishWraps:LoxPie:TurnipStew:SerpentStew:BlackSoup:WolfMeatSkewer:WolfJerky:CookedWolfMeat:CookedHareMeat,true,true,6,0.66,200,600  
GoblinShaman,specificOffspring=GoblinBrute(Goblin:80/GoblinBrute:10),specificOffspring=GoblinShaman(GoblinBrute:70)  
GoblinBrute  
GoblinShaman:GoblinBrute  

__size:__ default=1, options: 0.5-4  
multiplier to determine how far away it checks for other creatures, most creatures you will not have to change.
Lox should be at least 2, Vanilla Bosses should be 3, 4 is only if it is massive!
You can use decimals and specify a smaller range if you choose such as 0.5 for a small creature such as a hen


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

