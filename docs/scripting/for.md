# `for (...)`

The for loop is probably the most seen loop used in Hercules scripting, this is usually used to loop through arrays and execute a series of commands for each array entry. But you can use it every time you need to execute a series of commands x times. For loops are build up of 3 or 4 parts, depending on how they are used. The general buildup for a For loop is as following:

```c
for (initialization(1); condition(2); update(3)) {
	Code to execute(4);
}
```

If you don't know what all parts do, don't panic, since I'm going to explain that now ;)

- _variable initialization_: This part of the for loop usually contains a `set` command to initialize the counter variable. Most codes use `@i`, `@j` etc as those counter variables.
- _condition_: This part is a logical expression, the same thing as the one you find inside a `if (...)`. For example, `@i < 10`, will be true as long as the variable `@i` is smaller then 10.
* _variable update_: This, together with the expression, is the loop part of the script. Each time the for loop restarts (that is, when the previous run has ended, and it jumped back to it) the expression is evaluated. If the result of the expression is true, then the action will be executed, that is why the action usually contains a increment on the counter variable. The action is not executed when the loop is initiated (the initialization part is used then).
* _Code to execute_: This is, in theory, a optional part of the for loop. This part is usually used for any other commands then the counter increase done in action. Basically, all commands should be able to run in the action field. In the Athena Script Language, all of the code (with exception of the increment) is put into this part.

After all that explaining, it's time for a little example:

```c
for (set(@i, 0); @i < 10; set(@i, @i + 1)) {
	mes(@i);
}
```

This is one of the most simple for loops you can think of, but it serves well as executable example. When this for loop is started, a message window will be created with the following context:

```
0
1
2
3
4
5
6
7
8
9
```

Note that the 10 is not there, since `@i < 10` is false when @i is 10. What the loops does is the same as explained above. Firstly, the initilization is done (`set(@i, 0;`) and the expression is evaluated. Then, the code is executed (`mes(@i);`) and the end of the loop is reached, so it jumps back to the first part, and executes the action (`set(@i, @i + 1)`) (See how this replaces the initialization part?). Then it starts evaluating the expression (`@i < 10`), which is true since @i is 1. Because the expression is true, the code inside of the curlies is executed. This keeps on going until the expression is false, which will happen once @i is 10. As soon as that happens, it quits the loop and continues on the first line after the closing curly.
