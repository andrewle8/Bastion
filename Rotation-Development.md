Bastion offers developers multiple ways to write and maintain Rotation's for World of Warcraft users. 

Most developers are already familiar with [APLs](https://git.tinkr.site/4n0n/bastion/wiki/APL) from Simulation Craft, but in short, they're just a top down list of priorities for the bot to evaluate and potentually execute. The drawbacks however are that since SimC does not 'return' when an actor is deemed executable, you may have undesired execution of multiple actors at the same time. 

Bastion offers you alternative rotation development methods such as Spell conditions, or enabling you to write logic trees like most already are comfortable with. 

A few examples of how you may implement Spell conditions are as follows

With an APL 

```lua
local Tinkr, Bastion = ...

local RestoModule = Bastion.Module:New('resto_druid')

local SpellBook = Bastion.SpellBook:New()

local Moonfire = SpellBook:GetSpell(8921)
local DefaultAPL = Bastion.APL:New('default')

Moonfire:CastableIf(function(self)
    return Target:Exists() and self:IsKnownAndUsable() and not Player:IsCastingOrChanneling()
        and Player:CanSee(Target)
end)

Moonfire:Condition('refresh', function(self)
    return Target:GetAuras():FindMy(MoonfireAura):GetRemainingTime() <= 3
end)

Moonfire:Condition('apply', function(self)
    return not Target:GetAuras():FindMy(MoonfireAura):IsUp()
end)

DefaultAPL:AddSpell(
    Moonfire, 'refresh'
)

DefaultAPL:AddSpell(
    Moonfire, 'apply'
)

RestoModule:Sync(function()
    DefaultAPL:Execute()
end)

Bastion:Register(RestoModule)
```

Callbacks
```lua
local Tinkr, Bastion = ...

local RestoModule = Bastion.Module:New('resto_druid')

local SpellBook = Bastion.SpellBook:New()

local Moonfire = SpellBook:GetSpell(8921)
local DefaultAPL = Bastion.APL:New('default')

Moonfire:CastableIf(function(self)
    return Target:Exists() and self:IsKnownAndUsable() and not Player:IsCastingOrChanneling()
        and Player:CanSee(Target)
end)

Moonfire:Condition('refresh', function(self)
    return Target:GetAuras():FindMy(MoonfireAura):GetRemainingTime() <= 3
end)

Moonfire:Condition('apply', function(self)
    return not Target:GetAuras():FindMy(MoonfireAura):IsUp()
end)

RestoModule:Sync(function()
    Moonfire:Cast(Target, 'refresh')
    Moonfire:Cast(Target, 'apply')
end)

Bastion:Register(RestoModule)
```

Logic Tree
```lua
local Tinkr, Bastion = ...

local RestoModule = Bastion.Module:New('resto_druid')

local SpellBook = Bastion.SpellBook:New()

local Moonfire = SpellBook:GetSpell(8921)

RestoModule:Sync(function()
    if Target:Exists() and Moonfire:IsKnownAndUsable() and not Player:IsCastingOrChanneling() and Player:CanSee(Target)
        and Target:GetAuras():FindMy(MoonfireAura):GetRemainingTime() <= 3 then
        return Moonfire:Cast(Target)
    end

    if Target:Exists() and Moonfire:IsKnownAndUsable() and not Player:IsCastingOrChanneling() and Player:CanSee(Target)
        and not Target:GetAuras():FindMy(MoonfireAura):IsUp() then
        return Moonfire:Cast(Target)
    end
end)

Bastion:Register(RestoModule)
```