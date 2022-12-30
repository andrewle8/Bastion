Bastion's AuraTable class is a cached, Aura lookup table which allows developers to no longer need to iterate over unit memory (possibly) multiple times per frame. 

The Aura table abstracts away the potential complexity of implementing a lookup table, and it can be expanded upon in the future to better fit all developer needs. 

```lua
-- Constructor
function AuraTable:New(unit)
-- Get a units buffs
function AuraTable:GetUnitBuffs()
-- Get a units debuffs
function AuraTable:GetUnitDebuffs()
-- Update auras
function AuraTable:Update()
-- Get a units auras
function AuraTable:GetUnitAuras()
-- Get a units auras
function AuraTable:GetMyUnitAuras()
-- Clear the aura table
function AuraTable:Clear()
-- Check if the unit has a specific aura
function AuraTable:Find(spell)

function AuraTable:FindMy(spell)
-- Has any stealable aura
function AuraTable:HasAnyStealableAura()
-- Has any dispelable aura
function AuraTable:HasAnyDispelableAura(spell)
```