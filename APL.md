The included APL class offers developers an alternative approach to writing rotations, which is very reminiscent of SimCraft. 

Developers can define priority lists by adding Spells, Items, "manually" resolved Actions, and even other APLs themselves. 

```lua
-- Create a new APL
function APL:New(name)
-- Set a variable
function APL:SetVariable(name, value)
-- Get a variable
function APL:GetVariable(name)
-- Add a variable for evaluation
function APL:AddVariable(name, cb)
-- Add an action for evaluation
function APL:AddAction(action, cb)
-- Add a spell for evaluation
function APL:AddSpell(spell, condition)
-- Add an item for evaluation
function APL:AddItem(item, condition)
-- Add an APL for evaluation
function APL:AddAPL(apl, condition)
-- Execute an APL
function APL:Execute()
-- ToString()
function APL:__tostring()
```

[APLTrait](https://git.tinkr.site/4n0n/bastion/wiki/APLTrait)
[APLActor](https://git.tinkr.site/4n0n/bastion/wiki/APLActor)