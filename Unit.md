Bastion provides a Unit class which wraps away some of the complexity or annoyances of World of Warcraft's Unit functions. Aswell as providing the developer with cached and performant Aura access. 

```lua

function Unit:__index(k)
-- tostring
function Unit:__tostring()
-- Constructor
function Unit:New(unit)
-- Check if the unit is valid
function Unit:IsValid()
-- Check if the unit exists
function Unit:Exists()
-- Get the units token
function Unit:Token()
-- Get the units name
function Unit:GetName()
-- Get the units GUID
function Unit:GetGUID()
-- Get the units health
function Unit:GetHealth()
-- Get the units max health
function Unit:GetMaxHealth()
-- Get the units health percentage
function Unit:GetHP()

function Unit:GetHealthPercent()
-- Get the units power type
function Unit:GetPowerType()
-- Get the units power
function Unit:GetPower(powerType)
-- Get the units max power
function Unit:GetMaxPower(powerType)
-- Get the units power percentage
function Unit:GetPP(powerType)
-- Get the units power deficit
function Unit:GetPowerDeficit(powerType)
-- Get the units position
function Unit:GetPosition()
-- Get the units distance from another unit
function Unit:GetDistance(unit)
-- Is the unit dead
function Unit:IsDead()
-- Is the unit alive
function Unit:IsAlive()
-- Is the unit a pet
function Unit:IsPet()
-- Is the unit a friendly unit
function Unit:IsFriendly()
-- Is the unit a hostile unit
function Unit:IsHostile()
-- Is the unit a boss
function Unit:IsBoss()
-- Is the unit a target
function Unit:IsTarget()
-- Is the unit a focus
function Unit:IsFocus()
-- Is the unit a mouseover
function Unit:IsMouseover()
-- Is the unit a tank
function Unit:IsTank()
-- Is the unit a healer
function Unit:IsHealer()
-- Is the unit a damage dealer
function Unit:IsDamage()
-- Is the unit a player
function Unit:IsPlayer()
-- Is the unit a player controlled unit
function Unit:IsPCU()
-- Get if the unit is affecting combat
function Unit:IsAffectingCombat()
-- Get the units class id
function Unit:GetClass()
-- Get the units auras
function Unit:GetAuras()
-- Get the raw unit
function Unit:GetRawUnit()
-- Check if two units are in melee
function Unit:InMelee(unit)
-- Check if the unit can see another unit
function Unit:CanSee(unit)
-- Check if the unit is casting a spell
function Unit:IsCasting()
-- Check if the unit is channeling a spell
function Unit:IsChanneling()
-- Check if the unit is casting or channeling a spell
function Unit:IsCastingOrChanneling()
-- Check if the unit can attack the target
function Unit:CanAttack(unit)
-- Check if unit is interruptible
function Unit:IsInterruptible(percent)
-- Get the number of enemies in a given range of the unit and cache the result for .5 seconds
function Unit:GetEnemies(range)

function Unit:GetPartyHPAround(distance, percent)
-- Is moving
function Unit:IsMoving()

function Unit:GetComboPoints(unit)
-- IsUnit
function Unit:IsUnit(unit)
```