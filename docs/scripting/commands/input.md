# `input()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
input(<variable>[, <min value>[, <max value>]]);
```

## Description

This command will make an input box pop up on the client connected to the [invoking character](../RID.md), to allow entering of a string or digits only, depending on variable's type.

Normally you cannot input a negative number with this command, to prevent exploits in badly written scripts, which would let people, for example, put negative amounts of [Zeny](../../Zeny.md) into a bank script and receive free Zeny as result. The default values for `min value` and `max value` are specified as `input_min_value` and `input_max_value` respectively in `conf/script.conf`.

The command has two additional optional arguments and a return value to safely override this behavior, when required. Depending on the variable type used, the min, max, and return value have different meanings:

- For **strings** min and max specify the minimum and maximum string length. The return value is -1, if the string was too short, 1, if it was too long, otherwise 0.
- For **numbers** min and max specify the minimum and maximum value, the variable is allowed to be set to. If the entered value is outside the specified range `[min, max]`, it is capped to the nearest valid value. The return value is -1 for too small values, 1 for too large values, otherwise 0.

## Examples

```c
mes("[Woman]");
mes("Try and guess the number I am thinking of.");
mes("The number will be between 1 and 10.");
next();

set(.@number, rand(1, 10));
while (input(.@guess, 1, 10)) {
	mes("[Woman]");
	mes("Didn't you listen before? The number is between 1 and 10.");
	next();
}

mes("[Woman]");
if (.@guess == .@number) {
	mes("Well done, that was the number I was thinking of.");
} else {
	mes("Sorry, that wasn't the number I was thinking of.");
}
close();
```

```c
mes("[Man]");
mes("You need a password to pass.");
next();

input(.@pwd$);
if (.@pwd$ != "s3cr3t") {
	mes("[Man]");
	mes("Get out.");
	close();
}
```
