# `query_logsql()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
query_logsql("your MySQL query"{, <array variable>{, <array variable>{, ...}}});
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

==Description==
Executes an SQL query. A 'select' query can fill array variables with up 
to 128 rows of values, and will return the number of rows (the array size).

Note that 'query_sql' runs on the main database while 'query_logsql' runs 
on the log database.

==Examples==
    [[set]] @nb, [[query_sql]]("select name,fame from `char` ORDER BY fame DESC LIMIT 5", @name$, @fame);
    [[mes]] "Hall Of Fame: TOP5";
    [[mes]] "1."+@name$[0]+"("+@fame[0]+")"; // Will return a person with the biggest fame value.
    [[mes]] "2."+@name$[1]+"("+@fame[1]+")";
    [[mes]] "3."+@name$[2]+"("+@fame[2]+")";
    [[mes]] "4."+@name$[3]+"("+@fame[3]+")";
    [[mes]] "5."+@name$[4]+"("+@fame[4]+")";

==See Also==
* http://dev.mysql.com/doc/refman/5.6/en/
* [[escape_sql]];
