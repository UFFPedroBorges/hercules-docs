# `setitemscript()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
setitemscript(<item id>, <"{ new item script }">{, <type>});
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

==Description==
Set a new script bonus to the Item. Very useful for game events.
You can remove an item's itemscript by leaving the itemscript argument 
empty. Returns 1 on success, or 0 on fail (item_id not found or new item 
script is invalid).

Type can optionally be used indicates which script to set (default is 0):
    0 - Script
    1 - OnEquip_Script
    2 - OnUnequip_Script

==Examples==
    [[setitemscript]] 2637,"{ if(isequipped(2236)==0)end; if(getskilllv(26)){skill 40,1;}else{skill 26,1+isequipped(2636);} }"; // new bonus
    [[setitemscript]] 2637,""; // now without bonus.

==See Also==
* [[setiteminfo]]
