# HW Scripts | Advanced ATM Robbery [ESX] [QBCORE] [OX]

## Introduction
This script provides a comprehensive Lua solution for advanced ATM robbery scenarios in FiveM servers, compatible with both ESX and QBCore frameworks. It allows players to engage in dynamic criminal activities by hacking ATMs and looting cash rewards. The script features detailed configurations for police interaction, item requirements, cooldown management, and Discord logging.

## :white_check_mark: Features
- **ATM Hacking**: Players can attempt to hack ATMs using specified items.
- **Cash Looting**: Successfully hacked ATMs yield cash rewards for players.
- **Cooldown Management**: ATMs have cooldown periods after being hacked to prevent rapid exploitation.
- **Police Interaction**: Police are notified of ongoing robberies and receive blips indicating robbery locations.
- **Discord Logging**: Robbery events can be logged to Discord webhooks for server administration.

## :globe_with_meridians: Dependencies
- [es_extended](https://github.com/ESX-Org/es_extended) or [QBCore](https://github.com/qbcore-framework/qb-core)
- [ox_inventory](https://github.com/overextended/ox_inventory)
- [ox_lib](https://github.com/overextended/ox_lib)
- [hw_utils](https://hw-scripts-store.tebex.io/package/6258214) (Free)
- [cd_dispatch](https://codesign.pro/package/4206357) (Paid) → If set in config
- [linden_outlawalert](https://github.com/thelindat/linden_outlawalert) (Free) → If set in config

## :white_check_mark: Configuration
The configuration options are available in the `config.lua` file and include settings for mode selection, debug logs, localization, framework choice (ESX or QBCore), notification preferences, police involvement, cooldown management, hacking item definition, reward settings, and ATM locations.

```lua
Config = {}

Config.Mode = 'active' -- Choose between modes (active, dev, test)
Config.checkForUpdates = true -- Recommended to leave as 'true'
Config.Debug = true -- Want to enable debug logs?

Config.Locale = 'en' -- Currently supported (english)
Config.Framework = 'ESX' -- or 'QBCore'
Config.TargetSystem = 'qtarget'  -- Options: 'ox_target' or 'qtarget'

Config.Logs = true -- Do you want to enable discord logging?
Config.Webhook = 'https://discord.com/api/webhooks/1239762534223843470/aLhX16APpTy5049Y74tMiXkEP2qM_65pUXlI4sm3Ij8Q8cwIZo0fWHORAhPf6gjYMi81' -- Webhook URL here
Config.BotName = 'HW Logs' -- What should the bot be named?
Config.LogTitle = 'ATM Robbery Logs' -- Title of the log
Config.LogColor = 65280  -- A decimal representation of a hex color code (e.g., blue)

Config.NotificationType = 'ox_lib'  -- Options: 'ox_lib', 'esx', 'qbcore'
Config.NotificationDuration = 4500 -- Duration for notifications in milliseconds

Config.PoliceJobs = {
    'police',
    'sheriff'
}

Config.PoliceRequired = 0 -- Required cops needed to be online
Config.PoliceNotify = true -- Should police get notified?
Config.PoliceBlip = true -- Should they get a blip where ATM is robbery?
Config.DispatchType = 'linden'
Config.AlertBlipTime = 30 -- seconds
Config.AlarmTimer = 30000 -- milliseconds

Config.ATMRobberyTime = 60 -- seconds
Config.CooldownTime = 5 -- seconds = cooldown between crack and looting
Config.GlobalCooldownTime = 600 -- seconds (10 minutes) = will  basicly disable script for 10 minutes

Config.HackingItem = 'hack_phone' -- The item required to hack the ATM
Config.Reward = { min = 10000, max = 18000 } -- Reward you get from looting a ATM

Config.ATMs = {
    { model = 'prop_atm_03', coords = vector3(112.64, -819.49, 31.34) },  -- Add as many ATMs as needed
}

Config.Dealer = {
    model = 's_m_m_highsec_01',
    coords = vector3(345.5158, -993.6245, 28.3707),
    heading = 245.0,
    menu = {
        { label = 'Buy Hacking Phone - $5000', value = 'hack_phone', price = 5000 },
        { label = 'Buy Lockpick - $1000', value = 'lockpick', price = 1000 }
    }
}
```

## :wrench: Download & Installation
Follow these steps to set up the script on your ESX server:

1. **Download the Files**: Download the script files from the provided source.
2. **Copy to Server Resource Directory**: Place the `hw_advancedATMrobbery` folder in the server resource directory.
3. **Update `server.cfg`**: Add the following line to your `server.cfg` file:
    ```cfg
    start hw_advancedATMrobbery
    ```
4. **Start Your Server**: Restart or start your ESX server to load the `hw_advancedATMrobbery` resource.

If help is needed, you can contact me via Discord. A link for that will be provided in the console upon restarting the script. Alternatively, you can search for HenkW00 on Google, GitHub, or CFX.

Enjoy the script, and I hope you find it useful! ❤️
