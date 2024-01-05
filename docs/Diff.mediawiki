{{OtherUse|the text difference file format|the binary patches mainly used for client modification|Hexing}}
=Diff files=
A diff file is a file to make:
*implementation of a modification easier
*check what and where you modified things
*share your modifications with the rest of the world
*it is also an easy way for people that give support on forums to check themselves what is wrong to the modifications you made

==Creating .diff files using the tortoise menu==
#right click on the folder
#goto TortoiseSVN menu
#click create patch
#save as .diff file

==Manually Creating .diff files (knowing the mechanics and repairing .diffs if needed)==
#create a new txt file
#rename the .txt extention to .diff
#start with pointing out the index (path where the diff files will patch)
#*example:[code]Index: src[/code]
#add a ========================================= line to indicate the next file
#*example:[code]=========================================[/code]
#add the patch of the file where content will be removed (---) and add the revision
#*example:[code]--- src/common/mmo.c	(revision 12300 Stable)[/code]
#add the path of the file where content will be added (+++) and add (working copy)
#*example:[code]+++ src/common/mmo.c	(working copy)[/code]
#add the location of the lines that need to be modified in this way:
##@@
##-100: start reading original lines at line 100
##,5: read 5 original lines
##+100: start reading new lines at line 100
##,7: read 7 new lines
##@@
#*example:[code]@@ -100,5 +100,7 @@[/code]
#add a <space> and write a line that is from the original text (this line will be unmodified) and all others starting with a space
#*[color=red]A SPACE IS NEEDED, IF YOU COPY A DIFF FROM A FORUM APPLY THE SPACES YOURSELF[/color]
#*example:[code]		this line will be unmodified[/code]
#add a "-" and write the line that must be modified
#*example:[code]-this line will be removed from the original code[/code]
#add a "+" and write the line that need to be placed to replace or added to the original code
#*example:[code]+this line will be added in the new code[/code]
#**full example on a @@ -x,7 +x,8 @@:[code]line1: this line will be unmodified
line2: this line will be unmodified
line3:-this line will be deleted
line4:+this line will replace line 3
line5:+this line will add a line of code
line6: this line will be unmodified, but will move down one line
line7: 
line8: this line will be unmodified, move down one line (same as the line above since an <enter> counts as a line)[/code]
#**[color=red]NOTICE= THE <enter> ON LINE 7 MUST START WITH A <space> as well[/color]

==Using .diff/.patch files to patch your server==
'''Windows''':
#go place the folder in the index folder
#richt click the *.diff file and go to TortoiseSVN menu
#click patch

'''Linux''':
 cd /path/to/your/server/folder
 patch -p0 < /path/to/patch/file/filename.extension

=Example of a .diff file=
 <nowiki>Index: map/clif.c
===================================================================
--- map/clif.c	(revision 13318)
+++ map/clif.c	(working copy)
@@ -6745,7 +6745,7 @@
 	/*==========================================
 	 * Marry [DracoRPG]
 	 *------------------------------------------*/
-	void clif_marriage_process(struct map_session_data *sd)
+	/*void clif_marriage_process(struct map_session_data *sd)
 	{
 		int fd;
 		nullpo_retv(sd);
@@ -6755,8 +6755,8 @@
 		WFIFOW(fd,0)=0x1e4;
 		WFIFOSET(fd,packet_len(0x1e4));
 	}
+	*/
-	
	 /*==========================================
	  * Notice of divorce
	  *------------------------------------------*/
Index: map/clif.h
===================================================================
--- map/clif.h	(revision 13318)
+++ map/clif.h	(working copy)
@@ -53,8 +53,8 @@
	 #endif
	 
	 // packet DB
-#define MAX_PACKET_DB		0x400
-#define MAX_PACKET_VER		22
+#define MAX_PACKET_DB		0x500
+#define MAX_PACKET_VER		23
	 
	 struct s_packet_db {
	 	short len;</nowiki>

== See Also ==
* [[wikipedia:Diff#Unified_format]]

[[Category:File Formats]]