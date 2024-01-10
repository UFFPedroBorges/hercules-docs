# `return`

## Syntax

```c
return [<return value>];
```

## Description

This command causes the script execution to leave previously called function with [`callfunc()`](callfunc.md) or script with [`callsub()`](callsumb.md) and return to the location, where the call originated from. Optionally a return value can be supplied, when the call was done using the function form.

Using this command outside of functions or scripts referenced by `callsub()` will result in error and termination of the script.

## Examples

```c
	set(.@var, callsub(L_myAddition, .@a_val, .@b_val));
	mes("The result is " + .@var + ".");
	close();
L_myAddition:
	return getarg(0) + getarg(1);
```

```c
	set(.@var, callfunc("MyAddition", .@a_val, .@b_val));
	mes("The result is "+.@var+".");
	close();
	// ...

function	script	MyAddition	{
	return getarg(0) + getarg(1);
}
```

!!! info
	Assuming .@a_val and .@b_val being 1, both examples would yield a message displaying, that the result is 2.

```c
	mes("Oh no...");
	close2();
	callsub(L_scream);
	end;
L_scream:
	npctalk("Iiiiiiiiiiiiieeeeeeeeeeeeeeeeeeeeeeeeek!!!");
	return;
```
