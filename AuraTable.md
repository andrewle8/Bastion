Bastion's AuraTable class is a cached, Aura lookup table which allows developers to no longer need to iterate over unit memory (possibly) multiple times per frame. 

The Aura table abstracts away the potential complexity of implementing a lookup table, and it can be expanded upon in the future to better fit all developer needs. 

```lua
function AuraTable:New(unit)
function AuraTable:OnUpdate(auras)
function AuraTable:RemoveInstanceID(instanceID)
function AuraTable:AddOrUpdateAuraInstanceID(instanceID, aura)
function AuraTable:GetUnitBuffs()
function AuraTable:GetUnitDebuffs()
function AuraTable:Update()
function AuraTable:GetUnitAuras()
function AuraTable:GetMyUnitAuras()
function AuraTable:Clear()
function AuraTable:Find(spell)
function AuraTable:FindMy(spell)
function AuraTable:FindAny(spell)
function AuraTable:HasAnyStealableAura()
function AuraTable:HasAnyDispelableAura(spell)
```