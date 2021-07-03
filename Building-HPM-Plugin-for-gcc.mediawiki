This is a guide on how to prepare your gcc environment for a new [[HPM]] plugin.
= Guide =
In your '''src/plugins/Makefile.in''' file you should find something like:
 ################  PLUGIN CONFIGURATION  ##############################
 #                                                                    #
 # When you add a plugin, add its name here:                          #
 # Example: if you have a plugin named my_cool_plugin.c and another   #
 # one named my_second_plugin.c, add them to the list like this:      #
 #                                                                    #
 # MYPLUGINS = my_cool_plugin my_second_plugin                        #
 #                                                                    #
 # Note: DO NOT include the .c extension!!!                           #
 
 MYPLUGINS = 
add your plugin name (without the .c extension), after '''MYPLUGINS =''' save and close.<br/>
Lastly, run '''./configure''' and '''make plugins''' command at the root folder of Hercules, and you're good to go.


Edit '''conf/plugins.conf'''
and add your plugin in the plugins list:

 plugins_list: [
        /* Enable HPMHooking when plugins in use rely on Hooking */
        "HPMHooking",
        //"example",
        //"other",
        "my_cool_plugin",
        "my_second_plugin",
 ]


Run your server.(And plugins will be loaded)

[[HPM]]
[[Category:Installation]]