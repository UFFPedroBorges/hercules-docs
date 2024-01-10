# `prompt()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
prompt("<option>"{, "<option>", ...});
```

```c
prompt("<option>{:<option>:<option>}");
```

!!! warning
	The rest of this document hasn't been converted to Markdown yet.

== Description ==
This function is a handy replacement for '[[menu]]' for some specific cases where you don't want a complex label structure - like, for example, asking simple yes-no questions. It will return the number of menu option picked, starting with 1. Like '[[menu]]', it will also set the variable @menu to contain the option the user picked.

And like '[[menu]]', the selected option is consistent with grouped options and empty options.

'[[prompt]]' works almost the same as '[[select]]', except that when a character clicks the Cancel button, this function will return 255 instead.

== Examples ==
 [[if]]([[select]]("Yes:No") == 1) [[mes]] "You said yes, I know.";
 
 [[select]]("21","22","23");
 [[set]] .@opt,20+@menu;
 
 [[set]] .@choice$,"Apple:Banana:Lemon";
 [[select]](.@choice$);
 [[explode]](.@option$,.@choice$,":");
 [[mes]] "You have chosen "+.@option$[@menu-1];
