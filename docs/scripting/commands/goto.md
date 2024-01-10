# `goto()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
goto <label>;
```

## Description

This command will make the script execution jump to the specified label. It is often used by beginners in conjunction with [`if (...)`](../if.md), before they get accustomed to other conditional statements, such as [`for (...)`](../for.md) or [`switch (...)`](../switch.md). While advanced scripters typically discourage using `goto()`, it can come handy when requiring to leave a complex nested loop without having to use flags or even more complicated code.

## Examples

```c
	if (checkriding())
		goto(L_riding);
	mes("Yay, you're not riding a Peco.");
	close();

L_riding:
	mes("Please dismount your Peco first.");
	close();
```
