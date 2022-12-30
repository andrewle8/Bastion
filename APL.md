The included APL class offers developers an alternative approach to writing rotations, which is very reminiscent of SimCraft. 

Developers can define priority lists by adding Spells, Items, "manually" resolved Actions, and even other APLs themselves. 

```lua
-- Constructor
function APL:New(name)
-- Add a variable to the APL
function APL:SetVariable(name, value)
-- Get and evaluate a variable
function APL:GetVariable(name)
-- Add a manual action to the APL
function APL:AddAction(action, cb)
-- Add a spell to the APL
function APL:AddSpell(spell, condition)
-- Add an APL to the APL (for sub APLs)
function APL:AddAPL(apl, condition)
-- Execute the APL
function APL:Execute()
-- tostring
function APL:__tostring()
```