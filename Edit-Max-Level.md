One of the most common issues during server configurations is setting the max base and job levels. The process involves a 2-part editing--the source code and the configuration files.

**Note**

As of May 3rd 2014, [Commit: b6b3f58](https://github.com/HerculesWS/Hercules/commit/b6b3f58795288701d0e162d43fa6f0a47af913b3#diff-39) editing the max level has been moved to `/src/common/mmo.h`.

## Editing The Source Code

### `/map/map.h`

Open `\src\common\mmo.h` and look for this line of code:

```
#define MAX_LEVEL 175
```

Change `175` to your desired maximum value, i.e.

```
#define MAX_LEVEL 1000
```

### Note
_Some custom releases already have support for 1000 as the MAX_LEVEL and deems this part not necessary._

# Compiling The Server
After revisions in the source code, these changes will not take effect unless the .EXEs are recompiled.

See [[Compiling]].

## Editing The Configuration and Database Files

### Configuration Files

Open `/conf/battle/client.conf` and look for this line of code:

```
max_lv: 99
```

and

```
aura_lv: 99
```

Modify these to your desire values. But take note of the maximum values had in your source. Any value exceeding the supported values will be automatically reverted to `99`.

### Database files

Depending on whether you are using renewal or not, open up the correct file: `/db/re/exp_group_db.conf` and `/db/pre-re/exp_group_db.conf`.

`exp_group_db.conf` sets the required experiences for both base levels and job levels. It separates the necessary experience points by groups (First Jobs, Second Jobs, Third Jobs).

An example is shown below:

```
FirstClasses: {
		MaxLevel: 99
		Exp: [
			350, 550, 900, 1500, 2200, 3200, 3800, 4200, 4550, 5000,
			5500, 6000, 6100, 6350, 6700, 7350, 8000, 8400, 8800, 9200,
			9700, 10300, 11000, 11800, 13000, 14000, 15000, 16000, 17000, 18000,
			19000, 20000, 21000, 22000, 23200, 24000, 26000, 27500, 29000, 30000,
			31500, 33000, 34000, 36000, 37500, 38000, 40000, 42000, 44500, 47000,
			49000, 51000, 53000, 55000, 57000, 59000, 61500, 63000, 65000, 67000,
			69000, 70000, 73000, 77000, 80000, 84000, 88000, 91000, 95000, 110000,
			128000, 140000, 155000, 163000, 170000, 180000, 188000, 195000, 200000, 230000,
			260000, 300000, 350000, 400000, 480000, 550000, 600000, 680000, 750000, 900000,
			1000000, 1200000, 1500000, 1800000, 2100000, 2400000, 2800000, 3300000
		]
	}
```
When you increase the `MaxLevel` for a certain group, make sure to add corresponding experience requirements in the array as well.