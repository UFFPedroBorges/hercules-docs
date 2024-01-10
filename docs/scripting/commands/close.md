# `close()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
close();
```

## Description

This command will create a 'close' button in the message window for the invoking character. This is one of the ways to end a speech from an [NPC](../../NPC.md). Once the button is clicked, the NPC script execution will end, and the message box will disappear. If no window is currently on screen, the script ends right away.

## Examples

```c
mes("[Woman]");
mes("I am finished talking to you, click the close button");
close();
mes("This command will not run at all, cause the script has ended.");
```
