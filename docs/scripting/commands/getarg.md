# `getarg()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
getarg(<index>[, <default value>]);
```

```c
getarg(<index>[, <"default value">]);
```

## Description

This function retrieves a parameter inside a function, which was passed into an invoking [`callsub()`](callsub.md) or [`callfunc()`](callfunc.md) call. The parameters are referred to by an zero-based `index`, which means, the first parameter has index 0, the second parameter 1, and so on. Optionally a `default value` can be specified, which will be used, when no parameter was passed with given index (optional parameter functionality for script functions).

If there is no such parameter at given index and no default value exists, or if the invoking script is not a function, the script terminates with an error.

!!! note
	The parameter `default value` is available since r10773.

## Examples

```c
	callsub(L_dosomething, "toast");
	end;
L_dosomething:
	mes("*does something with a " + getarg(0, "not recognized thing") + "*");
	close2();
	return;
```

!!! info
	This results in message `*does something with a toast*`. If `"toast"` were not passed as parameter, the message would be `*does something with a not recognized thing*`.
