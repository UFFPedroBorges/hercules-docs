## Building Mapcache
### Windows
First download [this vcxproj file](http://www.mediafire.com/file/nb9dh5vjl6ceqis/mapcache.vcxproj) and place it in the respective vcproj folder. Vcproj-14 is for the most recent version of Microsoft Visual Studio, the other folders are for older versions of it. Open the respective Hercules-xx.sln, Hercules-14.sln is for the most recent version of MVS, then right click the solution and hover over "Add" and select "Existing project..." from the menu.

Next, [[compile|Compiling-Windows]] your mapcache.

Then for Windows 7+ operating systems, navigate to your root Hercules folder (same place where your Hercules-xx.sln's are), click the address bar so the folder path is highlighted, then type cmd and hit enter. A command prompt will open for that folder's path. Copy and paste this into the command prompt, then hit enter:

map-server --load-plugin mapcache --rebuild-mapcache

If your conf/grf-files.txt is configured correctly, it will begin rebuilding the mapcache.

## Required Mapcache Files
Open conf/grf-files.txt and add your data folder path, **NOT** including the data folder itself in the path! GRF files are no longer supported by the mapcache tool, use only a data folder. An existing GRF can be extracted with a GRF tool to obtain its data folder.

**Examples:**

data_dir: C:\Users\JohnD\Documents\Data Folder\
NOTE: This will go to C:\Users\JohnD\Documents\Data Folder\data

In order for mapcache to work, you must have your desired map listed in db/map_index, conf/map/maps.conf, and it must also be inside of data/resnametable.txt client side. Additionally, you must have a .gnd, .rsw, and .gat file for your map inside of your data folder.