# Account ID (AID)

An **account id** uniquely identifies an account, not only inside the database, but also in inter-server communication.

Accounts can be classified in 2 types, based on its "Gender":

- Player account, for accounts with gender Female (F) or Male (M)
- Server account, for accounts with gender S

For player accounts, the "Gender" information is used to determine the initial gender selection when
creating a character in-game. For old client versions, where gender selection was not possible, this was
the gender of all characters in the game account.

Account IDs are used to associate account-wide data with an account, such as:

- Characters list
- [account variables](../scripting/variables.md)

In-game it is mostly used as a [game id (GID)](./gid.md).

It should not be confused with [character id (CID)](./cid.md) which identifies a character.
