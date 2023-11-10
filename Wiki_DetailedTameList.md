# In Depth Explanations of Tamelist

An overview of configuring the Tamelist can be found [here](https://github.com/meldurson/AllTameable/blob/main/Wiki_Tamelist.md)  
Every line, if no attributes named will be formated like so:

`name, commandable, tamingTime, fedDuration, consumeRange, consumeSearchInterval, consumeHeal, consumeSearchRange, consumeItems, changeFaction, procretion, maxCreatures, pregnancyChance, pregnancyDuration, growTime`

Any line starting with a # will be skipped from calculating into the tamelist

__Here is a block of some creatures:__

    *Default,false,1300,300,1,10,30,15,Raspberry:Blueberries:Carrot:Turnip:Mushroom:Cloudberry:OnionSoup:Onion,false,true,7,0.66,90,2000
    Boar
    *Tier_1,true,1500,300,1.4
    Deer
    Neck,consumeItems=SerpentMeat:FishRaw:Bread:Raspberry:Blueberries:Cloudberry:Carrot:Mushroom:MushroomYellow:MushroomBlue:Turnip,egg=drake(1200:#00FF00:0.3)
    StoneGolem,true,2300,300,2,10,30,20,CopperOre:IronOre:SilverOre:TinOre:Ruby,true,false
    
    ###Goblins###
    *Goblins,true,2300,500,2,10,90,15,SerpentMeatCooked:CookedLoxMeat:BloodPudding:FishWraps:LoxPie:TurnipStew:SerpentStew:BlackSoup:WolfMeatSkewer:WolfJerky:CookedWolfMeat:CookedHareMeat,false,true,5,0.66,200,3200
    Goblin,-1,group=AllGoblin
    GoblinBrute,group=AllGoblin,size=1.7,canMateWithSelf=false
    GoblinShaman,group=AllGoblin,specificOffspring=GoblinBrute(Goblin:80/GoblinBrute:10),specificOffspring=GoblinShaman(GoblinBrute:70) 


__Line:__ 
`*Default,false,1300,300,1,10,30,15,Raspberry:Blueberries:Carrot:Turnip:Mushroom:Cloudberry:OnionSoup:Onion, false,true,7,0.66,90,2000`  
\- Will set the default for all creatures going forward until the next default is set. This is due to the `*Default` at the beginning of the line:  
\- It is set to not be commandable with the `false` and have a taming time of `1300` seconds.  
\- Once it consumes an item it will be fed for `300` seconds.  
\- It can consume items up to `1`m away (The default for Boars).  
\- Will look for food every `10` seconds.  
\- Will heal `30` health when eating*(if set in config to heal). Will look for food in a radius of `15`m.  
\- Will be able to eat `Raspberry:Blueberries:Carrot:Turnip:Mushroom:Cloudberry:OnionSoup:Onion`.  
\- When tamed it will not change factions due to being set to `false` so it will not attack untamed of the same creature.  
\- It will also be able to procreate as procreation is set to `true`.  
\- When attempting to procreate, the max amount of creatures in the area that it can breed with is `7`, if there are more than that it will not procreate.  
\- There is a 34% chance to procreate every time it attempts to procreate (every 10 seconds) this is due to being set to `0.66`. The lower the number the more likely it is: `0.2` will make it 80% chance, `0.99` will give it a 1% chance.  
\- The creature will be pregnant for `90`s.  
\- The offspring will take `2000`s to grow up.

__Line:__
`Boar`  
\- Since the previous line was set with a `*Default` line and all it has of the aspects we want, this will be equivalent to a line such as:  
`Boar,true,1300,300,1,10,30,15,Raspberry:Blueberries:Carrot:Turnip:Mushroom:Cloudberry:OnionSoup:Onion,false,true,7,0.66,90,2000`  

__Line:__
`*Tier_1,true,1500,300,1.4`  
\- As this line starts with a '*' with `*Tier_1` then it will overwrite and set the default.  
\- This will set it to commandable with the `true`.  
\- Have a taming time of `1500` seconds.  
\- Will not change the current default, having a fed time of `300` seconds.  
\- Changes the consume range to `1.4`m.  
\- The rest will be kept from the first line `*Default`  

__Line:__
`Deer`  
\- Since the previous line modified part of the default with `*Tier_1` line, this will be equivalent to a line such as:  
`Deer,true,1500,300,1.4,10,30,15,Raspberry:Blueberries:Carrot:Turnip:Mushroom:Cloudberry:OnionSoup:Onion,false,true,7,0.66,90,2000`  

__Line:__
`Neck,consumeItems=SerpentMeat:FishRaw:Bread:Raspberry:Blueberries:Cloudberry:Carrot:Mushroom:MushroomYellow:MushroomBlue:Turnip, egg=drake(1200:#00FF00:0.3)`  
\- This will start with the default as a base and since we specified the `consumeItems=...` it will change the consumeItems from `Raspberry:Blueberries:Carrot:Turnip:Mushroom:Cloudberry:OnionSoup:Onion` to `SerpentMeat:FishRaw:Bread:Raspberry:Blueberries:Cloudberry:Carrot:Mushroom:MushroomYellow:MushroomBlue:Turnip`  
\- The special aspect `egg` is also specified with the part `egg=drake(1200:#00FF00:0.3)` which sets the offspring to be an egg that hatches when close to a fire.  
\-The format of the egg is `eggtype(hatchtime:HexColor:size)` with the options for eggtype being either `chicken` or `drake`, in this case drake is used.  
\- This specific line sets the offspring to be a drake egg that is 30% (`0.3`) the size of the original drake egg and is green (`#00FF00`).  
\- The egg will hatch after `1200` seconds into a *Mini Neck* which will grow into a Neck after an aditional `2000` seconds (From the Default).  
 
__Line:__
`StoneGolem,true,2300,300,2,10,30,20,CopperOre:IronOre:SilverOre:TinOre:Ruby, true,false`  
\- As you can see, you do not need to specify "food" as the consumable items, they can be any item that can be dropped on the ground.  
\- After the consumeItems atribute is set you can see that the `changeFaction` is set to `true`. This will make it so after taming it will also be hostile towards other StoneGolem where normally when a creature is tamed it will not be hostile towards the same creature.    
\- The next part is the setting for `procreation` which is set to `false` so it will not be able to procreate. Each Stone Golem that you want to be tamed will have to be tamed from the wild.  
\- Since `procreation` is set to `false` then it does not matter what the values for `maxCreatures, pregnancyChance, pregnancyDuration, growTime` so we can just leave them as default.  

__Line:__
`###Goblins###`  
\- Since this line starts with a '#' then it is not attempted to be loaded in as a configuration.  
\- The extra # are just to make it look like a heading and are not necessary.  

__Line:__`*Goblins,true,2300,500,2,10,90,15,SerpentMeatCooked:CookedLoxMeat:BloodPudding:FishWraps:LoxPie:TurnipStew:SerpentStew:BlackSoup:WolfMeatSkewer:WolfJerky:CookedWolfMeat:CookedHareMeat, false,true,5,0.66,200,3200`  
\- As this line starts with a '*' with `*Goblins` then it will overwrite and set the default.  

__Line:__
`Goblin,-1,group=AllGoblin`  
\- As you can see, in the `commandable` section it is set to `-1`. This makes it so the creature is not tameable.  
\- The second part with `group=AllGoblin` will set the group it is a part of to `AllGoblin` meaning if there are tamed creatures that are also in the `AllGoblin` group that it will not be hostile towards them.  

__Line:__
`GoblinBrute,group=AllGoblin,size=1.7,canMateWithSelf=false`  
\- This will take the default set from the `*Goblins` line, and change the group to also be `AllGoblin`.   
\- Now if there are tamed Goblin Brutes they will not be hostile to wild Goblins.  
\- Since Brutes are quite large, when trying to mate, the default range that is used may not be ideal. Therefore we change the size with `size=1.7` which is 1.7 times the size of default. (for example, Lox should have a size of 2 to be vanilla size)  
\- If we want the brutes to have to breed with other creatures and not themselves then we can set `canMateWithSelf=false`.  
\- This is very useful when specifying a male and female of the same creature (or humans), you can set the male to `canMateWithSelf=false` and the female to have `specificOffspring` when mating with the male.  

__Line:__`GoblinShaman,group=AllGoblin, specificOffspring=GoblinBrute(Goblin:80/GoblinBrute:10), specificOffspring=GoblinShaman(GoblinBrute:70)`  
\- This will also change the group to be `AllGoblin`. So now all of the types of goblins will not be hostile towards each other.     
\- The second part `specificOffspring=GoblinBrute(Goblin:80/GoblinBrute:10)` specifies that there should be specific offspring if the Goblin Shaman attempts to mate with a Goblin Brute.  
\- In this case, when the Goblin Shaman mates with a Goblin Brute there is an `80`% chance it will produce a `Goblin`, `10`% chance it will produce a `GoblinBrute`, and since that only adds up to 90% the remaining (10%) will be set to `GoblinShaman`.  
\- You can specify more than one `specificOffspring`. In this case we also specified specific offspring if mating with other `GoblinShaman` using the part `specificOffspring=GoblinShaman(GoblinBrute:70)` which would have a `70`% chance of the offspring being a `GoblinBrute` and 30% chance it would be a `GoblinShaman`.  
\- In general when you specify `specificOffspring` it is in the form `Mate(offspring1:chance1/offspring2:chance2/...)` where if the chances do not add up to 100 then the remaining will be the set the the original creature.


## References
This is what the default creatures would look like if put into the tamelist:

    Boar,false,1800,600,1,15,30,10,Raspberry:Blueberries:Carrot:Turnip:Mushroom:Onion,false,true,5,0.33,60,3000
    Wolf,true,1800,600,1.4,15,30,10,RawMeat:NeckTail:FishRaw:DeerMeat:Sausages:LoxMeat,false,true,4,0.33,60,3000
    Lox,false,1800,600,4,15,30,10,Barley:Cloudberry:Flax,false,true,5,0.33,120,6000,size=2
    Hen,false,1800,600,1,15,30,10,CarrotSeeds:OnionSeeds:TurnipSeeds:BeechSeeds:BirchSeeds:Barley:Dandelion,false,true,10,0.33,60,1800
    
## Premade Tamelists  

* [TameList Vanilla](https://github.com/meldurson/AllTameable/blob/main/TameList%20Vanilla.zip) currated list with increasing difficulty to tame
* [TameList Simple](https://github.com/meldurson/AllTameable/blob/main/TameList%20Simple.zip) sticks to vanilla taming except for what you can feed
    
    
    
    
    
    
    
    
    
