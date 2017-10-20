# Changelog

## [v2017.10.22] <sub>October 22 2017</sub>

### Added

- Added the script command `getmapinfo()`, allowing to obtain misc information about a map. (#1852)
- Added an option to restrict party leader changes to characters on the same map. Controlled by the setting `party_change_leader_same_map` (defaults to true). (#1812)

### Changed

- Extended the script command `logmes()` with an option to log to the `atcommandlog` table. (#1843)

### Deprecated

- ...

### Removed

- ...

### Fixed

- Corrected the Kafra dialog in case a Doram without the Summoner's Basic Skill attempts to open the Storage. (#1864)
- Changed the cell stack counting algorithm to ignore invisible NPCs, improving the Dancer Quest experience as well as other cases of hidden NPCs blocking off certain cells. (#1827)

### Security

- ...

### Other

- New versioning scheme and project changelogs/release notes (#1853)

[v2017.10.22]: https://github.com/HerculesWS/Hercules/compare/6b1fe2d069cb0251bc5798767f97454ab63a47c0..v.2017.10.22
