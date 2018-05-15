# Installation:
- Manually renaming :
    In your "Borderlands 2\Binaries\Win32"-folder find your current "steam_api.dll".
    Rename it to "steam_api_org.dll". Seems to be case sensitive, so double check. Then copy one of the included "steam_api.dll"'s into that folder, depending on what features you want.

- create "autoexec.txt" in the Binaries-folder where your patch-file is in and put "exec YOURPATCHFILENAME.txt" inside.

Different features in different versions:

- "AutoexecAndGravityMode"    : Has both Autoexec and the Random Gravity-Mode
- "NoAutoexecNoGravityMode"   : Neither Autoexec, nor Random Gravity
- "NoAutoexecWithGravityMode" : No Autoexec but Random Gravity
- "AutoexecNoGravityMode"     : Autoexec but no Random Gravity


!!! All versions have the F8-Hotkey to "exec autoexec.txt" !!!

# Current Features:
- Autoexec (with skipping Autoexec via. CTRL)
- Random Gravity-Mode
- Notification whether the SparkService is initialized or not (Online hotfixes if yes and vice versa), if autoexec is skipped.

## Autoexec:
This is finally some kind of "real" autoexec. No longer simulated simulated keyboard inputs. Rather the games own function is being called with proper parameters.

You also have the option to skip the autoexec by holding CTRL on the screen "Press any key".
Hold CTRL here, then press any other key and keep holding CTRL. Once the game reports back that you are in the "Main Menu", and you're holding CTRL, it'll tell you that execution has been skipped.

Currently a hardcoded hotkey is also implemented to execute "autoexec.txt". Simply have the game in the Foreground and press F8. You should see a message in the game chat.

* Notes:
- Unlike executing the patch manually, you'll not see any kind of response if you open the console after executing the patch. (Yet?)
- However, should there be an issue, like File wasn't found, it'll still tell you in the Console.

## Random Gravity-Mode:
This will randomize the gravity in random intervals (2-10 seconds).
Tweaking the range of the random gravity is most likely still needed.

To start this mode, Press CTRL+F9. You should now see a message in the In-Game-Chat.
To disable this mode again, press CTRL+F10. You'll see a message that the mode has been disabled.


# Known Issues:
- Previous random crashes have been reduced by A LOT!

## Not tested:
- How and if it works in multiplayer (Random Gravity)

## Expect:
- Autoexec or (bypassing autoexec)
- Random Gravity (if you select a version that contains this feature)
- MAYBE a crash at some point

# Disclaimer
Obviously use at your own risk. It may cause a random gamecrash or similiar.

# Credits
- c0dycode

# Thanks
- TheFeckless
- Warranty Voider
