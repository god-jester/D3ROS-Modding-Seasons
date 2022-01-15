# Diablo III (ROS) - Seasonal PS4 Modding

This guide aims to provide concise, accurate instructions to use publicly available homebrew and PC tools to bring edited saves into Season 25 and beyond on PS4 and PS5. I put this all together and abused my first leaderboard on August 11, 2021

In this guide I will show you step-by-step what I did and which tools and information I used.

### Contact Me

* **Discord Server:**   **https://jester.dev**
* **My Discord:**   **jester#0001**
* **PSN:**   **jesterSellsSaves**
* **Email:**   [diablo@jester.dev](mailto:diablo@jester.dev)
  
## Required Hardware
- [x] Working Windows PC to run the required tools
- [x] USB drive for copying saves between consoles, with an existing Season 25 save copied to it
- [x] "**Console A**" - unmodified PS4/PS5 fully updated and able to play Diablo 3 online
- [x] "**Console B**" - modifiable PS4 console on FW 9.00

## Required Software
- [x] [D3StudioFork - A Diablo 3 Save Editor](https://github.com/god-jester/D3StudioFork/releases/latest) by me
- [x] [PS4OfflineAccountActivator 9.00](https://github.com/charlyzard/PS4OfflineAccountActivator) by barthen, updated by charlyzard
- [x] [PS4 Save Mounter v1.9.3](https://github.com/ctn123/Binary-Releases/releases/latest) by ChendoChap, updated by ctn123
- [x] PC FTP client: [FileZilla](https://filezilla-project.org/download.php?show_all=1)
- [x] Both of the following payloads running on **Console B**:
  - **GoldHEN v2.0b2+** by [SiSTR0](https://github.com/SiSTR0/SiSTR0)
  - **PS4Debug** by jogolden, updated by ctn123, built into his PS4 Save Mounter
- The most convenient way to launch GoldHEN is to visit http://ithaqua.exploit.menu, use the DNS servers `165.227.83.145` and `192.241.221.79` on your console to get there easier

## Import your encrypted Diablo 3 save to Console B
1. On **Console B**, launch GoldHEN, navigate to Home Screen Settings -> ★GoldHEN★ -> Enable BinLoader Server, and it will give a notification in the top left of your LAN IP
2. Launch PS4 Save Mounter, input **Console B** LAN IP and click Send Payload
3. Launch PS4OfflineAccountActivator, input **Console B** LAN IP and click Connect, click Get Users
    * NOTE: Your dashboard might freeze and restart the UI, wait for it to restart and click Connect then Get Users again
4. Paste the PSN ID of your account into the box of zeroes next to a newly created offline account
    * NOTE: Your PSN ID is the name of the folder on your USB drive under PS4->SAVEDATA
5. Click Set ID & Activate, reboot your console, sign into newly activated account
6. Copy your existing Diablo 3 save from your USB to System Storage

## Decrypt your Diablo 3 save to use with [D3StudioFork](https://github.com/god-jester/D3StudioFork/releases/latest)
1. Sign into your newly activated account on **Console B**, then launch GoldHEN again and enable both the BinLoader and FTP servers
2. On your PC, create a folder for your decrypted save, we will name ours `PS4Save`
3. Launch PS4 Save Mounter, input **Console B** LAN IP, click Send Payload, click Connect, click Patch, click Get Users, click Get Games, select Diablo 3 from dropdown (probably `CUSA00242` for US RoS disc), click Search, click Mount
4. Open FTP client on your PC, connect to **Console B** LAN IP and port (the GoldHEN default FTP port is `2121`), navigate to `/mnt/pfs/` and there should be a `savedata_xxxxxxxx_CUSAxxxx_autosave` folder, open it
5. Download to your `PS4Save` folder the following items: `heroes` folder, `account.dat`, `profile.dat`, and `prefs.dat`
    * **NOTE: If it exists, ignore the `sce_sys` folder completely, do not modify/delete/replace it!**
6. Click Unmount in PS4 Save Mounter

## Open your Diablo 3 save with D3StudioFork
1. [Download D3StudioFork](https://github.com/god-jester/D3StudioFork/releases/latest) and extract to a folder, we will name ours `D3S`
2. Launch `D3StudioFork v3.x.exe`, click open save, and navigate to your `PS4Save` folder. Select `account.dat` and click Open. This can take an extremely long time to load with larger saves and more characters
    * NOTE: D3StudioFork was developed for Seasonal modding and game update v2.7.2, so you shouldn't need to make any changes besides checking the "Seasonal" box on the Hero tab if you need to convert a hero, and all lists are fully up to date
3. Make changes to your save, then click File -> Save All

## Inject and export your modified PS4 save
1. Launch PS4 Save Mounter, input **Console B** LAN IP, click Send Payload, click Connect, click Patch, click Get Users, click Get Games, select Diablo 3 from dropdown (probably `CUSA00242` for US RoS disc), click Search, click Mount
2. Open FTP client on your PC, connect to **Console B** LAN IP and port (the GoldHEN default FTP port is `2121`), navigate to `/mnt/pfs/` and there should be a `savedata_xxxxxxxx_CUSAxxxx_autosave` folder, open it
3. Upload from your `PS4Save` folder the following items: `heroes` folder, `account.dat`, `profile.dat`, and `prefs.dat`
    * **NOTE: If it exists, ignore the `sce_sys` folder completely, do not modify/delete/replace it!**
4. Click Unmount in PS4 Save Mounter
5. Plug USB drive into **Console B**, and copy your edited Diablo save from **System Storage** to **USB Storage Device**
6. Your save can now be copied back to your unmodified console to play online


### Happy Modding!

<hr>

## Special Thanks
* Thank you to **EckoTc** for sharing your experience and resources with me a few days after I picked up the game and pieced everything together. Cheers for reaching out and collaborating with me and the many other modders you've helped!
* Thank you to **GoobyCorp aka Visual Studio** for creating D3Edit, STL/GAM parsing tools, protobuf extraction, and much more. You've been the homie for many years and I will always appreciate your knowledge
* Thank you to **Tonic-Box** for compiling the most complete set of resources and guides that I stumbled upon when first looking into this stuff
  * I religiously read his excellent [D3ROS Modding Guide](https://github.com/Tonic-Box/D3ROS-Modding-Guide), and I suggest you do the same. Specifically his [full list of editor tricks](https://github.com/Tonic-Box/D3ROS-Modding-Guide/tree/main/EditorTricks) without any fluff
  * Listed and credited in his guide are all significant current and past contributors to the D3 modding community, so I will not repeat them all here. Visit his guide and read it over thoroughly.
