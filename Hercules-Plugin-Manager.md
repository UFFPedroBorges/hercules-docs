The **Hercules Plugin Manager**, often referred to as the [[HPM]], is yet another [[Hercules Original]].

# Building a plugin

### What does building a plugin mean?

To build a plugin is the same as to [compile](https://github.com/HerculesWS/Hercules/wiki/Compiling) a plugin. This means that you want to use an existing plugin in a server.

### Where do I start?

The [[C]] code for the plugin normally won't have discrepancies. In order to compile the plugin, certain criteria must be met depending on your Operating System.

There are two (2) guides below: One for Windows and the other for everything else which should work on any *nix distro, as well as on OSX.

### I use a Windows Machine, what guide should I follow?
[Building HPM Plugin for MSVC](https://github.com/HerculesWS/Hercules/wiki/Building-HPM-Plugin-for-MSVC)

### I use a *nix based system (Linux or OSX), what guide should I follow?
[Building HPM Plugin for gcc](https://github.com/HerculesWS/Hercules/wiki/Building-HPM-Plugin-for-gcc)

# Creating a plugin

### What does creating a plugin mean?

Creating a plugin means to develop/design your custom source code edits that introduces new systems into RO. For example, the people who release plugins in the [Plugin Releases](http://herc.ws/board/forum/142-plugin-releases/) forum created plugins. People who use the plugins that they made should follow the **building a plugin** guide shown above.

**This is usually what more advanced users do, so if you're not sure if you're creating a plugin or not, you most likely aren't creating a plugin.**

After following the [building a plugin](#Building_a_plugin "wikilink")
guide, all thats left is for your plugin's code to be made, the
following will guide you through the basics of how a
[HPM](HPM "wikilink") plugin works.

## HPM Events

Events are functions in a plugin that are triggered by the **Hercules
Plugin Mananger** when they meet certain criteria.  
\* `void plugin_init (void)`

  -   - Triggered when the server starts

  - `void plugin_final (void)`
    
      - Triggered when the server starts to shut itself down

  - `void server_ready (void)`
    
      - Triggered after the server is done starting, and is online.

  - `void server_post_final (void)`
    
      - Triggered after the server's main shutdown procedures are
        complete, core functionality such as memory manager, timer, and
        sockets are still available at this point.

With the [HPM](HPM "wikilink") you only need to code the events your
plugin will use.

## HPM Hooks

In Hercules, hooking is a simple operation, it is possible to hook an
infinite number of times to the over 2k hookable functions (all the
interfaced ones, accounting for over 99% of map server)  
HPExport void plugin\_init (void)
{

`   addHookPre("pc->dropitem",my_pc_dropitem_preHook);  /* int my_pc_dropitem_preHook(struct map_session_data *sd,int *n,int *amount) */`  
`   addHookPost("pc->dropitem",my_pc_dropitem_postHook);/* int my_pc_dropitem_postHook(int retVal, struct map_session_data *sd,int *n,int *amount) */`  
`}`

Hooks receive all function params as pointers, whereas the original may
be

`int pc_dropitem(struct map_session_data *sd,int n,int amount)`

the one for the hook shall be

`(struct map_session_data *sd,int *n,int *amount)`

which allows for hooks to modify any and all data as it pleases.  
postHooks receive one additional param, which accounts for the result of
the original
function,

`int `<name>`(int retVal, struct map_session_data *sd,int *n,int *amount)`

In this case it'd allow for the postHook to react properly to what the
original returned, in this case (for pc\_dropitem) 0 (failure) or 1
(success)  
A full usage of this is demonstrated in the [HPM](HPM "wikilink")'s
sample 

## HPM @commands

The [HPM](HPM "wikilink") makes it very simple to provide
[@commands](@commands "wikilink") through plugins.  
You define a new atcommand exactly as it'd normally be done in
  
**Example:**

`ACMD(sample) {//@sample command - 5 params: const int fd, struct map_session_data* sd, const char* command, const char* message, struct AtCommandInfo *info`  
`   clif->message(fd,"You used the @sample command!");`  
`   ShowDebug("I'm being run! message -> '%s' by '%s'\n",message,sd->status.name);`  
`   return true;`  
`}`

After that you just have to link your new command, to do that you use
the `void plugin_init (void)` event.

`addAtcommand("sample",sample);`

and voila, your plugin now adds the **@sample** command.  
A full usage of this is demonstrated in the [HPM](HPM "wikilink")'s
sample 

As of
[778facb21f](https://github.com/HerculesWS/Hercules/commit/778facb21f822cea549939c8dbee886e1cd342aa),
atcommands loaded via plugins will overwrite default/original commands
with the same name.

## HPM Script Commands

The [HPM](HPM "wikilink") makes it very simple to provide through
plugins.  
You define a new script command exactly as it'd normally be done in
  
**Example:**

`BUILDIN(sample) {//script command 'sample(num);' - 1 param: struct script_state* st`  
`   int arg = script_getnum(st,2);`  
`   ShowInfo("I'm being run! arg -> '%d'\n",arg);`  
`   return true;`  
`}`

After that you just have to link your new script command, to do that you
use the `void plugin_init (void)`
event.

`addScriptCommand("sample","i",sample); //note the 2nd param is this commands' arg-types (in this case, a number)`

and voila, your plugin now adds the **sample** script command.  
A full usage of this is demonstrated in the [HPM](HPM "wikilink")'s
sample 

## HPM Console Commands

The [HPM](HPM "wikilink") makes it very simple to provide through
plugins.  
You define a new console command exactly as it'd normally be done in   
**Example:**

`CPCMD(sample) {//console command 'sample' - 1 param: char *line`  
`   ShowInfo("I'm being run! arg -> '%s'\n",line?line:"NONE");`  
`}`

After that you just have to link your new script command, to do that you
use the `void plugin_init (void)`
event.

`addCPCommand("this:is:a:sample",CPCMD_A(sample)); // note the first param is the path to this command, in this case it translates to 'this is a sample' and everything afterwards is the commands' params`

and voila, your plugin now adds the **sample** console command.  
A full usage of this is demonstrated in the [HPM](HPM "wikilink")'s
sample 

## HPM Custom Packets

The HPM makes it possible for a plugin to add or override packets within
all 3
servers  
**Example:**

`/* sample packet implementation */`  
`/* cmd 0xf3 - it is a client-server existent id, for clif_parse_GlobalMessage */`  
`/* in this sample we do nothing and simply redirect */`  
`void sample_packet0f3(int fd) {`  
`   struct map_session_data *sd = session[fd]->session_data;`  
`   `  
`   if( !sd ) return;/* socket didn't fully log-in? this packet shouldn't do anything then! */`  
  
`   ShowInfo("sample_packet0f3: Hello World! received 0xf3 for '%s', redirecting!\n",sd->status.name);`  
  
`   clif->pGlobalMessage(fd,sd);`  
`}`  
`void plugin_init(void) {`  
`   addPacket(0xf3,-1,sample_packet0f3,hpClif_Parse);`  
`}`

and voila, your plugin just changed the map server's **0xf3** packet to
pass by **sample\_packet0f3** prior to being sent to
**clif\_parse\_GlobalMessage**  
A full usage of this is demonstrated in the [HPM](HPM "wikilink")'s
sample 

## HPM Custom Data Structs

The HPM makes it possible for a plugin to create and append structs to
existent data, this feature is currently supported on player units
(map\_session\_data) and network pipes
(socket\_data)  
**Example:**

`/* can be of any size, using any data types */`  
`struct sample_data_struct {`  
`   struct point lastMSGPosition;`  
`   unsigned int someNumber;`  
`};`  
`/* appends/reads sample_data_struct in a network session data entry (socket_data) */`  
`void some_function_receiving_a_socket_fd(int fd) {`  
`   struct sample_data_struct *data;`  
  
`   if( !(data = HPMi->getFromSession(session[fd],HPMi->pid,0)) ) {`  
`       CREATE(data,struct sample_data_struct,1);`  
`       `  
`       data->lastMSGPosition.map = 1;`  
`       data->lastMSGPosition.x = 150;`  
`       data->lastMSGPosition.y = 150;`  
`       data->someNumber = rand()%777;`  
`       `  
`       ShowInfo("Created Appended session[] data, %d %d %d %d\n",data->lastMSGPosition.map,data->lastMSGPosition.x,data->lastMSGPosition.y,data->someNumber);`  
`       HPMi->addToSession(session[fd],data,HPMi->pid,0,true);`  
`   } else {`  
`       ShowInfo("Existent Appended session[] data, %d %d %d %d\n",data->lastMSGPosition.map,data->lastMSGPosition.x,data->lastMSGPosition.y,data->someNumber);`  
`       if( rand()%4 == 2 ) {`  
`           ShowInfo("Removing Appended session[] data\n");`  
`           HPMi->removeFromSession(session[fd],HPMi->pid,0);`  
`       }`  
`   }`  
`}`

and voila, your plugin becomes capable of appending and handling your
custom struct data  
A full usage of this is demonstrated in the [HPM](HPM "wikilink")'s
sample 

## HPM Function Overloading

Thanks to [Hercules Renewal Phase
One](Hercules_Renewal_Phase_One "wikilink"), you're capable of
overloading all functions covered by the [Hercules Renewal Phase
One](Hercules_Renewal_Phase_One "wikilink") interfaces, with your
plugin.  
**Example:**

`int my_custom_check_target_function( struct block_list *src, struct block_list *target,int flag) {`  
`   //<...> code`  
`}`  
`void server_ready(void) {`  
`   battle = GET_SYMBOL("battle");`  
`   battle->check_target = &my_custom_check_target_function;`  
`}`

and voila, your plugin just overloaded the game server's
**battle\_check\_target** function with your plugin's own, this is
greatly handy to ensure your customs do not create conflicts when
updating your [Hercules Repository](Hercules "wikilink")

# Other Features

Is there something you'd like to do with your plugin that requires
modifications to [HPM](HPM "wikilink")'s core? [let us
know](http://herc.ws/board/forum/55-suggestions/), and we'll do our best
to make it happen.  
[Post your suggestions here](http://herc.ws/board/forum/55-suggestions/)

# Support

Need help writing your plugin? [post your question on our support
forum](http://herc.ws/board/forum/26-source-support/)

[script commands](Category:Script_Command "wikilink") [console
commands](Category:Console_Command "wikilink")
