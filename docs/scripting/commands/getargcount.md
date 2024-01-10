# `getargcount()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
getargcount();
```

## Description

To be used inside functions/callsub labels, returns quantity of arguments provided

## Example

### In callsub:

```c
mapname,x,y,z	script	SampleCallSub	123,{
	mes("The number of arguments in the callsub is: " + callsub(SAMPLE_CS, 1, 2, 3, 4, 5, 6));
	close();

SAMPLE_CS:
	return getargcount();
	end;
}
```

!!! info
	This should return the message:  
	The number of arguments in the callfunc is 6 

### In callfunc:

```c
mapname,x,y,z	script	SampleCallSub	123,{
	mes("The number of arguments in the callfunc is: " + callfunc(SAMPLE_CS, 1, 2, 3, 4, 5));
	close();
}

function	script	funcName	{
	return getargcount();
}
```

!!! info
	This should return the message:  
	The number of arguments in the callfunc is 5 
