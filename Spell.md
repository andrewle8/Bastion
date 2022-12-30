Bastion's Spell class provides a wrapper around various World of Warcraft Spell functions, allowing developers to more easily interact with spells.


```lua

function Spell:__index(k)
-- tostring
function Spell:__tostring()
-- Constructor
function Spell:New(id)
-- Get the spells id
function Spell:GetID()
-- Get the spells name
function Spell:GetName()
-- Get the spells icon
function Spell:GetIcon()
-- Get the spells cooldown
function Spell:GetCooldown()
-- Return the castable function
function Spell:GetCastableFunction()
-- Return the precast function
function Spell:GetPreCastFunction()
-- Get the on cast func
function Spell:GetOnCastFunction()
-- Get the spells cooldown remaining
function Spell:GetCooldownRemaining()
-- Cast the spell
function Spell:Cast(unit, condition)
-- Check if the spell is known
function Spell:IsKnown()
-- Check if the spell is on cooldown
function Spell:IsOnCooldown()
-- Check if the spell is usable
function Spell:IsUsable()
-- Check if the spell is castable
function Spell:IsKnownAndUsable()
-- Check if the spell is castable
function Spell:Castable()
-- Set a script to check if the spell is castable
function Spell:CastableIf(func)
-- Set a script to run before the spell has been cast
function Spell:PreCast(func)
-- Set a script to run after the spell has been cast
function Spell:OnCast(func)
-- Get was looking
function Spell:GetWasLooking()
-- Click the spell
function Spell:Click(x, y, z)
-- Check if the spell is castable and cast it
function Spell:Call(unit)
-- Check if the spell is in range of the unit
function Spell:IsInRange(unit)
-- Get the last cast time
function Spell:GetLastCastTime()
-- Get time since last cast
function Spell:GetTimeSinceLastCast()
-- Get the spells charges
function Spell:GetCharges()
-- Get the spells charges remaining
function Spell:GetChargesRemaining()
-- Create a condition for the spell
function Spell:Condition(name, func)
-- Get a condition for the spell
function Spell:GetCondition(name)
-- Evaluate a condition for the spell
function Spell:EvaluateCondition(name)
-- Check if the spell has a condition
function Spell:HasCondition(name)
-- Set the spells target
function Spell:SetTarget(unit)
-- Get the spells target
function Spell:GetTarget()
-- IsMagicDispel
function Spell:IsMagicDispel()
-- IsCurseDispel
function Spell:IsCurseDispel()
-- IsPoisonDispel
function Spell:IsPoisonDispel()
-- IsDiseaseDispel
function Spell:IsDiseaseDispel()

function Spell:IsSpell(spell)
```