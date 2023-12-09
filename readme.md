# MSWATCHER2
![splash screen](https://github.com/kyranops/MSWatcher2/blob/main/assets/splash.png?raw=true)

MSWatcher2 is a monitoring utility for MapleStory that helps to monitor your game for prespecified scenarios. It does so by matching target assets with the current game view and sending a Discord alert when the event is observed. MSWatcher2 also provides input assist to improve QOL of certain repetitive inputs.
MSWatcher2 **does not** perform any packet-sniffing or other actions that would constitute as hacking, and it **is not** a macro utility and **will not** help you farm.
> MSWatcher2 simply watches for you, so you don't have to.

***
## Event Detection
MSWatcher2 monitors your screen constantly to alert your Discord. Some of the scans that are bundled by default include:
- Rune Appeared on Map
- Character not moving
- Character is dead
- Violetta Test Appeared and Lie Detector Failed
- All Chat messages or GM Chat messages
- Hitting Air detection (i.e. Attacking in a map with mobs disabled or in town)
- Strangers/Guildmate/Friend on map detection
> This list is fully extensible - You can add your own scans without knowing how to code

***
## Input Assist
MSWatcher2 monitors your screen constantly and performs actions when certain events occur. Some of the input assist functions that are bundled by default include:
- Automatic Login from Title Screen (Including 2FA input, world/channel selection)
- Automatic Secondary Password Input (Useful for accessing storage, Vmatrix, Cash shop gifting etc.)
- Automatic Revive when Character is dead
- Automatic Blink when Character is stuck

Other functions that are currently in beta includes:
- Automatic CC when certain conditions are met (e.g. number of people, time)
- Automatic navigation to training map by Hyper Teleport Rock
- Automatic relogin if game disconnects or Maple Crashes
> New functions are constantly being developed if there is enough interest in a desired function

***
## Designed for Customizability
All alerts can be toggle on/off, and alert messages can be fully customized without having to code
New alerts can also be added by the user without requiring coding knowledge, and can be added straight from the config.ini file
Alerts can be integrated with other native Discord functions, including @everyone pings or other discord bots to manage alert logs
*Full instructions provided in readme.txt*

***
## Lifetime Upgrades and Improvements
MSWatcher2 started out as a passion project and I am constantly working on it to make it better and more efficient. 
New functions are always being added and existing functions are enhanced for reliability Updating is also a simple process, as MSWatcher2 is fully backwards compatible. 
The newest version will always be provided in the [dist](https://github.com/kyranops/MSWatcher2/tree/main/dist) folder. Simply drag-and-drop the new MSWatcher2.exe (and config.ini if specified)
***