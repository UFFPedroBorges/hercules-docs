{{infobox/software
|caption=KPatcher
|heading=[[Image:KPatcher.png|250px]]<br>KPatcher with default skin after minimal configuration.
|developer=ProjectRO Development Team
|version=2.4.4437.61917 / February 23, 2012
|os=Windows 2000/XP/Vista/7
|lang=Multilingual (7)
|type=Patch Client
|license=unknown (closed source)
|web=unknown}}
'''KPatcher''' is a Ragnarok Online auto-patcher, written in Embarcadero C++ Builder XE2. It was originally developed in the Russian eAthena community[http://www.eathena.ws/board/index.php?showtopic=216716], but later released as multi-language version[http://www.eathena.ws/board/index.php?showtopic=247878], currently supporting Russian, English, Spanish, Japanese, Chinese, Portuguese and Indonesian, with further languages being planned. It consists of the patcher binary itself and a tool for creating configuration. It works on Windows 2000, Windows XP and higher.

==Features==
* Fast merge GRF/GPF files;
* Defragment GRF file;
* Delete files from the GRF on the mask;
* Deleting files from your client on a mask;
* Unpack the RGZ/RAR archives;
* The ability to patch any GRF file in the folder with patcher;
* Unique auto update;
* Support for the official patch server;
* Simple skinning;
* Remote file settings and auto update;
* Support for custom buttons.

==Files==
#Patcher folder contents:
#* '''KPatcher.exe''' (''Patcher's executable file'')
#* '''ConfigTool.exe''' (''used to add your config, custom icon file and generate a CRC32 sum of any file'')
#* Simple config file ''Example.kpsf''
#* Simple skin files
#* Simple icon file
#* Language files
#Web folder contents:
#* Simple ''kpatcher.php''
#* Simple remote settings ''settings.ini''
#* Simple auto update ''update.ini''
#* Simple patch lists ''plist.ini'' and old format ''plist.plt''


==Configuration==
To get a workable version of the patcher you will need to follow a few simple steps:
# Make a skin (''optional'');
# Write own ''.kpsf'' file using ''Example.kpsf'';
# Using '''ConfigTool.exe''' pack the own ''.kpsf'' file into the patcher exe;
# Write ''settings.ini'';
# Write own ''.php'' file using as example ''kpatcher.php'';
# Upload ''.kpsf'' and ''.php'' files to your webserver;
# Create patch list and upload to your webserver.

===Skins===
To control the skins patcher uses a special file style.ini, the structure of which we analyze.
# The dimensions of the main window, buttons, and information lines are changed automatically, depending on the content;
# For skin use *.bmp or *.png with transperence color $ff00ff, all other formats without transperence;
# For buttons use *.png with AlphaTransperence.
# All elements of the skin using the same parameters to specify the size and spacing:
#* Left - Number of pixels to the left;
#* Top - Number of pixels away from the top;
#* Width - Width of the element;
#* Height - Height of the element;
# All the buttons has at least three states, the buttons that trigger a specific action have a additional state:
#* Active - button is active and can be pressed;
#* Inactive - button is not active at all (only for buttons that trigger the feature);
#* Hover - pointer hovers over the button;
#* Pressed - button is pressed, the action will be taken after releasing the button.
# Text elements ('''[Status]''' and '''[Info]''') has two of its parameters which are responsible for the color and font size:
#* Color - color of the text;
#* FontSize - text size.

===Patch List===
The patch list is a simple text file, which uses one line for each patch. Patches are distinguished by a unique id (abbreviated with '''PID''' in examples below), which must increase with each patch, usually starting with 1. Lines beginning with // are considered a comment and ignored, which can also be used for disabling patches. Following patch types exist:
* '''PAU'''<br>Specifies patch for updating the patcher.<pre>PAU:CRC:patcher.upd</pre>CRC is the checksum of the new patcher executable '''patcher.upd'''. If the CRC of the current patcher differs, update of the patcher will occur. Might{{unsure}} appear everywhere in the patch list, but preferably at the beginning.
* '''GRF'''<br>Specifies a patch, which will be applied to a GRF archive. This type has two forms; the first applies the patch to the main archive as specified in settings, the other applies the patch to the GRF archive specified before the type.<pre>PID:GRF:2010-09-30palettefix.gpf</pre><pre>PID:adata.grf:GRF:2010-09-30palettefix.gpf</pre>
* '''ARCH'''<br>Specifies, that the patch is a ZIP archive, which will be extracted into the folder, where the patcher resides, including the folder structure stored inside the archive.<pre>PID:ARCH:newclient.zip</pre>
* '''GDF'''<br>Specifies a file, to be removed from the main GRF archive.<pre>PID:GDF:data\clientinfo.xml</pre>This type also accepts [http://en.wikipedia.org/wiki/Regular_expression regular expressions], such as deleting all palette files (*.pal), would be:<pre>PID:GDF:^.+\.pal$</pre>
* '''CDF'''<br>Specifies a local file to be deleted from the folder, where the patcher resides.<pre>PID:CDF:dinput.dll</pre>

====Example====
 PAU:CRC:patcher.upd
 //1:GRF:pal.gpf
 2:GRF:rdata.grf
 3:ARCH:lib.zip
 //4:ARCH:data.zip
 5:GDF:data\clientinfo.xml
 6:CDF:dinput.dll
 7:name.grf:GRF:patch.grf

==External Links==
* [http://www.eathena.ws/board/index.php?showtopic=247878 Official KPatcher Topic (English)]
* [http://www.eathena.ws/board/index.php?showtopic=216716 Official KPatcher Topic (Russian)]

[[Category:Patchers]]