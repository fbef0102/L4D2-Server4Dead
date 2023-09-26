# If you appreciate my work, you can [PayPal Donate](https://paypal.me/Harry0215?locale.x=zh_TW) me.
> Click [Code->Download Zip](https://github.com/fbef0102/L4D2-Server4Dead/archive/refs/heads/main.zip) to download package
# Linux Server Files/Windows Server Files
* Main
	* **[SourceMod](https://www.sourcemod.net/downloads.php?branch=1.11-dev)**
		* **v1.11-git6934** by AlliedModders LLC	
	
	* **[MetaMod](https://www.sourcemm.net/downloads.php?branch=1.11-dev)**
		* **v1.11-git1148** by AlliedModders LLC
	
	* **[stripper](https://www.bailopan.net/stripper/snapshots/1.2/)** - Add, filter and modify map entities
		* **v1.2.2-git141** by BAILOPAN - Modify Map
	
	* **[l4dtoolz](https://github.com/Accelerator74/l4dtoolz/releases)** - Unlock Server Slot Limit
		* **v1.1.0.2** by ivailosp、Accelerator74
	
	* **[Tickrate Enabler](https://github.com/accelerator74/Tickrate-Enabler/releases)** - Unlock Tickrate
		* **v1.5** by ProdigySim、Spirit_12、Accelerator74
	
	* **[pounce_damage_uncap](https://github.com/accelerator74/Pounce-Damage-Uncap/actions)** - Unlock Hunter Pounce Damage
		* **v1.1.0.0** by Spirit_12 & Accelerator74

* Extenstion
	* **l4d2_bugfixes** - Fix bugs on server have more than 8 players
		* **v1.0.2** by [V10](https://forums.alliedmods.net/showthread.php?t=121945)
		* **[windows](https://forums.alliedmods.net/showpost.php?p=2721138&postcount=295)** by Spirit_12, 
		* **[linux](https://forums.alliedmods.net/showpost.php?p=2752412&postcount=301)** by SpaceWashingMachine
			```php
			1. Survivor finale score bug when 5+ players
			2. Charger stop bug when 5+ players
			3. Witch incorrect player attack when 5+ players
			```
		
	* **DoS Protect** - Prevents and records attempted DoS (Denial-of-Service) attacks
		* **v1.1.0.0** by [Zephyrus](https://forums.alliedmods.net/showthread.php?t=196990)
		* **[windows](https://github.com/cravenge/DoS-Protect_SM)** by cravenge
			```php
			//print all logged attacks, the number of packets received and the time of the last one.
			dosp_attacks 
			```

	* **[builtinvotes](https://github.com/L4D-Community/builtinvotes/actions)** - Let plugins use the L4D/L4D2/TF2 built-in vote screens.
		* **v0.7.0** by Powerlord, A1mDev
	
	* **[sourcescramble](https://github.com/nosoop/SMExt-SourceScramble/releases)** - memory patches & allocate memory
		* **v0.7.1.1** by nosoop
	
	* **[REST in Pawn](https://github.com/ErikMinekus/sm-ripext/releases)** - Provides HTTP and JSON natives for plugins
		* **v1.3.1** by ErikMinekus
	
	* **[SteamWorks](https://github.com/hexa-core-eu/SteamWorks/releases)** - Exposes SteamWorks functions to Developers
		* **v1.2.4** by KyleS & hexa-core-eu
	
	* **[Actions](https://forums.alliedmods.net/showthread.php?t=336374)** - Extension provides a natives to hook action event handlers and create custom actions
		* **v3.5.1** by BHaType
	
	* **CollisionHooks** - Provides a straightforward and easy way to hook and modify collision rules between entities.
		* **v1.3** by [VoiDeD](https://forums.alliedmods.net/showthread.php?t=197815)、[Spirit_12](https://github.com/Satanic-Spirit/Collisionhook)、[A1mDev](https://github.com/L4D-Community/Collisionhook/actions)

* Extra File
	* **[GeoLite2-City](https://www.maxmind.com/en/home)** - addons\sourcemod\configs\geoip\GeoLite2-City.mmdb
		* **2023-05-19** by MAXMIND
	
	* **[GeoLite2-Country](https://www.maxmind.com/en/home)** - addons\sourcemod\configs\geoip\GeoLite2-Country.mmdb
		* **2023-05-19** by MAXMIND

# Server Install
* **Step 1:** A [clean L4D2 Dedicated Server](https://github.com/fbef0102/L4D2-Server4Dead/blob/master/README.md#how-to-download-l4d2-dedicated-server-files).

* **Step 2:** Choose "Windows Server files" or "Linux Server files" (depending on the operating system of your server), and place the files provided in the correct folder.

* **Step 3:** Adjust your **server_rates.cfg** to match your rates accordingly.  
	* For 100 Tickrate, you'd want these settings:
		```php
		sm_cvar sv_minrate 				"100000"
		sm_cvar sv_maxrate 				"100000"
		sm_cvar sv_minupdaterate 		"101"
		sm_cvar sv_maxupdaterate 		"101"
		sm_cvar sv_mincmdrate 			"101"
		sm_cvar sv_maxcmdrate 			"101"
		sm_cvar rate					"100000"
		sm_cvar net_splitpacket_maxrate "50000"
		sm_cvar fps_max    				"0"
		```

* **Step 4:** Change the Launch Parameters.
	```
	-console -game left4dead2 -port 27016 +log on +map c2m1_highway +exec server +sv_lan 0 -tickrate 100
	```

# How to download L4D2 Dedicated Server files:
* **Step 1:** Download [steamcmd](https://developer.valvesoftware.com/wiki/SteamCMD).

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
		```
	* Ubuntu => 20.10
		```
		sudo dpkg --add-architecture i386; sudo apt update; sudo apt install curl wget file tar bzip2 gzip unzip bsdmainutils python3 util-linux ca-certificates binutils bc jq tmux netcat lib32gcc1 lib32stdc++6 libsdl2-2.0-0:i386 steamcmd
		```
	* Debian =< 10
		```
		sudo dpkg --add-architecture i386; sudo apt update; sudo apt install curl wget file tar bzip2 gzip unzip bsdmainutils python3 util-linux ca-certificates binutils bc jq tmux netcat lib32gcc1 lib32stdc++6
		```
	* Debian => 11
		```
		sudo dpkg --add-architecture i386; sudo apt update; sudo apt install curl wget file tar bzip2 gzip unzip bsdmainutils python3 util-linux ca-certificates binutils bc jq tmux netcat lib32gcc-s1 lib32stdc++6
		```
	* CentOS
		```
		yum install epel-release
		yum install curl wget tar bzip2 gzip unzip python3 binutils bc jq tmux glibc.i686 libstdc++ libstdc++.i686
		```

# Others
* <b>[L4D1-Server4Dead](https://github.com/fbef0102/L4D1-Server4Dead)</b>: Setup your own L4D1 Servers.
* <b>[L4D1_2-Plugins](https://github.com/fbef0102/L4D1_2-Plugins)</b>: L4D1/2 general purpose and freaky-fun plugins.
* <b>[L4D2-Plugins](https://github.com/fbef0102/L4D2-Plugins)</b>: L4D2 Competitive enhancement, bug/glitch fixes, general purpose and freaky-fun plugins.
* <b>[Game-Private_Plugin](https://github.com/fbef0102/Game-Private_Plugin)</b>: Private Plugin List.
