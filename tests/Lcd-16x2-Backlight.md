
 
I've been fighting with this LCD to light up as per tutorial is outlined. As soon as I connect any wire to the 5V the Arduino's lights go out. I've been trying countless of other tutorials, tried adding a pen or a 220K resistor both. Nothing.
 
**DOWNLOAD ✅ [https://oraselic.blogspot.com/?d=2A0SIH](https://oraselic.blogspot.com/?d=2A0SIH)**


 
It wasn't until I came across a random Google image that used three wires connected to the side of the LCD did my backlight turn on. But, that method doesn't really work since I want to show data on the lcd.
 
If the lights on the Arduino turn off when you connect your display then you may very well have the power connections to the display reversed. There are a very few displays with the functions of pins 1 and 2 reversed.

Probably you will not belive this. I have a lcd display just like that one, the only way I got the light to show up was connecting pin 16 (marked K) to +5V trough a 470 ohm resistor and pin 15 (marked A) to 0V.
 
Looking at the board it looks to have only 1 resistor valued 100 ohms between the anode and the led pin that's marked as anode. In the silkscreen all looks ok, so I agree with you, the led must have been mounted backwards. If that's the case, I can live with it.
 
I have a UNO clone on order too, a pro mini and a couple of ATtiny85 but I quite like the Nano (and it's the only one I have right now).
If I could make the ATtiny to control the LCD, the RTC and the T/H sensor I might even shove this in a project box.
 
When I bought that lcd I had 0 experience, and didn't knew that there were I2C ones, and I didn't noticed that it was a inverted LCD that totally needs the backlight. Before I got the light working I had to shine a flashlight from the side in order to see that the lcd was actually doing something.
 
I got out a Sparkfun white on black 16x2 that I have had for a few years now and was testing some things on a circuit I'm working with. Apparently it's a GDM1602K according to Sparkfun's website, unless they changed the model since I bought it.
 
I'm confused because my entire project measured at power supply to Vin is only 35mA. Everything is running off of a 5V 2A buck stepdown module, and the Arduino is powered through the Vin pin. I measured the volatage at the A-K pins on the LCD and it was at 5.0-5.1V, and the current there measured about 16-17mA, so the Arduino and everything else is using about 18mA. There are 3 DS18B20 temp sensors and an SD micro breakout module connected as well.
 
To be clear, I do not have a current limiting resistor on the backlight. I measured the project current by connecting the power from positive output of the 5V power supply to my red lead, then my black lead to the point where the power connects to the circuit. DMM is an Extech 355 and I had my leads on the mA and COM sockets, measuring mA DC.
 
I followed several guides, including the one on the Arduino website. I tried several different pin layouts only to find the characters not showing on the screen. On the other hand, the backlight works fine. Turning the potentiometer does nothing.
 
Since I went through multiple pin layouts (alternating my code to accommodate the current pin layout) I can safely assume that the pins are not the problem. Also, I did the tests on 2 separate Arduinos (Uno and Nano).
 
The Arduino sketch doesn't fit your wiring, so it can't be used without modifications.
The other sketch should be working, but as floresta suggests: check the display pin sequence.
What happens when you turn the potmeter?
 
(2) Get the power and contrast working properly. This involves only pins 1, 2, and 3 on most LCD modules. You should be able to just barely see blocks on one row of a two row display and on two rows of a four row display.
 
NOTE: The Arduino has not been used yet, except as a possible source for the power needed for the first two steps. Do not try to go any further until this is working. If you don't see the blocks then no amount of program code will help.
 
@Don: Backlight and contrast work the way you described. Even I think everything is the way you wrote step by step, I will do it again and confirm. The backlight in the photo I couldn't use a resistor to limit the current, it was to dark. The second display I tried, I used a 220 Ohms resistor.
 
Now the big BUT: But after he gave me back my parts, I recognized my wires were very loose. I pushed them harder into the breadboard. I still went through your step by step. And... it worked. I rewired to the original Arduino example and it worked as well.
 
So my guess is that the loose wires caused connectivity problems. We checked also the wires with an oscilloscope and saw the data packages. So what, I'm happy now that I can start now my original quest
 
I would switch to using a i2c backpack that is soldered to LCD
That will reduce the wire count (arduino pins) to only two instead of 6.
If you use my hd44780 library (which can be found in the IDE library manager)
it will also be faster than using the LiquidCrystal library with 6 pins and you can have full backlight control as well as some other features like automatic line wrapping.
 
This 16 2 LCD packs 32 characters into an outline smaller than that of most two-line displays. An LED backlight enables optimal viewing in all lighting conditions. This unit uses the HD44780 interface found on most parallel character displays.
 
This 16-character, 2-line parallel liquid crystal display achieves a large viewing area in a compact package. It features a yellow-green LED backlight and uses the common HD44780 interface (330k pdf), so sample interface code is widely available for a variety of microcontrollers. This LCD is also available without a backlight.
 
The DDRAM address 0x00 corresponds to the first character of the top line, address 0x0F corresponds to the last character of the top line, address 0x40 corresponds to the first character of the second line, and address 0x4F corresponds to the last character of the second line.
 
The backlight in this LCD is composed of LEDs in series. The total voltage drop across these LEDs is typically 4.2 V and the recommended current through the LEDs is 120 mA. You should use a current limiting resistor RLIMIT as shown above where:
 
In the diagram above, VBACKLIGHT is shown as 5 V, but you are not restricted to 5 V; any voltage above the diode-drop voltage will work as long as you choose the appropriate value for your current-limiting resistor. You can also use a PWM-controlled MOSFET to achieve variable dimming of the backlight if so desired.
 
Ok, I have been trying so hard to figure this out, looking at a bunch of posts, but I couldn't find a solution that works. I am trying to turn off the LCD backlight after 30 seconds. Is there a pretty straight forward solution.
 
You have not provided any information about the LCD h/w you are using nor the library being used to control it.
There are many different types of LCDs out there and if/how they support backlight control can very substantially.
 
Controlling the backlight depends on the LCD hardware being used and library being used to control it.
Some LCD h/w includes support to control the backlight and some don't.
Some LCD libraries come with support for the LCD backlight h/w control, should it be available, and some don't.
You have to have h/w that supports backlight control to control the backlight.
If you have a library that knows how to use it the backlight h/w you can use library functions to control it.
 
If the library doesn't come with backlight support, you can still do it by adding you own code in the sketch, but only if the h/w supports backlight control.
In some cases you may have to add a small bit of h/w circuity to control the backlight.
 
Things at the h/w and s/w level must be very exact so you need to specify EXACTLY what you have and how you have it wired up.
i.e. there is no such library as "liquid crystal". There is a LIquidCrystal library though - that library does not support backlight control even if the h/w does.
 
With respect to the hd44780 library.
It is easy to install and use.
The library comes with multiple i/o classes and which you use will depend on the LCD hardware you have.
If you using pin control to control the LCD, you would use the hd44780\_pinIO i/o class.
There are many examples that show how to use it, but basically it the same as using the LiquidCrystal library other than the header files you include and your lcd object declaration, but the constructor parameters are the same as LiquidCrystal.
 
If you have a LCD keypad shield, the examples will support controlling the backlight.
If you have wired up your own LCD, then you will have add a bit if circuitry to control the backlight. Basically it is a transistor and resistor.
 
bperrybap:
This is not enough information we can't see your LCD h/w or your wiring.
You need to provide us more information about the h/w and how things are wired up and which library you are using.
 
Learn how to wire the LCD 16x2 to Arduino Uno in a few simple steps. The primary components for this circuit are: Arduino Uno - R3 and LCD 16x2. Drag and drop these components onto the canvas, and instantly get a list of secondary parts, wiring...
 a2f82b0cb4
 
