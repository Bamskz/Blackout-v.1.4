## Notices
* The script will not function properly unless your exploit fully supports / includes these following functions & libraries:
  - `isfolder()`, `makefolder()` & `delfolder()`
  - `isfile()`, `writefile()` & `delfile()`
  - `getgenv()`
  - `queue_on_teleport()`
  - `Drawing`
* This script will store your changed settings every 10 seconds passed. You can also disable this feature: 
```lua
getgenv().Aimbot.Settings.SaveSettings = false
```
* This script is indeed universal, but it might not run on games with specific character constructions (custom characters).
* A recommended exploit to run this script on is [Krampus/RO-EXEC](https://loader.live).
## Environment
The script's environment is stored as:
```lua
getgenv().Aimbot
```
More on how to configure the aimbot below this part.
## Configuration
This script includes settings which can be easily configured to your preference.
### Preview Of The Settings
```lua
getgenv().Aimbot.Settings = {
    SendNotifications = true,
    SaveSettings = true, -- Re-execute upon changing
    ReloadOnTeleport = true,
    Enabled = true,
    TeamCheck = false,
    AliveCheck = true,
    WallCheck = false, -- Laggy
    Sensitivity = 0, -- Animation length (in seconds) before fully locking onto target
    ThirdPerson = false, -- Uses mousemoverel instead of CFrame to support locking in third person (could be choppy)
    ThirdPersonSensitivity = 3, -- Boundary: 0.1 - 5
    TriggerKey = "MouseButton2",
    Toggle = false,
    LockPart = "Head" -- Body part to lock on (Character part's name)
}

getgenv().Aimbot.FOVSettings = {
    Enabled = true,
    Visible = true,
    Amount = 90,
    Color = "255, 255, 255",
    LockedColor = "255, 70, 70",
    Transparency = 0.5,
    Sides = 60,
    Thickness = 1,
    Filled = false
}
```

⚠️WARNING⚠️ - ***The WallCheck function is very laggy, it is recommended you have it set as*** **false** ***at all times!***

By reading the visual representation of the configuration part of the environment table, it should be pretty easy to configure the script afterwards. Here are some examples:

### Script Examples

The following script will disable the aimbot temporarily: 
```lua
getgenv().Aimbot.Settings.Enabled = false
```
You can also change the color of the FOV Circle:
```lua
getgenv().Aimbot.FOVSettings.Color = "50, 255, 70" -- The colors must be fed as strings in RGB format. [(R)ed (0 - 255); (G)reen (0 - 255); (B)lue (0 - 255)]
```
**The script only accepts RGB configurations in strings as colors, if you input anything else, the script will break and not execute. Read below on how to fix this.**

You can also disable FOV Checking incase you don't find it useful / don't need it:
```lua
getgenv().Aimbot.FOVSettings.Enabled = false
```
If you want the script to work in third person, you can enable the *ThirdPerson* setting:
```lua
getgenv().Aimbot.Settings.ThirdPerson = true
```
If you want to edit the sensitivity for the third person mode:
```lua
-- The locking animation becomes faster as you increase the value (meaning 5 = fastest). The script becomes choppy if you increase the value.
getgenv().Aimbot.Settings.ThirdPersonSensitivity = 3 -- Boundary: 0.1 - 5
```

## Hotkey
If you want to change the key you want to press to trigger the Aimbot, configure the ***TriggerKey*** setting.
- *Examples* :
```lua
getgenv().Aimbot.Settings.TriggerKey = "E" -- E is the key's name (This is equivalent to Enum.KeyCode.E, except, the script only handles strings)
```
```lua
getgenv().Aimbot.Settings.TriggerKey = "MouseButton1" -- MouseButton1 is the key's name [LMB] (This is equivalent to Enum.UserInputType.MouseButton1, except, the script only handles strings)
```
This script will work if the input type selected is either a *KeyCode* or *UserInputType* so all you have to input is the last part / the key's name.
- Read: [KeyCode](https://developer.roblox.com/en-us/api-reference/enum/KeyCode), [UserInputType](https://developer.roblox.com/en-us/api-reference/enum/UserInputType) 
## Functions
This script includes built-in functions to control the Aimbot.
The functions can be accessed by indexing **Functions** in the Environment. Example:
```lua
getgenv().Aimbot.Functions
```
### Their purposes
* `Functions:Exit()`
  - Exits (unexecutes) the script and leaves no traces back.
* `Functions:Restart()`
  - Restarts the script, good for incase the script starts lagging.
* `Functions:ResetSettings()`
  - Factory resets the settings and wipes the previous ones that were saved to the workspace.

- Exit
```lua
getgenv().Aimbot.Functions:Exit()
```
- Restart
```lua
getgenv().Aimbot.Functions:Restart()
```
- Reset Settings
```lua
getgenv().Aimbot.Functions:ResetSettings()
```
