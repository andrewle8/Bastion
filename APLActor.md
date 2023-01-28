Developers will likely never create an APLActor directly, however they will be given one by calling the APL:Add*** functions. Most developers will be interested in the AddTraits method, which lets you reuse predefined logic evaluated once per APL iteration, instead of on every spell.

```lua
function APLActor:New(actor)
function APLActor:AddTraits(...)
function APLActor:GetActor()
function APLActor:Evaluate()
function APLActor:Execute()
function APLActor:HasTraits()
function APLActor:__tostring()
```

```lua
local Facing = function(t)
    return Bastion.APLTrait:New(function()
        return Player:IsFacing(t)
    end)
end

SpecialAPL:AddSpell(
    Kick:CastableIf(function(self)
        return KickTarget:Exists() and Player:InMelee(KickTarget) and
            self:IsKnownAndUsable() and
            not Player:IsCastingOrChanneling()
    end):SetTarget(KickTarget)
):AddTraits(
    Facing(KickTarget)
)
```

[APLTrait](https://git.tinkr.site/4n0n/bastion/wiki/APLTrait)
[APL](https://git.tinkr.site/4n0n/bastion/wiki/APL)