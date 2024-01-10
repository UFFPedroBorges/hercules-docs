# `setiteminfo()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
setiteminfo(<item id>, <type>, <value>);
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

==Description==
This function will set some value of an item.
Returns the new value on success, or -1 on fail (item_id not found or 
invalid type).

'''Valid types are:'''
     0 - Buy Price; 
     1 - Sell Price; 
     2 - Item Type;
     3 - maxchance (Max drop chance of this item e.g. 1 = 0.01% , etc..
         if = 0, then monsters don't drop it at all (rare or a quest item)
         if = 10000, then this item is sold in NPC shops only
     4 - sex; 
     5 - equip; 
     6 - weight; 
     7 - atk; 
     8 - def; 
     9 - range;
     10 - slot; 
     11 - look; 
     12 - elv; 
     13 - wlv; 
     14 - view id

==Examples==
    [[setiteminfo]] 7049,6,9990; // Stone now weighs 999.0
    [[setiteminfo]] 512,0,3000; // Apple Buy Price is 3000

==See Also==
* [[setitemscript]]
