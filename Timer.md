Bastion provides a basic Timer class to allow developers to time various things, for example Bastion exposes a Combat Timer to watch how long the player has been in combat. 

```lua
-- Constructor
function Timer:New(type)
-- Start the timer
function Timer:Start()
-- Get the time since the timer was started
function Timer:GetTime()
-- Check if the timer is running
function Timer:IsRunning()
-- Reset the timer
function Timer:Reset()
```