# BL2 AutoexecDLL

# Installation:
- Manually renaming :
    In your "Borderlands 2\Binaries\Win32"-folder find your current "steam_api.dll".
    Rename it to "steam_api_org.dll". Seems to be case sensitive, so double check. Then copy one of the included "steam_api.dll"'s into that folder, depending on what features you want.

Different features in different versions:
- "AutoexecAndGravityMode"    : Has both Autoexec and the Random Gravity-Mode
- "NoAutoexecNoGravityMode"   : Neither Autoexec, nor Random Gravity
- "NoAutoexecWithGravityMode" : No Autoexec but Random Gravity
- "AutoexecNoGravityMode"     : Autoexec but no Random Gravity

!!! All versions have the F8-Hotkey to "exec Patch.txt" !!!

# Current Features:
- Autoexec (with skipping Autoexec via. CTRL)
- Random Gravity-Mode

## Autoexec:
This is finally some kind of "real" autoexec. No longer simulated simulated keyboard inputs. Rather the games own function is being called with proper parameters.

You also have the option to skip the autoexec by holding CTRL on the screen "Press any key".
Hold CTRL here, then press any other key and keep holding CTRL. Once the game reports back that you are in the "Main Menu", and you're holding CTRL, it'll tell you that execution has been skipped.

Currently a hardcoded hotkey is also implemented to execute "Patch.txt". Simply have the game in the Foreground and press F8. You should see a message in the game chat.

* Notes:
- Unlike executing the patch manually, you'll not see any kind of response if you open the console after executing the patch. (Yet?)
- However, should there be an issue, like File wasn't found, it'll still tell you in the Console.

## Random Gravity-Mode:
This will randomize the gravity in random intervals (2-10 seconds).
Tweaking the range of the random gravity is most likely still needed.

To start this mode, Press CTRL+F9. You should now see a message in the In-Game-Chat.
To disable this mode again, press CTRL+F10. Sometimes you need to hold this combo for like a second. You'll see a message that the mode will be disabled and shortly after you should see a message that the mode has been disabled.


# Known Issues:
- When skipping/applying the autoexec or enabling the Random Gravity-Mode, the game might crash. Not too sure why yet. Simply restart the game and try again.

## Not tested:
- How and if it works in multiplayer (Random Gravity)

## Expect:
- Autoexec or (bypassing autoexec)
- Random Gravity (if you select a version that contains this feature)
- Probably a crash at some point ¯\_(ツ)_/¯

# Credits:
- c0dycode
- TheFeckless: For his awesome SDK-Generator and tutorial
- Warranty Voider: For his "Proxy DLL Maker"