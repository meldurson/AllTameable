# In Depth Explanations of Tamelist

Every line, if no attributes named will be formated like so:

`name, commandable, tamingTime, fedDuration, consumeRange, consumeSearchInterval, consumeHeal, consumeSearchRange, consumeItems, changeFaction, procretion, maxCreatures, pregnancyChance, pregnancyDuration, growTime`

Any line starting with a # will be skipped from calculating into the tamelist

__Here is a block for the lowest Tier creatures:__

    *Default,false,1300,300,1,10,30,15,Raspberry:Blueberries:Carrot:Turnip:Mushroom:Cloudberry:OnionSoup:Onion,false,true,7,0.66,90,2000
    Boar
    *Tier_1,true,1500,300,1.4
    Deer
    Greyling,consumeItems=SerpentMeatCooked:NeckTailGrilled:CookedMeat:CookedLoxMeat:Bread:Raspberry:Blueberries:Carrot:Turnip:Mushroom:Cloudberry:Honey:Mushroom:MushroomYellow:MushroomBlue:MinceMeatSauce:DeerStew:CookedDeerMeat:BoarJerky:BlackSoup:WolfMeatSkewer:WolfJerky:CookedWolfMeat:OnionSoup:Onion:CookedHareMeat
    Neck,consumeItems=SerpentMeat:FishRaw:Bread:Raspberry:Blueberries:Cloudberry:Carrot:Mushroom:MushroomYellow:MushroomBlue:Turnip,egg=drake(1200:#00FF00:0.3)
__The First Line:__  
`*Default,false,1300,300,1,10,30,15,Raspberry:Blueberries:Carrot:Turnip:Mushroom:Cloudberry:OnionSoup:Onion,false,true,7,0.66,90,2000`  
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

__The Second Line:__  
`Boar`  
\- Since the previous line was set with a `*Default` line and all it has of the aspects we want, this will be equivalent to a line such as:  
`Boar,true,1300,300,1,10,30,15,Raspberry:Blueberries:Carrot:Turnip:Mushroom:Cloudberry:OnionSoup:Onion,false,true,7,0.66,90,2000`  

__The Third Line:__  
`*Tier_1,true,1500,300,1.4`  
\- As this line starts with a '*' with `*Tier_1` then it will overwrite and set the default.  
\- This will set it to commandable with the `true`.  
\- Have a taming time of `1500` seconds.  
\- Will not change the current default, having a fed time of `300` seconds.  
\- Changes the consume range to `1.4`m.  
\- The rest will be kept from the first line `*Default`  

__The Fourth Line:__  
`Deer`  
\- Since the previous line modified part of the default with `*Tier_1` line, this will be equivalent to a line such as:  
`Deer,true,1500,300,1.4,10,30,15,Raspberry:Blueberries:Carrot:Turnip:Mushroom:Cloudberry:OnionSoup:Onion,false,true,7,0.66,90,2000`  

__The Fifth Line:__  
`Greyling,consumeItems=SerpentMeatCooked:NeckTailGrilled:CookedMeat:CookedLoxMeat:Bread:Raspberry:Blueberries:Carrot:Turnip:Mushroom:Cloudberry:Honey:Mushroom:MushroomYellow:MushroomBlue:MinceMeatSauce:DeerStew:CookedDeerMeat:BoarJerky:BlackSoup:WolfMeatSkewer:WolfJerky:CookedWolfMeat:OnionSoup:Onion:CookedHareMeat`  
\- This will start with the default as a base and since we specified the `consumeItems=...` it will change the consumeItems from `Raspberry:Blueberries:Carrot:Turnip:Mushroom:Cloudberry:OnionSoup:Onion` to `SerpentMeatCooked:NeckTailGrilled:CookedMeat:CookedLoxMeat:Bread:Raspberry:Blueberries:Carrot:Turnip:Mushroom:Cloudberry:Honey:Mushroom:MushroomYellow:MushroomBlue:MinceMeatSauce:DeerStew:CookedDeerMeat:BoarJerky:BlackSoup:WolfMeatSkewer:WolfJerky:CookedWolfMeat:OnionSoup:Onion:CookedHareMeat`  
 
__The Sixth Line:__  
`Neck,consumeItems=SerpentMeat:FishRaw:Bread:Raspberry:Blueberries:Cloudberry:Carrot:Mushroom:MushroomYellow:MushroomBlue:Turnip,egg=drake(1200:#00FF00:0.3)`  
\- This will start with the default as a base and since we specified the `consumeItems=...` it will change the consumeItems  
\- The special aspect `egg` is also specified with the part `egg=drake(1200:#00FF00:0.3)` which sets the offspring to be an egg that hatches when close to a fire.  
\-The format of the egg is `eggtype(hatchtime:HexColor:size)` with the options for eggtype being either `chicken` or `drake`, in this case drake is used.  
\- This specific line sets the offspring to be a drake egg that is 30% (`0.3`) the size of the original drake egg and is green (`#00FF00`).  
\- The egg will hatch after `1200` seconds into a *Mini Neck* which will grow into a Neck after an aditional `2000` seconds (From the Default).  


## References
This is what the default creatures would look like if put into the tamelist:

    Boar,false,1800,600,1,15,30,10,Raspberry:Blueberries:Carrot:Turnip:Mushroom:Onion,false,true,5,0.33,60,3000
    Wolf,true,1800,600,1.4,15,30,10,RawMeat:NeckTail:FishRaw:DeerMeat:Sausages:LoxMeat,false,true,4,0.33,60,3000
    Lox,true,1800,600,4,15,30,10,Barley:Cloudberry:Flax,false,true,5,0.33,120,6000,size=2
    Hen,false,1800,600,1,15,30,10,CarrotSeeds:OnionSeeds:TurnipSeeds:BeechSeeds:BirchSeeds:Barley:Dandelion,false,true,5,0.33,60,3000,specificOffspring=Hen(Chicken:100)
    
    
    
    
    
    
    
    
    
    
    
    
