Bastion provides a magical "Cacheable" data type which uses Lua meta programming to create a cached representation of another object without losing object parody. 

> IE, a Cacheable Unit representation will maintain all methods and magic functionality found on a regular Unit instance

```lua
-- On index check the cache to be valid and return the value or reconstruct the value and return it
function Cacheable:__index(k)
-- When the object is accessed return the value
function Cacheable:__tostring()
-- Create
function Cacheable:New(value, cb)
-- Try to update the value
function Cacheable:TryUpdate()
-- Update the value
function Cacheable:Update()
-- Set a new value
function Cacheable:Set(value)
-- Set a new callback
function Cacheable:SetCallback(cb)
```