[//]: # (Fuck you D-R-A-S-T-I-C: liar, drama queen, exhaustingly verbose, condescending, elitist piece of shit)
[//]: # (Fuck you TnuC_INC: jealous, angry, petty, drug addict. and you're slow af)
[//]: # (Fuck you VXDeviLsSonXV: thief, liar, leech, clout chaser, borderline talentless, drug addicted divorcee)
[//]: # (All of you nerds have been sweating over this shit for years. I did it better and faster, and you will not regain the #1 spots.)

# Diablo III (ROS) - Seasonal PS4 Modding

This guide aims to provide concise, accurate instructions to use publicly available homebrew and PC tools to bring edited saves into season 24 and beyond on PS4.

Weeks after I first jumped on the leaderboards with fully modified gear and ethereal weapons (Aug 11th 2021), a group of people cropped up claiming to have been doing this for years; allegedly sneaking "legit" gear and stat mods into seasons after Save Wizard removed Advanced Mode support for the game... pretending that they were protecting the integrity of seasonal play.

***This is called "closet cheating"*** - skipping the work of grinding the season while pretending you worked for it - and it's something I am firmly against. Go big or go home!

In this guide I will show you step-by-step what I did and which tools and information I used.

### Contact Me
* **Discord:** ***jester#0001***
* **PSN:** ***jesterSellsSaves***
* **Email:** [jester.psn@xbl.ninja](mailto:jester.psn@xbl.ninja)
  
### Special Thanks
* Thank you to **EckoTc** for sharing your experience and resources with me a few days after I picked up the game and pieced everything together. Cheers for reaching out and collaborating with me and the many other modders you've helped!
* Thank you to **goobycorp aka Visual Studio** for creating D3Edit, STL/GAM parsing tools, CPK extraction, and much more. You've been the homie for many years and I will always appreciate the knowledge you share 
* Thank you to **Tonic-Box** for compiling the most complete set of resources and guides that I stumbled upon when first looking into this stuff
  * I religiously read his excellent [D3ROS Modding Guide](https://github.com/Tonic-Box/D3ROS-Modding-Guide), and I suggest you do the same. Specifically his [full list of editor tricks](https://github.com/Tonic-Box/D3ROS-Modding-Guide/tree/main/EditorTricks) without any fluff

Listed and credited in his guide are all significant current and past contributors to the D3 modding community, so I will not repeat them all here. Visit his guide and read it over thoroughly, especially if you are not already familiar with save editing and the related concepts.

## Required Hardware
1. Working PC to run the required tools
2. "Console A" - Unmodified PS4/PS5 fully updated and able to play Diablo 3 online
3. Disc copy of Diablo 3 for PS4. This is for Console B, you may use a digital copy for Console A
4. USB drive (exFAT/FAT32) for copying saves between your PC, Console A, and Console B
5. "Console B" - Modifiable PS4 console ready to launch payloads
* The most convenient way to launch payloads on Console B is to visit public exploit hosts through the PS4 web browser on a vulnerable firmware: 
  * [hippie68](https://hippie68.github.io/): The cleanest and most professional public host (in my opinion)
  * [Night King](https://night-king-host.github.io/): The most comprehensive and very frequently updated. Has the ctn123 updated PS4Debug (not necessary, but very good)
  * [Al-Azif](https://cthugha.exploit.menu/): The most well-known host that has accompanying DNS servers to auto-redirect your browser. Very comprehensive and even includes Switch and WiiU exploits!

## Required Software
- [x] [D3 Studio - A save editor for Diablo 3 RoS/Eternal](https://github.com/Tonic-Box/D3Studio/releases/latest)
- [x] [PS4 Save Mounter by ChendoChap, updated by Joonie86 and ctn123](https://github.com/ctn123/Binary-Releases/releases/latest)
- [ ] ~~__*Spooky homebrew that will be shared later*__~~
- [x] PC FTP client: I love both [FileZilla](https://filezilla-project.org/download.php?show_all=1) and [WinSCP](https://winscp.net/eng/download.php)
- [x] Both of the following payloads running on Console B:
  * Persistent FTP: I use and love **GoldHEN v1.1 by SiSTR0**, but other persistent FTP servers will work fine
  * **PS4Debug** by jogolden, updated by GiantPluto and Joonie86: I prefer the recently updated **v1.5.4.4 by CTN**, but any working version will do

## Inject and export your modified PS4 save
1. Insert Diablo 3 disc into Console B and launch the game
2. Progress past the title screen and calibrate the gamma, close the game
3. Connect PS4 Save Mounter, input Console B LAN IP, click Connect, click Patch, click Get Users, click Get Games, select CUSA00242 from dropdown, press Search, press Mount
4. Open FTP client on PC, connect to Console B (default port is `2121`), navigate to `/mnt/pfs/savedata_xxxxxxxx_CUSA00242_autosave`
5. Copy your already-modded `heroes` folder, `account.dat`, `profile.dat`, `prefs.dat` files to this directory
6. Click Unmount in PS4 Save Mounter
7. Plug USB drive into Console B, Copy Diablo save from `System Storage` to `USB Storage Device`
- [ ] The full details of the rest of the steps will be posted Soon<sup>TM</sup>
  

<sub>I will be finishing this guide in the coming days</sub>
