It's unlikely developers will ever create or remove notifications directly, however they may use a NotificationList, particularly the one defined by Bastion already. 

```lua
function Notification:New(list, icon, text)
function Notification:Remove()
```

```lua
    Bastion.Notifications:AddNotification(Efflorescence:GetIcon(), "Efflorescence requested")
```