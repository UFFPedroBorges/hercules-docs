# `detachrid()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
detachrid();
```

## Description

These commands allow the manipulation of the script's [currently attached](../RID.md#Usage) player. While [`attachrid()`](attachrid.md) allows attaching of a different player by using it's [account id](../AID.md) for the parameter `rid`, `detachrid()` makes the following commands run, as if the script was never invoked by a player.

In case, that the player cannot be attached, such as, when the player went offline in the mean time, `attachrid()` returns 0, otherwise 1.

## Examples

```c
mes("Enter a name of a player.");
next();
input(.@playername$);
set(.@playerid, getcharid(3, .@playername$)); // retrieve rid of another player
set(.@invokeid, getcharid(3));                // retrieve rid of the current player

detachrid();                                  // detaches the current player,
                                              // although not necessary before attachrid

if (.@playerid && attachrid(.@playerid)) {     // playerid is 0, if player is offline
	dispbottom("Hello! *^__^*");
} else {
	set(.@playerid, 0);                       // indicate attachrid failure
}

if (attachrid(.@invokeid)) {                  // attach back to the first player
	if (.@playerid) {
		mes("I have said hello to " + .@playername$ + ".");
	} else {
		mes("I was not able to reach " + .@playername$ + ".");
	}
	close();
}
end;
```

!!! info
	This will allow one player to specify the name of an another, which is then greeted by the script. Afterwards the invoking player is informed, whether or not the player was told "hello". The return value of attachrid should be always checked for success, otherwise the script terminates on the next command, which requires an attached player, on failure.
