# `jobchange()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
jobchange(<job number>{, <upper flag>});
```

## Description

This command will change the job class of the invoking character. It does work using the job IDs, but you can also use job names. The full list of job names and the IDs they correspond to can be found in [db/const.txt](https://github.com/HerculesWS/Hercules/blob/stable/db/const.txt).

This command will also set a permanent character-based variable `jobchange_level` which will contain the job level at the time right before changing jobs, which can be checked for later in scripts.

!!! remark
	`upper flag` can alternatively be used to specify the type of job one changes to.

### Upper Values

| Value | Description |
| ----- | ----------- |
| -1 or not set | Preserves the current job type |
| 0 | Normal/Standard Classes |
| 1 | High/Advanced Classes |
| 2 | Baby Classes |

## Examples

!!! example
	This would change your player into a Swordman

```c
jobchange(1);
```

!!! example
	This would change your player into a Swordman High

```c
jobchange(4002);
```

!!! example
	This would change your player into a Swordman

```c
jobchange(Job_Swordman);
```

!!! example
	This would change your player into a Swordman High

```c
jobchange(Job_Swordman_High);
```

!!! example
	This would change the character to a high swordsman.

```c
jobchange(Job_Swordman, 1);
```
