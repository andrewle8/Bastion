The Aura class is a helpful wrapper around World of Warcraft's built in Aura methods. 

It serves to try and provide simplicity to the developer by extracting common function calls into an encapsulated object, but the real performance gains come from it's integration Bastion's [AuraTable](https://git.tinkr.site/4n0n/bastion/wiki/AuraTable) class. 

```lua

function Aura:__index(k)

function Aura:__tostring()
-- Constructor
function Aura:New(unit, index, type)

function Aura:CreateFromUnitAuraInfo(unitAuraInfo)
-- Check if the aura is valid
function Aura:IsValid()
-- Check if the aura is up
function Aura:IsUp()
-- Get the auras index
function Aura:GetIndex()
-- Get the auras type
function Aura:GetType()
-- Get the auras name
function Aura:GetName()
-- Get the auras icon
function Aura:GetIcon()
-- Get the auras count
function Aura:GetCount()
-- Get the auras dispel type
function Aura:GetDispelType()
-- Get the auras duration
function Aura:GetDuration()
-- Get the auras remaining time
function Aura:GetRemainingTime()
-- Get the auras expiration time
function Aura:GetExpirationTime()
-- Get the auras source
function Aura:GetSource()
-- Get the auras stealable status
function Aura:GetIsStealable()
-- Get the auras nameplate show personal status
function Aura:GetNameplateShowPersonal()
-- Get the auras spell id
function Aura:GetSpell()
-- Get the auras can apply aura status
function Aura:GetCanApplyAura()
-- Get the auras is boss debuff status
function Aura:GetIsBossDebuff()
-- Get the auras cast by player status
function Aura:GetCastByPlayer()
-- Get the auras nameplate show all status
function Aura:GetNameplateShowAll()
-- Get the auras time mod
function Aura:GetTimeMod()
-- Check if the aura is a buff
function Aura:IsBuff()
-- Check if the aura is a debuff
function Aura:IsDebuff()
-- Check if the aura is dispelable by a spell
function Aura:IsDispelableBySpell(spell)
```