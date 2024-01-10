# `setcashmount()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
setcashmount();
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

== Description ==
The '[[setcashmount]]' function toggles cash mount for the invoking character.
It will return 1 if successful, 0 otherwise.
<br /><br />
&nbsp;&nbsp;&nbsp;&nbsp; Note: Character must not be mounting a non-cash mount (eg. dragon, peco, 
	  wug, etc.)<br />
<br />
The accompanying function will return 1 if the invoking character has a 
cash mount and 0 if they don't.
