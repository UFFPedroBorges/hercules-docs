## Building Mapcache
### Windows
To use Hercules' Mapcache, open up its vcxproj located in the vcproj-11 to vcproj-14 folders. Which one you will need depends on the version of Microsoft Visual Studio you are using. Microsoft Visual Studio 2015 will use vcproj-14, earlier versions of the software will use the other folders instead. Alternatively, you can open "Hercules-14.sln" which compiles your entire server plus the mapcache.

Next, [[compile|Compiling-Windows]] your mapcache.

## Required Mapcache Files
Open conf/grf-files.txt and add your .grf or data folder path (NOT including the data folder itself in the path!) In order to use a GRF file, it must not already be open in a grf editor or any other software. If a GRF is currently in use when mapcache tries to use it, you may get an error that says: "grf read error".

**Examples:**

data_dir: C:\Users\JohnD\Documents\Data Folder\
NOTE: This will go to C:\Users\JohnD\Documents\Data Folder\data

grf: C:\Program Files (x86)\YourServer\Server.grf

In order for mapcache to work, you must have your desired map listed in db/map_index, conf/map/maps.conf, and it must also be inside of resnametable.txt and mapnametable.txt client side. Additionally, you must have a .gnd, .rsw, and .gat file for your map inside of your data folder.

## Using Mapcache
Run mapcache.exe and it will start building the cache. If you did something incorrectly, close mapcache, delete the db/mapcache.dat it created, and run mapcache again. If you run mapcache again without deleting the old mapcache, you may get an error stating: "An error as occured while reading map_cache_fp" or "An error as occured in fread while reading map_cache."