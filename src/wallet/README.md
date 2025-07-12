# wallet/

## Purpose
Manages private keys, addresses, and transactions for users. Handles wallet encryption, backup, and storage. The wallet subsystem is responsible for generating addresses, signing transactions, and tracking balances.

## Key Classes
- `CWallet`: Main wallet class, manages keys and transactions
- `CWalletTx`: Wallet transaction metadata
- `LegacyScriptPubKeyMan`, `DescriptorScriptPubKeyMan`: Key management for legacy and descriptor wallets

## Wallet Types
- **Legacy Wallets:** Use `wallet.dat` (Berkeley DB), support traditional address formats
- **Descriptor Wallets:** Introduced in v0.21.0, use descriptors for flexible address management
- **Hardware Wallets:** Supported via external signing interfaces

## Encryption & Backup
- Wallets can be encrypted with passphrases (see `encryptwallet` RPC)
- Backup your wallet regularly; descriptor wallets require both `wallet.dat` and descriptor files
- ChaCha20 and AES are used for encryption (see `chacha20.h`)

## Key Management
- Private keys: 256-bit values, stored encrypted
- Public keys: Derived from private keys, used for addresses
- Addresses: Encoded public keys (base58, bech32)

## Historical Note
- Major wallet structure changes: Descriptor wallets introduced in v0.21.0 (2021)
- Legacy wallets use `wallet.dat` (Berkeley DB); descriptor wallets use `wallet.dat` + descriptors

## Exercise
- Create a new wallet on testnet:
  ```powershell
  .\bitcoin-cli.exe -testnet createwallet "testwallet"
  ```
- List wallet addresses and generate a new one.
- Backup and restore a wallet using the CLI.
- Research the formats and lengths of private/public keys. Where are they stored?
- How does wallet encryption (e.g., ChaCha) work?

## Research
- What are the formats and lengths of private/public keys? Where are they stored?
- How does wallet encryption (e.g., ChaCha) work?

[Next: util/README.md](../util/README.md)
