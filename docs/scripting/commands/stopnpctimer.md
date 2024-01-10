# `stopnpctimer()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
stopnpctimer({<attach flag>});
```

```c
stopnpctimer("<NPC name>"{, <attach flag>});
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

==Description==
This script command acts as a partner to the [[initnpctimer]] and [[startnpctimer]] script commands. When called, it will stop any active NPC timer from ticking but will not reset the tick value to 0. When [[startnpctimer]] is called after this command, the timer will resume from the tick that it was stopped at.

==Examples==
* Stop an NPC timer after 30 seconds of processing.
 [[OnInit|OnInit]]:
     [[Initnpctimer|initnpctimer]];
     [[End|end]];
 
 [[OnTimer|OnTimer]]30000:
     [[Announce|announce]] "30 seconds has expired.", bc_all|bc_npc;
     stopnpctimer;
     end;
