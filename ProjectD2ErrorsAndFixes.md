# How to Fix The "armor.bin"/Gateway/Patching Failed/Updater Failed/Missing Resolution/Weird Inventory/Wrong Account Name/Wrong Password Error in Project Diablo 2.

### The reason this happens is because `ProjectDiablo.dll` fails to load. When this fails to load, Diablo 2 tries to automatically patch to 1.14d when the game loads. Since we are playing on a mod, we do not want this. Diablo 2 fails to update because its modded, which leaves the game in a corrupted state.
### The way to determine the reason why your `ProjectDiablo.dll` fails to load is as follows:

#### Check your `ProjectD2` folder inside your `Diablo II` folder. If `ProjectDiablo.dll`, then it's failing to load. If `ProjectDiablo.dll` is NOT there, that means your anti-virus is quarantining it. So far, Windows Defender, McAfee, and Bitdefender have also been known to quarantine the file.
#### If the file is there, you are likely missing the redistributables.
#### If your game worked previously but doesn't now and the file is missing, Windows Defender is catching something new they added which flags more than just `ProjectDiablo.dll` it seems.

## If `ProjectDiablo.dll` is there:

1. **99% of the time, you're missing the Redistributables needed.**
	- You can obtain them [here](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads). You need the x86 and x64 links under 2015/2017/2019.
		- You can find the direct links [here](https://aka.ms/vs/16/release/vc_redist.x86.exe) and [here](https://aka.ms/vs/16/release/vc_redist.x64.exe).
			- Yes, you need both.
2. **On the chance that it is the 1%, try installing outside of the Program Files folder or running the launcher in Administrator.**

## If `ProjectDiablo.dll` is *NOT* there:

1. **If the game worked before, PD2 team released a patch that Windows Defender now flags. Disable Windows Defender real-time scanning.**
	1. Go to Start Menu > Settings > Update & Security > Windows Security.
	2. Click on Virus & threat protection.
	3. Under 'Protection history', find `ProjectDiablo.dll` and restore it and allow it.
		- You will have to do this every time ProjectD2 updates most likely.
	4. The BEST fix is to add your Diablo 2 folder to the Exclusions folder for Windows Defender after performing Step 3. This will ensure you do not have to do this fix every time PD2 updates.
2. **If the game working before doesn't apply to you, start with Step 1. anyway.**
3. **Check your own anti-virus for quarantines. Make sure you restore the `ProjectDiablo.dll` file similarly to how Step 1. describes.**
4. **You could just disable your anti-virus outright (real-time protection). This does not always work though which is why Step 3. is recommended.**

# How to Fix the "d2data.mpq" Error in ProjectD2

### The reason this happens is because downgrading from 1.14 is finnicky and the MPQFixer doesn't work for all people. The solution is to go to the source and get the original MPQs from the older installers. Install Diablo 2 using the provided legacy installer links and install PD2 into the new install.
- [Mega.nz](https://mega.nz/#!e9thyD6A!ExGJuZUtvRJ2c8DrxSL0ihCouh-ARbdVxODXIqVt3dc)
- [Google Drive](https://drive.google.com/file/d/0BwtmRlAuN2x8X2FoWmhoR2pWQ2s/view)
- [OneDrive](https://onedrive.live.com/redir?resid=C9512C8BBA34920C!1795&authkey=!AHKYNghIssoWWVs&ithint=file%2czip)
- [Mediafire](http://www.mediafire.com/file/51r3c5s6hezsruz/DiabloII_113c_Installer.zip/file)
- [Torrent](https://cdn.discordapp.com/attachments/157962768534863872/160784109642186753/DiabloII_113c_Installer.zip.torrent)

# How to Fix the c0000005 Error in ProjectD2

## Context: You press `Play` on the Launcher and you receive the error.

### Possibility 1: Compatibility

#### Sometimes Diablo 2 just isn't nice, especially if you're installing into a Diablo 2 version that is lower than 1.14.

1. For `Game.exe` in the `ProjectD2` folder, go to its properties and set the compatibility mode to `Windows XP SP2` or `Windows XP SP3`.
2. For both `Game.exe` and `PD2Launcher.exe` in the `ProjectD2` folder, go to their properties and set both of them to `Run as admininstrator`.

### Possibility 2: DEP

#### I don't know the technicalities behind it, but some people need to perform the "DEP" fix.

1. **Go to your Start Menu and simply start typing `Control Panel` and click it.**
2. **Click `System`.**
3. **Click `Advanced system settings` on the left menu.**
4. **Under the `Advanced` tab, under the `Performance` section, click `Settings`.**
5. **Click the `Data Execution Prevention` (DEP) tab.**
6. **Click `Turn on DEP for essential Windows programs and services only`.**
7. **Restart your PC.**

### Possibility 3: Cinematics Bug

#### PD2 reintroduced the old Cinematics bug where if your game client has no sound (usually through `-ns`), you crash on cinematics, including the intro cinematics.

1. **If you do not have sound, get sound.**
2. **If you do have sound, try [this fix](https://www.indirectsound.com/). Place the sound dll into both your `Diablo II` and `ProjectD2` folders because I do not know which one is read from and I'm too lazy to figure it out.**

### Possibility 4: Missing Dependency

#### I have yet to figure out what makes this bug. Typically, it is either some form of corruption or missing a required library that is not listed anywhere.

1. **Try repairing the launcher by installing again and repairing.**
2. **Try making sure your Windows is up to date with everything a computer generally needs.**
	1. [.NET Framework 3.5](https://docs.microsoft.com/en-us/dotnet/framework/install/dotnet-35-windows-10) and [.NET Framework 4.8](https://dotnet.microsoft.com/download/dotnet-framework/net48)
	2. [As many Redistributables as you can](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads). Both x86 and x64 versions.
	3. Make sure Windows is up-to-date.
	4. Update your drivers, especially your audio and video card drivers.

## Context: You travel to a new Act in-game.

### Almost always because of -ns. See [here]().

## Context: Hovering over item or skill descriptions.

### You have a non-English Diablo II installation. Must be English Diablo II. Or your game is corrupted, re-install.

## Context: Killed Ventar the Unholy in Baal's fourth wave.

### I have yet to figure out why this happens. Other fixes have not seemed to help this issue. Usually not related to language or locale. Perhaps an issue with non-English Windows? Issue not solved, sorry.

# How to Fix the Halt Error in ProjectD2

## Context: Existing character joins the game.

- If you are able to create a new character and join a game but cannot join a game with an existing character because your game crashes with a Halt error, your character may have been corrupted somehow. This is not proven, waiting may simply fix it. I would be worried though, especially if it's online.
- If creating a new character still gives you a Halt error, then you likely have a bad install.
	- Be sure your game is a completely fresh install. You cannot copy and paste. You cannot re-use files from a previously modded install. Install Diablo II and then LOD and then PD2 all into the same folder.
