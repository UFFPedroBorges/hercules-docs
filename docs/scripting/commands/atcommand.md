# `atcommand()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
atcommand("Command Line");
```

## Description

This command will run the given command line exactly as if it was typed in from the keyboard by the player connected to the invoking character, and that character belonged to an account which had GM level 99.

This command has a lot of good uses, I am sure you can have some fun with this one.

## Examples

```c
// This will ask the invoker for a character name and then use the '@nuke'
// GM command on them, killing them mercilessly.
input(@player$);
atcommand("@nuke " + @player$);
```
