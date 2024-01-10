# `gettimestr()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
gettimestr(<"format">, <max length>);
```

## Description

This function returns the current system time and date as a string, according to given `format`, which has same syntax as the one of C library function [strftime](http://www.cplusplus.com/reference/clibrary/ctime/strftime/). The parameter `max length` specifies the maximum length of the string returned.

## Examples

```c
mes(gettimestr("%Y-%m/%d %H:%M:%S", 21));
```

!!! info
	Would print out the full current date and time, ex. "2010-10/30 07:48:37".

### Example compile under MSVC

!!! notice
	This example compile under MSVC 2010

```c
prontera,156,192,6	script	Time Sample	8W_SOLDIER,{
	mes("System Tick : "+ gettimetick(0));
	mes(" Time Tick  : "+ gettimetick(1));
	mes(" UNIX Tick  : "+ gettimetick(2));
	mes(" GetTime(1) : "+ gettime(GETTIME_SECOND) +" (Sec)"); // 15 (second 0~59)
	mes(" GetTime(2) : "+ gettime(GETTIME_MINUTE) +" (Min)"); // 04 (minute 0~59)
	mes(" GetTime(3) : "+ gettime(GETTIME_HOUR) +" (Hour)"); // 5 (hour 0~23)
	mes(" GetTime(4) : "+ gettime(GETTIME_WEEKDAY) +" (WeekDay)"); // 2 (Sun=0,Sat=6 0~6)
	mes(" GetTime(5) : "+ gettime(GETTIME_DAYOFMONTH) +" (MonthDay)"); // 22 (day 1~31)
	mes(" GetTime(6) : "+ gettime(GETTIME_MONTH) +" (Month)"); // 12 (month 1~12)
	mes(" GetTime(7) : "+ gettime(GETTIME_YEAR) +" (Year)"); // 2015 (year)
	mes(" GetTime(8) : "+ gettime(GETTIME_DAYOFYEAR) +" (No.day in year)"); // 356 (day of the year)
	mes(" GetTimeStr : %Y-%m/%d %H:%M:%S,40");
	mes(gettimestr("%Y-%m/%d %H:%M:%S",40)); // 2015-12/22 05:04:15
	next();
	mes("%a : "+ gettimestr("%a",19)); // Tue (short week)
	mes("%A : "+ gettimestr("%A",19)); // Tuesday (long week)
	mes("%b : "+ gettimestr("%b",19)); // Dec (short month)
	mes("%B : "+ gettimestr("%B",19)); // December (long month)
	mes("%c : "+ gettimestr("%c",19)); // 12/22/15 05:04:15 (== %x %X)
	mes("%d : "+ gettimestr("%d",19)); // 22 (day 01~31)
	mes("%H : "+ gettimestr("%H",19)); // 05 (hour 00~23)
	mes("%I : "+ gettimestr("%I",19)); // 05 (hour 01~12)
	mes("%j : "+ gettimestr("%j",19)); // 356 (day of the year)
	mes("%m : "+ gettimestr("%m",19)); // 12 (month 01~12)
	mes("%M : "+ gettimestr("%M",19)); // 04 (minute 00~59)
	mes("%p : "+ gettimestr("%p",19)); // AM (AM / PM)
	mes("%S : "+ gettimestr("%S",19)); // 15 (second 00~59)
	mes("%U : "+ gettimestr("%U",19)); // 51 (Week number with the first Sunday as the first day of week one (00-53))
	mes("%w : "+ gettimestr("%w",19)); // 2 (Sun=0,Sat=6 0~6)
	mes("%W : "+ gettimestr("%W",19)); // 51 (Week number with the first Monday as the first day of week one (00-53))
	mes("%x : "+ gettimestr("%x",19)); // 12/22/15 (== %m/%d/%y)
	mes("%X : "+ gettimestr("%X",19)); // 05:04:15 (== %H:%M:%S)
	mes("%y : "+ gettimestr("%y",19)); // 15 (year 00~99)
	mes("%Y : "+ gettimestr("%Y",19)); // 2015 (year)
	mes("%z : "+ gettimestr("%z",19)); // cannot determine timezone, this is blank
	mes("%Z : "+ gettimestr("%Z",19)); // cannot determine timezone, this is blank
	mes("%% : "+ gettimestr("%%",19)); // print '%' sign
	close();
}
```

### Old Example compile under Cygwin

!!! notice
	This example was compile under Cygwin provided by Bowiebowie. The script can be found [here](http://www.eathena.ws/board/index.php?s=&showtopic=181741&view=findpost&p=1329705).

```c
prontera.gat,157,181,6	script	Time Sample	105,{
	mes("System Tick : "+ gettimetick(0));
	mes(" Time Tick  : "+ gettimetick(1));
	mes(" UNIX Tick  : "+ gettimetick(2));
	mes(" GetTime(1) : "+ gettime(1) +" (Sec)");
	mes(" GetTime(2) : "+ gettime(2) +" (Min)");
	mes(" GetTime(3) : "+ gettime(3) +" (Hour)");
	mes(" GetTime(4) : "+ gettime(4) +" (WeekDay)"); // (day in the week 0~6)
	mes(" GetTime(5) : "+ gettime(5) +" (MonthDay)"); // (Day of the month)
	mes(" GetTime(6) : "+ gettime(6) +" (Month)");
	mes(" GetTime(7) : "+ gettime(7) +" (Year)");
	mes(" GetTime(8) : "+ gettime(8) +" (No.day in year)");
	mes(" GetTimeStr : %Y-%m/%d %H:%M:%S,40");
	mes(gettimestr("%Y-%m/%d %H:%M:%S",40)); // 2007-07/27 16:59:22
	next();
	mes("%a : "+ gettimestr("%a",19)); // Tue (short week)
	mes("%A : "+ gettimestr("%A",19)); // Tuesday (long week)
	mes("%b : "+ gettimestr("%b",19)); // Jul (short month)
	mes("%B : "+ gettimestr("%B",19)); // July (long month)
	mes("%c : "+ gettimestr("%c",19)); // Tue Jul 24 16:30
	mes("%C : "+ gettimestr("%C",19)); // 20 (year ->20<-07)
	mes("%d : "+ gettimestr("%d",19)); // 24 (day 01~31)
	mes("%D : "+ gettimestr("%D",19)); // 07/24/07 (month/day/year)
	mes("%e : "+ gettimestr("%e",19)); // 24 (day  1~31)
	mes("%F : "+ gettimestr("%F",19)); // 2007/07/24 (year/month/day)
	next();
	mes("%g : "+ gettimestr("%g",19)); // 07 (year 00~99)
	mes("%G : "+ gettimestr("%G",19)); // 2007 (year)
	mes("%h : "+ gettimestr("%h",19)); // Jul (short month) ( == %b )
	mes("%H : "+ gettimestr("%H",19)); // 16 (hour 00~23)
	mes("%I : "+ gettimestr("%I",19)); // 04 (hour 01~12)
	mes("%j : "+ gettimestr("%j",19)); // 205 (day of the year)
	mes("%k : "+ gettimestr("%k",19)); // 16 (hour  0~23)
	mes("%l : "+ gettimestr("%l",19)); //  4 (hour  1~12)
	mes("%m : "+ gettimestr("%m",19)); // 07 (month 01~12)
	mes("%M : "+ gettimestr("%M",19)); // 30 (minute 00~59)
	next();
	mes("%p : "+ gettimestr("%p",19)); // PM ( AM / PM )
//	mes("%p : "+ gettimestr("%P",19)); // pm ( am / pm ) <-- not supported !!
	mes("%r : "+ gettimestr("%r",19)); // 4:30:00 PM ( == %I:%M:%S %p )
	mes("%R : "+ gettimestr("%R",19)); // 16:30 (==%H:%M)
	mes("%S : "+ gettimestr("%S",19)); // 57 (second 00~59)
	mes("%T : "+ gettimestr("%T",19)); // 16:30:00 (hour:minute:sec)
	mes("%u : "+ gettimestr("%u",19)); // 2 (number of the week 1~7, Sun = 7)
	mes("%U : "+ gettimestr("%U",19)); // 29 (range 00 through 53), starting with the first Sunday as the first day of the first week. Days preceding the first Sunday in the year are considered to be in week 00.
	next();
	mes("%V : "+ gettimestr("%V",19)); // 30 (range 01 through 53). ISO weeks start with Monday and end with Sunday. Week 01 of a year is the first week which has the majority of its days in that year; this is equivalent to the week containing the year's first Thursday, and it is also equivalent to the week containing January 4. Week 01 of a year can contain days from the previous year. The week before week 01 of a year is the last week (52 or 53) of the previous year even if it contains days from the new year.
	mes("%w : "+ gettimestr("%w",19)); // 2 (number of the week 0~6, Sun = 0)
	mes("%W : "+ gettimestr("%W",19)); // 30 (The week number of the current year as a decimal number (range 00 through 53), starting with the first Monday as the first day of the first week. All days preceding the first Monday in the year are considered to be in week 00.)
	mes("%x : "+ gettimestr("%x",19)); // 07/24/07
	mes("%X : "+ gettimestr("%X",19)); // 16:40:23
	close();
}
```
