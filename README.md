# If you appreciate my work, you can [PayPal Donate](https://paypal.me/Harry0215?locale.x=zh_TW) me.
> Click [Code->Download Zip](https://github.com/fbef0102/L4D2-Server4Dead/archive/refs/heads/main.zip) to download package
# Linux Server Files/Windows Server Files
* Main
	* **[SourceMod](https://www.sourcemod.net/downloads.php?branch=1.11)**
		* **v1.11-git6968** by AlliedModders LLC	
	
	* **[MetaMod](https://www.sourcemm.net/downloads.php?branch=1.11)**
		* **v1.11-git1155** by AlliedModders LLC
	
	* **[stripper](https://www.bailopan.net/stripper/snapshots/1.2/)** - Add, filter and modify map entities
		* **v1.2.2-git141** by BAILOPAN - Modify Map
	
	* **[l4dtoolz](https://github.com/fbef0102/l4dtoolz/releases)** - Unlock Server Slot Limit
		* **v1.1.0.2** by ivailosp、Accelerator74
	
	* **[Tickrate Enabler](https://github.com/fbef0102/Tickrate-Enabler/releases)** - Unlock Tickrate
		* **v1.6** by ProdigySim、Spirit_12、Accelerator74、Forgetest
	
	* **[pounce_damage_uncap](https://github.com/accelerator74/Pounce-Damage-Uncap/actions)** - Unlock Hunter Pounce Damage
		* **v1.1.0.0** by Spirit_12 & Accelerator74

* Extenstion
	* **[builtinvotes](https://github.com/L4D-Community/builtinvotes/actions)** - Let plugins use the L4D/L4D2/TF2 built-in vote screens.
		* **v0.7.0** by Powerlord, A1mDev
	
	* **[sourcescramble](https://github.com/nosoop/SMExt-SourceScramble/releases)** - memory patches & allocate memory
		* **v0.7.1.4** by nosoop
	
	* **[REST in Pawn](https://github.com/ErikMinekus/sm-ripext/releases)** - Provides HTTP and JSON natives for plugins
		* **v1.3.1** by ErikMinekus
	
	* **[SteamWorks](https://github.com/hexa-core-eu/SteamWorks/releases)** - Exposes SteamWorks functions to Developers
		* **v1.2.4** by KyleS & hexa-core-eu
	
	* **[Actions](https://forums.alliedmods.net/showthread.php?t=336374)** - Extension provides a natives to hook action event handlers and create custom actions
		* **v3.8.8** by BHaType

	* **[Resolve Collision](https://forums.alliedmods.net/showthread.php?t=344019)** - Fixes longstanding issues with low nb_update_frequency
		* **1.10.1** by BHaType

	* **CollisionHooks** - Provides a straightforward and easy way to hook and modify collision rules between entities.
		* **v1.3** by [VoiDeD](https://github.com/voided/CollisionHook)、[Spirit_12](https://github.com/Satanic-Spirit/Collisionhook)、[A1mDev](https://github.com/L4D-Community/Collisionhook)

* Extra File
	* **[GeoLite2-City](https://www.maxmind.com/en/home)** - addons\sourcemod\configs\geoip\GeoLite2-City.mmdb
		* **2024-05-14** by MAXMIND.com
	
	* **[GeoLite2-Country](https://www.maxmind.com/en/home)** - addons\sourcemod\configs\geoip\GeoLite2-Country.mmdb
		* **2024-05-14** by MAXMIND.com

# Server Install
* **Step 1:** A [clean L4D2 Dedicated Server](#how-to-download-l4d2-dedicated-server-files).

* **Step 2:** Choose "Windows Server files" or "Linux Server files" (depending on the operating system of your server), and place the files provided in the correct folder.

* **Step 3:** Adjust your **server_rates.cfg** and **l4d2_resolve_collision.cfg** to match your server tickrate accordingly.  
	* For 100 Tickrate, you'd want these settings:
		1. ```cfg/server_rates.cfg```
			```php
			sm_cvar sv_minrate 				"100000" 	// tickrate * 1000
			sm_cvar sv_maxrate 				"100000" 	// tickrate * 1000
			sm_cvar sv_minupdaterate 		"101"	 	// tickrate +1
			sm_cvar sv_maxupdaterate 		"101"		// tickrate +1
			sm_cvar sv_mincmdrate 			"101"		// tickrate +1
			sm_cvar sv_maxcmdrate 			"101"		// tickrate +1
			sm_cvar net_splitpacket_maxrate "50000" 	// (tickrate÷2) * 1000
			sm_cvar fps_max					"0"
			```

		2. ```cfg/l4d2_resolve_collision.cfg```
			```php
			// Multiplier of commons collision force
			// 30tick = 0.65, 60tick = 0.15, 100tick = 0.05, 128tick = 0.04
			z_resolve_zombie_collision_multiplier "0.05"
			```
  

* **Step 4:** Change the Launch Parameters.
	```
	-console -game left4dead2 -port 27016 +log on +map c2m1_highway +exec server +sv_lan 0 -tickrate 100 -maxplayers 31
	```

# How to download L4D2 Dedicated Server files:
* **Step 1:** [Download steamcmd](https://developer.valvesoftware.com/wiki/SteamCMD#Downloading_SteamCMD).

* **Step 2:** Launch steamcmd, steamcmd would automatically download required files .

* **Step 3:** After it says "Loading Steam API...OK.", type
	* ```force_install_dir ./l4d2/```
	* ```login anonymous```
	* ```app_update 222860 validate```

* **Step 4:** Finish downloading and close steamcmd.
	* ```exit```

* **Step 5 (Linux Only):** Dependencies ([Source](https://linuxgsm.com/servers/l4d2server/))
	* Ubuntu =< 20.04
		```
		sudo dpkg --add-architecture i386; sudo apt update; sudo apt install curl wget file tar bzip2 gzip unzip bsdmainutils python3 util-linux ca-certificates binutils bc jq tmux netcat lib32gcc1 lib32stdc++6 libsdl2-2.0-0:i386 steamcmd
		sudo apt install lib32z1
		```
	* Ubuntu => 20.10
		```
		sudo dpkg --add-architecture i386; sudo apt update; sudo apt install curl wget file tar bzip2 gzip unzip bsdmainutils python3 util-linux ca-certificates binutils bc jq tmux netcat lib32gcc1 lib32stdc++6 libsdl2-2.0-0:i386 steamcmd
		sudo apt install lib32z1
		```
	* Debian =< 10
		```
		sudo dpkg --add-architecture i386; sudo apt update; sudo apt install curl wget file tar bzip2 gzip unzip bsdmainutils python3 util-linux ca-certificates binutils bc jq tmux netcat lib32gcc1 lib32stdc++6
		sudo apt-get install zlib1g
		```
	* Debian => 11
		```
		sudo dpkg --add-architecture i386; sudo apt update; sudo apt install curl wget file tar bzip2 gzip unzip bsdmainutils python3 util-linux ca-certificates binutils bc jq tmux netcat lib32gcc-s1 lib32stdc++6
		sudo apt-get install zlib1g
		```
	* CentOS
		```
		yum install epel-release
		yum install curl wget tar bzip2 gzip unzip python3 binutils bc jq tmux glibc.i686 libstdc++ libstdc++.i686
		yum install zlib.i686
		```
# Optional Files
* Extension
	* **[cutlrbtreefix](https://github.com/fdxx/cutlrbtreefix/releases)** - Fixed server crash "CUtlRBTree overflow"
		* **v0.3** by fdxx
		
	* **[Accelerator](https://forums.alliedmods.net/showthread.php?t=277703)** - Crash Reporting That Doesn't Suck
		* **v2.5.0-cd575aa** by asherkin
		* 🟥 In Linux system, does not work if install this extension with **builtinvotes** and **CollisionHooks**

# Others
* <b>[L4D1-Server4Dead](https://github.com/fbef0102/L4D1-Server4Dead)</b>: Setup your own L4D1 Servers.
* <b>[L4D1_2-Plugins](https://github.com/fbef0102/L4D1_2-Plugins)</b>: L4D1/2 general purpose and freaky-fun plugins.
* <b>[L4D2-Plugins](https://github.com/fbef0102/L4D2-Plugins)</b>: L4D2 Competitive enhancement, bug/glitch fixes, general purpose and freaky-fun plugins.
* <b>[Game-Private_Plugin](https://github.com/fbef0102/Game-Private_Plugin)</b>: Private Plugin List.
