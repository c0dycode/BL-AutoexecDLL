# Warning:
The BL2 DLL-Autoexec.zip and BLTPS DLL-Autoexec.zip contain unstable versions and are considered "outdated". If you have issues with those, there's no need to contact me.

If you want to help me fix (mainly) crashes atm., use the PluginTestBL2.zip or PluginTestTPS.zip, depending on which game you use.

Instructions are in the included Readme.txt.

!READ IT! It's there for a reason!


# Installation:
- Manually renaming :
    In your "Borderlands 2\Binaries\Win32"-folder find your current "PhysXExtensions.dll".
    Rename it to "PhysXExtensions_org.dll" (exactly like that, because we're going to forward calls meant for that dll to it. It's also case sensitive, so double check.) 
    
    Then copy one of the included "PhysXExtensions.dll"'s into that folder, depending on what features you want.

- create "autoexec.txt" in the Binaries-folder where your patch-file is in and put "exec YOURPATCHFILENAME.txt" inside.

OPTIONAL:
Make the "autoexec.txt" look like this:
```
Online=exec YourOnlineHotfixPatch.txt
Offline=exec YourOfflineHotfixPatch.txt
Fastmode=true
```


Different features in different versions:

- "AutoexecAndGravityMode"       : Has both Autoexec and the Random Gravity-Mode
- "NoAutoexecNoGravityMode"      : Neither Autoexec, nor Random Gravity
- "NoAutoexecWithGravityMode"    : No Autoexec but Random Gravity
- "AutoexecNoGravityMode"        : Autoexec but no Random Gravity
- "AutoexecNoGravityModeOffline" : Auoexec, no gravity and forced Offline-Hotfixes

!!! All versions have the F8-Hotkey to "exec autoexec.txt" !!!

# Current Features:
- Autoexec (with skipping Autoexec via. CTRL)
- Random Gravity-Mode (only BL2)
- Notification whether the SparkService is initialized or not (Online hotfixes if yes and vice versa), if autoexec is skipped.
- Fastmode

## Autoexec:
This is finally some kind of "real" autoexec. No longer simulated simulated keyboard inputs. Rather the games own function is being called with proper parameters.

You also have the option to skip the autoexec by holding CTRL on the screen "Press any key".
Hold CTRL here, then press any other key and keep holding CTRL. Once the game reports back that you are in the "Main Menu", and you're holding CTRL, it'll tell you that execution has been skipped.

Currently a hardcoded hotkey is also implemented to execute "autoexec.txt". Simply have the game in the Foreground and press F8. You should see a message in the game chat.

* Notes:
- Unlike executing the patch manually, you'll not see any kind of response if you open the console after executing the patch. (Yet?)
- However, should there be an issue, like File wasn't found, it'll still tell you in the Console.

## Random Gravity-Mode (BL2 only):
This will randomize the gravity in random intervals (2-10 seconds).
Tweaking the range of the random gravity is most likely still needed.

To start this mode, Press CTRL+F9. You should now see a message in the In-Game-Chat.
To disable this mode again, press CTRL+F10. You'll see a message that the mode has been disabled.

## Fastmode: Skips the Loading screen before the "Press any key"-Menu and the "Press any key"-Menu itself.
For optimal results, skip the "2K", "Gearbox" and "NVidia"-logos manually as fast as you can, or disable them in "WillowEngine.ini".
You can find it here:
```
Documents\My Games\Borderlands 2\WillowGame\Config
```

Then look for
```
[FullScreenMovie]
bForceNoMovies=FALSE
StartupMovies=2K_logo
StartupMovies=Gearbox_logo
StartupMovies=NVidia
StartupMovies=Loading
```

and change it to

```
[FullScreenMovie]
bForceNoMovies=FALSE
StartupMovies=;2K_logo
StartupMovies=;Gearbox_logo
StartupMovies=;NVidia
StartupMovies=;Loading
```

# Changes (Most Recent at the Top)
- Switched from using steam_api.dll to PhysXExtensions.dll (fixes launching the game via steam)
- Should have fixed Status of the SparkService when skipping autoexec
- Hotkey-Exec now checks whether to exec the Offline or Online-Hotfix patch (setup autoexec.txt accordingly and make sure to convert Patchfiles to online/offline via FilterTool/BLCMM)
- Removed checking for Window-Titles, using the "HWND" stored by the game itself instead (should fix usage of multiple game instances)
- Added MessageBox in case the original steam_api.dll hasn't been renamed properly
- Added NoAutoexecNoGravityModeOffline
- Added Fastmode
- Added a version for forced offline Hotfixes
- Added configuration to allow execution of different files, depending on whether you can use online hotfixes or not
- Previous random crashes have been reduced by A LOT!
 
# Known Issues:
- You tell me :P

## Not tested:
- How and if it works in multiplayer (Random Gravity)

## Expect:
- Autoexec or (bypassing autoexec)
- Random Gravity (if you select a BL2 version that contains this feature)
- MAYBE a crash at some point

# Disclaimer
Obviously use at your own risk. It may cause a random gamecrash or similiar.

# Credits
- c0dycode

# Thanks
- TheFeckless
- Warranty Voider


# Support
If you enjoy my work and would like to support me, feel free to do so here :)

[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=CRVHLK9MURS9Q)
