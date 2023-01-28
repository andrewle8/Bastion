Refreshable objects are helper modules similar to Cacheable that allow for classes to self refresh. However unlike Cacheable's they are not cached and evaluate every access.

```lua
function Refreshable:__index(k)
function Refreshable:__tostring()
function Refreshable:New(value, cb)
function Refreshable:TryUpdate()
function Refreshable:Update()
function Refreshable:Set(value)
function Refreshable:SetCallback(cb)
```

```lua
    return Bastion.Refreshable:New(self.objects[tguid], function()
        local tguid = ObjectGUID(token)
        if self.objects[tguid] == nil then
            if token == 'none' then
                self.objects[tguid] = Unit:New(token)
            else
                self.objects[tguid] = Unit:New(Object(tguid))
            end
        end
        return self.objects[tguid]
    end)

```

[Cacheable](https://git.tinkr.site/4n0n/bastion/wiki/Cacheable)