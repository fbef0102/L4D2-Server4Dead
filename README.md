# If you appreciate my work, you can [PayPal Donate](https://paypal.me/Harry0215?locale.x=zh_TW) me.
> Click [Code->Download Zip](https://github.com/fbef0102/L4D2-Server4Dead/archive/refs/heads/main.zip) to download package
# Linux Server Files/Windows Server Files
* Main
	* <b>[SourceMod](https://www.sourcemod.net/downloads.php?branch=1.11-dev) 				1.11-git6905</b> 	    by AlliedModders LLC
	* <b>[MetaMod](https://www.sourcemm.net/downloads.php?branch=1.11-dev) 				1.11-git1148</b> 	    by AlliedModders LLC
	* <b>[stripper](https://www.bailopan.net/stripper/snapshots/1.2/) 				1.2.2-git129</b> 		by BAILOPAN - Modify Map
	* <b>[l4dtoolz](https://github.com/Accelerator74/l4dtoolz/releases) 				1.1.0.2</b> 		    by ivailosp、Accelerator74 - Unlock Server Slot Limit
	* <b>[Tickrate Enabler](https://github.com/accelerator74/Tickrate-Enabler/releases)		1.5</b> 	    		by ProdigySim、Spirit_12、Accelerator74 - Unlock Tickrate
	* <b>[pounce_damage_uncap](https://github.com/accelerator74/Pounce-Damage-Uncap/actions)	1.1.0.0</b> 	    	by Spirit_12 & Accelerator74 - Unlock Hunter Pounce Damage

* Extenstion
	* <b>l4d2_bugfixes 			1.0.2</b> 			by [V10](https://forums.alliedmods.net/showthread.php?t=121945), [windows](https://forums.alliedmods.net/showpost.php?p=2721138&postcount=295) by Spirit_12, [linux](https://forums.alliedmods.net/showpost.php?p=2752412&postcount=301) by SpaceWashingMachine - Fix bugs on server have more than 8 players
		* Survivor finale score bug when 5+ players
		* Charger stop bug when 5+ players
		* Witch incorrect player attack when 5+ players
	* <b>[geoipcity](https://forums.alliedmods.net/showthread.php?t=132470)				1.1.2</b>				by GoD-Tony - Get the city names from an IP address
	* <b>[voicehook](https://forums.alliedmods.net/showthread.php?t=279231)				3.0</b>				by Accelerator74 - The player who at the moment speak.
	* <b>[dosprotect](https://forums.alliedmods.net/showthread.php?t=196990)			1.0</b>					by Zephyrus - The player who at the moment speak.
	* <b>[builtinvotes](https://github.com/L4D-Community/builtinvotes/actions)			0.6.6</b>				by Powerlord, A1mDev - Let plugins use the L4D/L4D2/TF2 built-in vote screens.
	* <b>[sourcescramble](https://github.com/nosoop/SMExt-SourceScramble/releases)			0.7.1</b>				by nosoop - memory patches & allocate memory
	* <b>[REST in Pawn](https://github.com/ErikMinekus/sm-ripext/releases)			1.3.1</b>				by ErikMinekus - Provides HTTP and JSON natives for plugins
	* <b>[SteamWorks](https://github.com/hexa-core-eu/SteamWorks/releases)				1.2.3</b>				by KyleS & hexa-core-eu - Exposes SteamWorks functions to Developers
	* <b>[[L4D2] Actions](https://forums.alliedmods.net/showthread.php?p=2771953)				2.7</b>				by BHaType - Extension provides a natives to hook action event handlers and create custom actions
	* <b>CollisionHooks	 	0.2</b> 				by [VoiDeD](https://forums.alliedmods.net/showthread.php?t=197815)、[Spirit_12](https://github.com/Satanic-Spirit/Collisionhook)、[A1mDev](https://github.com/L4D-Community/Collisionhook/tree/fix-windows) - Provides a straightforward and easy way to hook and modify collision rules between entities.

# Server Install
**Step 1:** A [clean L4D2 Dedicated Server](https://github.com/fbef0102/L4D2-Server4Dead/blob/master/README.md#how-to-download-l4d2-dedicated-server-files).

**Step 2:** Choose "Windows Server files" or "Linux Server files" (depending on the operating system of your server), and place the files provided in the correct folder.

**Step 3:** Adjust your **server_rates.cfg** to match your rates accordingly.  
* For 100 Tickrate, you'd want these settings:
>sm_cvar sv_minrate 			"100000"

>sm_cvar sv_maxrate 			"100000"

>sm_cvar sv_minupdaterate 		"101"

>sm_cvar sv_maxupdaterate 		"101"

>sm_cvar sv_mincmdrate 			"101"

>sm_cvar sv_maxcmdrate 			"101"

>sm_cvar rate				"100000"

>sm_cvar net_splitpacket_maxrate "50000"

>sm_cvar fps_max    "0"


**Step 4:** Change the Launch Parameters.
  * -console -game left4dead2 -port 27016 +log on +map c2m1_highway +exec server +sv_lan 0 -tickrate 100

# How to download L4D2 Dedicated Server files:
**Step 1:** download [steamcmd](https://developer.valvesoftware.com/wiki/SteamCMD).

**Step 2:** launch steamcmd , steamcmd would automatically download required files .

**Step 3:** after it says "Loading Steam API...OK.", type
* force_install_dir ./l4d2/
* login anonymous
* app_update 222860 validate

**Step 4:** finish downloading and quit.


# Others
* <b>[L4D1-Server4Dead](https://github.com/fbef0102/L4D1-Server4Dead)</b>: Setup your own L4D1 Servers.
* <b>[L4D1_2-Plugins](https://github.com/fbef0102/L4D1_2-Plugins)</b>: L4D1/2 general purpose and freaky-fun plugins.
* <b>[L4D2-Plugins](https://github.com/fbef0102/L4D2-Plugins)</b>: L4D2 Competitive enhancement, bug/glitch fixes, general purpose and freaky-fun plugins.
* <b>[Game-Private_Plugin](https://github.com/fbef0102/Game-Private_Plugin)</b>: Private Plugin List.
