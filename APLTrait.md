APLTraits are special micro-optimized logic containers which isolate rotation logic and hoist it to the top of an APL evaluation, caching it per APL execution to try and mitigate unneeded repetitive code. 

```lua
function APLTrait:New(cb)
function APLTrait:Evaluate()
function APLTrait:__tostring()
```

```lua
local Facing = function(t)
    return Bastion.APLTrait:New(function()
        return Player:IsFacing(t)
    end)
end

local HealthOverHalf = Bastion.APLTrait:New(function() return Player:GetHP() > 50 end)
```

[APLActor](https://git.tinkr.site/4n0n/bastion/wiki/APLTrait)
[APL](https://git.tinkr.site/4n0n/bastion/wiki/APL)