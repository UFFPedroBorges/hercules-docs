# `setnpctimer()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
setnpctimer(<tick>{, "NPC Name"});
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

== Description ==
The '[[setnpctimer]]' is a command that will explicitly set a NPC timer to a given tick. 
'[[getnpctimer]]' provides timer information. Its parameter defines what type:

 0 - Will return the current tick count of the timer.
 1 - Will return 1 if there are remaining [[OnTimer]]<ticks>:" labels in the 
	 specified NPC waiting for execution.
 2 - Will return the number of times the timer has triggered and will 
	 trigger an "OnTimer<tick>:"  label in the specified NPC.

== Example ==
Here is an example which will help you to understand how the '''setnpctimer''' command works.

 [[OnTimer]]15000:
 [[set]] $quote,rand(5);
 [[if]]($quote == 0) goto Lquote0;
 if($quote == 1) [[goto]] Lquote1;
 if($quote == 2) goto Lquote2;
 if($quote == 3) goto Lquote3;
 if($quote == 4) goto Lquote4;
      Lquote0:
      [[npctalk]] "If 0 is randomly picked you will see this";
      '''setnpctimer''' 0;
      [[end]];
      Lquote1:
      npctalk "If 1 is randomly picked you will see this";
      '''setnpctimer''' 0;
      end;
      Lquote2:
      npctalk "If 2 is randomly picked you will see this";
      '''setnpctimer''' 0;
      end;
      Lquote3:
      npctalk "If 3 is randomly picked you will see this";
      '''setnpctimer''' 0;
      end;
      Lquote4: 
      npctalk "If 4 is randomly picked you will see this";
      '''setnpctimer''' 0;
      end;


Example 2:
<pre>
	mes "[Man]";
	mes "Ok, I will let you have 30 more seconds...";
	close2;
	initnpctimer;
	// Notice the 'close2'. If there were a 'next' there the timer would 
	// be changed only after the player pressed the 'next' button.
	end;

	OnTimer30000:
		setnpctimer getnpctimer(0)+30000;  //Will directly Call OnTimer60000.
		end;

	OnTimer60000:
		announce "Only 30 seconds passed, but OnTimer60000 Called.",bc_all;
		end;
</pre>
