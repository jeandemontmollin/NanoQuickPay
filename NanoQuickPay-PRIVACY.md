# Nano QuickPay — Privacy Policy

**Last updated:** 10 November 2026  
**Applies to:** Nano QuickPay Chrome extension and macOS companion application, version 0.4.0.

## Overview

Nano QuickPay is a self-custody Nano (XNO) payment tool. It detects Nano payment requests on a web page you choose, communicates with a locally installed macOS helper, and allows you to authorize transactions using Touch ID. This policy describes the data processed by the extension and companion application.

## Data processed and why

- **Payment information:** Your Nano wallet address, account balance, recipient wallet address, payment amount, transaction hash, and confirmation status are processed to display your wallet and initiate or verify payments.
- **Website information:** When you open the extension on a supported web page or rescan the page, it examines payment-related links, elements, visible text, and visible QR codes. To detect QR codes, the extension can capture and analyze an image of the visible tab locally. The full page or screenshot is not intentionally uploaded to the developer. The page URL is passed to the local macOS helper when a payment is initiated; the helper validates the source and stores the website hostname with the transaction record.
- **Local payment history:** The companion application stores outgoing payment details, including timestamp, amount, recipient address, originating website hostname, and transaction hash, on your Mac. It uses this record to display recent payments and enforce spending limits.
- **Preferences and settings:** The extension stores your one-click payment preference locally in Chrome. The companion application stores wallet settings and limits on your Mac.
- **Authentication material:** During wallet setup, a Nano seed may be generated or provided by you to derive the wallet's private key. The seed is not intentionally saved by Nano QuickPay. The private key is stored in your macOS login Keychain, not in the Chrome extension. Touch ID authentication is handled locally by macOS. Nano QuickPay does not obtain or store your fingerprint data.

## Sharing and external services

Nano QuickPay does not sell user data or use it for advertising, profiling, creditworthiness evaluation, or lending.

To function, the companion application contacts a Nano RPC provider to query account state, validate proof-of-work, broadcast signed transactions, and check confirmations. **The default RPC service is `https://rpc.nano.to`**; users can configure a different provider. The provider necessarily receives the information contained in applicable RPC requests and may receive connection metadata, such as your IP address, under its own privacy practices. Transactions broadcast to the Nano network become part of its public ledger, and on-chain transaction data may be visible to others.

Proof-of-work is generated locally by default. If you configure an external proof-of-work provider, the required work parameters and any configured API credentials are sent to that provider. The Chrome extension's detected full page content and screenshots are not intentionally sent to those providers.

## Storage, retention, and deletion

- The Chrome extension stores its user preference in local browser storage.
- The native helper stores configuration, payment history, and proof-of-work cache files under `~/.nano-quickpay` on your Mac.
- The private key is held in the macOS login Keychain and accessed by the native signer following a fresh Touch ID authorization.
- Nano QuickPay does not automatically delete the local payment-history file after a fixed retention period. Removing the Chrome extension does not necessarily remove macOS companion data. The companion uninstaller removes its Keychain item and native registration, but intentionally leaves `~/.nano-quickpay` (including payment history) in place; users can separately remove that folder after making any records they wish to keep.
- Transactions already broadcast to the Nano network cannot be deleted from the public ledger by uninstalling the product.

## Security

The application is designed to keep wallet secrets on the user's Mac and to require Touch ID before the native signer retrieves the private key for transaction signing. Nano QuickPay is experimental beta software; users should test it with small amounts of XNO. No software or network service can guarantee absolute security.

## Chrome Web Store Limited Use

Nano QuickPay uses information accessed through Chrome extension permissions only to provide and support its disclosed Nano payment functionality. The use of information received from Google APIs will adhere to the Chrome Web Store User Data Policy, including the Limited Use requirements. No data is sold or transferred to third parties for advertising or unrelated purposes.

## Changes

This policy may be updated if the extension or companion application's data practices change. The latest policy will be published at this page, with an updated date.

## Contact

**Developer contact:** jean.de.montmollin@hotmail.com
