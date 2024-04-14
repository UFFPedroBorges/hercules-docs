# Character ID (CID)

A **character ID** uniquely identifies a character, not only inside the database, but also in inter-server communication.

It associates data specific to a character, such as:

- Character name
- Character gender
- [character variables](../scripting/variables.md)
- [status ailments](../overview/source/status-list.md)

The character ID fulfills the same role as a combination of [account ID (AID)](./aid.md)
and character's slot ID, which means, if two character ids match their account IDs are automatically
the same as well.

The Character ID typically increments starting from 150000 and going up.
