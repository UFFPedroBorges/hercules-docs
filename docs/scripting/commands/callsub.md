# `callsub()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
callsub(<label>{, <argument>, ...<argument>});
```

## Description

This command will go to a specified label within the current script (do NOT use quotes around it) coming in as if it were a [`callfunc()`](callfunc.md) call, and pass it arguments given, if any, which can be recovered there with [`getarg()`](getarg.md).

When done there, you should use the [`return`](return.md) command to go back to the point from where this label was called.

This is used when there is a specific thing the script will do over and over, this lets you use the same bit of code as many times as you like, to save space and time, without creating extra NPC objects which are needed with [`callfunc()`](callfunc.md).

A label is not callable in this manner from another script.

## Examples

```c
	mes("[Woman]");
	mes("Lets see if you win");
	callsub(Check, 2);
	mes("Well done you have won");
	close();
Check:
	if (!rand(getarg(0)))
		return;
	mes("Sorry you lost");
	close();
```
