# `changebase()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
changebase(<job ID number>);
```

## Description
This command will change the appearance of the invoking character to that 
of a specified job class. Nothing but appearance will change.

## Examples

```
2338,Wedding_Dress,Wedding Dress,5,43000,,500,,0,,0,119529470,7,0,16,,0,1,0,{ bonus(bMdef, 15); changebase(22); }
```

```c
changebase(Job_Novice); // Changes player to Novice sprite.
```

```c
changebase(Class); // Changes player back to default sprite.
```
