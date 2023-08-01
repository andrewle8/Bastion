Bastion's ItemBook module is used to encapsulate all of the developer defined Items (however it's possible that Items can be added to the ItemBook as they become relevant in the code, perhaps through an event watcher for other unit's Item usage) 

```lua
function ItemBook:New()
function ItemBook:GetItem(id)
```