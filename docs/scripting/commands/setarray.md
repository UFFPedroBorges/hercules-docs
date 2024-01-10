# `setarray()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
setarray(<array name>[<first value>], <value>{, <value>...<value>});
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

==Description==
This command will allow you to quickly fill up an array in one go. Check the 
Kafra scripts in the distribution to see this used a lot.

First value is the index of the first element of the array to alter.
==Examples==
<pre>
    [[setarray]] .@array[0],200,200,200;
    [[setarray]] .@array[1],300,150;
    // will produce:
    // .@array[0]=200
    // .@array[1]=300
    // .@array[2]=150
</pre>


==String Array==
 [[setarray]] @array$[0],"word1","word2","word3","word4";
 // will produce:
 // @array$[0] = word1
 // @array$[1] = word2
 // @array$[2] = word3
 // @array$[3] = word4

 // Example
  [[setarray]] .@maps$[0],"guild_vs1","guild_vs2";
  [[if]](class < 10) {[[warp]] .@maps$[1],0,0; }
  [[if]](class > 10) {[[warp]] .@maps$[2],0,0; }
