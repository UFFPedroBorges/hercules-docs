On this page, you will be able to learn the steps on how to add your Custom Job.

## Pre-Requirements
Before you begin, it is a good idea to prepare some things you will need:
- A Job ID (referenced as `<YOUR_JOB_ID>`)
- A Job Constant (referenced as `<YOUR_JOB_CONST>` and `<Your_Job_Const>` -- for different cases)
- A eAthena Job System Job ID (referenced as `<YOUR_EA_JOB_ID>`)

### Job ID (`<YOUR_JOB_ID>`)
Job IDs are the unique numerical value that represents it (just like we have IDs for items, monsters, etc). They must:
- Not conflict with other Jobs, Monsters, Homunculus, Mercenaries, NPCs IDs.
- Be in a range the client understands as Job IDs

**TODO:** Document the ranges that the client considers as Job IDs.

**TIP:** Try to keep it close to an existing ID range. You can view the existing IDs in `db/constants.conf`, search for `comment__: "Job IDs"`.

For this page, whenever you see `<YOUR_JOB_ID>`, use this number (without `<>`).

### Job Constant (`<YOUR_JOB_CONST>` and `<Your_Job_Const>`)
Job Constants are unique names associated to each job number (just like we have AegisName and Sprite for items and monsters). This allows you to reference this job by a name instead of a magical number in your code.

They must be unique in Hercules and are usually all uppercase (example: `MY_COOL_JOB`) in some cases and camel cased in others.

For this page, whenever you see `<YOUR_JOB_CONST>`, use this constant name (without `<>`) in all upper case (e.g.: `MY_COOL_JOB`). And when you see `<Your_Job_Const>` use it as `My_Cool_Job`.


### eAthena Job System ID (`<YOUR_EA_JOB_ID>`)
The eAthena Job System ID is a special ID that uses bit flags to create certain relationships between jobs.

Opposed to the plain job IDs used by RO, eAthena job system IDs carries information such as the base class of an character (regardless of their current job upper), their job upper (regardless of their class), etc.

This is used by Hercules to make certain comparisons, both in source and scripts. So it is recommended to follow the pattern when adding your job.

You can read more about it in [eAthena Job ID System](https://github.com/HerculesWS/Hercules/blob/stable/doc/ea_job_system.txt)

Some examples:
```C
MAPID_MY_JOB = 16, // 1-1 job (YOUR_EA_JOB_ID = 16)

MAPID_MY_21_JOB = JOBL_2_1 | MAPID_MY_JOB, // 2-1 job of "My_Job" (YOUR_EA_JOB_ID = JOBL_2_1 | MAPID_MY_JOB)
```

For this page, whenever you see `<YOUR_EA_JOB_ID>`, use this eAthena job ID.



# Server-side changes

## Conf changes

### `conf/messages.conf`

> Note: You can alternatively use `confg/import/msg_conf.txt` if you want to use imports/avoid touching herc files.

In this file you will add the human-readable name of your job. Used for some server messages.

Find an empty ID (the range around 600 ~ 700 is reserved for jobs, you may use it) and add a row for your job:
```
682: Baby Soul Reaper
// Add
683: My Custom Job
```

For this page, whenever you see `<MSG_ID>`, use the ID you set here (example: `683`)


## Source changes

### `src/common/class.h`
1. Add your job constant and ID in it, like that:
```C
ENUM_VALUE(<YOUR_JOB_CONST>, <YOUR_JOB_ID>)
```

  > **Note:** It is recommended to keep it sorted by ID


### `src/map/map.h`
1. Search for the enum with the `MAPID_*` values, its first element is:
```
MAPID_NOVICE = 0,
```
2. Add your Job's eAthena Job ID in there, for example:
```C
MAPID_<YOUR_JOB_CONST> = <YOU_EA_JOB_ID>,
```

  > **Note 1:** It is recommended to put it at the right place, sorted by ID

  > **Note 2:** Do not put first jobs after `MAPID_1_1_MAX`. Doing so will mess how Hercules understands each job and may cause other errors.


### `src/char/inter.c`
1. Search for `inter_job_name` function
2. Add another case for your job and its name message id:
```C
static const char *inter_job_name(int class)
{
	switch (class) {
	// ...
	case JOB_<YOUR_JOB_CONST>:
		return inter->msg_txt(<MSG_ID>);
	// ...
	default:
	// ...
	}
}
```

### `src/map/pc.c`
1. Search for `pc_job_name` function
2. Add another case for your job and its name message id:
```C
static const char *pc_job_name(int class)
{
	switch (class) {
	// ...
	case JOB_<YOUR_JOB_CONST>:
		return msg_txt(<MSG_ID>);
	// ...
	default:
	// ...
	}
}
```

3. Search for `pc_check_job_name` function
4. Add an entry in the `names` array for your job:

	> This string will be used for ItemDB, etc.

```C
	{ "<My_Job_Const>", JOB_<My_Job_Const> },
```


### `src/map/script.c`
1. Search for `script->constdb_comment("Job masks / Job map_ids");`

	> This is where Hercules adds source constants to the script engine

2. Add your constant here:
```C
	script->set_constant("EAJ_<YOUR_JOB_CONST>", MAPID_<YOUR_JOB_CONST>, false, false);
```

### Recompile the server
Now that you have performed all required source changes, recompile it.


## Database

### `db/constants.conf`
This file gives constant values to the script engine.

Search for:
```
comment__: "Job IDs"
```

And add your job constant somewhere below it (keep it sorted by ID to make it easier)
```
	Job_<Your_Job_Const>:        <YOUR_JOB_ID>
```


### `db/{pre-}re/job_db.conf`
This file contains the general definitions of the job.

Copy the structure on the "Entry Structure" section and make a new entry in the file using it.

Replace `Job_Name` with `<Your_Job_Const>` and configure the other fields as you wish, following the documentation in the file.

A minimal example may look like that:
```
<Your_Job_Const>: {
	BaseExpGroup: "FirstClasses"
	JobExpGroup: "SoulLinker"
	ParametersGroup: "ThirdClasses"
	Inherit: ("Soul_Linker")
}
```


### `db/job_db2.txt`
This file contains the stats bonus the job gains in each level.

Add an entry for your job in the following structure:
```
// Your job name
<YOUR_JOB_ID>,<JobLv1_Bonus>,<JobLv2_Bonus>,...
```

`JobLvX_Bonus` is one of the following values:
- 0 = No stat bonus at this job level
- 1 = STR increased by 1 at this job level
- 2 = AGI increased by 1 at this job level
- 3 = VIT increased by 1 at this job level
- 4 = INT increased by 1 at this job level
- 5 = DEX increased by 1 at this job level
- 6 = LUK increased by 1 at this job level


### `db/{pre-}re/skill_tree.conf`
This file contains the skill tree of your job.

Copy the structure on the "Entry Structure" section and make a new entry in the file using it.

Replace `Job_Name` with `<Your_Job_Const>` and configure the other fields as you wish, following the documentation in the file.

A minimal example may look like that:
```
<Your_Job_Const>: {
	skills: {
		SM_SWORD: 10 // SM_SWORD goes up to level 10
		SM_TWOHAND: {
			MaxLevel: 10 // SM_TWOHAND goes up to level 10
			SM_SWORD: 1  // And requires SM_SWORD Lv 1 to be learned first
		}
	}
}
```

And with that ends the server-side modifications.



# Client side changes (Lua clients)
> **TODO**

# Client Side changes (Very old clients before Lua)

> **Note 1:** XRAY Required unless you plan to replace 3rd class id's.

> **Note 2:** This guide is meant for very old clients (prior to renewal, like 2010 and before)

> **Note 3:** This guide continues using `<Your_Job_Const>` but it is not really required to be the same as in the server, using the same is just meant to help visualizing the flow.

## Sprites
Copy the sprite files of your job to:
- Male: `data\sprite\ÀÎ°£Á·\¸öÅë\³²\` folder
- Female: `data\sprite\ÀÎ°£Á·\¸öÅë\¿©\` folder

Male sprite names:
- `<Your_Job_Const>_³².spr`
- `<Your_Job_Const>_³².act`

Female sprite names:
- `<Your_Job_Const>_¿©.spr`
- `<Your_Job_Const>_¿©.act`


## data/Class_tab.txt
1. Find this
```
!52
°Ë»ç
¸¶¹ý»ç
```

2. Add your custom class
```
!<YOUR_JOB_ID>
<Your_Job_Const>
!52
°Ë»ç
¸¶¹ý»ç
```


## data/imf_tab.txt
1. Find this
```
!52
°Ë»ç
¸¶¹ý»ç
```

2. Add your custom class

> **FIXME:** What is this name?
```
!<YOUR_JOB_ID>
¼ºÁ÷ÀÚ
!52
°Ë»ç
¸¶¹ý»ç
```


## data/reality_dir_tab.txt
1. Find this
```
!52
°Ë»ç\\°Ë»ç
¸¶¹ý»ç\\¸¶¹ý»ç
```

2. Add your custom class
> **FIXME:** What is this value?
```
!<YOUR_JOB_ID>
¼ºÁ÷ÀÚ\\¼ºÁ÷ÀÚ
!52
°Ë»ç\\°Ë»ç
¸¶¹ý»ç\\¸¶¹ý»ç
```


## data/reality_tab.txt
1. Find this
```
!52
°Ë»ç
¸¶¹ý»ç
```

2. Add your custom class
> **FIXME:** What is this value?
```
!<YOUR_JOB_ID>
¼ºÁ÷ÀÚ
!52
°Ë»ç
¸¶¹ý»ç
```


## data/monstrosity_tab.txt
1. Find this
```
!47
1_M_01
1_M_02
1_M_03
```

2. Add your custom class
```
!<YOUR_JOB_ID>
<Your_Job_Const>
!47
1_M_01
1_M_02
1_M_03
1_M_04
```
