Bastion provides a basic Command library for users to define and manage their own commands within scripts. 

```lua
function Command:__tostring()
function Command:New(prefix)
function Command:Register(command, helpmsg, cb)
function Command:Parse(msg)
function Command:OnCommand(msg)
function Command:PrintHelp()
```