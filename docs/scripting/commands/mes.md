# `mes()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
mes("<message>");
```

```c
mes("<Line 1>", "<Line 2>", "<Line 3>");
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

==Description==

The most basic scripting command.<br>
Displays a window with '''<message>''' in it to the invoking character, if the window already exists, it will just display the given message.<br>
Notice that mes does not create a ''next''  or  ''close'' button, so you have to create one using the [[next]] or [[close]] command, otherwise the player will be stuck in your script.<br><br>
Use the  +  operator to give out multiple messages combined with variables or some commands(for example [[countitem]], [[getitemname]] or [[strcharinfo]])in one mes.<br><br>
Use "^<Red><Green><Blue> " in front of the message to give '''<message>''' a color.<br>
<Red><Green><Blue> stand for three hexadecimal numbers, representing the color components of Red Green and Blue in the wanted colour, like a html-code(see examples).
<br> Do not forget to set the color to black again, by putting "^000000" after your message, exept you want to color your whole text...<br>
<br>
Be careful: <span style="color:#ff00ff>Magenta</span> (ff00ff) is considered as transparent in the client, using it in a Dialogue will result in a weird (or funny) effect.

==Examples==
<pre>mes "Hello World";
//Will open up a text box with:</pre>
Hello World

<pre>mes "Hello 1","Hello 2","Hello 3";
// This will Generate 3 lines</pre>
Hello 1<br />
Hello 2<br />
Hello 3

<pre>mes "Hello"+strcharinfo(0)+", how are you?";
// Will upon up a textbox printing:</pre>
Hello Charname, how are you?

<pre>mes "^FF0000 Hello World^000000";
//Will open up a text box with</pre>
<span style="color:#FF0000">Hello World</span>

<pre>mes "\'Hello!\'";
// use \as prefix to include Symbols:
// will print:</pre>
'Hello!'
