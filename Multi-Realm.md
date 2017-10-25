Multi-Realm is a configuration in which a [login server](Login-Server) connects to more than one [Realm](Realm), which are pairs of 1 [char server](Character-Server) and 1 [map server](Map-Server).

```
login ──┬────────── (char ─ map)
        ├────────── (char ─ map)
        └────────── (char ─ map)
```
In this configuration, each [Realm](Realm) is isolated from one another, but uses the same [login server](Login-Server) to provide [SSO](https://en.wikipedia.org/wiki/Single_sign-on)

## Purpose
The Multi-Realm configuration makes it possible to link together many entirely different games. Each Realm has its own separate mob dbs, npc scripts, items, configuration, etc.

## Configuration
(TO-DO)

## Inter-Realm communication
(TO-DO)