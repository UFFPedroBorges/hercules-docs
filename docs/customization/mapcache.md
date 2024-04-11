# Mapcache

## What is the mapcache?

Utilising the mapcache allows you to process the maps you've configured in the `db` and `conf` folder, with respect to the `conf/grf-files.txt`. Building the mapcache allows you to:

* make custom maps,
* edit existing maps,
* allows your server to recognize the maps found in the client,
* allows your server and client to agree on map information (passable and non-passable terrain among other information),
* stores this information in a [cache](https://en.wikipedia.org/wiki/Cache_(computing)?oldformat=true) format easily usable by your server executables.

## Building Mapcache for Hercules

Back in eAthena and rAthena days, mapcache was a separate executable file `mapcache.exe` that you run to process the client.

In Hercules, the mapcache tool is incorporated as a [Hercules Plugin](https://github.com/HerculesWS/Hercules/wiki/Hercules-Plugin-Manager), which is run using the `map-server.exe` as a loaded plugin that processes the maps as the map-server is starting up.

### Requirements

You must know what your Operating System is. Is it a Windows? a Unix-based system?

### What you will learn

In building the mapcache for Hercules, you will learn how to:

1. Configure the mapcache plugin for your server.

2. Recompile the plugins to build the mapcache plugin.

3. Know how to use a terminal or command prompt, to run the `map-server` with the the mapcache plugin loaded and instructions to rebuild the cache.

### Instructions

1. Determine what your operating system is. _Is it Windows? Unix?_ This will determine which guides you should follow when [compiling](https://github.com/HerculesWS/Hercules/wiki/Compiling) and running command line/terminal scripts.

2. Configure the mapcache plugin. To do so, you must read about [how plugins are compiled](https://github.com/HerculesWS/Hercules/wiki/Hercules-Plugin-Manager#Building_a_plugin).

3. Next, you need to [compile your server](https://github.com/HerculesWS/Hercules/wiki/Compiling). 

4. Configure your `conf/grf-files.txt` so that the server knows where to find the client-side map files.

5. On your server, configure your `db/map_index.txt` and `conf/map/maps.conf` so that you can include your custom maps. Read and follow the Configuring the `grf-files.txt` section below.

6. On your client, ensure that your custom map is included in the `data/resnametable.txt` file, and that the corresponding `yourmap.gnd`, `yourmap.rsw`, and `yourmap.gat` is found in the data folder of your client.

7. Open your command prompt or terminal to your root server folder, and run the following command:

```
map-server --load-plugin mapcache --rebuild-mapcache
```

8. That will execute the `map-server` executable with the `mapcache` plugin and instructing it to rebuild the mapcache.

9. Once it has finished running, your mapcache has been rebuilt and your server and client agree on the data about the maps. Go and test whether your map exists.

***

#### Configuring the `grf-files.txt`

1. Open `conf/grf-files.txt`
2. Add your data folder path.
3. Do not include the data folder itself in the path (see example).

**Can I use the GRF files option?**

No. GRF files are no longer supported by the `mapcache` tool, so use only the data folder option.

**But I need to use the GRF cause my files are there!**

If you have files in the GRF which you have to include, use a [[GRF extraction]] tool to obtain its data folder.

**Examples:**

```
data_dir: C:\Users\JohnD\Documents\Data Folder\
```

This will refer to the data folder found at `C:\Users\JohnD\Documents\Data Folder\data`.

## References / Extended Reading
1. [Myriad's Mapcache Generation 2018](https://herc.ws/board/topic/15868-guide-mapcache-generation-2018/#comment-90027)
