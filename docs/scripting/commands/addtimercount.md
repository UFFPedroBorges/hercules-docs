# `addtimercount()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
addtimercount("NPC::OnLabel", <ticks>);
```

## Description

These commands will create, destroy, and delay a countdown timer - `addtimer()` to
create, `deltimer()` to destroy and `addtimercount()` to delay it by the specified
number of ticks. For all three cases, the event label given is the identifier of
that timer. The timer runs on the character object that is attached to the script (and I'm not sure what happens when nothing is attached), and can have multiple instances. When the label is ran, it is ran as if the player that the timer runs on has clicked the NPC.

When this timer runs out, a new execution thread will start in the specified NPC
object at the specified label. If no such label is found in the NPC object, it
will run as if clicked.

The ticks are given in 1/1000ths of a second.

## See Also

- [`addtimer()`](addtimer.md)
- [`deltimer()`](deltimer.md)
