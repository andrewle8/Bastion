The MythicPlusUtils module aims to provide developers with critical situational information to optimize rotations for high-end mythic plus gameplay automation, such as affix timers, boss timers, debuff lists, interrupt lists, and more. 

Currently the module only has a simple debuff logger implemented which will serve as a critical utility to accumulate important information that otherwise may be incorrect or difficult to find (WoW Head may use the wrong IDs for the right spells)

To enable the logging you may type `/bastion mplus debuffs` 

```lua
function MythicPlusUtils:New()
function MythicPlusUtils:ToggleDebuffLogging()
function MythicPlusUtils:CastingCriticalKick(unit, percent)
```