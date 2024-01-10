# `changelook()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.


## Syntax

```c
changelook(<look type>, <look value>);
```

## Description

Identical to [`setlook()`](setlook.md), but only client side (doesn't save).

## Example

!!! info
	The following code is a good example of the use of `changelook()`. It uses [`bindatcmd()`](bindatcmd.md) to assign `@afk` some code to use, then detects the players upper headgear, changes it to show the AFK hat and allows the player to use the command again to put their original hat back.


```c
-	script	atcmd_afk	-1,{
OnInit:
	bindatcmd("afk", "atcmd_afk::OnAFK");
	end;

OnAFK:
	if (@AFK) {
		set(@AFK, 0);
		changelook(4, headupper); // Changes "head top" to use the players previous headgear sprite
		dispbottom("Away From Keyboard mode disabled.");
		end;
	} else {
		set(@AFK, 1);
		headupper = getlook(4); // getlook(4) fetches the "head top" id and assigns it to headupper for later use
		changelook(4, 471); // Changes "head top" to use the sprite with view id 471 (AFK Hat)
		dispbottom("Away From Keyboard mode enabled.");
		end;
	}
}
```

!!! note
	As '''changelook''' is only a client-side visual change, it doesn't send any changes to be saved towards the char server. It keeps your current headgear as it is, but just changes the view id.
