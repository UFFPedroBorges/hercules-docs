# `searchstores()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
searchstores(<uses>, <effect>);
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

==Description==
Invokes the store search window, which allows to search for both vending and buying stores. Parameter uses indicates, how many searches can be started, before the window has to be reopened. Affect value effects, what happens, when a result item is double-clicked and can be one of the following:
*0 = Shows the store's position on the mini-map and highlights the shop sign with yellow color, when the store is on same map as the invoking player.
*1 = Directly opens the shop, regardless of distance.

Works with clients 2010-08-03aRagexeRE or newer, and revisions from r14732 (Trunk) onwards.

==Examples==
 searchstores 10,1;
Item Universal_Catalog_Gold (10 uses, effect: open shop)

==See Also==
* [[buyingstore]]
