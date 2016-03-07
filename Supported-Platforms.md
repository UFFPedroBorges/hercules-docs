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

- debian 8 'jessie': primary platform (*->supported after version 9 is released*)
- debian 7 'wheezy': supported platform (no known issues; *->unsupported after version 9 is released*)
- debian 6 'squeeze': unsupported

## CentOS and Red Hat Enterprise Linux

The current stable version is a primary platform. The previous stable version is supported, but may require upgrading the development tools. Older versions are unsupported, regardless of upstream support.

- CentOS 7, RHEL 7: primary platform (*->supported after version 8 is released*)
- CentOS 6, RHEL 6: supported platform (recommended upgrade to GCC 4.7 or newer; *->unsupported after version 8 is released*)
- CentOS 5, RHEL 5: unsupported

## Ubuntu Server

The latest LTS version is a primary platform. The latest version -- if not a LTS version --  is a supported platform. The previous LTS version is a supported platform for 4 months after the next version is released. Older versions are unsupported.

- Ubuntu 14.04 LTS Trusty Tahr: primary platform (*->supported after 2016-04; ->unsupported after 2016-08*)
- Ubuntu 15.10 Wily Werewolf: supported platform (no known issues; *->unsupported after 2016-07*)
- Ubuntu 15.04 Vivid Vervet: unsupported
- Ubuntu 14.10 Utopic Unicorn: unsupported
- Ubuntu 13.10 Saucy Salamander: unsupported
- Ubuntu 13.04 Raring Ringtail: unsupported
- Ubuntu 12.10 Quantal Quetzal: unsupported
- Ubuntu 12.04 LTS Precise Pangolin: unsupported

## Gentoo

Gentoo is a rolling release, and has no versions. The stable branch is a primary platform (x86 and amd64), while the unstable (~x86 or ~amd64) is unsupported. Support on other architectures is unknown.

- x86 / amd64: primary (assuming up to date system)
- ~x86 / ~amd64: unsupported

## FreeBSD

The latest FreeBSD release is a primary platform. The previous release is supported, but only for as long as it is supported upstream. Any older versions are unsupported.

- FreeBSD 10: primary (*->supported after version 11 is released*)
- FreeBSD 9: supported (*->unsupported after 2016-12*)
- FreeBSD 8: unsupported

## Mac OS X

The last version of Mac OS X is a primary platform, assuming the latest version os Xcode is installed. The previous version is a supported platform. Older versions are supported

- OS X 10.11 El Capitan: primary platform (*->supported after version 10.12 is released*)
- OS X 10.10 Yosemite: supported platform (*->unsupported after version 10.12 is released*)
- OS X 10.9 Mavericks: unsupported

## OpenBSD

The latest OpenBSD release is supported, but it isn't a primary platform.

## NetBSD

The latest NetBSD release is supported, but it isn't a primary platform.

## Raspbian

Hercules runs on the Raspberry Pi, and was tested on Raspbian. The latest release is a supported platform.

## Other Linux / UNIX Distributions

The status on other linux distributions is unknown. Hercules will likely run on them if they derive from, or use similar versions of the development tools as the previously described platforms.

## Microsoft Windows

Windows (both server and workstation versions) are primary platform, for as long as they're within their upstream Mainstream Support period. Versions within their upstream Extended Support period are supported. Older versions are unsupported.

- Windows Server 2012: primary (*->supported after 2018-01-09*)
- Windows Server 2008 R2: supported (*->unsupported after 2020-01-14*)
- Windows Server 2003 R2: unsupported
- Windows 10: primary (*->supported after 2020-10-13*)
- Windows 8.1: primary (*->supported after 2018-01-09*)
- Windows 7: supported (*->unsupported after 2020-01-14*)
- Windows Vista: supported (*->unsupported after 2017-04-11*)
- Windows XP: unsupported

### Visual Studio

Visual Studio versions are also subject to platform support status. The latest version of Visual Studio (unless there are existing issues) is the primary platform, while older versions are supported at the discretion of the development team and may become unsupported as soon as they are out of their Mainstream Support period.

- Visual Studio 2015: supported (*aiming to move to primary platform*)
- Visual Studio 2013: primary (*->supported after version 2015 becomes a primary platform*)
- Visual Studio 2012: supported (*->unsupported likely after 2018-01-09*)
- Visual Studio 2010: unsupported (currently working for legacy reasons)
- Visual Studio 2008: unsupported (likely not working)
