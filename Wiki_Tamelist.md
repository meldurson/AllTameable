# How to Format the TameList
You can have as many __TameList__ files in your config folder as you want and they will all be read.
Every file that you want to be read when the game loads should be a __.cfg__ and have a name starting with __AllTameable_TameList__:  
### Examples:   
- __AllTameable_TameList.cfg__  
- __AllTameable_TameList_From_Default.cfg__
- __AllTameable_TameList__*ModName*__.cfg__

### Premade TameLists

* [TameList Vanilla](https://github.com/meldurson/AllTameable/blob/main/TameList%20Vanilla.zip) curated list with increasing difficulty to tame.
* [TameList Simple](https://github.com/meldurson/AllTameable/blob/main/TameList%20Simple.zip) sticks to vanilla taming except for what you can feed.


## Configuration

A more detailed explanation and example of configuring the TameList can be found [here](https://github.com/meldurson/AllTameable/blob/main/Wiki_DetailedTameList.md)  

__Each line on the TameList that does not start with a '#' will be attempted to read as a tameable creature.__

Each line is separated by commas __,__ and will read from left to right until there are no more items.  

__The order is as follows:__  
`name, commandable, tamingTime, fedDuration, consumeRange, consumeSearchInterval, consumeHeal, consumeSearchRange, consumeItems, changeFaction, procretion, maxCreatures, pregnancyChance, pregnancyDuration, growTime`  

### The descriptions of the options in the config are as follows:
* __name:__ This is where you put the IDs of the creatures you are adding separated by a : (colon) (List of IDs [here](https://valheim-modding.github.io/Jotunn/data/prefabs/character-list.html))
* __commandable:__ This sets the ability to order them to follow you or not
* __tamingTime:__ This is the time it will take to tame the creature (in seconds)
* __fedDuration:__ This is how long a creature will be full for after it eats (in seconds)
* __consumeRange:__ This is the max range the creature can be at to eat food
* __consumeSearchInterval:__ This is how often the creature checks to see if food is in range to decides whether it needs it (in seconds)
* __consumeHeal:__ This is how much health each food provides
* __consumeSearchRange:__ This is the range the creature can detect food from
* __consumeItems:__ This is where you put the ID's of the items you want the creature to eat, put a : symbol in between each food (doesn't need to be a food item)
* __changeFaction:__ This is whether the creature will change faction when tamed (If set to true it will attack/get attacked by anything that attacks you)
* __procretion:__ This is whether the creature can breed to produce offspring (can set to _overwrite_ if there is already an offspring programmed in that you want to replace)
* __maxCreatures:__ This is the max number of creatures within range that can breed with or are offspring, if it exceeds this, they will stop breeding
* __pregnancyChance:__ This is the chance the creature has of becoming pregnant, Lower number = higher chance (scales from 0.00 to 1.00)
* __pregnancyDuration:__ This is how long the creature is pregnant for (In seconds)
* __growTime:__ This is how long it takes for offspring to grow into an adult (In seconds)

__Examples:__  
This is what the default Boar would look like if put into the TameList:

    Boar,false,1800,600,1,15,30,10,Raspberry:Blueberries:Carrot:Turnip:Mushroom:Onion,false,true,5,0.33,60,3000
If you want to add the ability to tame Deer and make it so it can eat any vegetarian food, you could add:

    Deer,true,1500,300,1.4,10,30,15,Raspberry:Blueberries:Carrot:Turnip:Mushroom:Cloudberry:OnionSoup:Onion,false,true,7,0.66,90,2000

To make two different prefabs able to breed with each other separate their ID with a colon such as:  

    RRRN_HumanMale:RRRN_HumanFemale,true,900,150,2,10,30,20,CookedMeat,true,true,10,0.66,150,500

* This will allow for both humans to breed with each other and have an equal chance of the offspring being one or the other.

To make a creature tameable by trading set commandable to "trade" and then format trades as Tradeitem=TradeAmount:  

    Dverger,trade,BlackCore=5:Coins=999

* This will allow to tame a Dverger with either 5 Black Cores or 999 Coins (Note: if wanting to tame by feeding and trade then place trade line after feed line)


To make a creature not tameable you set the line to the creature's name plus a -1 such as:  

    Wolf,-1

* This will not allow for wolves to be tamed.

__Note:__ This should be used on servers to set creatures you don't want tamed.


Any line starting with a # in AllTameable_Tamelist will be skipped from calculating into the TameList.  
You can multiple AllTameable_Tamelist\*.cfg files where \* can be anything such as AllTameable_Tamelist_RRR.cfg  

### Setting the Default
Starting a line with a '\*' will then set all attributes in that as the default going forward allowing to only specify attributes you change,  
You can specify a new default at any time by starting a new line with '\*' as shown below the Boar will have the same attributes as Default and Deer with have the same attributes as Tier_1 the Neck will have the same attributes as Tier_1 with different consumeItems.  

    *Default,true,1500,300,1.4,10,30,15,Raspberry:Blueberries:Carrot:Turnip:Mushroom:Cloudberry:OnionSoup:Onion,false,true,7,0.66,90,2000
    Boar
    *Tier_1,true,1500,300,1.4,10,30,15,Raspberry:Blueberries:Carrot:Turnip:Mushroom:Cloudberry:OnionSoup:Onion,false,true,7,0.66,90,2000
    Deer
    Neck,consumeItems=SerpentMeat:FishRaw:Bread:Raspberry:Blueberries:Cloudberry:Carrot:Mushroom:MushroomYellow:MushroomBlue:Turnip


### Specifying Attributes
You can specify any attribute by "name=value"  
__example:__ 

    *Default,true,1500,300,1.4,10,30,15,Raspberry:Blueberries:Carrot:Turnip:Mushroom:Cloudberry:OnionSoup:Onion,false,true,7,0.66,90,2000
    Surtling,consumeItems=Coal:ElderBark  
This will use all the default values except for consumeItems.  
__This can make your TameLists more readable and if you want to change something it will be faster to change as you may only need to change the default values.__

## Custom Options:

### **Custom options have to be referenced by name in your TameList files.\**

__canMateWithSelf:__ default=true, options:true,false  
Makes it so can only mate with other creatures that have been specified and not creatures with the same prefab *(Useful for male/female of same creature)*  

__specificOffspring:__ default=none, specify in the form __Mate(offspring1:chance1/offspring2:chance2/...)__  
The following will make it so can only breed Goblins when breeding GoblinShaman and GoblinBrute with an 80% chance and when breeding two GoblinShaman there is a 70% chance to get a GoblinBrute and 30% to get a GoblinShaman.

    Goblin,-1  
    *GoblinElites,true,2300,500,2,10,90,15,SerpentMeatCooked:CookedLoxMeat:BloodPudding:FishWraps:LoxPie:TurnipStew:SerpentStew:BlackSoup:WolfMeatSkewer:WolfJerky:CookedWolfMeat:CookedHareMeat,false,true,5,0.66,200,3200  
    GoblinShaman,specificOffspring=GoblinBrute(Goblin:80/GoblinBrute:10),specificOffspring=GoblinShaman(GoblinBrute:70)  
    GoblinBrute  

__size:__ default=1, options: 0.5-4  
multiplier to determine how far away it checks for other creatures, most creatures you will not have to change.
Lox should be at least 2, Vanilla Bosses should be 3, 4 is only if it is massive!
You can use decimals and specify a smaller range if you choose such as 0.5 for a small creature such as a hen.

    Lox,true,2000,150,3,10,30,20,Barley:Cloudberry:Flax:Onion,false,true,6,0.66,150,4500,size=2

__group:__ default=none  
Groups are used to determine if mobs will be hostile towards each other, if two mobs have the same group then if one is tamed and the other wild they will still not attack each other.  
group can equal whatever name you want for example, if you add group=AllGoblin to all of the goblins they will not attack each other if one is tamed and the other is wild.

__egg:__ drake/chicken(hatchtime:color:size),  default(1800:default:1)  
Have the creature lay an egg that will hatch into a mini version.  
Choose which egg to copy, how long it will take to hatch when near a fire, if you want to change the color, if you want to change the size.  
by default you do not need to specify anything other than the egg type such as egg=drake or egg=chicken   
the color is specified as a hex code such as #FFFFFF for white or #FF0000 for red.  
an example would be the following which would have necks lay a smaller version of the dragon egg with a color of green and a hatch time of 20 minutes.  

    Neck,egg=drake(1200:#00FF00:0.3)

__offspringName:__ default=Mini *Name of Adult*  
Do you want to overwrite the Mini name with a custom name. An example below is for deer wanting the children to be named Fawn.  
_Be careful about putting this in a default line_ as all subsequent creatures will have identical names until you specify another default with offspringName or an offspringName is set on that creature.  

    Deer,offspringName=Fawn



__requiredWorldKeys:__ default=None  
Do you want to require a boss or creature to be killed before you are able to tame this creature? Any world key can be specified (be careful though, if you misspell it, you will not be able to tame this creature).  
Below is an example that requires you to defeat both Eikthyr and Modor to be able to tame wolves.   

    Wolf,requiredWorldKeys=defeated_dragon:defeated_eikthyr



