Bastion's Module class wraps away various complexities of a developer defined script which would be meant to interact with Bastion's main ticker loop. This is where you would define something like a rotation and hand off it's logical assesment tree or APL for Bastion to iterate every time the engine 'ticks' 

```lua
function Module:__tostring()
function Module:New(name)
function Module:Enable()
function Module:Disable()
function Module:Toggle()
function Module:Sync(func)
function Module:Unsync(func)
function Module:Tick()
```