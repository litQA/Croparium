# Croparium 4.6.5-beta
## Dec 26, 2025

#### New Content

##### Configuration Files
Added 5 new configuration keys.

###### English Configuration File


```
{
  "This value determines whether the condition of surrounding farmland will affect the growth rate of crops (Default: true)": true,
  "This value determines whether farmland soaked by magma will turn water into cobblestone upon contact (Default: true)": true,
  "This value determines whether the reactor core consumes the module durability (Default: true)": true,
  "This value determines the horizontal range multiplier when the reactor core takes effect  (Default: 6.0)": 6.0,
  "This value determines the vertical range multiplier when the reactor core takes effect  (Default: 1.0)": 1.0
}
```


###### Chinese Configuration File


```
{
  "该数值决定周围耕地状态是否会影响作物的生长速率 (默认: true)": true,
  "该数值决定被岩浆浸润的农田接触到水是否将水转换为圆石 (默认: true)": true,
  "该数值决定反应核心是否消耗模块的耐久度 (默认: true)": true,
  "该数值决定反应核心生效时作用的水平方向范围乘数 (默认: 6.0)": 6.0,
  "该数值决定反应核心生效时作用的垂直方向范围乘数 (默认: 1.0)": 1.0
}

```

##### Commands

- Added command /cropariumReload, only available on the server side. After execution, it will immediately re-read the existing configuration file or automatically create one if the file is missing.

##### Achievement

- Added New Achievement: **No more hunger**.
- Obtain the Agricultural Reaction Module. Seedlings form shade, golden ears fill the granary—once a persistent pursuit for subsistence, it harbors the sincerity of a lifetime of tilling the land.

#### Changes

##### Reactor Core

- Removed the hard-coded restriction on the effective range; supports custom adjustment of the effective range after activation through the configuration file. Please fully understand its mechanism before making adjustments.


  - Length & Width = 2 × Horizontal Range Multiplier × Base Level + 1

  - Height = 2 × Vertical Range Multiplier × Base Level - 1

- Range calculation rules: Taking the reactor core coordinates as the center, a cubic effective area is formed. The specific formulas are:

- Default parameters: The default horizontal range multiplier is 6.0, and the default vertical range multiplier is 1.0.

- Important note: Excessively large multiplier settings may disrupt game balance and cause significant performance impacts on certain devices; it is recommended to adjust reasonably.

- Added a configuration item to control whether the reactor core consumes module durability during operation; the consumption function is enabled by default.

##### Farmland & Crop Mechanism Adjustments

- The impact of surrounding farmland conditions on crop growth rate can be enabled/disabled through the configuration file (enabled by default). When disabled, a preset fixed growth rate will be used.

- Whether water will be converted to cobblestone when farmland soaked by magma comes into contact with water can be controlled through the configuration file (enabled by default).

##### Configuration File Loading

- Game initialization phase: Only performs the configuration file creation operation, without reading the file content.

- World loading phase: Automatically reads the configuration file content and applies the configuration parameters.

#### Fixes

- Fixed the issue where the game failed to start when jauml was not installed. Now, not installing jauml will no longer cause a crash, but only missing configuration file-related functions.

- Fixed an issue causing unexpected drops of crop products.

- Fixed the crash issue caused by entering invalid numbers in the numeric items of the English configuration file.

- Fixed the issue where the server crashed when the client did not agree to the stance confirmation pop-up GUI.

#

# Croparium 4.5.2

## Dec 24, 2025

#### Backport

* Backported new features from 4.6.4 to Minecraft Forge 1.19.4, NeoForge 1.20.4, 1.20.6, 1.21.4
* Built on the existing stable branch for non-mainstream MC versions, ensuring save file compatibility
* This version does NOT include all new features from 4.6.4-stable

# 

# Croparium 3.4.0

## Dec 24, 2025

#### Backport

* Backported new features from 4.6.4 to Minecraft NeoForge 1.21.0-4
* Built on the existing stable branch for non-mainstream MC versions, ensuring save file compatibility
* This version does NOT include all new features from 4.6.4-stable

# 

# Croparium 4.6.4

## Dec 23, 2025

\[Stable Release]

# 

# Croparium 4.6.3-beta

## Dec 22, 2025

#### New Content

* New "Agriculturel Reactor Module" for Reactor Core: When equipped, it can automatically ripen crops such as wheat, carrots, and potatoes and harvest their products; supports synergy with other modules (e.g., when paired with the Automatic Smelting Reactor Module, the harvested products will be the results after smelting in a furnace directly).
* New dual Experience Module linkage effect: When both slots of the Reactor Core are equipped with Experience Reactor Modules, no items will be dropped, and the experience output will be increased to 3 times the original value.
* New Module Repair Mechanism: Damaged modules or blank modules can be used to craft corresponding modules with full durability.

#### Changes

* Optimized Reactor Core activation performance: When placed on a base and the base level is ≥ 1, it can be activated immediately.
* Feature Removal: Deleted the crop ripening function of the Reactor Core when the base level is 4 (this function has been upgraded and migrated to the Agriculture Reactor Module).
* Configuration Limit Optimization: When the configuration value of the Reactor Core update cycle is < 10, the minimum value of 10 will take effect forcibly to avoid experience issues caused by abnormal configuration.
* Experience Orb Performance Optimization: After equipping the Experience Reactor Module, the generated experience orbs will be merged into large experience orbs instead of the original large number of small experience orbs.
* Sound Effect Optimization: Optimized the sound feedback for cultivating hard farmland.
* Replaced the texture of the Fortune Reaction Module.
* Updated Japanese localization text.
* Updated the text content of the Japanese confirmation GUI.

# 

# Croparium 4.6.1-beta

## Dec 19, 2025

#### New Content

* Added Biomass Crops
* Added Leather Crop, Ink Sac Crop, Glow Ink Sac Crop. Among them, the Glow Ink Sac Crop emits light with a brightness level of 10.

##### General

* Added configuration files (Path: config/croparium).
* Two files, "English Config.json" and "中文配置.json", will be automatically generated when the mod is loaded for the first time.

###### For English Players

**Use `English Config.json` directly. The content of the file is as follows:**


```
{

"This value determines whether entuties will take damage when walking on farmland soaked with lava (Defaut: true)": true,

"This value determines whether the right-click to harvest crops function is enabled (Defaut: true)": true,

"This value determines whether smelted items will drop when harvesting crops with a tool enchanted with fire aspect using right-click (Defaut: true)": true,

"This value determines whether the reactor core is enabled (Defaut: true)": true,

"This value determines the base number of items dropped when right clicking to harvest (Default: 2.0)": 2.0,

"This value determines the extra number of items dropped when breaking mature crops (Default: 0.0)": 0.0,

"This value determines how fast the crop grows, bigger the value is, slower the crops grow  (Default: 3.0)": 3.0,

"This value determines how frequently the reactor core refreshes, and setting this value too low may cause lag (Default: 180.0)": 180.0,

"This value determines the success rate of obtaining embryo shards each time in the classic stonecutter  (Default: 0.3)": 0.3

}
```

###### 中文玩家

**使用`中文配置.json`，文件内容如下：**


```
{

"启用中文配置（英文配置文件将被忽略）": false,

"该数值决定实体在被岩浆浸润的农田上行走时是否会受到伤害 (默认: true)": true,

"该数值决定是否启用右键收获作物功能 (默认: true)": true,

"该数值决定使用火焰附加的工具右键收获作物时是否掉落熔炼后的物品 (默认: true)": true,

"该数值决定是否启用反应核心 (默认: true)": true,

"该数值决定是否可以用矿芯碎片催熟对应作物 (默认: true)": true,

"该数值决定右键收获时的基础掉落物数量 (默认: 2.0)": 2.0,

"该数值决定破坏成熟作物时的额外掉落物数量 (默认: 0.0)": 0.0,

"该数值决定作物成长快慢，数值越大，作物成长速度越慢 (默认: 3.0)": 3.0,

 "该数值决定反应核心刷新周期，过低的数值可能会导致卡顿 (默认: 180.0)": 180.0,

"该数值决定每次在经典切石机中提取矿芯碎片的成功率 (默认: 0.3)": 0.3

}
```

* 配置项与英文文件对应；中文玩家需将`启用中文配置（英文配置文件将被忽略）`设为true。

#### Change

* Reduced the activation delay of the Reactor Core after being placed on the base.

# 

# Croparium 4.5.0-beta

## Dec 13, 2025

#### New Content

##### Added 4 advancements

* **No Need to Dig Deep**: Unlocked upon first entering the game
* **Master of Disassembly**: Collect all types of embryo shards from vanilla Minecraft
* **Mineral Seed Collector**: Gather all mineral-type seeds from vanilla Minecraft
* **Control Core**: Obtain one Blank Reacor Module

#### Changes

* Added a 40% chance to drop an additional corresponding item when harvesting mature crops with right-click
* Optimized crop loot tables, increased the expected value of base drops and seed quantities when breaking crops
* Modified the trigger condition for the advancement Not Enough Minerals: Accumulatively extract any material 50 times in the Classic Stonecutter

#### Fixes

* Fixed an issue where lava-infused farmland would occasionally burn dropped items
* Fixed an issue where item stacks were still consumed when using Ore Core Shards to accelerate crop growth in Creative Mode
* Fixed an issue where tools still lost durability when tilling farmland with pickaxes or shovels in Creative Mode
* Fixed an occasional crash when tilling wasteland
* Fixed an issue where one ancient debris loot pool in the Netherite Crop loot table was not linked to Fortune Enchantment, resulting in lower-than-expected drop quantities of Netherite Crop products

# 

# Croparium 4.4.0

## Dec 13, 2025

#### New Content

* Added the Echo Shard Plant; it can be planted on Biomass Farmland, allowing players to cultivate it on this type of farmland.
* Configured unlock items for all craftable items in the mod. After players obtain the corresponding specific items, they can unlock and view the complete crafting recipes of the items in the Book of Knowledge, aimed at optimizing the onboarding experience for new players who have not installed mods like JEI or REI.

#### Changes

* Updated the textures of Overworld crops and Biomass crops, and replaced
* Replace the textures of Biomass crop seeds with brand-new ones.
* Replaced the original "grass model" of Biomass crops with a "crop model".
* **Content Removal**: Due to gameplay iteration needs, "Sculk Farmlands" and "Sculk Embryo Shard", have been removed, and the related gameplay will be replaced by biomass'.

##### Drop and Harvest Mechanics

* When mature Biomass plants are destroyed or harvested by right-clicking, a probability mechanism of "dropping 1 additional corresponding resource" is added to increase planting benefits.
* For all mature plants when destroyed, the probability of "drawing a loot pool with more than 1 seed" is increased from 50% to 67%.
* When mature Netherite plants are destroyed, the probability of "drawing a loot pool with more than 1 Ancient Debris" is increased from 50% to 80%.
* When right-clicking to harvest plants, if the base drop quantity of the plant is greater than 1, the minimum drop count is adjusted to have a floor of 1, slightly reducing the drop quantity.

#### Fixes

* Fixed the interaction bug where mature Turtle Scute Plants did not drop Turtle Scutes when harvested by right-clicking.
* Fixed the interaction bug where mature Slime Ball Plants did not drop Slime Balls when harvested by right-clicking.
* Fixed the functional abnormality where the Reactor Core could not properly harvest mature Slime Ball Plants.
* Fixed the functional abnormality where the Reactor Core could not properly harvest mature Turtle Scute Plants.
* Fixed the issue where Nautilus Shell Plants lacked a loot table; previously, no items were dropped when this plant was destroyed.

# 

# Croparium 4.3.2

## Dec 10, 2025

#### New Content

* Added identification symbols for activated base levels in the Reactor Core GUI Panel.

#### Change

* Optimized the operational stability of the pop-up GUI for Japanese clients.

# 

# Croparium 4.3.1-beta

## Dec 9, 2025

#### Fix

* Incorrect crafting recipe for the Autogathering Reactor Module.

# 

# Croparium 4.3.0-beta

## Dec 9, 2025

## Support

**(Version of Forge 1.20.1) Updated Forge build to 47.4.13.**

#### New Content

##### Reactor Core Module

Added multiple exclusive functional reactor modules for the reactor core, which can be installed into the reactor core (each reactor core can hold up to 2 modules simultaneously).

The specific effects of each module are as follows:

###### Auto-Smelting Reactor Module

* Automatically converts ores dropped within the range of the reactor core into smelted products.
* Installing this module repeatedly will not stack its effects.

###### Auto-Collection Reactor Module

* Automatically gathers ores dropped within the range of the reactor core to the coordinates of the reactor core.
* Installing this module repeatedly will not stack its effects.

###### Experience Reactor Module

* Each successful collection of mature crops will automatically generate 3 experience orbs at the location of the reactor core.
* Installing this module repeatedly can stack the experience output effect.

###### Fortune Reactor Module

* When harvesting crops, there is a 1/3 chance to trigger an additional drop of 1 product.
* Installing this module repeatedly can stack the additional drop.

#### Changes

##### Crop Yield Balance Optimization

**In response to the game balance imbalance caused by excessively high crop yields in previous versions, this update adjusts the crop yield mechanism to slow down the overall development rhythm and optimize the long-term gaming experience. The specific adjustment contents are as follows:**

###### Crop Loot Table Adjustments

* For most mature crops, the maximum drop quantity of corresponding products after destruction is reduced by 2;
* For Slime and Ender Pearl crops, the maximum drop quantity of corresponding products after destruction is reduced by 1;
* For Copper, Lapis Lazuli, and Redstone crops, the maximum drop quantity of corresponding products after destruction is reduced by 3;
* Seed Drop Mechanic Optimization: When the main-hand tool has no Fortune enchantment, the probability of dropping 1 seed after destroying mature crops is 50%. The Fortune enchantment can still increase the maximum drop quantity, but the bonus magnitude is reduced.
* The specific probability distribution is shown in the following table:

| Drop Quantity | No Fortune | Fortune I | Fortune II | Fortune III | Fortune n (n>1) |
|---------------|------------|-----------|------------|-------------|--------------------|
| 1             | 50%        | 50%       | 50%        | 50%         | 50%                |
| 2             | 50%        | 25%       | 16.7%      | 12.5%       | 1/[2(n-1)]         |
| 3             | 0%         | 25%       | 16.7%      | 12.5%       | 1/[2(n-1)]         |
| 4             | 0%         | 0%        | 16.7%      | 12.5%       | 1/[2(n-1)]         |
| 5             | 0%         | 0%        | 0%         | 12.5%       | 1/[2(n-1)]         |
| Average | 1.5 | 1.75 | 2.0 | 2.25 | (n+6)/4 |



* Special Crop Adaptation: Crops with an original maximum drop quantity of 2 (such as Netherite crops) are uniformly adapted to the above seed drop mechanism after this update;

###### Right-Click Harvest Mechanic Adjustments

* The base right-click harvest quantity is reduced by 1;
* Enchantment Effect Adaptation: When the main-hand tool has Looting or Fortune enchantment, the drop mechanism of right-click harvest is consistent with that of destroying crops — the probability of dropping 1 product is 50%, the probability of dropping n products is 1/\[2(n-1)], and the average drop quantity is (n+6)/4.



#### Fix

* Fixed the issue where destroying some crops with a main-hand tool enchanted with both Silk Touch and Fortune would abnormally drop more crops.

# 

# Croparium 4.2.0-beta

## Dec 2, 2025

#### New Content

* Added Japanese localization support, and a "Position Compliance Confirmation" GUI for Japanese players.

#### Changes

##### Adjusted the effective range of the Reactor Core

* Length and width: 12 × Level + 1
* (e.g., at Level 4, length and width are 49 blocks, equivalent to extending 24 blocks outward in all directions from the Reaction Core
* Height: 2 × Level - 1

##### Farmlands

* For all farmland except Ocean Resource Farmland, adjusted the model height from 15 to 15.75.
* Optimized the texture of Prismarine Farmland to match the consistent gradient dynamic texture of Prismarine.

#### Fix

* Fixed the issue where the center of the Reactor Core's effective range was misaligned.

# 

# Croparium 4.1.1-beta

## Dec 1, 2025

#### Fix

* Debug messages would occasionally appear in the world chat channel.

# 

# Croparium 4.1.0-beta

## Dec 1, 2025

#### Changes

* Nether Embryo Shards can now be used as fuel in Furnaces and Blast Furnaces, smelting 16 items each.
* Sweet Embryo Shards and Biomass Embryo Shards can be placed in Composters as fertilizer, with a 100% compost success rate.
* When Embryo Shards are shooted from a Dispenser, they will ripen all corresponding crops within 16 blocks in front.

#### Fixes

* Resolved the abnormal issue where holding items without the #embryo\_materials tag could still extract Overworld Core Shards (Affected versions: NeoForge 1.20.4, 1.20.6)

# 

# Croparium 4.0.1-beta

## Nov 30, 2025

#### Support

**Forge 1.19.4, 1.20.1**

* Fixed: The issue where holding any item not in the #cp\_lib:embryo\_materials tag allows extracting overworld\_embryo\_shard.

# 

# Croparium 4.0.1-beta

## Nov 25, 2025

#### Support

**Forge 1.19.4, 1.20.1, NeoForge 1.20.4, 1.20.6, 1.21.1, 1.21.4, 1.21.8**

#### New Content

##### Added the Embryo Shard Block series

* Introduced 9 exclusive embryo blocks corresponding to each type of embryo shard. The crafting recipe is "9 embryo shards of the corresponding type".
* Including: Overworld Embryo Block, Nether Embryo Block, End Embryo Block, Ocean Embryo Block, Sweet Embryo Block, Deep Dark Embryo Block, Hard Embryo Block, Biomass Embryo Block, and Aether Embryo Block.

##### Achievements

###### Insufficient Mineral Reserves

* Unlocked by extracting Stones in the Classic Stonecutter and getting 7 Overworld Embryo Shards.

###### Early Alpha

* Unlocked by obtaining the Classic Stonecutter and Reactor Core.

###### Reaction Core Engineer

* Unlocked by upgrading the Reactor Core's activation base to level 4.

#### Changes

##### Adjusted Reactor Core's effect range

###### Before adjustment

* A cube range centered on the Reactor Core with side length "2 × Base Level + 5"

###### After adjustment

* A cuboid range centered on the Reactor Core with height "2 × Base Level - 1" and length/width "6 × Pedestal Level + 1"
* Corresponding maximum effect range change: From 13×13×13 cube to 27×27×7 cuboid



##### Damage mechanism for magma-moistened farmland

* No longer take damage when walking on this farmland while sneaking or wearing boots enchanted with Frost Walker.
* Entities will be set on fire for 2 seconds when walking on this farmland without sneaking or wearing Frost Walker boots.
* Meanwhile, the fire damage from the farmland is increased from 1 point per tick to 2 points.

#### Fixes

* Fixed the issue where item stacks would abnormally decrease when planting the mod's crop seeds in Creative Mode.
* Fixed the issue where the block placement animation was missing for the player's main and off hands when planting the mod's crop seeds.

# 

# Croparium 3.3.1

## Nov 19, 2025

* Fix missing crafting recipe for Reactor Core.
* Crafting recipe adjustment for Rotten Flesh Block \& Fermented Biomass Block: 3×3 → 2×2.

# 

# Croparium 3.3.0

## Nov 10, 2025

* Added the new item "Fermented Biomass Block", which can be crafted shapelessly with 1 Fermented Spider Eye and 8 any raw animal meat (or other specific animal resources), and can be used to extract Biomass Embryo Shards.

# 

# Croparium 3.2.1

## Nov 2, 2025

#### \[Forge 1.20.1]·CRITICAL FIX

* Resolved a crash issue that occurred when launching the game.

#### Fix

* Resolved the issue where honeycomb farms moistened with royal jelly could not plant crops.

# 

# Croparium 3.2.0

## Nov 1, 2025

#### New Content

* Added 2 new ore plants: Flint Plant and Dripstone Plant. Both must be planted on Overworld Farmland.
* Added 12 new biomass plants: Blaze Rod, Whirlwind Rod (available in 1.21+), Shulker Shell, Gunpowder, Ender Pearl, Slime Ball, Magma Cream, Phantom Membrane, Ghast Tear, Dragon's Breath, Turtle Scute, Armadillo Scute (available in 1.20.6+). All must be planted on Biomass Farmland.
* Tuff and Dripstone Block can now be tilled into corresponding Overworld Ore Farmland.

#### Changes

* Farmland moistened by Lava will no longer burn items on top of it.
* Honey Fluid from "The Bumblezone" mod can now moisten Sweet Farmland by default.
* Royal Jelly Fluid from "The Bumblezone" mod can moisten Sweet Farmland, with a higher priority than other fluids/blocks marked "required\_by\_sweetfarmland". Sweet Farmland moistened by Royal Jelly has a different appearance from regular moist Sweet Farmland, and plants on it grow faster.

#### Fixes

* Fixed the issue where Andesite could not be tilled into farmland.
* Fixed the issue where the moist state of Prismarine Farmland and Dark Prismarine Farmland did not affect the growth rate of surrounding crops.

# 

# Croparium 3.1.1

## Oct 21, 2025

#### Hot Fix

* Resolved the bug where breaking mature Clay Crops failed to drop any items.

# 

# Croparium 3.1.0

## Oct 21, 2025

* Added Prismarine Shard Plant and Prismarine Gravel Plant, requiring Marine Farmland.​
* Added Nautilus Shell Plant, requiring Biomass Farmland.​
* Added Clay Plant, requiring Overworld Ore Farmland.​
* Added Rotten Flesh Block. It is crafted from 9 Rotten Flesh and can be used to extract biomass embryo shard.

# 

# Croparium 3.0.6

## Oct 20, 2025

Stable Release

# 

# Croparium 3.0.6-rc

## Oct 19, 2025

* Adds Farmland for Marine Resourse.

# 

# Croparium 3.0.6-alpha

## Oct 19, 2025

* Minor optimizations.
* Fixed: "Sweet Embryo Shard" not maturing its corresponding crop types.
* Ported v3.0 features to Forge1.20.1.

#### ⚠️ Important Compatibility Note

***For players with existing worlds on Forge 1.20.1***

* This update is not compatible with v2.x of the mod.
* Recommend creating a new world to avoid issues.
* Using old worlds results in item loss.

# 

# Croparium 3.0.5

## Oct 16, 2025

**NeoForge 1.21.1 Only**

* Fixed the Issue: Missing some specific support for Aether Dimension Mod content.

# 

# Croparium 3.0.3

## Oct 9, 2025

#### Fixes

* When right-clicking on modded farmland, players were unable to perform any actions other than sowing seeds, including the inability to place blocks.​
* Mature plants obtained via Silk Touch could not be placed back onto farmland, even if the dimension matched.

# 

# Croparium 3.0.2

## Oct 7, 2025

* Resolved: Unintended Debug Messages in Chat During Crop Ripening

# 

# Croparium 3.0.1

## Oct 7, 2025

#### Minor Fixes and Adjustments

* Renamed the block "tile stonecutter" to "classic stonecutter"
* Plants at growth stage 1 can no longer be obtained via Silk Touch, and their corresponding item form has been removed
* Fixed the issue where right-clicking to extract "Embryo Shards" from the "classic stonecutter" would place a block simultaneously
* Adjusted the content related to "Crawling Farmland" in line with the changes in the new version of the "arphex" mod

# 

# Croparium 3.0.0 Dev

## Oct 7, 2025

#### Important Notes​

* **This version features extensive refactoring of the underlying code. Version 3.0 and all subsequent versions are incompatible with v2.2.1 and earlier.​**
* **Do NOT load existing world saves to upgrade to this version or later! Upgrading from v2.2.1 or earlier will result in complete loss of previous mod-related data.​**

#### New Content

###### New Farmland Blocks

* Cobblestone Farmland, Granite Farmland, Andesite Farmland, Diorite Farmland, Blackstone Farmland, Depthrock Farmland, Shiverstone Farmland, Dradstone Farmland, Obsidian Farmland, Crying Obsidian Farmland, Soul Sand Farmland, Soul Soil Farmland, Crawling Slate Farmland​

###### New Vanilla Crops

* Honey Crop, Honeycomb Crop​

###### Tweaks of Coal Crop

* Added fuel properties to Coal Ore Seeds and the item forms of Coal Ore Crops​

###### Removed Ore Crops from Cross-Mod Integrations

* Content from different cross-mod integrations will now be standalone mods, with this mod serving as their dependency​##Adjusted Reactor Core Usage Logic Must be placed on a structure similar to a beacon base to function​Effective range is tied to the base level, maxing out at Level 5​Reactor Core will not work without a base​

###### Removed Crop Decomposition Function

* With the new right-click harvest feature, obtaining crops via Silk Touch and then decomposing them is no longer necessary; the Silk Touch crop acquisition feature is retained​

###### Removed Game Rule "Crop Lazy Mode"

* When accelerating crop growth, 1-3 growth points will be randomly added​

The probability of extracting Embryo Shards in the Tile Stonecutter is fixed at 32%​

###### Optimized Crop Growth Mechanism

* Crop growth process is smoother, but total growth time is extended​Correspondingly optimized the acquisition difficulty of Embryo Shards to make it more accessible​

#### Technical Updates​

##### Added Farmland Classification Tags 

**For distinguishing plantable crop types**

* **#farmland\_dimension\_overworld**: For Overworld Ore Crops, including Cobblestone Farmland, Cobbled Deepslate Farmland, Granite Farmland, Andesite Farmland, Diorite Farmland​
* **#farmland\_dimension\_nether**: For Nether Ore Crops, including Basalt Farmland, Blackstone Farmland​
* **#farmland\_dimension\_end**: For End Ore Crops, including End Stone Farmland​
* **#farmland\_dimension\_sweet**: For Honey Crops, including Honeycomb Farmland​
* **#farmland\_dimension\_deep**: For Deep Dark Dimension Ore Crops, including Sculk Stone Farmland, Depthrock Farmland, Shiverstone Farmland, Dradstone Farmland​
* **#farmland\_dimension\_tough**: For Tough Ore Crops, including Obsidian Farmland, Crying Obsidian Farmland, Deadrock Farmland​
* **#farmland\_dimension\_biomass**: For Biomass Crops, including Soul Sand Farmland, Soul Soil Farmland, Crawling Slate Farmland​
* **#farmland\_dimension\_aether**: For Aether Dimension Crops, including Holystone Farmland​
* **#farmlands**: Marks all farmland types (Note: Do not add custom farmland blocks directly to this tag; ore crops only recognize dimension-specific tags prefixed with "#farmland\_dimension\_". Custom farmland blocks should be added to the corresponding dimension tag, which will automatically inherit to this tag)​

##### Adjusted Fluid Tags for Farmland Blocks

* \#required\_by\_waterfarmlands (Fluids for water-based farmlands)​
* \#required\_by\_lavafarmlands (Fluids for lava-based farmlands)​
* \#required\_by\_sweetfarmlands (Fluids for sweet-type farmlands)​

##### Adjusted Tags for Ore Embryo Shard Extraction Items

* \#embryo\_material\_overworld: For extracting Overworld Ore Embryo Shards​
* \#embryo\_material\_nether: For extracting Nether Ore Embryo Shards​
* \#embryo\_material\_end: For extracting End Ore Embryo Shards​
* \#embryo\_material\_sweet: For extracting Sweet Embryo Shards​
* \#embryo\_material\_deep: For extracting Deep Dark Embryo Shards​
* \#embryo\_material\_tough: For extracting Tough Ore Embryo Shards​
* \#embryo\_material\_biomass: For extracting Biomass Embryo Shards​
* \#embryo\_material\_aether: For extracting Aether Embryo Shards​

##### Added Ore Seed Classification Tags

* \#crop\_seeds\_overworld
* \#crop\_seeds\_nether
* \#crop\_seeds\_end
* \#crop\_seeds\_sweet
* \#crop\_seeds\_deep
* \#crop\_seeds\_tough
* \#crop\_seeds\_biomass
* \#crop\_seeds\_aether​
* Universal tag: #crop\_seeds (includes all ore seeds)​

##### Adjusted Crop Growth State Tags:​

###### Renamed

* \#crop\_stage0→#crop\_state0
* \#crop\_stage1→#crop\_state1
* \#crop\_stage2→#crop\_state2​
* \#unmaturecrop→#crop\_unmature (automatically inherits elements from #crop\_state0 and #crop\_state1)​

###### Removed tag

* \#crop\_stage\_a​

###### Note

* Do not add elements directly to #crop\_unmature; add corresponding crop state blocks to #crop\_state0, #crop\_state1, or #crop\_state2​



##### Added NBT Tags for Ore Crops in Growth State 2

* Drop Items: Describes items dropped when harvesting via right-click​
* Smelt Drop Items: Describes items dropped when harvesting via right-click (if the main-hand item has the "Fire Aspect" enchantment)​
* Extra Drop Num: Describes the extra drop quantity when harvesting via right-click

# 

# Croparium 2.2.1

## Oct 1, 2025

#### Fix

* Fixed the bug where mod-specific mineral seeds could not be crafted in 1.21+ versions of the mod.

# 

# Croparium 2.2.0

## Oct 1, 2025

#### Summary

**Added a new right-click-to-harvest interaction for mature mineral plants and a new "Reactor Core" block that accelerates mineral plant growth and enables automatic harvesting.**

#### New Interaction

* This feature only takes effect when the "Crop Lazy Mode" game rule is enabled.
* Right-click on a mature mineral plant to harvest it directly. The plant will drop 2 corresponding ores and revert to its initial growth state.
* If your main hand tool has the Fortune or Looting enchantment, there is a probability of dropping additional ores based on the enchantment level.
* (Pro tip: Try harvesting with a sword enchanted with Fire Aspect—you might get a nice surprise!)

#### Reactor Core

* Only works when the "Crop Lazy Mode" game rule is enabled.
* Added a new functional block: the Reactor Core. It accelerates the growth speed of mineral plants at the same height within an 11×11 area centered on itself.
* When a mineral plant matures, the Reactor Core will automatically harvest it—dropping 2 ores and reverting the plant to its initial growth state. Harvested ores will converge around the block.
* Acceleration effects from multiple Reactor Cores with different phases can stack.
* When activated by a Redstone signal, this block will pause its operation.
* Note: Excessive use of this feature may cause significant performance impacts on older devices.

#### Fix (1.21+ Versions Only)​

* Fixed the bug where no items would drop when mod-specific mineral plants are broken in 1.21+ versions of the mod.​



# 

# Croparium 2.1.2

## Sep 29, 2025

#### Critical Bug Fixes​

**For Version 1.21 and Above**

* Resolved the issue where right-clicking the Tile Stonecutter had no effect when attempting to extract Embryo Shard from most stones that should support this extraction function.

# 

# Croparium 2.1.1

## Sep 29, 2025

#### Fix

* Debug information is unexpectedly appeared in the chat bar

# 

# Croparium 2.1.0

## Sep 29, 2025

#### New Content

###### Added mineral planting support for the Twilight Forest mod

* Twilight Forest ore crops must be planted on Deadrock Farmland (reclaimed from Deadrock and its variants) and require lava as the "water source";
* Deadrock is extremely hard, so reclaiming Deadrock Farmland consumes 20 tool durability (Unbreaking enchantment is ineffective);
* Deadrock Farmland shares the same high hardness and explosion resistance as Deadrock, and can only be mined with a diamond-tier or higher pickaxe;
* Deadrock Farmland "moistened" by lava emits light (brightness level 10), and entities walking on it take continuous damage similar to magma blocks;
* If Crop Lazy Mode is false, Twilight Forest ore crops require: brightness ≤ 10, no exposure to open sky to survive;
* The corresponding ore embryo shard is the tough embryo shard.

###### Added mineral planting support for \[ArPhEx] Arthropod Phobia Expansions + Horror Bosses (Spider Moth) mod

* Ore crops of this mod must be planted on Basalt Farmland and ripened with Nether Embryo Shards.

###### Added Honeycomb Farmland and a new fluid: Excessively Sweet Water

* Honeycomb Farmland needs Excessively Sweet Water to be moistened;
* The corresponding ore embryo shard is the honey embryo shard.
* Added planting support for some items from The Bumblezone
* These crops must be planted on Honeycomb Farmland and ripened with honey embryo shards.

#### Changes

* Optimized the growth mechanism of ore crops to make their growth smoother; all ore crops in this mod now use a unified growth mechanism:
* Ore crops have 4 growth stages. When the game tick updates, the plant calculates the growth probability based on the environment within the surrounding 3×3×3 cube; the moisture state of the farmland and the number of surrounding farmlands both affect the growth probability.
* Removed the mod's original three game rules (cropGrowRestrict, cropCutEnable, cropRipeningEnable) and merged them into a new rule: Crop Lazy Mode. Its specific effects are as follows:
* Controls whether there are environmental restrictions on crop survival;
* Controls whether ore plants can be decomposed in the tile stonecutter;
* Ore embryo shard ripening: If Crop Lazy Mode is true, the crop enters the next stage directly; if false, only 30% chance to enter the next stage;
* Stone extraction in tile stonecutter: 30% success rate when Crop Lazy Mode is true, 10% success rate when false.
* Tough Ore Embryo Shard has the twice chance to extract successfully

#### Fixe

* Fixed the issue where Cobble Sculk Stone was not dropped when breaking Sculk Stone Farmland.

# 

# Croparium 2.0.0

## Sep 27, 2025

**A Lot of New Features**

#### New Content

* Added support for ore planting from the Thermal mod series.



* Added the following block tags:

\#croparium:crop\_dimension\_overworld - Plants with minerals from the Overworld

\#croparium:crop\_dimension\_nether - Plants with minerals from the Nether

\#croparium:crop\_dimension\_aether - Plants with minerals from the Aether

\#croparium:crop\_dimension\_end - Plants with minerals from the End

\#croparium:crop\_dimension\_sculk - Plants with minerals from the Sculk dimension

\#croparium:crop\_stage0 - Mineral plants at growth stage 0

\#croparium:crop\_stage1 - Mineral plants at growth stage 1

\#croparium:crop\_stage2 - Mineral plants at growth stage 2

* Added the following item tags:

\#croparium:cropseeds - Seeds of ore plants

\#croparium:unmaturecrop - Immature ore plants (corresponding to block tag #croparium:crop\_stage1)

\#croparium:maturecrop - Mature ore plants (corresponding to block tag #croparium:crop\_stage2)

###### Modified and added tags for blocks required to extract ore embryo shards from various dimensions:

* Tag for extracting ore embryo shard blocks: #croparium:embryo\_stone\_overworld, by default includes: #forge:stone, #forge:cobblestone, #minecraft:base\_stone\_overworld
* Tag for extracting nether embryo shard blocks: #croparium:embryo\_stone\_nether, by default includes: #forge:netherrack, minecraft:basalt, minecraft:polished\_basalt, minecraft:smooth\_basalt, minecraft:magma\_block
* Tag for extracting aether embryo shard blocks: #croparium:embryo\_stone\_aether, by default includes: aether:holystone, aether:icestone, aether:mossy\_holystone
* Tag for extracting end embryo shard blocks: #croparium:embryo\_stone\_end, by default includes: #forge:end\_stones
* Tag for extracting sculk embryo shard blocks: #croparium:embryo\_stone\_sculk, by default includes: deeperdarker:sculk\_stone, deeperdarker:cobbled\_sculk\_stone, deeperdarker:gloomslate, deeperdarker:cobbled\_gloomslate, deeperdarker:blooming\_sculk\_stone

###### Logic Improvements

* Refactored the logic for planting, growing, and maturing of the mod's plants. Optimized the logic for "moisturizing" the mod's farmland blocks.
* Added an intuitive effect to moist basalt farmland: entities standing on its top surface will continuously take damage similar to magma blocks.

###### Added a game rule: cropGrowRestrict. 

This rule controls whether ore crops can only be planted in specified environments, disabled by default. Forced to enable in Hard difficulty. Specific environmental requirements:

* Overworld ore crops: environmental light level ≤ 7
* Nether ore crops: surrounding light level ≥ 12
* Aether ore crops: exposed to sky above and surrounding light level ≥ 12
* End ore crops: surrounding light level = 0
* Otherside ore crops: surrounding light level = 0 and Y-coordinate (height) ≤ 0

#### Changes

* Optimized the farmland degradation process. Now, moist farmland blocks will first degrade to "unmoistened" farmland blocks after game tick update if necessary fluids are missing within 4 blocks. For "unmoistened" farmland blocks, they will degrade to corresponding stone blocks after game tick update if necessary fluids are missing within 4 blocks.
* Farmland blocks requiring water sources can now stay moist if there are water-containing blocks nearby.
* Ore crop growth speed was too slow, so this update increased it by approximately 57% (from 0.035 to 0.055).
* The success probability of extracting embryo shards from dimension-specific stone blocks is adjusted to: 16% in non-Hard game modes; 8% in Hard game mode.

#### Fixes

* Fixed the bug where mature emerald plants drop nothing when broken.
* Fixed the bug where end stone farmland had a full block collision box; its collision box height is now 15.
* Fixed the bug where some vanilla mineral plants could still be matured with bone meal.
* Fixed the bug where end stone farmland had an incorrect water source detection range when moistening.

# 

# Croparium 1.3.0

## Sep 25, 2025

#### Fixes

* Resolved an issue where crops from the Simple Ores mod could not be broken down into their corresponding ores in the stonecutter block.

#### Changes

* When breaking down ore plants in the stonecutter block, the resulting minerals now spawn at the center of the stonecutter's upper surface, instead of at a corner of the upper surface.
* Ore crops at growth stage 1 can now be harvested with Silk Touch to drop the plant itself. Right-clicking the stonecutter block while holding such plants will still allow decomposition, but will consistently drop 2 corresponding ores with no corresponding seeds.
* Modified the types of stones that can be used to extract embryo shards in the stonecutter block, as follows:

###### Ore Embryo Shard (for overworld ore crops):

* Items tagged with forge:stone, items tagged with minecraft:base\_stone\_overworld, cobblestone, mossy cobblestone, and cobbled deepslate.

###### Nether Embryo Shard (for nether ore crops):

* Items tagged with forge:netherrack, basalt, polished basalt, and smooth basalt.

###### End Embryo Shard (for end ore crops):

* Items tagged with forge:end\_stones.

###### For Ore Embryo Shard and Nether Embryo Shard, two new tags have been added respectively

* croparium:overworld\_embryo\_stone and croparium:nether\_embryo\_stone, allowing players to customize and expand the types of stones that can be used for extraction.

#### New Content

* Added the game rule cropRipeningEnable (true by default), which controls whether embryo shards can be used to ripen corresponding ore crops.

# 

# Croparium 1.2.0

## Sep 23, 2025

#### New Function

##### Tile Stonecutter's New function

* When you break mature ore crops with a tool enchanted with Silk Touch in your main hand, the crop itself will drop. If you hold these dropped crops and right-click the tile stonecutter, the crops can be disassembled into more of the corresponding minerals. Note that no seeds will be obtained through this disassembly process.

##### New Game Rule

* The aforementioned new function may potentially disrupt the game balance. Therefore, a game rule "/gamerule cropCutEnable" has been added. By default, this rule is set to "false". Only when the rule is set to "true" will the function "right-clicking the tile stonecutter with mature crops to disassemble them" be allowed.​
* You can modify this game rule either during world creation or in-game by using the command "/gamerule cropCutEnable true(false)".

# 

# Croparium 1.1.0

## Sep 23, 2025

* Added support for planting the Soul Crystal and Reinforced Echo Shard items from the Deeper and Darker mod.​
* Added support for planting the Qarium Ore from the FakeForge mod.​
* Added support for planting Qa RoseGold from the Qa Extends \& Waste Innovations mod. Note: This crop requires planting on End stone Farmland.​
* Added support for planting Salt from the Maple mod.

# 

# Croparium 1.0.1

## Sep 22, 2025

* Resolved the problem where seeds in the Aether mod could not be crafted, as well as the inability to till soil on Holy Stone.​
* Fixed the missing crafting recipe for vanilla Emerald Seeds.

# 

# Croparium 1.0

## Sep 22, 2025

* Official Release

# 

# Croparium 25w39a

## Sep 21, 2025

* Added support for minerals from the Aether mod. Minerals in the Aether must be planted on Holy Farmland, which is cultivated from Holy Stone.​
* Renamed "Stone Crafting Table" to "Tile Stonecutter". The usage method has been adjusted: hold the corresponding stone in your right hand and right-click the Tile Stonecutter to use it.​ No redstone energy is needed any more.
* Added the Aether variant of Embryo Shard. This variant can be obtained by using stones from the Aether via the Tile Stonecutter.

# 

# Croparium 25w38b

## Sep 20, 2025

* Added support for Zinc Ore from the Create mod, including proper integration with mining mechanics and crushing systems .
* Expanded compatibility to include core ores from the SimpleOres mod.
* Expanded compatibility for Immersive Engineering mod.
* Optimized performance for ore crop maturation

# 

# Croparium 25w38a



## Sep 20, 2025

* Added Emerald Crop.​
* Left-hand holding of Ore Seeds now allows planting.​
* Now, Overworld crops require ore embryo shard to ripen, while Nether crops require nether ore embryo shard for ripening.​ (Bone meal will no longer work )
* The Stone Crafting Table now requires Redstone power to function.


