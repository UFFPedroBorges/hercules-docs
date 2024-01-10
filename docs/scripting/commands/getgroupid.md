# `getgroupid()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
getgroupid();
```

!!! remark
	`getgroupid()` is the new `getgmlevel()` as the gm level system has been rewritten to fit for group id's.

## Description

This function will return the id of player group the account to which the invoking player belongs.

## Examples

```c
mes("Your group ID is: " + getgroupid());
close();
```

## See Also

- [conf/groups.conf](https://github.com/HerculesWS/Hercules/blob/stable/conf/groups.conf)
