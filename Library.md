Bastion offers powerful library injection for project wide script reuse. 

Conceptually, it was designed to make reusable code as simple as possible from modules, while still offering a simplistic approach for all developers, it most closely reflects that of NodeJS. 

```lua
function Library:New(library)
function Library:ResolveExport(export)
function Library:Resolve()
function Library:DependsOn(other)
function Library:Import(library)
```

There's many methods in the Library class, however the only ones that *matter* for developers are going to be :New and :Import

Let's break down creating a basic library, and explain some ground rules. 

```lua
-- scripts/Libraries/ExampleDependency.lua

local Tinkr, Bastion = ...

Bastion:RegisterLibrary(Bastion.Library:New({
    name = 'Dependable',
    exports = {
        default = function() -- Libraries that have a (default) will force this value to be the first return when the Library is imported
            local Dependable = {}

            Dependable.__index = Dependable

            function Dependable:Test(a)
                print(a)
            end

            return Dependable
        end,
        Test = 5, -- Libraries can have many exports, however there's a couple of quirks to be aware of from a Library development standpoint
        Add = function() -- For example, when exports are resolved, function types are automatically invoked, if we wanted to return a function and not get an arbitrary return value we would have to write the code as such
        	return function(a,b)
            	return a + b
            end
        end,
        --5, -- Direct variable exports such as this will be hard to work with since Lua does not offer destructuring like JavaScript or other languages, you should just assign values to keys. 
    }
}))

```

An example of usage would be as such. 

```lua
--scripts/ExampleModule.lua

local Tinkr, Bastion = ...
local ExampleModule = Bastion.Module:New('ExampleModule')
local Player = Bastion.UnitManager:Get('player')

-- Create a local spellbook
local SpellBook = Bastion.SpellBook:New()

local FlashHeal = SpellBook:GetSpell(2061)

-- Get a global spell (this can collide with other modules, so be careful)
-- This is useful for caching common spells that you might not actually cast, and to avoid needless spell creation inline
local FlashHeal = Bastion.Globals.SpellBook:GetSpell(2061)

local Dependable, OtherExports = Bastion:Import('Dependable')

Dependable:Test(OtherExports.Test)

ExampleModule:Sync(function()
    if Player:GetHP() <= 50 then
        FlashHeal:Cast(Player)
    end
end)

Bastion:Register(ExampleModule)
```

Modules aren't the only place you can import Libraries, Libraries allow for other Libraries to be imported inside of them, and they attempt to detect Circular Dependency errors dynamically. 

Here's an example of how to import other Libraries into a Library. 

```lua
-- scripts/Libraries/ExampleLibrary.lua

local Tinkr, Bastion = ...

Bastion:RegisterLibrary(Bastion.Library:New({
    name = 'AdvancedMath',
    exports = {
        default = function(self) -- Function exports are called when the library is loaded
            -- Return default first, and then the remaining exports
            local Dependable, OtherExports = self:Import('Dependable')

            -- local CircularDependency = self:Import('Circular') -- Causes a circular dependency error

            Dependable:Test(OtherExports.Test)

            local AdvancedMath = {}

            AdvancedMath.__index = AdvancedMath

            function AdvancedMath:Add(a, b)
                return a + b
            end

            return AdvancedMath
        end
    }
}))

```