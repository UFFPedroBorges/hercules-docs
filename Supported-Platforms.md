Hercules guarantees a different level of compatibility with each of the platforms it can compile and run on.

# Support Levels

* **primary**: A platform Hercules is actively developed and tested on. Hercules aims to compile (without errors or warnings), and run without issues on these platforms.
* **supported**: A platform Hercules is intended to run on. Hercules aims to compile (without errors), and run without issues on these platforms. Tests may not be automated, but may depend on users reports.
* **unsupported**: A platform Hercules is not intended to run on. Hercules may or may not run on these platforms, and may require workarounds to work. Compatibility is not a goal of the development team, but pull requests may be accepted, as long as they don't hinder development on other platforms, or degrade the quality or increase complexity of the existing code for the supported platforms.
* **unknown**: A platform Hercules was not tested on. It is unknown whether it can work on it.

# Platforms

## Debian Linux

The current stable distribution (currently version 9 'stretch') is a primary platform, while the oldstable (currently version 8 'jessie') gets gradually phased out from primary to supported.
Older (obsolete stable releases other than oldstable), or newer (testing, unstable) releases are unsupported.

| System             | Support Status | Primary platform until | Supported until       |
| ------------------ | -------------- | ---------------------- | --------------------- |
| Debian "sid"       | *unsupported*  |                        |                       |
| Debian 10 "buster" | *unknown*      |                        |                       |
| Debian 9 "stretch" | **primary**    | release of version 10  | release of version 11 |
| Debian 8 "jessie"  | supported      |                        | release of version 10 |
| Debian 7 "wheezy"  | *unsupported*  |                        |                       |
| Debian 6 "squeeze" | *unsupported*  |                        |                       |

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

(2): It's recommended to upgrade the development tools to include GCC 4.9 or newer (devtoolset-3 or newer).

## Ubuntu Server

The latest LTS version is a primary platform. The latest version -- if not an LTS version -- is a supported platform. The previous LTS version is a supported platform for 4 months after the next version is released. Older versions are unsupported.

| System                         | Support Status    | Primary platform until  | Supported until |
| ------------------------------ | ----------------- | ----------------------- | --------------- |
| Ubuntu 19.04 Disco Dingo       | *unknown*         |                         |                 |
| Ubuntu 18.10 Cosmic Cuttlefish | supported         |                         | April 2019      |
| Ubuntu 18.04 Bionic Beaver     | **primary**       | April 2020 (rel. 20.04) | August 2020     |
| Ubuntu 17.10 Artful Aardvark   | *unsupported*     |                         |                 |
| Ubuntu 17.04 Zesty Zapus       | *unsupported*     |                         |                 |
| Ubuntu 16.10 Yakkety Yak       | *unsupported*     |                         |                 |
| Ubuntu 16.04 LTS Xenial Xenus  | *unsupported* (3) |                         |                 |
| Ubuntu 15.10 Wily Werewolf     | *unsupported*     |                         |                 |
| Ubuntu 15.04 Vivid Vervet      | *unsupported*     |                         |                 |
| Ubuntu 14.10 Utopic Unicorn    | *unsupported*     |                         |                 |
| Ubuntu 14.04 LTS Trusty Tahr   | *unsupported*     |                         |                 |

(3): Although unsupported, Hercules is very likely to still work on this version

## Gentoo

Gentoo is a rolling release, and has no versions. The stable branch is a primary platform (amd64) or a supported platform (x86), while the unstable (~x86 or ~amd64) is unsupported. Support on other architectures is unknown.

| System        | Support Status | Primary platform until   | Supported until          |
| ------------- | -------------- | ------------------------ | ------------------------ |
| Gentoo x86    | supported      |                          | Always (rolling release) |
| Gentoo amd64  | **primary**    | Always (rolling release) |                          |
| Gentoo ~x86   | *unsupported*  |                          |                          |
| Gentoo ~amd64 | *unsupported*  |                          |                          |

## FreeBSD

The latest FreeBSD release is a primary platform. The previous release is supported, but only for as long as it is supported upstream. Any older versions are unsupported.

| System        | Support Status  | Primary platform until | Supported until                                       |
| ------------- | --------------- | ---------------------- | ----------------------------------------------------- |
| FreeBSD 12.x  | **primary** (4) | release of version 13  | last 12.x release + 2 years, or release of version 14 |
| FreeBSD 12.0  | **primary**     | release of version 13  | 12.1 release + 3 months, or release of version 14     |
| FreeBSD 11.x  | supported (4)   |                        | last 11.x release + 2 years, or release of version 13 |
| FreeBSD 11.2  | supported       |                        | September 2021 (expected), or release of version 13   |
| FreeBSD 11.1  | *unsupported*   |                        |                                                       |
| FreeBSD 11.0  | *unsupported*   |                        |                                                       |
| FreeBSD 10.4  | *unsupported*   |                        |                                                       |

(4): version 'y.x' refers to the latest release in the 'y' branch.

## macOS

The last version of macOS is a primary platform, assuming the latest version of Xcode is installed. The previous version is a supported platform. Older versions are unsupported.

| System                  | Support Status | Primary platform until   | Supported until             |
| ----------------------- | -------------- | ------------------------ | --------------------------- |
| macOS 10.14 Mojave      | **primary**    | release of version 10.15 | release of version 10.16    |
| macOS 10.13 High Sierra | supported      |                          | release of version 10.15    |
| macOS 10.12 Sierra      | *unsupported*  |                          |                             |

## OpenBSD

The latest OpenBSD release is supported, but it isn't a primary platform.

| System      | Support Status | Primary platform until | Supported until        |
| ----------- | -------------- | ---------------------- | ---------------------- |
| OpenBSD 6.4 | supported      |                        | release of version 6.5 |
| OpenBSD 6.3 | *unsupported*  |                        |                        |
| OpenBSD 6.2 | *unsupported*  |                        |                        |
| OpenBSD 6.1 | *unsupported*  |                        |                        |
| OpenBSD 6.0 | *unsupported*  |                        |                        |

## NetBSD

The latest NetBSD release is supported, but it isn't a primary platform.

| System     | Support Status | Primary platform until | Supported until        |
| ---------- | -------------- | ---------------------- | ---------------------- |
| NetBSD 8.0 | supported      |                        | release of version 8.1 |
| NetBSD 7.1 | *unsupported*  |                        |                        |
| NetBSD 7.0 | *unsupported*  |                        |                        |
| NetBSD 6.1 | *unsupported*  |                        |                        |

## Raspbian

Hercules runs on the Raspberry Pi, and was tested on Raspbian. The latest release is a supported platform.

| System           | Support Status | Primary platform until | Supported until             |
| ---------------- | -------------- | ---------------------- | --------------------------- |
| Raspbian Stretch | supported      |                        | release of the next version |
| Raspbian Jessie  | *unsupported*  |                        |                             |

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
Primary support for more than one version of Windows Server and more than one version of Windows won't be guaranteed in any case. As such, when a new version is released, the current primary supported version may switch to supported.

| System                     | Support Status | Primary platform until | Supported until |
| -------------------------- | -------------- | ---------------------- | --------------- |
| Windows Server v.1903      | *unknown*      |                        |                 |
| Windows Server v.1809      | **primary**    | April 2019 (estimated) | 2020-05-11      |
| Windows Server v.1709      | supported      |                        | 2019-04-09      |
| Windows Server 2016        | supported      | 2022-01-11             | 2027-01-11      |
| Windows Server 2012 R2     | supported      |                        | 2023-01-10      |
| Windows Server 2012        | supported      |                        | 2023-01-10      |
| Windows Server 2008 R2 SP1 | supported      |                        | 2020-01-14      |
| Windows Server 2008 R2     | *unsupported*  |                        |                 |
| Windows Server 2008 SP2    | *unsupported*  |                        |                 |
| Windows Server 2008        | *unsupported*  |                        |                 |
| Windows 10 (latest ver.)   | **primary**    | next update            | 2026-10-13      |
| Windows 10 v.1809          | **primary**    | next update            | 2020-05-12      |
| Windows 10 v.1803          | supported      |                        | 2019-11-12      |
| Windows 10 v.1709          | supported      |                        | 2019-04-09      |
| Windows 10 v.1703          | *unsupported*  |                        |                 |
| Windows 10 v.1607          | *unsupported*  |                        |                 |
| Windows 10 v.1511          | *unsupported*  |                        |                 |
| Windows 10 RTM (v.1507)    | *unsupported*  |                        |                 |
| Windows 8.1                | supported      |                        | 2023-01-10      |
| Windows 8                  | *unsupported*  |                        |                 |
| Windows 7 SP1              | supported      |                        | 2020-01-14      |
| Windows 7                  | *unsupported*  |                        |                 |
| Windows Vista SP2          | *unsupported*  |                        |                 |
| Windows Vista              | *unsupported*  |                        |                 |
| Windows XP SP3             | *unsupported*  |                        |                 |
| Windows XP                 | *unsupported*  |                        |                 |

### Visual Studio

Visual Studio versions are also subject to platform support status. The latest version of Visual Studio (unless there are existing issues) is the primary platform, while older versions are supported at the discretion of the development team and may become unsupported as soon as they are out of their Mainstream Support period.
Support for more than three versions of Visual Studio won't be guaranteed in any case. As such, when a new version is released, the currently oldest supported version may be dropped.

| Version                         | Support Status | Primary platform until       | Supported until               |
| ------------------------------- | -------------- | ---------------------------- | ----------------------------- |
| Visual Studio 2019              | *unknown*      |                              |                               |
| Visual Studio 2017 Version 15.9 | **primary**    | Release of VS 2019           | 2022-04-12 or next 3 releases |
| Visual Studio 2017              | *unsupported*  |                              |                               |
| Visual Studio 2015 Update 3     | supported      |                              | 2020-10-13 or next 2 releases |
| Visual Studio 2015 Update 2     | *unsupported*  |                              |                               |
| Visual Studio 2015              | *unsupported*  |                              |                               |
| Visual Studio 2013 Update 5     | supported      |                              | 2019-04-09 or next release    |
| Visual Studio 2013 Update 4     | *unsupported*  |                              |                               |
| Visual Studio 2013              | *unsupported*  |                              |                               |
| Visual Studio 2012              | *unsupported*  |                              |                               |
| Visual Studio 2010              | *unsupported*  |                              |                               |

(5): This version is currently known to work, for legacy reasons. Continued support is not guaranteed.