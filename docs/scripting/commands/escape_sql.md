# `escape_sql()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
escape_sql(<value>);
```

## Description

Converts the value to a string and escapes special characters so that it's
safe to use in [`query_sql()`](query_sql.md). Returns the escaped form of the given value.

## Examples

```c
set(.@str$, "John's Laptop");
set(.@esc_str$, escape_sql(.@name$)); // Escaped string: John\'s Laptop
```

## See Also

- [`query_sql()`](query_sql.md)
