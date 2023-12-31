Bastion's ClassMagic module is mainly a helper function which abstracts away Lua meta programming complexity to enable developers to access various Bastion module methods as "getter variables" instead. For example, if a developer wants to get a Unit's name they can do so by typing `Unit:GetName()` or `Unit.name`

```lua
local ClassMagic = {}
ClassMagic.__index = ClassMagic

function ClassMagic:Resolve(Class, key)
    if Class[key] or Class[key] == false then
        return Class[key]
    end

    if Class['Get' .. key:sub(1, 1):upper() .. key:sub(2)] then
        local func = Class['Get' .. key:sub(1, 1):upper() .. key:sub(2)]

        -- Call the function and return the result if there's more than one return value return it as a table
        local result = { func(self) }
        if #result > 1 then
            return result
        end

        return result[1]
    end


    if Class['Get' .. key:upper()] then
        local func = Class['Get' .. key:upper()]

        -- Call the function and return the result if there's more than one return value return it as a table
        local result = { func(self) }
        if #result > 1 then
            return result
        end

        return result[1]
    end

    if Class['Is' .. key:upper()] then
        local func = Class['Is' .. key:upper()]

        -- Call the function and return the result if there's more than one return value return it as a table
        local result = { func(self) }
        if #result > 1 then
            return result
        end

        return result[1]
    end

    return Class[key]
end

return ClassMagic

```