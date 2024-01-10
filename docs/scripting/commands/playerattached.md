# `playerattached()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
playerattached();
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

==Description==
Returns the [[RID]] of the player currently attached to the script. It will return 0 if none is attached, or if the attached player is no longer on the map server. It is wise to check for the attached player in script functions that deal with timers as there is no guarantee the player will still be logged on when the timer triggers.

==Example==
 [[mes]] "Please wait for a bit...";
 [[sleep2]] 5000;
 
 [[if]](!playerattached())
 {
     [[announce]] "It appears, that the winner could not even wait 5 seconds for the prize..",bc_all;
     [[end]];
 }
 
 [[getitem]] 512,100;  // Apple
 mes "Here you go, enjoy your prize.";
 [[close]];
