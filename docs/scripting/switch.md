# `switch (...)` / `case`

## Syntax

```c
switch (<expression>) {
	...
}
```

## Description

The switch statement is similar to a series of [`if (...)`](if.md) statements on the same expression. In many occasions, you may want to compare the same variable (or expression) with many different values, and execute a different piece of code depending on which value it equals to. This is exactly what the `switch (...)` statement is for.

It is important to understand how the `switch (...)` statement is executed in order to avoid mistakes. The `switch (...)` statement executes line by line (actually, statement by statement). In the beginning, no code is executed. Only when a [`case`](case.md) statement is found with a value that matches the value of the switch expression the [`case`](case.md) statement(s) will to executed. The parser continues to execute the statements until the end of the `switch (...)` block, or the first time it sees a [`break`](break.md) statement. If you don't write a [`break`](break.md) statement at the end of a [`case`](case.md)'s statement list, the parser will go on executing the statements of the following [`case`](case.md) (fall-through).

## Example

```c
// Returns the number of refines on your top headgear
set(.@refCount, getequiprefinerycnt(EQI_HEAD_TOP));
// Output a message
switch (.@refCount) {
// 0 means no refine yet
case 0:
	mes("No refine on your top headgear yet?");
	mes("You need to go to the refiner!");
	break;

// +1
case 1:
	mes("Your top headgear is +1!");
	break;
// +2
case 2:
	mes("Your top headgear is +2!");
	break;

// +3
case 3:
	mes("Your top headgear is +3!");
	break;

// +4
case 4:
	mes("Your top headgear is +4!");
	// NOTE: no break here means the code from "case 5" will be executed afterwards!

// +5
case 5:
	mes("Your top headgear is +5!");
	break;

// [...]

// This case will be triggered if no other case was triggered yet
default:
	mes("Your top headgear has upgrades above +5!");
	break;
}
```

## Next Example

```c
switch (rand(1, 3)) {
case 1:
	mes("Randomly Selected Number is 1");
	break;
case 2:
	mes("Randomly Selected Number is 2");
	break;
case 3:
	mes("Randomly Selected Number is 3");
	break;
}
```

## Next Example

```c
switch (select("Menu 1:Menu 2:Menu 3")) { 
case 1: 
	mes("Menu 1 message");
	close(); 
	break;
case 2: 
	mes("Menu 2 message");
	close(); 
	break;
case 3: 
	mes("Menu 3 message");
	close(); 
	break;
}
```
