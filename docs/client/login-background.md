*( Wanted Page done by Uzieal ~ July 2, 2013 Please leave for contact / update / quality control reasons. Thank you! )*

# Login Background Introduction

First of all there are a few formats to keep in mind, There are older Clients (before 2010-01-26 RagexeRE) that simply
use one Login Background and Newer Clients which use Two Alternating backgrounds that are formed from slices that the
Client uses to make up a single larger image. Where as Older Clients using the single background format do not make use
of the split / sliced images to create a Client Login Background.

# Clients before 2010-01-26 RagexeRE

These clients use "bgi_temp.jpg" (Single image as a Background) For these older clients simply create a new 1024x768
Jpeg Image of your own and name it "bgi_temp.jpg" then place it in;

`the folder ...svn/data/texture/À¯ÀúÀÎÅÍÆäÀÌ½º/    `

`( `*`Or Alternatively`*` )`

`the folder ...svn/data/texture/유저인터페이스/    `

Then your done and you should have a working Login Background (Note: This is only for clients before "2010-01-26
RagexeRE")

# Clients beyond 2010-01-26 RagexeRE

These clients use 24 sliced images to make up two 1024x768 Bitmap Images that Alternate from one login to the next.

( *First Login Background* ) - \[*Alternating*\] is made up of these slices;

"t2_¹è°æ1-1.bmp", "t2_¹è°æ1-2.bmp", "t2_¹è°æ1-3.bmp", "t2_¹è°æ1-4.bmp"

"t2_¹è°æ2-1.bmp", "t2_¹è°æ2-2.bmp", "t2_¹è°æ2-3.bmp", "t2_¹è°æ2-4.bmp"

"t2_¹è°æ3-1.bmp", "t2_¹è°æ3-2.bmp", "t2_¹è°æ3-3.bmp", "t2_¹è°æ3-4.bmp"

"t2_¹è°æ4-1.bmp", "t2_¹è°æ4-2.bmp", "t2_¹è°æ4-3.bmp", "t2_¹è°æ4-4.bmp"

( *Second Login Background* ) - \[*Alternating*\] is made up of these slices;

"t3_¹è°æ1-1.bmp", "t3_¹è°æ1-2.bmp", "t3_¹è°æ1-3.bmp", "t3_¹è°æ1-4.bmp"

"t3_¹è°æ2-1.bmp", "t3_¹è°æ2-2.bmp", "t3_¹è°æ2-3.bmp", "t3_¹è°æ2-4.bmp"

"t3_¹è°æ3-1.bmp", "t3_¹è°æ3-2.bmp", "t3_¹è°æ3-3.bmp", "t3_¹è°æ3-4.bmp"

"t3_¹è°æ4-1.bmp", "t3_¹è°æ4-2.bmp", "t3_¹è°æ4-3.bmp", "t3_¹è°æ4-4.bmp"

Just because newer clients use two login backgrounds does not mean to utilize only a single login background you have to
use an older client. With newer clients through "Diffing" your "Client.exe" you may choose to only use either the first
or second login backgrounds. Keep in mind however, even if you choose to use a newer client and Diff it so you only have
one login background you will still have to utilize the split / sliced image method to create a view-able & working
login background.

# Ragnarok Login Background Splitting Tools

*(Always be cautious when downloading)*

Now that we know about the formats lets pick a method of creation for new clients. There are many tools developed by
various members of the Ragnarok emulation community to take care of correctly converting the splicing and splitting of a
single Jpeg image you would like to use as your Login Background. Using one of these tools is the fastest most efficient
method of creating a working login background for (2010-01-26 RagexeRE) and Newer Clients.

[Ragnarok Online Login Screen Generator
(ROLSG)](http://rathena.org/board/index.php?app=core&module=attach&section=attach&attach_id=1882) --- ( Credit:
Wiskovisky )

"[rAthena / Tools / Login_Background](http://rathena.sourceforge.net/tools/login_background/)" ---------------------- (
Credit: rAthena )

[Convert.php](https://raijero.svn.sourceforge.net/svnroot/raijero/dev/Brian/convert.php)
----------------------------------------------------------- ( Credit: BrianL )

[RagBgSplitter_0.2](http://rathena.org/board/files/file/2561-ragnarok-background-splitter/)
-------------------------------------------------- ( Credit: mkbu95 )

Most of these programs will split a 1024x768 Jpeg Image into 12 slices &

convert plus save them into Bitmap Image Slices in a specified directory.

# After Splitting Tool Conversion

After using one of the above splitting tools to create our newly converted Jpeg to Bitmap images we then locate the
directory in which the images were converted and stored or saved and we proceed to move these newly created slices from
said directory in which they were saved into by the image slicing tool and (Depending on if you Diffed your Client to
only allow one background or not) you then place all 12 or 24 of the spliced images into

`the folder ...svn/data/texture/À¯ÀúÀÎÅÍÆäÀÌ½º/    `

`( `*`Or Alternatively`*` )`

`the folder ...svn/data/texture/유저인터페이스/    `

# Alternative Manual Conversion

Alternatively one could split a 1024x768 Jpeg image into 12 equal slices / segments using any number of programs and
save them each individually in the Bitmap format then properly place and name the 12 manually sliced Bitmap images. For
each of the Alternating Login Backgrounds if you choose to use both. Instead of using one of the Ragnarok Login
Background Splitting Tools. Then save to the same directory listed in the above formatted steps.

# 2012+ Clients Change Introduction

Please note that in 2012+ Clients there seems to be a new format gravity has introduced to their Login Background. This
change is from Dual Alternating Login Background Clients toa once again fixed single Login Background however there are
other changes, most notably the image format. To create this single Login Background it should be comprised of the
following files;

"t_¹è°æ1-1.bmp", "t_¹è°æ1-2.bmp", "t_¹è°æ1-3.bmp", "t_¹è°æ1-4.bmp"

"t_¹è°æ2-1.bmp", "t_¹è°æ2-2.bmp", "t_¹è°æ2-3.bmp", "t_¹è°æ2-4.bmp"

"t_¹è°æ3-1.bmp", "t_¹è°æ3-2.bmp", "t_¹è°æ3-3.bmp", "t_¹è°æ3-4.bmp"

"t_¹è°æ4-1.bmp", "t_¹è°æ4-2.bmp", "t_¹è°æ4-3.bmp", "t_¹è°æ4-4.bmp"

"t_¹è°æ1-1.tga", "t_¹è°æ1-2.tga", "t_¹è°æ1-3.tga", "t_¹è°æ1-4.tga"

"t_¹è°æ2-1.tga", "t_¹è°æ2-2.tga", "t_¹è°æ2-3.tga", "t_¹è°æ2-4.tga"

"t_¹è°æ3-1.tga", "t_¹è°æ3-2.tga", "t_¹è°æ3-3.tga", "t_¹è°æ3-4.tga"

"t_¹è°æ4-1.tga", "t_¹è°æ4-2.tga", "t_¹è°æ4-3.tga", "t_¹è°æ4-4.tga"

So far it is unknown if there are any tools to convert an image into this format automatically (hint hint), however you
may manually create your own image. This is still sliced into 12 quadrants both in Bitmap and Targa format. If you do
not wish to use this format, all you need to do is simply remove the existing images from the GRF / data folder
directory. The newer GRF's have yet to get rid of the previous images for the Alternating Dual Login Backgrounds so if
you decide that is the format you would rather use you should be able to use the previous format of Alternating Dual
Login Backgrounds or Diff your Client to use the first or second login background.

[Category:Client Configuration](Category:Client_Configuration "wikilink")
