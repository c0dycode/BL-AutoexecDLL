# Requirements:
- Borderlands PluginLoader (already included in the zip-files) https://github.com/c0dycode/BorderlandsPluginLoader


# Installation:
- Download the zip-file suited for your game and put the ddraw.dll + Plugins-folder into the Win32-folder where youre games .exe-file is in. For example: C:\Steam\steamapps\common\Borderlands 2\Binaries\Win32

- create "autoexec.txt" in the Binaries-folder where your patch-file is in.

Make the "autoexec.txt" look like this:
```
Online=exec YourOnlineHotfixPatch.txt
Offline=exec YourOfflineHotfixPatch.txt
Fastmode=true
ForceOfflineHotfixes=false
```

You can leave out Online= and Offline= and just have "exec Patch.txt" in there aswell.

# Current Features:
- Autoexec (with skipping Autoexec via. CTRL)
- Notification whether the SparkService is initialized or not (Online hotfixes if yes and vice versa)
- Fastmode
- Force Offline Hotfixes

## Autoexec:
This is finally some kind of "real" autoexec. No longer simulated simulated keyboard inputs. Rather the games own function is being called with proper parameters.

You also have the option to skip the autoexec by holding CTRL on the screen "Press any key".
Hold CTRL here, then press any other key and keep holding CTRL. Once the game reports back that you are in the "Main Menu", and you're holding CTRL, it'll tell you that execution has been skipped.

Currently a hardcoded hotkey is also implemented to execute "autoexec.txt". Simply have the game in the Foreground and press F8. You should see a message in the game chat.

* Notes:
- Unlike executing the patch manually, you'll not see any kind of response if you open the console after executing the patch. (Yet?)
- However, should there be an issue, like File wasn't found, it'll still tell you in the Console.

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
- Removed old versions and switched to the Plugin-version by default now
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
- There's a chance of the game crashing when you reach the main menu every once in a blue moon. Should be very very very rare though
- You tell me :P

## Not tested:

## Expect:
- Autoexec or (bypassing autoexec)
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
