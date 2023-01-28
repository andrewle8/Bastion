It's unlikely developers will ever create a new NotificationList, however they may use Bastion's default one to display notifications to a user. 

```lua
function NotificationsList:New()
function NotificationsList:AddNotification(icon, text)
function NotificationsList:Update()
function NotificationsList:RemoveNotification(notification)
function NotificationsList:RemoveAllNotifications()
```

```lua
    Bastion.Notifications:AddNotification(Efflorescence:GetIcon(), "Efflorescence requested")
```