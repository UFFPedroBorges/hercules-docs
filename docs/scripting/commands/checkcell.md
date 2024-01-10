# `checkcell()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
checkcell("<map name>", <x>, <y>, <type>);
```

## Description

This command will return 1 or 0, depending on whether the specified cell 
has the `type` flag set or not. There are various types to check, all 
mimicking the server's cell_chk enumeration. The types can be found in 
[`db/const.txt`](https://github.com/HerculesWS/Hercules/blob/master/db/const.txt).

The meaning of the individual types can be confusing, so here's an overview.

### Overview

- `cell_chkwall`/`cell_chkwater`/`cell_chkcliff`: these check directly for the _terrain component_ of the specified cell.
- `cell_chkpass`/`cell_chkreach`/`cell_chknopass`/`cell_chknoreach`: passable = not wall & not cliff, reachable = passable wrt. no-stacking mod
- `cell_chknpc`/cell_chkbasilica`/cell_chklandprotector`/`cell_chknovending`/`cell_chknochat`: these check for specific dynamic flags (name indicates what they do)

## Examples

```c
 	mes("Pick a destination map.");
 	input(.@map$);
 	mes("Alright, now give me the coordinates.");
 	input(.@x);
 	input(.@y);
 	if (!checkcell(.@map$, .@x, .@y, cell_chkpass)) {
 		mes("Can't warp you there, sorry!");
 		close();
 	} else {
 		mes("Ok, get ready...");
 		close2();
 		warp(.@map$, .@x, .@y);
 		end;
 	}
```

## See Also

- [`setcell()`](setcell.md)
- [`setwall()`](setwall.md)
- [`delwall()`](delwall.md)
