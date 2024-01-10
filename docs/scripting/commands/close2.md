# `close2()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
close2();
```

## Description

This command will create a 'close' button in the message window for the invoking character. This is one of the ways to end a speech from an [NPC](../../NPC.md). Once the button is clicked, the message box will disappear, but unlike [`close()`](close.md) the script execution will continue. So after a `close2()` command an [`end`](end.md) command must follow to terminate the script. If no window is currently on screen, the [invoking character](../../RID.md) will get stuck in the NPC.

## Examples

```c
mes("[Woman]");
mes("I am finished talking to you, click the close button.");
close2();
dispbottom("This will be shown at the characters chat window.");
end;
```

```c
mes("Thank you for using");
mes("the Kafra Services.");
close2();
cutin("", 255);
end;
```

!!! info
	Probably the most common usage of this command. Removing a previously set cutin, after the NPC dialog is closed.
