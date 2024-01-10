# `getgmlevel()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
getgmlevel();
```

## Description

This function will return the level of the account to which the invoking player belongs.

## Examples

```c
mes("Your GM level is: " + getgmlevel());
close();
```

## See Also

- [`getgroupid()`](getgroupid.md) (`getgroupid()` is the new `getgmlevel()` as the gm level system has been rewritten to fit for group id's.)
- [conf/groups.conf](https://github.com/HerculesWS/Hercules/blob/stable/conf/groups.conf)
