Bastion's ObjectManager is an isolated single iteration ObjectManager meant to try and optimize maintaining lists of objects in a performant way. Eventually developers will be able to define their own lists to be watched, but this isn't implemented at this time. 

```lua
function ObjectManager:New()
function ObjectManager:Refresh()

-- ObjectManager.enemies -> List
-- ObjectManager.friends -> List
-- ObjectManager.activeEnemies -> List
-- ObjectManager.explosives -> List
```

````lua
    Bastion.ObjectManager.activeEnemies:each(function(unit)
        if cb(unit) then
            return true
        end
    end)
    ```
````
