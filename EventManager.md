Bastion provides a multi-purpose Event Manager, both wrapping World of Warcraft's own event system, as well as providing a Bastion specific event system for developers to create event driven logic. 

> Note, developers are very unlikely to construct a new event manager as Bastion already does this in it's core file. 

```lua
function EventManager:New()
function EventManager:RegisterEvent(event, handler)
function EventManager:RegisterWoWEvent(event, handler)
function EventManager:TriggerEvent(event, ...)
```