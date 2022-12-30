Bastion's ItemBook module is used to encapsulate all of the developer defined Items (however it's possible that Items can be added to the ItemBook as they become relevant in the code, perhaps through an event watcher for other unit's Item usage) 

> Note, it's very unlikely a developer will ever define their own ItemBook as Bastion already initializes one it's core file. 

```lua
function ItemBook:New()
function ItemBook:GetItem(id)
```