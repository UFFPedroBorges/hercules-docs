# GM Commands

## Syntax

- `@<command> {<param 1> <param 2> ...}`
- `#<command> <target> {<param 1> <param 2> ...}`

## Description

GM commands (also called atcommands because of the **@** prefix) can be used to perform a wide array of tasks in-game,
such as system administration, database queries, player actions, and collecting information regarding a player, party,
guild, pet, and/or homunculus. For a full list of atcommands,
please see [`doc/atcommands.txt`](https://github.com/HerculesWS/Hercules/blob/stable/doc/atcommands.txt)

## Examples

### atcommands

```
@item 909 10
```

Entering this command in-game will give the invoking player a the item 909 (Jellopy) in the amount of 10.

### charcommands

```
#item Ind 909 10
```

Entering this command in-game will give the target player, Ind, the item 909 (Jellopy) in the amount of 10.

## Notes

While it is common knowledge throughout the [Ragnarok Online](https://en.wikipedia.org/wiki/Ragnarok_Online) community that atcommands use
the **@** symbol, the symbol used can be changed to any other character by adjusting **atcommand_symbol** and
**charcommand_symbol** in
[`conf/atcommand.conf`](https://github.com/HerculesWS/Hercules/blob/stable/conf/atcommand.conf)

### Exceptions

| Symbol      | Reason                 |
|-------------|------------------------|
| (0x00-0x1f) | control-characters     |
| %           | party chat symbol      |
| $           | guild chat symbol      |
| /           | client commands symbol |
