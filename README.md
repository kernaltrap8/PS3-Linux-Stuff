# PS3-Linux-Stuff
Repo of some outdated and new Linux stuff for the PLAYSTATION3

# Disclamer and notes
I am not the author or creator of any of this, this is just a archive. (Also, to access USBs in Petitboot's BusyBox shell, use `tmp/petitboot/mnt/sda1` for NORs, and `tmp/petitboot/mnt/sdd1` for NANDs, these are paths btw, so `cd` into them.)

# External downloads
YellowDogLinux for Slims and Phats (KDE): https://archive.midnightchannel.net/SonyPS/Firmware/download/5138ddeb5df7c0a8b9d271839822d64c/yellowdog-6.1-ppc-DVD_20090201_NEW_PS3.iso

# How to use these tools
REBUG 4.84.2 REX is required to install and use Petitboot (OtherOS++), however if you want to go the old rout use the older files at your own risk! Side note: we have NAND testers for EVILNAT 4.89.3, so when that releases i'll go thru the steps to install it there :D

EVILNAT 4.89.3 PEX/DPEX: https://mega.nz/folder/NQN2HDAZ#gVvcyARer28dIB3nwaLjuQ

# How to install Petitboot and RedRibbon GNU/Linux
Its pretty simple to install, really. First you'll need two flash drives, and depending on your model, a USB hub. 
And you'll need a keyboard and mouse, obvoiusly. 
Download the Petitboot image for your model, if you dont know what model is a NAND or a NOR, look at this: https://www.psdevwiki.com/ps3/SKU_Models
Once you know your models flash type, grab either the `dtbimage.ps3.bin` (NOR) or `dtbimage.ps3.bin.minimal` (NAND). Put that on a USB. Next, grab the REBUG 4.84.2 REX PUP from the `REBUG` folder in the repo. Put that on a USB in `/PS3/UPDATE`. (EDIT: grab it here instead, GitHub file restrictions are stupid: https://archive.midnightchannel.net/SonyPS/Firmware/download/0835d81e3c581f3bdfdfbe86fca5e192/REBUG_CRC%5B67E4A95C%5D_FW%5Bv4.84.2_RE%5D_PS3UPDAT.PUP) Go to the console, and plug the USB into it. If you are on REBUG already, skip down to `Installing Petitboot and RedRibbon`. If you are on EVILNAT, you will need to enable QA in CFW Tools: `Custom Firmware Tools > COBRA Tools > QA Tools > Enable QA`.
After its enabled, reboot and go to the System catagory on the XMB, and scroll all the way down. Now do this button combo: `L1+L2+R1+R2+L3+DPAD DOWN`. Enter Debug Settings and enable `System Update Debug`. Once thats done install REBUG as you would any CFW. Now that its installed lets get Petitboot and RedRibbon up and running!

# Installing Petitboot and RedRibbon
First, make sure REBUG TOOLBOX is installed by going to Game, if its not go to `Package Manager > Install Package Files > Install from package folders on internal drive`. Install REBUG TOOLBOX, and open it. Once its opened go to the `CEX/DEX` section and select `Rewrite target id` (or something like that). If it asks for `eid_root_key` then go to the very last column and select `Dump eid_root_key`. Once it reboots go back into REBUG TOOLBOX. Now rwrite the target_id. It will reboot again, enter the TOOLBOX again and now select `Swap CEX/DEX Kernals`. Now that your on DEX it will reboot, and now you can go back to the TOOLBOX and select `Resize VFLASH/NAND regions 5 to allow OtherOS`. This will be on the last column. Once its done reboot, enter the TOOLBOX again, and make sure your USB is in the right most USB port on the console. Now select `Install petitboot` from the last column. It will take a bit, once its done it should say `Petitboot installed. Enjoy OtherOS`.
Congrats, OtherOS is installed. Now we need to install the OS itself. Go to the first column and select `Boot OtherOS > Current LV2 Patches`. It will now boot to Petitboot. Grab your USB again and download the folders from RedRibbon GNU-Linux (LXDE 14.03) in the repo. Put these on the root of the USB drive. Plug it back into the PS3, and wait for it to scan. Select Live `Failsafe` from the list of options. It should say `System is going down now...` and then a few Tux's will appear on screen (and 8 SPE Tux's!). Wait for it to boot. At this point have another drive plugged in for the install. But before that, I would like to talk about out sponsor, Raid Shaddow Legends (not really). Anyway, take this time to look around the OS, and see if you like it. Now select `Install` from the Desktop. Go thru the prompts, and when it asks to install choose your USB device and follow along (***ALL DATA WILL BE ERASED FROM THE TARGET DRIVE***). Once its done formatting and installing, reboot and remove the live drive (one with the ISO files on it). Now as long as you have the USB in the PS3 you can boot into Linux.

# Installing Petitboot and RedRibbon - Subsection 2
Since 4.89.3 is close to release, I may as well update this repo. Oncxe 4.89.3 is installed, head over to CFW Tools. Go to `CFW Tools > CEX/DEX Tools > Convert to DEX`. If you dont have your ERK dumped, do so by going to `CFW Tools > Dump Tools > Dump ERK`. This should dump it to either `dev_usb000`, or `dev_hdd0/tmp`. Once its dumped go back to `CEX/DEX` Tools and convert to DEX. Once done make sure to swap the kernals. Then reboot. Once the console is back on go back to `CFW Tools` and this time select `Linux Tools > Resize VFLASH/NAND regions 5`. After this is done, reboot, then go back to this repo and download the petitboot image for your console. Put this image on the root of a USB, and plug the USB into the right most port. Now go back to `Linux Tools` and select `Install petitboot from external USB device`, it will say you need to format, ignore this unless you plan on installing RedRibbon on internal HDD. Once its done, reboot the console. Now you can boot Petitboot from either Linux Tools or in REBUG TOOLBOX. 

# Conclusion
This was made possible by REBUG Team, as well as Habib, Geohot, EVILNAT, and other fellow PS3 homebrew devs (you know who you are)

Thanks everyone, and have a great day

James
