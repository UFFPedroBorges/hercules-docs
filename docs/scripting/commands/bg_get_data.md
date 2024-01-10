# `bg_get_data()`

!!! warning
	This page may contain outdated information, incompatible with the current version of Hercules and its coding standards.

## Syntax

```c
bg_get_data(<BG Team ID>, <type>);
```

## Description

This command is part of the Battleground System and returns information about the selected BG team. For now there is only type 0 possible (maybe more will come sometime).

### Type

| Value | Description |
| ----- | ----------- |
| 0 | Count of team members (0 if team not found). |
