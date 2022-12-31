Bastion aims to provide helper utility modules for end-game content where rotations may need to have a greater understanding of different mechanics, such as boss ability timers, critical debuffs to dispel, and awareness of where the player is within the given contents map (Such as having an understanding that we may be close to a difficult boss, so we should aim to save our cooldowns)

While these are all great things in theory, the module is still in early development and may take some time to include these features, and more. 

The MythicPlusUtils module aims to provide developers with critical situational information to optimize rotations for high-end mythic plus gameplay automation, such as affix timers, boss timers, debuff lists, interrupt lists, and more. 

Currently the module only has a simple debuff logger implemented which will serve as a critical utility to accumulate important information that otherwise may be incorrect or difficult to find (WoW Head may use the wrong IDs for the right spells)

To enable the logging you may type `/bastion mplus debuffs` 

```lua
function MythicPlusUtils:New()
function MythicPlusUtils:ToggleDebuffLogging()
function MythicPlusUtils:HasCriticalDispel(unit)
```