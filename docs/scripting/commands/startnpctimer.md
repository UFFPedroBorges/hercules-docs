# `startnpctimer()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
startnpctimer({<attach flag>});
```

```c
startnpctimer("<NPC name>"{, <attach flag>});
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

==Description==
This script command works almost exactly like [[initnpctimer]], however calling this method does not reset the timer for the NPC. When called, it will resume the timer if it has been stopped using [[stopnpctimer]], and it will not reset the NPC timer tick to 0.

==Parameters==
See [[initnpctimer#Parameters|initnpctimer]].

==Examples==
* Start or stop an NPC timer using menus.
 [[switch]]( select("Resume timer", "Stop timer") )
 {
     [[case]] 1:
          startnpctimer;
          [[end]];
 
     case 2:
          stopnpctimer;
          end;
 }
 
 [[OnTimer]]60000:
     [[announce]] "This will only ever be called once.", bc_all|bc_npc;
     end;
