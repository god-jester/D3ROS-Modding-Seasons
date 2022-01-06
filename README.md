[//]: # (Fuck you D-R-A-S-T-I-C: liar, drama queen, exhaustingly verbose, condescending, elitist piece of shit)
[//]: # (Fuck you TnuC_INC: jealous, angry, petty, drug addict. and you're slow af)
[//]: # (Fuck you VXDeviLsSonXV: thief, liar, leech, clout chaser, borderline talentless, drug addicted divorcee)
[//]: # (All of you nerds have been sweating over this shit for "7+ years." I did it better and faster, and you will not regain the #1 spots)

# Diablo III (ROS) - Seasonal PS4 Modding

This guide aims to provide concise, accurate instructions to use publicly available homebrew and PC tools to bring edited saves into season 25 and beyond on PS4.

Weeks after I first jumped on the leaderboards with fully modified gear and ethereal weapons (Aug 11th 2021), a group of people cropped up claiming to have been doing this for years; allegedly sneaking "legit" gear and stat mods into seasons after Save Wizard removed Advanced Mode support for the game... pretending that they were protecting the integrity of seasonal play.

***This is called "closet cheating"*** - skipping the work of grinding the season while pretending you worked for it - and it's something I am firmly against. Go big or go home!

In this guide I will show you step-by-step what I did and which tools and information I used.

### Contact Me

* **Discord Server:**   **http://jester.dev**
* **My Discord:**   **jester#0001**
* **PSN:**   **jesterSellsSaves**
* **Email:**   [diablo@jester.dev](mailto:diablo@jester.dev)
  
### Special Thanks
* Thank you to **EckoTc** for sharing your experience and resources with me a few days after I picked up the game and pieced everything together. Cheers for reaching out and collaborating with me and the many other modders you've helped!
* Thank you to **goobycorp aka Visual Studio** for creating D3Edit, STL/GAM parsing tools, CPK extraction, and much more. You've been the homie for many years and I will always appreciate the knowledge you share 
* Thank you to **Tonic-Box** for compiling the most complete set of resources and guides that I stumbled upon when first looking into this stuff
  * I religiously read his excellent [D3ROS Modding Guide](https://github.com/Tonic-Box/D3ROS-Modding-Guide), and I suggest you do the same. Specifically his [full list of editor tricks](https://github.com/Tonic-Box/D3ROS-Modding-Guide/tree/main/EditorTricks) without any fluff

Listed and credited in his guide are all significant current and past contributors to the D3 modding community, so I will not repeat them all here. Visit his guide and read it over thoroughly, especially if you are not already familiar with save editing and the related concepts.

## Required Hardware
- [x] Working PC (Windows) to run the required tools
- [x] "**Console A**" - unmodified PS4/PS5 fully updated and able to play Diablo 3 online
- [x] Disc copy of Diablo 3 for PS4. This is for **Console B**, you may use a digital copy for **Console A** if you wish
- [x] USB drive (ideally exFAT formatted) for copying saves between your PC, **Console A**, and **Console B**
- [x] "**Console B**" - modifiable PS4 console ready to launch payloads
* The most convenient way to launch payloads on **Console B** is to visit public exploit hosts through the PS4 web browser on a vulnerable firmware: 
  * [hippie68](https://hippie68.github.io/): The cleanest and most professional public host (in my opinion). Supports multiple payloads at once
  * [Night King](https://night-king-host.github.io/): Very comprehensive and very frequently updated. Has the ctn123-updated PS4Debug (not necessary, but very good)
  * [Al-Azif](https://cthugha.exploit.menu/): The most well-known host that has accompanying DNS servers to auto-redirect your browser. Extremely comprehensive and even includes Switch and WiiU exploits!

## Required Software
- [x] [D3StudioFork - A save editor for Diablo 3 RoS/Eternal](https://github.com/god-jester/D3StudioFork/releases/latest) by me
- [x] [PS4 Save Mounter](https://github.com/ctn123/Binary-Releases/releases/latest) by ChendoChap, updated by Joonie86 and ctn123
- [x] PC FTP client: I love both [FileZilla](https://filezilla-project.org/download.php?show_all=1) and [WinSCP](https://winscp.net/eng/download.php)
- [x] Both of the following payloads running on **Console B**:
  * Persistent FTP: I use and love **GoldHEN v1.1 by [SiSTR0](https://github.com/SiSTR0/SiSTR0)**, but other persistent FTP servers will work fine
  * **PS4Debug** by jogolden, updated by GiantPluto and Joonie86: I prefer the recently updated **v1.5.4.4 by ctn**, but any working version will be fine

## Decrypt your Diablo 3 save to use with D3 Studio
### If you DON'T already have a Diablo save on **Console B**:
1. Insert Diablo 3 disc into **Console B** and launch the game
2. Create a character and complete the first area to open Tristram gates, which will grant enough EXP to hit level 2
3. Pause and quit game, back out to title screen, and close application
4. You now have a valid save and hero file, proceed to the following section

### If you DO have an existing Diablo save on **Console B**:
1. On your PC, create a folder for your decrypted save, we will name ours `PS4Save`
2. Launch PS4 Save Mounter, input **Console B** LAN IP, press Connect, press Patch, press Get Users, press Get Games, select Diablo from dropdown (probably `CUSA00242` for USA RoS disc), press Search, press Mount
3. Open FTP client on your PC, connect to **Console B** LAN IP and port (the GoldHEN default FTP port is `2121`), navigate to `/mnt/pfs/savedata_xxxxxxxx_CUSAxxxx_autosave`
4. Download to your `PS4Save` folder the following items: `heroes` folder, `account.dat`, `profile.dat`, and `prefs.dat`
      * **NOTE: If it exists, ignore the `sce_sys` folder completely, do not modify/delete/replace it!**
5. Press Unmount in PS4 Save Mounter
6. Congrats, you now have a decrypted copy of your save, ready to open and modify with D3 Studio!

## Convert your character to Seasonal
1. [Download D3StudioFork](https://github.com/god-jester/D3StudioFork/releases/) and extract to a folder, we will name ours `D3S`
2. [Download the newest Affix_List.txt and GBID_List.txt](https://github.com/god-jester/D3ROS-Modding-Seasons/tree/main/D3Studio%20Lists) from my github and replace the existing files inside `D3S` folder
3. Launch `D3Studio - v3.5.exe`, press open save, and navigate to your `PS4Save` folder. Select `account.dat` and press Open. This can take an extremely long time to load with larger saves and more characters
4. Press the `Account` tab, press the `Raw` tab, expand `console_data` and change `version_required` to **271**, expand `digest` and change `season_id` to **25**
      <details>
      <summary><sub>Screenshot: Account > Raw</sub></summary>
        <img src="https://user-images.githubusercontent.com/90997402/134083334-cb60c1dd-04c0-4a19-96c7-9f5d5da7f552.png">
      </details>
      
5. Press the `Heroes` tab, press the tab with your character name, press the `Raw` tab, expand `digest` and set `season_created` to **25**
      <details>
      <summary><sub>Screenshot: Heroes > jester's Wiz > Raw</sub></summary>
      <img src="https://user-images.githubusercontent.com/90997402/134083370-4d13d12a-d1de-42d4-8558-7ff03e6b0084.png">
      </details>
      
6. Press `Save All` in the top left. Congrats! You have just converted a brand new offline character from RoS Disc v1.00 to a Season 25 online hero!
      
**DISCLAIMER: There are random tutorials in the wild suggesting you need to change many more values in the save. This is not true, the above is all that is required!**



## Inject and export your modified PS4 save
1. Make sure you have an existing Diablo save in your PS4 System Storage. If not, read the section: ***"If you DON'T already have a Diablo save on Console B"***
2. Launch PS4 Save Mounter, input **Console B** LAN IP, press Connect, press Patch, press Get Users, press Get Games, select Diablo from dropdown (probably `CUSA00242` for USA RoS disc), press Search, press Mount
3. Open FTP client on your PC, connect to **Console B** LAN IP and port (the GoldHEN default FTP port is `2121`), navigate to `/mnt/pfs/savedata_xxxxxxxx_CUSAxxxx_autosave`
4. Upload from your `PS4Save` folder the following items: `heroes` folder, `account.dat`, `profile.dat`, and `prefs.dat`
      * **NOTE: If it exists, ignore the `sce_sys` folder completely, do not modify/delete/replace it!**
5. Press Unmount in PS4 Save Mounter
9. Plug USB drive into **Console B**, and copy your modded Diablo save from **System Storage** to **USB Storage Device**

<hr>

### And that's it! These are the steps I used in early August when I did all of this myself for the first time.
### Happy Modding!

[//]: # (account_raw https://user-images.githubusercontent.com/90997402/134083334-cb60c1dd-04c0-4a19-96c7-9f5d5da7f552.png)
[//]: # (heroes_general https://user-images.githubusercontent.com/90997402/134083356-75063f32-0f8e-4baf-be5e-0ab1dcca930a.png)
[//]: # (heroes_raw https://user-images.githubusercontent.com/90997402/134083370-4d13d12a-d1de-42d4-8558-7ff03e6b0084.png)
