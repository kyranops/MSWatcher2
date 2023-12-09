===========================Installation Guide==========================
1. Extract the zip and save the folder anywhere (you can rename the folder) 
2. Create a shortcut to MSWatcher2.exe to Desktop etc. for easy access


===========================Quick Setup Guide===========================
1. [IMPORTANT] In config.ini check Core > Identifier and ensure that it is binded to you/your discord name
2. [IMPORTANT] If you want to use chat-to-text recognition you must download and install tesseract from https://github.com/UB-Mannheim/tesseract/wiki
	a.	Otherwise you must turn off ChatRecognitionOCR. You can do so in config.ini > Toggle Functions > ChatRecognitionOCR > False
	b.	If ChatRecognitionOCR is turned off, an image of your chat window will be sent to discord instead
3. [IMPORTANT] If you want to use damage skin recognition you must either
	a.	Switch to Epic Lulz Kekeke (default damage skin configured) or
	b.	Replace ds.png in img folder by taking a screenshot of your attacks and cropping a small section and saving over ds.png. Use the bundled ds.png as reference
		i.	Damage skin and screenshot should be opaque
		ii.	Use damage skins without numbers, preferable with repetitive patterns 


==========================Operating MSWatcher==========================
1. Prepare Maplestory for scanning
	a. Minimap should be fully expanded and docked to the top-left corner
	b. Chat should be fully expanded and docked to the bottom-left corner (above "exp" of exp bar)
	c. All UI elements must remain fully visible (minimap, chat, buffs)
2. Run the executable MSWatcher2.exe as admin
	a. If Windows Defender SmartScreen pops up please click "More info" > "Run Anyway". This security message occurs because this exe is unsigned, only on first boot of new exe
	b. Please ensure that the maximized minimap is visible at all times as it can be blocked by UI elements, Maplestory server wide notice (black bar at top of screen) etc.
	c. Please ensure that the chat window is docked to the bottom left corner, right above the exp bar, fully visible and expanded. Recommeded to have a chat set-up that excludes system messages
3. Do not run multiple instances of MSWatcher as this will cause repeated alerts
4. MSWatcher2 will perform a path checks and set-up before starting initial scan, you can minimize MSWatcher. Once started, you will be notified on Discord that the bot is running
5. Every 300 seconds, MSWatcher will send an alert to your discord channel to say that it is running normally, you can toggle or disable this in config.ini
6. If you are in Town or minimap is blocked, scans will pause for 15s. Simply go back to a training map and it will start again
7. Logs are captured for both alerts and errors in log.txt. You can disable this in config.ini
8. See <Notes on Discord> section beloow if facing issues with alerts


==============================Fixed Scans==============================
1. [CharacterInTown] - Checks if character is in town by looking for the quick move icon (mandatory) or npc icons (optional)
2. [MaplestoryDC] - Checks if 1 of 4 known DC screens are detected
3. [LieDetectorFailed] - Checks if the lie detector failed scan is detected
4. [ChatDetection] - Checks if white colored all chat or white colored GM chat is detected.
	a. ChatRecognitionOCR - If disabled, will send an image of the chat window to discord
	b. If enabled, will attempt to recognise the text and send the plain text to discord (tesseract mandatory)
5. [Mushbuff] - Checks if EXP 50% Buff (i.e. Mushbuff) if present on screen, and alert if exp buff icon missing. Needs both images to work properly
6. [CharacterStationary] - Check if character hasn't moved for x seconds based on threshold


========================Prebuilt Extendable Scans=======================
1. [CharacterDead] - Checks if character is dead. Will attempt to trigger auto-revive if auto-revive is enabled
2. [Stranger]/[Friend]/[Guildmate] - Checks if the player icon of the corresponding color is present on minimap
3. [Rune]/[Cursed Rune] - Checks if a rune or cursed rune has appeared
4. [ViolettaLieDetector] - Checks if violetta lie detector minigame has appeared
5. [NoDamageNumbers] - Checks if damage numbers are on the screen and alert when no damage numbers seen (Invert = True)


===========================Advanced Options=============================
1. This section provides further information on how to tailor MSWatcher2 to your specific preferences
2. Update ImgRootDirectoryOverride in the config.ini file if img folder path is different from the original. The default is the same folder as MSWatcher2.exe
3. Update other config in the config.ini file to modify alert delay, cooldown, alert message etc.
    a. All numerical values denote time in seconds
		i. [ScanInterval] is the delay in seconds between each time MSWatcher runs all the scans. Set to 0 for fastest, increase as needed to reduce load on cpu (default: 0)
		ii. [NormalOperationAlertInterval] MSWatcher will send a ping to discord in a regular interval (in seconds) to show that it is still running even if there are not alerts (default: 300)
		iii. [AlertCooldown] is the interval in seconds before MSWatcher tries to send the same alert again. This is to prevent being spammed on discord for the same alert. (default: 60)
    b. In fixed and extendable scan, all values must be enclosed in double quotes
		i.[Toggle] denotes whether a function is turned on or off. Set to "True" to turn on, "False" to turn off
    	ii.[ImgName] denotes name of the reference image. It must be exactly the same including file extension (.png) and they must be in the img folder
		ii. [Threshold] denotes how long a detection must persist before an alert is sent. e.g. Threshold "0" -> alert immediately, Threshold "5" -> alert if detected for 5s continuously
		iv. [Invert] deonates whether you want to scan for the presence or absence of the reference image. "False" = alert when detected, "True" = alert when NOT detected
		v. [AlertMsg] is the alert text that will be sent to discord, which you can customise. No double quotes (") in text body. Any @ tags is also usable in discord, hence you can @everyone etc.
4. [ADVANCED] The MSWatcher2 engine is able to handle additional scans as long as they follow the format of extendable scans. 
	a.	Simply add the new target image into img folder and add another entry within the Extendable Scan section (1 dictionary per scan)
	b. Formatting must be exactly the same, please do not miss commas
5. [ADVANCED] If you are facing issues with specific scans, you can replace the assets in the img folder by taking and cropping a new screenshot and saving to png format. 


=========================Notes on Discord==============================
1. Discord has a setting that will disable notifications to mobile app if the desktop is being actively used
2. You can modify this setting by going into Discord > App Settings > Notifications > Push Notification Inactive Time-out
3. Set this value to the minimum (i.e. 1 minute) in order to prevent the notification from being blocked
4. Discord may still sometimes block notifications, in such cases, add the @everyone tag in AlertMsg which will force discord to ping you
5. Otherwise, your phone/smartwatch may also have delayed notifications for discord which you may need to check
6. You can consider installing other discord specific bots to clean up your chat log periodically e.g. interpunct


========================Updating MSWatcher=============================
1. Existing features may be updated to broaden scan types, fix bugs or improve speed/accuracy.
2. New functions are also currently being worked on e.g. auto gotomap
3. Feature updates are free and optional. MSWatcher is backwards compatible as long as your unique identifier (in config.ini) is intact.
4. To update MSWatcher, download the new MSWatcher.exe provided and replace the existing MSWatcher.exe, config.ini does not need to be changed unless otherwise stated
5. Please ensure that the version number is higher or equal, downgrading can break MSWatcher.exe


======================Frequently Asked Questions=======================
Q:	My discord notifications are late, sometimes by a few minutes
A:	See "Notes on Discord" above

Q:	Chat detection false positive or false negatives
A:	Check chat.png and chatmask.png in the same folder as MSWatcher2.exe, is it capturing the correct area?
	Please ensure that the chat window is docked to the bottom left most corner, right above "exp"
	Mouse cursor in that area can cause false positives
	If too little text is sent it might not be detected (threshold is approx 6 characters including ign)

Q:	Chat detection text inaccurate
A:	Chat detection relies on real OCR which means there may be slight variation in results from time to time
	Chat detection is meant to help ascertain whether you should personally go check on your game and will not be 100% correct always

Q:	The console is not showing an alert even though it is present on my game
A:	Please ensure all UI element (e.g. Minimap, chat bar) are fully visible
	If still having issues, you can consider updating the assets in the img folder by taking new screenshots

Q:	The console is showing that MSWatcher is sending an alert but I am not receiving it in Discord
A:	Please ensure that your Identifier (in config.ini) is correct

Q:	I am getting alerts for no damage numbers even though I can see them on my screen
A:	Please ensure that ds.png in img folder has been updated according to the guidelines in the <Initial Setup> section above

Q:	Can MSWatcher be used in a virtual environment (HyperV, VMWare, VirtualBox)
A:	Yes, MSWatcher can be installed in either host or vm. If installed and operated from host, VM with MapleStory must be fully visible

Q:	Auto-login and auto2fa not working
A:	Ensure that MSWatcher2.exe is started as an admin. Ensure that usercredentials.ini is properly populated

Q:	Is running in admin mandatory
A:	Most scanning functions should still work without admin. Input assist may break