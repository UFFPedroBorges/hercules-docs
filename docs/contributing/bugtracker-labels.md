# Bugtracker labels

Issue tracker labels and cases where they should be used:

## Code Review

The `codereview:` labels are used for code review. They may be replaced by the native code review interface of GitHub in the near future.
Only one of these labels can be set at the same time. These labels are used only in pull requests.

### `codereview:accepted`

Code review was positive and the pull request can be accepted as is.

### `codereview:needsedits`

Some edits have been requested before the pull request can be accepted.

### `codereview:rejected`

Code review was negative and the pull request can't be accepted. This generally means the pull request should be closed without merging.

## Components

The `component:` labels are used to classify an issue or pull request based on the Hercules components it affects. Multiple of these labels can be set at any time, if the issue spans through several components.

### `component:client-interface`

Affecting the client interface (packets from/to the client)

### `component:core:HPM`

Affecting or related to the Hercules Plugin Manager and plugins.

### `component:core:scriptengine`

Affecting the script engine or the script commands.

### `component:core`

Affecting the Hercules core (i.e. not the game mechanics directly). Sub-categories may be created in future as deemed necessary.

### `component:databases`

Affecting the databases (as opposed to the source code) available in the `db/` folder. This is NOT for the SQL databases.

### `component:documentation`

Documentation issues.

### `component:mechanics:skills`

Affecting the skills' game mechanics.

### `component:mechanics`

Affecting the game mechanics in general. Sub-categories may be created in future, if deemed necessary.

### `component:other`

Any issues that don't fall in the explicitly described components.

### `component:scripts`

Affecting the scripts and NPCs.

### `component:SQL`

Affecting the SQL databases.

## Mode

These labels may be used to restrict an issue to a specific server mode. They are optional, and should only be used for issues that affect the game mechanics.

### `mode:pre-renewal`

For Pre-Renewal issues.

### `mode:renewal`

For Renewal issues.

## Severity

Issues should be categorized into one and only one severity level, using the `severity:` labels.
These labels are usually only used in bug reports, but they may also be used in pull requests.

### `severity:low`

* Cosmetic behavior
* Minor console errors or warnings
* Minor server mechanics that are not usually used by server owners behaving unexpectedly

### `severity:fair` (Incorrect mechanic or behavior)

* Incorrect gaming mechanic
  * Skill damage
  * Skill area
  * Monster behavior
  * Incorrect db value
  * Wrong NPC behavior (not causing any errors whatsoever)
  * Gaming systems such as BG, WOE etc.
* Minor server mechanics commonly used behaving unexpectedly
  * Incorrect gaming behavior
  * Party mechanics
  * Guild mechanics
* Database reading warnings

### `severity:medium` (Incorrect mechanics or behavior)

* GM commands not behaving accordingly to description
* Script command not behaving accordingly to what's expected (not necessarily documentation as ours doesn't describe all commands correctly)
* Commonly used features not working properly

### `severity:high` (Crashes and general instability)

* GM command causing crash
* Database reading errors
* Server systems not behaving accordingly to what's expected
* Wrong values being saved in databases
* Server instability
* Exploits that don't lead to too many problems (Consider emailing security@herc.ws instead - the GitHub bugtracker doesn't allow marking issues as confidential yet)

### `severity:critical` (Crashes and exploits)

* Regular player behavior leading to crash
  * Skills
  * Commands usually used by players
  * Gaming systems
* Script command causing to crash
* Impossibility of starting up server
* Impossibility of building correctly
* Server systems causing crashes
* Serious database typos that lead to exploits
* Exploits that lead to many problems (Consider emailing security@herc.ws instead - the GitHub bugtracker doesn't allow marking issues as confidential yet)

## Status

These labels are used to describe an issue's or a pull request's current status. In general, there should be only one status associated with each issue at one time, but there are exceptions (see the description of each label for more information).

### `status:code-review`

The pull request is awaiting code review.
The label is applied automatically when pull requests are created by external contributors. For pull requests created by internal collaborators or developers, the label should be set manually by the opener.
This label should only be used for pull requests.

### `status:confirmed`

The issue was confirmed to be valid.
This label should be applied only when an issue was verified.

### `status:duplicate`

The issue is a duplicate of another existing issue. When this label is applied, a comment should be added, linking to the other issue (so that they are cross-referenced for future reference).
When this label is applied, the issue should be closed.

### `status:inprogress`

The issue is being worked on, or the pull request still has ongoing work and should not be merged or reviewed yet.
This label is applied automatically to pull requests created by internal contributors or developers (unless the `status:code-review` label is applied manually), and it is applied automatically to any issues referenced by a pull request or branch.
This label may be applied at the same time as other status labels, such as `status:confirmed`, `status:need-aegis-confirmation`, `status:needinfo`.

### `status:invalid`

The issue isn't a Hercules bug (user mistake, intentional behavior, unsupported setup, etc)
When this label is applied, the issue should be closed.

### `status:need-aegis-confirmation`

The issue or fix should be verified in official servers before proceeding.
This label should be used when there are doubts about game mechanics, or when more information in general is needed (for example packet dumps).

### `status:needinfo`

More information is needed before the issue can he handled (for example, information on how to reproduce the issue or additional details)

### `status:on-hold`

The issue was put on hold until another issue is solved or a feature is implemented.
This label can co-exist with any other status label except `status:duplicate`, `status:invalid`, `status:unreproducible`, `status:wontfix`.

### `status:unreproducible`

The issue can't be reproduced, despite following the user-provided steps and/or information).
When this label is applied, the issue should be closed.

### `status:wontfix`

The issue can't/won't be fixed. This is generally used for official server behaviors that can't be fixed by the emulator, or official bugs that we decide not to emulate.
When this label is applied, the issue should be closed.

## Types

An issue or pull request should have one type.

### `type:bug`

The issue is a bug or describes an incorrect behavior that should be fixed. This label is also used for pull requests that resolve bugs.

### `type:enhancement`

The issue describes an enhancement or feature that should be implemented. This label is also used for pull requests that implement new features or apply enhancements.

### `type:question`

The issue is neither a bug nor an enhancement. This label is usually used for discussions.
