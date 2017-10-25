Multi-Realm is a configuration in which a [login server](Login-Server) connects to more than one [Realm](Realm), which are pairs of 1 [char server](Character-Server) and 1 [map server](Map-Server).

```
login ──┬────────── (char ─ map)
        ├────────── (char ─ map)
        └────────── (char ─ map)
```
In this configuration, each [Realm](Realm) is isolated from one another, but uses the same [login server](Login-Server) to provide [SSO](https://en.wikipedia.org/wiki/Single_sign-on) functionality and to [communicate](#inter-realm-communication) with each other.

## Purpose
The Multi-Realm configuration makes it possible to link together many entirely different games. Each Realm has its own separate mob dbs, npc scripts, items, configuration, etc. The Realms can be spread over multiple hosts, which makes it possible to have different servers for each region (ie America, Europe, Asia) to improve latency.

## Configuration
(TO-DO)

## Inter-Realm communication
(TO-DO)


<br><br>

---
See also [Multi-Zone](Multi-Zone)