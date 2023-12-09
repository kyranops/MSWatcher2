# MSWATCHER2
###### Keeping watch for you, so you don't have to.
![splash screen](https://github.com/kyranops/MSWatcher2/blob/main/assets/splash.png?raw=true)

## Introduction
MSWatcher2 is a monitoring utility for MapleStory that aims to reduce human effort in monitoring your bot in MapleStory.
- MSWatcher2 will constantly scan your screen for icons/pictures/text against the database and either send an alert or perform an action.
- MSWatcher2 also provides input assist to improve QOL of certain repetitive inputs.

MSWatcher2 **does not** perform any packet-sniffing or other actions that would constitute as hacking, and it **is not** a macro utility and **will not** help you farm.
> <img src="https://github.com/kyranops/MSWatcher2/blob/main/assets/icon.png?raw=true" alt="icon" width="15"/> MSWatcher2 simply watches for you, so you don't have to. 


***
## Event Detection
MSWatcher2 monitors your screen constantly to alert your Discord. Some of the scans that are bundled by default include:
- Critical Event Detection
    - Hitting Air Detection (i.e. Attacking in a map with mob spawn disabled or bot running in town)
    - All Chat messages or GM Chat messages
    - Violetta Test Appeared
    - Lie Detector Failed
- QOL Event Detection
    - Character not moving
    - Character is dead
    - Mushroom Buff Ended Detection
    - Rune Appeared on Map
    - Strangers/Guildmate/Friend on map Detection
    - Polo/Flamewolf Portal Detection
    - Especia Portal Detection (Totem Slash)

*Event detection scans are fully extensible - ***You can add your own scans without knowing how to code***

> <img src="https://github.com/kyranops/MSWatcher2/blob/main/assets/icon.png?raw=true" alt="icon" width="15"/> Discord Alert received when MSWatcher2 detects events, chat messages sent as picture
![discord alert example](https://github.com/kyranops/MSWatcher2/blob/main/assets/alertexample.png?raw=true)

Other scans that are currently in beta or planned for future development includes:
- OCR text recognition to extract text from all chat or gm chat
- Chat type differentiation to identify if it is party chat, buddy chat, guild chat etc
- Current EXP percentage detection

*New scans are constantly being developed if there is enough interest in a desired function*

***
## Input Assist
MSWatcher2 monitors your screen constantly and performs actions when certain events occur. This is particularly helpful when logging in remotely or from your phone.
Some of the input assist functions that are bundled by default include:
- Automatic Login from Title Screen (Including 2FA input, world/channel selection)
- Automatic Secondary Password Input (Useful for accessing storage, Vmatrix, Cash shop gifting etc.)
- Automatic Revive when Character is dead
- Automatic Blink when Character is stuck

> <img src="https://github.com/kyranops/MSWatcher2/blob/main/assets/icon.png?raw=true" alt="icon" width="15"/> Auto-login and auto2fa demo
![autologin demo](https://github.com/kyranops/MSWatcher2/blob/main/assets/autologin_demo.gif?raw=true)

Other functions that are currently in beta or planned for future development includes:
- Automatic CC when certain conditions are met (e.g. number of people, time)
- Automatic navigation to training map by Hyper Teleport Rock
- Automatic relogin if game disconnects or Maple Crashes

*New functions are constantly being developed if there is enough interest in a desired function*

***
## Fully Self-contained
All libraries and modules used by MSWatcher2 are fully packaged with the executable.
- There is no need to install C++, python, interception or any other programs
- This means that it can be deployed to new environments (e.g. a new VM) without having to install multiple dependant software.
- Everything that is needed will be included in the [dist](https://github.com/kyranops/MSWatcher2/tree/main/dist) folder and can be used plug-and-play style

*Exception: Tesseract.exe is needed if OCR is turned on. Default is Off*

## Low Profile, Low Impact
A key focus of MSWatcher2 is to minimize interaction with the game. This prevents any conflicts with other programs that may be running
- Will not interfere with any bot or macro that is currently running as input assist only runs in town
- Will not interfere with any existing rune solver or similar programs

## Designed for Customizability
The main codebase of MSWatcher2 is dynamic, every time it is started it will parse the contents in config.ini to generate the scan table.
Besides improving runtime, this means that scans can be **removed** or **added** without having to modify the codebase
- All alerts can be toggle on/off, and alert messages can be fully customized without having to code
- New alerts can be added by the user without requiring coding knowledge, and can be added straight into the config.ini file, no recompilation needed
- Alerts can be integrated with other native Discord functions, including @everyone pings or other discord bots to manage alert logs

*Full instructions provided in [readme.txt](https://github.com/kyranops/MSWatcher2/blob/main/dist/readme.txt)*

## Lifetime Upgrades and Improvements
MSWatcher2 is my personal passion project and I am constantly working on it to make it better and more efficient. 
- **Ongoing Development**: New functions are always being added and existing functions are enhanced for reliability Updating is also a simple process, as MSWatcher2 is fully backwards compatible.
- **Free Updates Forever**: Updates to existing functionalities of MSWatcher2 will be free and remain free
- The newest version will always be provided in the [dist](https://github.com/kyranops/MSWatcher2/tree/main/dist) folder. Simply drag-and-drop the new MSWatcher2.exe (and config.ini if specified)

***
## Getting Started
This project is closed source. Please reach out to me on [Discord](https://discordapp.com/users/157035482650378241) if you are interested.

A full guide on how to get set-up and configure MSWatcher2 is available in the readme.txt

***
## Changelog
- 30 Nov 2023: v2.31130_rev1a - Fixed issue where achievement megas get flagged as chat
- 09 Dec 2023: v2.31205_rev0a - Added input assist functions, fixed bugs and improved scan order. New config.ini