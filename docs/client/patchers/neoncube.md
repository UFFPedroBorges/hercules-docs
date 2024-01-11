{{infobox/software
|heading=[[Image:neoncube-oobe.png|250px]]<br>Neoncube after basic configuration with default skin.
|developer=Ansell "Cliffe" Cruz
|version=1.2 / December 21, 2006
|os=Windows NT/2000/XP/Vista/7
|lang=English
|type=Patch Client
|license=GPL 2 (open source)
|web=http://patch.neon-cube.net/ {{dead link}}
}}
To use this guide you must have a basic understanding of [[Hercules]], a [[wikipedia:Web_Server|Web Server]] and how to edit, upload and manipulate files. You also need to be versatile in making [[GRF]] and [[wikipedia:RAR_(file_format)|RAR]] files.

==Programs you need==
* [http://www.paradox924x.com/mirrors.html NeonCube]
* [http://www.grfbuilder.com/#download GRF Builder] (or any program that can create/edit GRFs)
* [http://www.rarlab.com/download.htm WinRAR] (or any program that can write .RAR files)

==Features==
* Supports patching 1 GRF file (with .GPF patches)
* Supports patching other files in the RO folder (with .RAR patches)
* Download patches over HTTP (does not have to be http: Port 80)
* Detailed download progress.
* Fully skin-able (control the width, height, X and Y coordinates of the buttons, windows, progress bar, and other controls using the neoncube.style file).
* Built-in web browser (can display HTML, PHP, ASP, XML and even pages with flash movies (requires IE flash player plugin)).
* Option to keep a backup of the GRF file.
* Supports file deletion (delete a file from the GRF or delete a file from the RO folder)
* Logs errors (neoncube/error.log)
* Best of all, it is open-source (GNU GPL).

==Setup==
There are client and server files that need to be properly setup to work together.
===Client Files===
# Download [http://patch.neon-cube.net/index.php?page=download NeonCube] {{dead link}}
# Extract the files to a temporary folder.
# Make a folder on your desktop called '''RO''' (this is where all the NeonCube client files will go)
# Copy the ''neoncube'' folder, ''neoncube.exe'', and ''neoncube.exe.Manifest'' into the '''RO''' folder on your desktop.
# You can rename ''neoncube.exe'' to something like ''ServerName'''''Patcher.exe'''
# In the ''neoncube'' folder, decide which skin you will use (or edit/create your own).  Delete the folders of the skins you are NOT using.
# Open ''neoncube/'''neoncube.ini''''' with a text editor (ex: WordPad)
# Read the examples then edit the values (all lines starting with ''';''' are comments and can be removed if you want).

Sample '''neoncube.ini'''
 <tt>[server]
 server_name	= YourRO
 notice_url	= yourro.com/patcher/index.html
 patch_site	= yourro.com
 patch_port	= 80
 patch_list	= /patcher/patchlist.txt
 patch_folder	= /patcher/patch/
 executable	= YourRO.exe
 registration_link	= <nowiki>http://yourro.com/cp/</nowiki>
 skin	= skin_rag
 grf_file	= yourro.grf
 Backup_GRF	= 1
 startup_option	= 3
 [general]
 archive_passphrase =</tt>
NOTES: 
* '''notice_url''' needs to be the full path to the Notice Page (including the page name)
* Be sure '''patch_folder''' has a trailing '''/'''


===Patch Server Files===
If your ''notice_url, patch_site, patch_list'' and ''patch_folder'' are different, keep track of them throughout the rest of this guide.
====/patcher/index.html====
This is the News Page that the patcher will display (supports HTML, PHP, ASP, XML)<br>
Create this file on the web server you defined with '''notice_url'''
====/patcher/patch/====
This is the folder where you will put all the patches you create.<br>
Create this folder on the web server you defined with ''patch_site'''
====/patcher/patchlist.txt====
This is the file that lists your patches and tells the NeonCube patcher (client) what to download and where to patch it.<br>
Create this file on the web server you defined with '''patch_site'''

Format:
 patch#<TAB>destination<TAB>patch_name

;patch#
:start with 1, and increment for each new patch
;destination
:GRF will patch the grf, FLD will extract to folder
;patch_name
:the name of the patch (including file extension, of course)
Sample '''patchlist.txt''' (take note of the TABs. Comments are allowed)
 //this will extract patch1.gpf into the data folder
 1	FLD	patch1.gpf
 //here, patch2.gpf will be mergegd with grf_file
 2	GRF	patch2.gpf
 //You can also delete files from the data folder.
 3	FLD	data\filenametodelete.xml*
 //Deleting files inside a GRF archive is still supported
 4	GRF	data\i_will_delete_you.txt*

==Making a .GPF patch==
# make a '''data''' folder somewhere (ex: on your Desktop)
# gather all the files you will be adding to your patch and put them in the '''data''' folder (recreating the proper directory structure, or course. So if loading screen is supposed to go ...\data\texture\À¯ÀúÀÎÅÍÆäÀÌ½º\'''loading00.jpg''' you have to make each of those folders inside your data folder)
# run GRF Builder, click '''New''' and pick a name and place to save your patch. (I'd recommend naming patches by date in YYYY-MM-DD format. That way, as players are patching they have an idea how far along they are, since NeonCube displays the current patch name. So for today, it'd be 2008-02-10.gpf)
# Then click '''Merge dir''' and browse to your '''data''' folder (on your Desktop if you put it there)
# Transfer or upload this file to your '''patch_site''' and put it in the '''patch_folder'''
# Edit your '''patch_list''' and add a line in the format described in [[#Client_Files]]


==Making a .RAR patch==
# make a folder called '''RO''' somewhere (ex: on your Desktop)
# then put all the files you want to patch into the "RO" folder, recreating the proper directory structure (ex: if you were patching the client, you'd put it directly inside the RO folder: ...\Desktop\'''RO\YouRO.exe''')
# You can even patch the data folder this way. Files would go inside ...\Desktop'''\RO\data\'''
# Then run WinRAR, click '''Add'''
# Pick a name and place to save the patch. (ex: name it by date in YYYY-MM-DD format)
# click the '''Files''' tab. Then next to "Files to Add" click '''Append'''
# now browse INTO the RO folder on your desktop, and select all the files '''INSIDE''' your RO folder
# click OK, ok, to compress the rar
# Transfer or upload this file to your '''patch_site''' and put it in the '''patch_folder'''
# Edit your '''patch_list''' and add a line in the format described in [[#Client_Files]]
Example:
 29	FLD	2007-12-29.rar
That means patch #29, FLD indicates it will be patching the '''folder''', not the grf.
and 2007-12-29.rar indicates the name of the patch, representing Dec. 29, 2007

==Common Errors==
===Failed to get /patcher/patchlist.txt===
This error indicates that the patcher is unable to locate the patch list file at the location you specified.
# Check ''patch_site'' directive.
# Check ''patch_list'' directive.

===Patch list parse error (unexpected non-zero patch number)===
This error indicates that your patchlist.txt file is present in the correct location. However, it also indicates that you have additional text/formatted/unformatted characters before your list actually begins.
# Open your patchlist.txt file and make sure there are no characters (even spaces) before your first patch number.


==See Also==
* [[GRF]]

==External Links==
* [http://patch.neon-cube.net/ Official Neoncube Homepage] {{dead link}}
* [http://www.eathena.ws/board/index.php?showtopic=130342 Official Neoncube Board Topic]

[[Category:Patchers]]