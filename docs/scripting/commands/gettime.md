# `gettime()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
gettime(<type>);
```

## Description

This function retrieves current system time and date values depending on parameter `type`:

- 1 Seconds (0 - 59)
- 2 Minutes (0 - 59)
- 3 Hours (0 - 23)
- 4 Day of Week (0: Sunday - 6: Saturday)
- 5 Day of Month (1 - 31)
- 6 Month (1 - 12)
- 7 Year (1970 - 2038)
- 8 Day of Year (1 - 366)

Any other value will cause the function to return -1. Only numbers are returned.

## Examples

```c
if (gettime(4) == 6) {
	mes("It's a Saturday. I don't work on Saturdays.");
	close();
}
```

## See Also

- [`gettimestr()`](gettimestr.md)
- [`gettimetick()`](gettimetick.md)
