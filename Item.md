Bastion's Item class provides a wrapper around various World of Warcraft Item functions, allowing developers to more easily interact with items. 

```lua
function Item:__index(k)
function Item:__tostring()
function Item:New(id)
function Item:GetID()
function Item:GetName()
function Item:GetIcon()
function Item:GetCooldown()
function Item:GetUsableFunction()
function Item:GetPreUseFunction()
function Item:GetOnUseFunction()
function Item:GetCooldownRemaining()
function Item:Use(unit, condition)
function Item:GetLastUseAttempt()
function Item:GetTimeSinceLastUseAttempt()
function Item:IsEquipped()
function Item:IsOnCooldown()
function Item:IsUsable()
function Item:IsEquippedAndUsable()
function Item:IsEquippable()
function Item:Usable()
function Item:UsableIf(func)
function Item:PreUse(func)
function Item:OnUse(func)
function Item:GetWasLooking()
function Item:Click(x, y, z)
function Item:Call(unit)
function Item:IsInRange(unit)
function Item:GetLastUseTime()
function Item:GetTimeSinceLastUse()
function Item:GetCharges()
function Item:GetChargesRemaining()
function Item:Condition(name, func)
function Item:GetCondition(name)
function Item:EvaluateCondition(name)
function Item:HasCondition(name)
function Item:SetTarget(unit)
function Item:GetTarget()
function Item:IsMagicDispel()
function Item:IsCurseDispel()
function Item:IsPoisonDispel()
function Item:IsDiseaseDispel()
function Item:IsItem(item)
function Item:GetSpell()
```