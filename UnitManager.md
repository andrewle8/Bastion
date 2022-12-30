Bastion's UnitManager is meant to act as a Cache layer between developer and Units, as well as enabling the developer various methods of enumerating their party and other units around them, such as enemies. 

Developers can also initialize custom units which abuse a magical caching layer to optimize their retrieval, and enable Unit parody with normal World of Warcraft units (Such as a "player" token)

```lua
function UnitManager:__index(k)
function UnitManager:New()
function UnitManager:Validate(token)
function UnitManager:Get(token)
function UnitManager:CreateCustomUnit(token, cb)
function UnitManager:EnumFriends(cb)
function UnitManager:EnumEnemies(cb)
function UnitManager:EnumUnits(cb)
function UnitManager:GetNumFriendsWithBuff(spell)
function UnitManager:GetNumFriendsAlive()
function UnitManager:GetFriendWithMostFriends(radius)
function UnitManager:FindFriendsCentroid(radius, range)
```