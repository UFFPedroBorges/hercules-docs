Hercules guarantees a different level of compatibility with each of the platforms it can compile and run on.

# Support Levels

* **primary**: A platform Hercules is actively developed and tested on. Hercules aims to compile (without errors or warnings), and run without issues on these platforms.
* **supported**: A platform Hercules is intended to run on. Hercules aims to compile (without errors), and run without issues on these platforms. Tests may not be automated, but may depend on users reports.
* **unsupported**: A platform Hercules is not intended to run on. Hercules may or may not run on these platforms, and may require workarounds to work. Compatibility is not a goal of the development team, but pull requests may be accepted, as long as they don't hinder development on other platforms, or degrade the quality or increase complexity of the existing code for the supported platforms.
* **unknown**: A platform Hercules was not tested on. It is unknown whether it can work on it.

# Platforms

## Debian Linux

The current stable distribution (currently version 8 'jessie') is a primary platform, while the oldstable (currently version 7 'wheezy') gets gradually phased out from primary to supported.
Older (obsolete stable releases other than oldstable), or newer (testing, unstable) releases are unsupported.

| System             | Support Status | Primary platform until | Supported until       |
| ------------------ | -------------- | ---------------------- | --------------------- |
| Debian "sid"       | *unsupported*  |                        |                       |
| Debian 9 "stretch" | *unknown*      |                        |                       |
| Debian 8 "jessie"  | **primary**    | release of version 9   | release of version 10 |
| Debian 7 "wheezy"  | supported (1)  |                        | release of version 9  |
| Debian 6 "squeeze" | *unsupported*  |                        |                       |

(1): There are no known issues, and Hercules is regularly tested on this platform by one or more of the developers despite not being one of the primary platforms.

## CentOS and Red Hat Enterprise Linux

The current stable version is a primary platform. The previous stable version is supported, but may require upgrading the development tools. Older versions are unsupported, regardless of upstream support.

| System   | Support Status | Primary platform until | Supported until      |
| -------- | -------------- | ---------------------- | -------------------- |
| CentOS 7 | **primary**    | release of version 8   | release of version 9 |
| RHEL 7   | **primary**    | release of version 8   | release of version 9 |
| CentOS 6 | supported (2)  |                        | release of version 8 |
| RHEL 6   | supported (2)  |                        | release of version 8 |
| CentOS 5 | *unsupported*  |                        |                      |
| RHEL 5   | *unsupported*  |                        |                      |

(2): It's recommended to upgrade the development tools to include GCC 4.7 or newer.

## Ubuntu Server

The latest LTS version is a primary platform. The latest version -- if not a LTS version --  is a supported platform. The previous LTS version is a supported platform for 4 months after the next version is released. Older versions are unsupported.

| System                            | Support Status | Primary platform until  | Supported until          |
| --------------------------------- | -------------- | ----------------------- | ------------------------ |
| Ubuntu 16.10 Yakkety Yak          | *unknown*      |                         |                          |
| Ubuntu 16.04 LTS Xenial Xenus     | **primary**    | April 2018 (rel. 18.04) | August 2018              |
| Ubuntu 15.10 Wily Werewolf        | *unsupported*  |                         |                          |
| Ubuntu 15.04 Vivid Vervet         | *unsupported*  |                         |                          |
| Ubuntu 14.10 Utopic Unicorn       | *unsupported*  |                         |                          |
| Ubuntu 14.04 LTS Trusty Tahr      | supported      |                         | August 2016              |
| Ubuntu 13.10 Saucy Salamander     | *unsupported*  |                         |                          |
| Ubuntu 13.04 Raring Ringtail      | *unsupported*  |                         |                          |
| Ubuntu 12.10 Quantal Quetzal      | *unsupported*  |                         |                          |
| Ubuntu 12.04 LTS Precise Pangolin | *unsupported*  |                         |                          |

## Gentoo

Gentoo is a rolling release, and has no versions. The stable branch is a primary platform (x86 and amd64), while the unstable (~x86 or ~amd64) is unsupported. Support on other architectures is unknown.

| System        | Support Status | Primary platform until   | Supported until |
| ------------- | -------------- | ------------------------ | --------------- |
| Gentoo x86    | **primary**    | Always (rolling release) |                 |
| Gentoo amd64  | **primary**    | Always (rolling release) |                 |
| Gentoo ~x86   | *unsupported*  |                          |                 |
| Gentoo ~amd64 | *unsupported*  |                          |                 |

## FreeBSD

The latest FreeBSD release is a primary platform. The previous release is supported, but only for as long as it is supported upstream. Any older versions are unsupported.

| System        | Support Status  | Primary platform until   | Supported until                                       |
| ------------- | --------------- | ------------------------ | ----------------------------------------------------- |
| FreeBSD 11.0  | *unknown*       |                          |                                                       |
| FreeBSD 10.x  | **primary** (3) | release of version 11    | last 10.x release + 2 years, or release of version 12 |
| FreeBSD 10.2  | **primary**     | release of version 11    | December 2016 (expected), or release of version 12    |
| FreeBSD 10.1  | supported       |                          | December 2016 (expected), or release of version 12    |
| FreeBSD 10.0  | *unsupported*   |                          |                                                       |
| FreeBSD 9.3   | supported       |                          | December 2016 (expected), or release of version 11    |
| FreeBSD 9.2   | *unsupported*   |                          |                                                       |
| FreeBSD 8.4   | *unsupported*   |                          |                                                       |

(3): version 'y.x' refers to the latest release in the 'y' branch.

## Mac OS X

The last version of Mac OS X is a primary platform, assuming the latest version os Xcode is installed. The previous version is a supported platform. Older versions are supported

| System                  | Support Status | Primary platform until   | Supported until             |
| ----------------------- | -------------- | ------------------------ | --------------------------- |
| macOS 10.12 Sierra      | *unknown*      |                          |                             |
| OS X 10.11 El Capitan   | **primary**    | release of version 10.12 | release of version 10.13    |
| OS X 10.10 Yosemite     | supported      |                          | release of version 10.12    |
| OS X 10.9 Mavericks     | *unsupported*  |                          |                             |

## OpenBSD

The latest OpenBSD release is supported, but it isn't a primary platform.

| System      | Support Status | Primary platform until | Supported until        |
| ----------- | -------------- | ---------------------- | ---------------------- |
| OpenBSD 6.0 | *unknown*      |                        |                        |
| OpenBSD 5.9 | supported      |                        | release of version 6.0 |
| OpenBSD 5.8 | *unsupported*  |                        |                        |

## NetBSD

The latest NetBSD release is supported, but it isn't a primary platform.

| System     | Support Status | Primary platform until | Supported until        |
| ---------- | -------------- | ---------------------- | ---------------------- |
| NetBSD 7.0 | supported      |                        | release of version 8.0 |
| NetBSD 6.1 | *unsupported*  |                        |                        |

## Raspbian

Hercules runs on the Raspberry Pi, and was tested on Raspbian. The latest release is a supported platform.

| System          | Support Status | Primary platform until | Supported until             |
| --------------- | -------------- | ---------------------- | --------------------------- |
| Raspbian Jessie | supported      |                        | release of the next version |

## Other Linux / UNIX Distributions

The status on other linux distributions is unknown. Hercules will likely run on them if they derive from, or use similar versions of the development tools as the previously described platforms.

| System                | Support Status | Primary platform until | Supported until             |
| --------------------- | -------------- | ---------------------- | --------------------------- |
| Linux Mint            | *unknown*      |                        |                             |
| SuSE Linux / openSuSE | *unknown*      |                        |                             |
| Fedora                | *unknown*      |                        |                             |
| Arch Linux            | *unknown*      |                        |                             |
| Slackware             | *unknown*      |                        |                             |
| Elementary OS         | *unknown*      |                        |                             |
| Mandriva              | *unknown*      |                        |                             |

## Microsoft Windows

Windows (both server and workstation versions) are primary platform, for as long as they're within their upstream Mainstream Support period. Versions within their upstream Extended Support period are supported. Older versions are unsupported.

| System                 | Support Status | Primary platform until | Supported until             |
| ---------------------- | -------------- | ---------------------- | --------------------------- |
| Windows Server 2012    | **primary**    | 2018-01-09             | 2023-01-10                  |
| Windows Server 2008 R2 | supported      |                        | 2020-01-14                  |
| Windows Server 2003 R2 | *unsupported*  |                        |                             |
| Windows 10             | **primary**    | 2020-10-13             | 2025-10-14                  |
| Windows 8.1            | **primary**    | 2018-01-09             | 2023-01-10                  |
| Windows 7              | supported      |                        | 2020-01-14                  |
| Windows Vista          | supported      |                        | 2017-04-11                  |
| Windows XP             | *unsupported*  |                        |                             |

### Visual Studio

Visual Studio versions are also subject to platform support status. The latest version of Visual Studio (unless there are existing issues) is the primary platform, while older versions are supported at the discretion of the development team and may become unsupported as soon as they are out of their Mainstream Support period.
Support for more than three versions of Visual Studio won't be guaranteed in any case. As such, when a new version is released, the currently oldest supported version may be dropped.

| Version                | Support Status    | Primary platform until       | Supported until               |
| ---------------------- | ----------------- | ---------------------------- | ----------------------------- |
| Visual Studio 2015     | **primary**       | next release                 | 2020-10-13 or next 3 releases |
| Visual Studio 2013     | supported         |                              | 2019-04-09 or next 2 releases |
| Visual Studio 2012     | supported         |                              | 2018-01-09 or next release    |
| Visual Studio 2010     | *unsupported* (4) |                              |                               |
| Visual Studio 2008     | *unsupported*     |                              |                               |

(4): This version is currently known to work, for legacy reasons. Continued support is not guaranteed.