Hercules guarantees a different level of compatibility with each of the platforms it can compile and run on.

# Support Levels

* **primary**: A platform Hercules is actively developed and tested on. Hercules aims to compile (without errors or warnings), and run without issues on these platforms.
* **supported**: A platform Hercules is intended to run on. Hercules aims to compile (without errors), and run without issues on these platforms. Tests may not be automated, but may depend on users reports.
* **unsupported**: A platform Hercules is not intended to run on. Hercules may or may not run on these platforms, and may require workarounds to work. Compatibility is not a goal of the development team, but pull requests may be accepted, as long as they don't hinder development on other platforms, or degrade the quality or increase complexity of the existing code for the supported platforms.
* **unknown**: A platform Hercules was not tested on. It is unknown whether it can work on it.

# Platforms

## Debian Linux

The current stable distribution (currently version 10 'buster') is a primary platform, while the oldstable (currently version 9 'stretch') gets gradually phased out from primary to supported.
Older (obsolete stable releases other than oldstable), or newer (testing, unstable) releases are unsupported.

| System               | Support Status | Primary platform until | Supported until       |
| -------------------- | -------------- | ---------------------- | --------------------- |
| Debian "sid"         | *unsupported*  |                        |                       |
| Debian 12 "bookworm" | *unknown*      |                        |                       |
| Debian 11 "bullseye" | **primary**    | release of version 12  | release of version 13 |
| Debian 10 "buster"   | supported      |                        | release of version 12 |
| Debian 9 "stretch"   | *unsupported*  |                        |                       |
| Debian 8 "jessie"    | *unsupported*  |                        |                       |

## CentOS and Red Hat Enterprise Linux

CentOS is supported for versions that have upstream support. CentOS 8 will be the last supported version, after which only CentOS Stream will be supported. Continued support for matching RHEL versions cannot be guaranteed past that point.

| System   | Support Status | Primary platform until | Supported until    |
| -------- | -------------- | ---------------------- | ------------------ |
| CentOS Stream | supported |                        | (rolling release)  |
| CentOS 8 | supported      |                        | December 31st 2021 |
| RHEL 8   | supported      |                        | December 31st 2021 |
| CentOS 7 | *unsupported*  |                        |                    |
| RHEL 7   | *unsupported*  |                        |                    |

## Ubuntu Server

The latest LTS version is a primary platform. The latest version -- if not an LTS version -- is a supported platform. The previous LTS version is a supported platform for 4 months after the next version is released. Older versions are unsupported.

| System                         | Support Status    | Primary platform until  | Supported until         |
| ------------------------------ | ----------------- | ----------------------- | ----------------------- |
| Ubuntu 22.04 Jammy Jellyfish   | *unknown*         |                         |                         |
| Ubuntu 21.10 Impish Indri      | supported         |                         | April 2022 (rel. 22.04) |
| Ubuntu 21.04 Hirsute Hippo     | *unsupported*     |                         |                         |
| Ubuntu 20.10 Groovy Gorilla    | *unsupported*     |                         |                         |
| Ubuntu 20.04 Focal Fossa       | **primary**       | April 2022 (rel. 22.04) | August 2022             |
| Ubuntu 19.10 Eoan Ermine       | *unsupported*     |                         |                         |
| Ubuntu 19.04 Disco Dingo       | *unsupported*     |                         |                         | 
| Ubuntu 18.10 Cosmic Cuttlefish | *unsupported*     |                         |                         |
| Ubuntu 18.04 Bionic Beaver     | *unsupported*     |                         |                         |
| Ubuntu 17.10 Artful Aardvark   | *unsupported*     |                         |                         |
| Ubuntu 17.04 Zesty Zapus       | *unsupported*     |                         |                         |

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
| FreeBSD 13.x  | **primary** (1) | release of version 14  | last 13.x release + 2 years, or release of version 15 |
| FreeBSD 13.0  | **primary**     | release of version 14  | 13.1 release + 3 months, or release of version 15     |
| FreeBSD 12.x  | supported (1)   |                        | last 12.x release + 2 years, or release of version 14 |
| FreeBSD 12.2  | supported       |                        | March 2022 (expected), or release of version 14       |
| FreeBSD 12.1  | *unsupported*   |                        |                                                       |
| FreeBSD 12.0  | *unsupported*   |                        |                                                       |
| FreeBSD 11.x  | *unsupported*   |                        |                                                       |
| FreeBSD 11.2  | *unsupported*   |                        |                                                       |

(1): version 'y.x' refers to the latest release in the 'y' branch.

## macOS

The last version of macOS is a primary platform, assuming the latest version of Xcode is installed (or GCC through Homebrew). The previous version is a supported platform. Older versions are unsupported.

| System                  | Support Status | Primary platform until   | Supported until           |
| ----------------------- | -------------- | ------------------------ | ------------------------- |
| macOS 12 Monterey       | **primary**    | release of version 13    | release of version 15     |
| macOS 11 Big Sur        | supported      | release of version 12    | release of version 14     |
| macOS 10.15 Catalina    | supported      |                          | release of version 13     |
| macOS 10.14 Mojave      | *unsupported*  |                          |                           |

## OpenBSD

The latest OpenBSD release is supported, but it isn't a primary platform.

| System      | Support Status | Primary platform until | Supported until        |
| ----------- | -------------- | ---------------------- | ---------------------- |
| OpenBSD 7.0 | supported      |                        | release of version 7.1 |
| OpenBSD 6.9 | *unsupported*  |                        |                        |
| OpenBSD 6.8 | *unsupported*  |                        |                        |
| OpenBSD 6.7 | *unsupported*  |                        |                        |
| OpenBSD 6.6 | *unsupported*  |                        |                        |
| OpenBSD 6.5 | *unsupported*  |                        |                        |
| OpenBSD 6.4 | *unsupported*  |                        |                        |
| OpenBSD 6.3 | *unsupported*  |                        |                        |
| OpenBSD 6.2 | *unsupported*  |                        |                        |
| OpenBSD 6.1 | *unsupported*  |                        |                        |
| OpenBSD 6.0 | *unsupported*  |                        |                        |

## NetBSD

The latest NetBSD release is supported, but it isn't a primary platform.

| System     | Support Status | Primary platform until | Supported until        |
| ---------- | -------------- | ---------------------- | ---------------------- |
| NetBSD 9.2 | supported      |                        | release of version 9.3 |
| NetBSD 9.1 | *unsupported*  |                        |                        |
| NetBSD 9.0 | *unsupported*  |                        |                        |
| NetBSD 8.2 | *unsupported*  |                        |                        |

## Raspbian

Hercules runs on the Raspberry Pi, and was tested on Raspberry Pi OS. The latest release is a supported platform.

| System                      | Support Status | Primary platform until | Supported until       |
| --------------------------- | -------------- | ---------------------- | --------------------- |
| Raspberry Pi OS 11 Bullseye | supported      |                        | release of version 12 |
| Raspberry Pi OS 10 Buster   | *unsupported*  |                        |                       |
| Raspbian 9 Stretch          | *unsupported*  |                        |                       |

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
In general, running Hercules on Windows on a production server is not recommended. Support is maintained for legacy reasons, for developers who prefer to use the Microsoft tools.

| System                     | Support Status | Primary platform until | Supported until |
| -------------------------- | -------------- | ---------------------- | --------------- |
| Windows Server 2022        | **primary**    |                        | 2026-10-13      |
| Windows Server v.20H2      | supported      |                        | 2022-05-10      |
| Windows Server v.2004      | supported      |                        | 2021-12-14      |
| Windows Server v.1909      | *unsupported*  |                        |                 |
| Windows Server v.1903      | *unsupported*  |                        |                 |
| Windows Server 2019        | supported      |                        | 2024-01-09      |
| Windows Server v.1809      | *unsupported*  |                        |                 |
| Windows Server 2016        | supported      | 2022-01-11             | 2027-01-12      |
| Windows Server 2012 R2     | supported      |                        | 2023-10-10      |
| Windows Server 2012        | supported      |                        | 2023-10-10      |
| Windows Server 2008 R2 SP1 | *unsupported*  |                        |                 |
| Windows Server 2008 R2     | *unsupported*  |                        |                 |
| Windows Server 2008 SP2    | *unsupported*  |                        |                 |
| Windows Server 2008        | *unsupported*  |                        |                 |
| Windows 11 v.21H2          | **primary**    | next update            | 2023-10-10      |
| Windows 10 v.21H2          | supported      |                        | 2023-06-13      |
| Windows 10 v.21H1          | supported      |                        | 2022-12-13      |
| Windows 10 v.20H2          | supported      |                        | 2022-05-10      |
| Windows 10 v.2004          | supported      |                        | 2021-12-14      |
| Windows 10 v.1909          | *unsupported*  |                        |                 |
| Windows 10 v.1903          | *unsupported*  |                        |                 |
| Windows 10 v.1809          | *unsupported*  |                        |                 |
| Windows 10 v.1803          | *unsupported*  |                        |                 |
| Windows 10 v.1709          | *unsupported*  |                        |                 |
| Windows 10 v.1703          | *unsupported*  |                        |                 |
| Windows 10 v.1607          | *unsupported*  |                        |                 |
| Windows 10 v.1511          | *unsupported*  |                        |                 |
| Windows 10 v.1507          | *unsupported*  |                        |                 |
| Windows 8.1                | supported      |                        | 2023-01-10      |
| Windows 8                  | *unsupported*  |                        |                 |
| Windows 7 SP1              | *unsupported*  |                        |                 |
| Windows Vista SP2          | *unsupported*  |                        |                 |
| Windows XP SP3             | *unsupported*  |                        |                 |

### Visual Studio

Visual Studio versions are also subject to platform support status. The latest version of Visual Studio (unless there are existing issues) is the primary platform, while older versions are supported at the discretion of the development team and may become unsupported as soon as they are out of their Mainstream Support period.
Support for more than three versions of Visual Studio won't be guaranteed in any case. As such, when a new version is released, the currently oldest supported version may be dropped.

| Version                          | Support Status | Primary platform until       | Supported until               |
| -------------------------------- | -------------- | ---------------------------- | ----------------------------- |
| Visual Studio 2022 Version 17.0  | **primary**    | next release                 | 2023-07-11 or next 3 releases |
| Visual Studio 2019 Version 16.11 | supported      |                              | 2029-04-10 or next 3 releases |
| Visual Studio 2019 Version 16.9  | *unsupported*  |                              |                               |
| Visual Studio 2019 Version 16.7  | *unsupported*  |                              |                               |
| Visual Studio 2019 Version 16.4  | *unsupported*  |                              |                               |
| Visual Studio 2019 Version 16.0  | *unsupported*  |                              |                               |
| Visual Studio 2017 Version 15.9  | supported      |                              | 2027-04-13 or next 3 releases |
| Visual Studio 2017 Version 15.0  | *unsupported*  |                              |                               |
| Visual Studio 2015 Update 3      | *unsupported*  |                              |                               |
| Visual Studio 2015 Update 2      | *unsupported*  |                              |                               |
| Visual Studio 2015               | *unsupported*  |                              |                               |
| Visual Studio 2013 Update 5      | *unsupported*  |                              |                               |
| Visual Studio 2013 Update 4      | *unsupported*  |                              |                               |
| Visual Studio 2013               | *unsupported*  |                              |                               |
