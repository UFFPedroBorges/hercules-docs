# `freeloop()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
freeloop(<toggle>);
```

## Description

Toggling this to enabled (1) allows the script instance to bypass the
infinite loop protection, allowing your script to loop as much as it may
need. Disabling (0) will warn you if an infinite loop is detected.

## Example

```c
freeloop(1); // enable script to loop freely

// Be aware with what you do here.
for (set(.@i, 0); .@i < .@bigloop; set(.@i, .@i + 1)) {
	dothis();
	// Be aware, it will block the emulator to process other
	// stuff (socket, timer, logic, etc.) until the loop end.
}

freeloop(0); // disable

for (set(.@i, 0); .@i < .@bigloop; set(.@i, .@i + 1)) {
	dothis();
	// throw an infinity loop error
}
```

## See Also

- [`while (...)`](../while.md)
- [`for (...)`](../for.md)
