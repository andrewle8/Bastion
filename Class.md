Bastion's Class module is a wrapper around World of Warcraft's unit class functions. However it's quite barebones and not used at the moment, but it would aim in the future to provide developers with relevant class specific information for whatever their needs may be. 

```lua

function Class:__index(k)
-- Constructor
function Class:New(locale, name, id)
-- Get the classes locale
function Class:GetLocale()
-- Get the classes name
function Class:GetName()
-- Get the classes id
function Class:GetID()
-- Return the classes color
function Class:GetColor()
```