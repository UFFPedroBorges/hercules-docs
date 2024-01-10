# `initnpctimer()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
initnpctimer({<attach flag>});
```

```c
initnpctimer({"<NPC name>"{, <attach flag>}});
```

## Description

This script command will begin an NPC-attached timer on the running or specified NPC. The timer will run internally in the NPC and is not attached to any player, so will continue to run even when there are no players logged on. It is important to note that an NPC can only run a single timer on itself at any given time. In order to process multiple timers, the script would have to use player based timers such as [`addtimer()`](addtimer.md).

The timer runs in milliseconds (1/1000th of a second) from 0, and calling this script command will begin a new timer (if a timer is not already running on the NPC) or reset the current timer on the NPC. To completely stop the NPC timer, the script command [`stopnpctimer()`](stopnpctimer.md) must be called, and to resume the timer (without resetting the current tick) the script command [`startnpctimer()`](startnpctimer.md) must be called.

The script can access a timer event by creating a label matching the format `OnTimer<tick>:` where the `<tick>` is replaced with a millisecond value to occur on. The NPC timer does not reset automatically once reaching one of these labels, therefore it is possible to multiple labels with incremented `<tick>` values to handle the same NPC timer (see examples below).

## Parameters

### Attach Flag

The flag value determines whether a player should be directly associated with this NPC timer. When flag is specified (a value of 1) the script will attach the player who is currently attached to the script, to the timer. If no player is attached to the script when this flag is specified, then the `initnpctimer()` call will fail.

If a player is successfully attached to the NPC timer, and logs out of the game, then the event label `OnTimerQuit:` will run on the NPC (the player will still be logged in at this point) to allow cleaning up and handling of the timer.

### NPC Name

If specified, the call to `initnpctimer()` will not apply to the current running script but will take effect on the NPC which exists with the passed NPC name. If an NPC could not be found with this name then the `initnpctimer()` call will fail.

## Examples

!!! example
	Announce every 1 second (resetting the timer after every 1000 milliseconds)

```c
	initnpctimer;
	end;

OnTimer1000:
	announce("1 second has passed!", bc_all | bc_npc);
	initnpctimer();
	end;
```

!!! example
	Announce at 5 and 10 seconds (stopping the timer once 10000 milliseconds is reached)

```c
	initnpctimer;
	end;

OnTimer5000:
	announce("5 seconds have passed!", bc_all | bc_npc);
	end;

OnTimer10000:
	announce("10 seconds have passed!!", bc_all | bc_npc);
	stopnpctimer();
	end;
```

!!! example
	Perform an event on a player every 60 seconds (resetting the timer after every 60000 milliseconds)

```c
	initnpctimer(1);
	end;

OnTimer60000:
	percentheal(10, 0);
	message(strcharinfo(0), "You were healed 10% HP!");
	initnpctimer(1);
	end;

OnTimerQuit:
	stopnpctimer();
	end;
```
