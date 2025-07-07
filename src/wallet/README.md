# wallet/

## Purpose
Manages private keys, addresses, and transactions for users. Handles wallet encryption and storage.

## Key Classes
- `CWallet`: Main wallet class
- `CWalletTx`: Wallet transaction
- `LegacyScriptPubKeyMan`, `DescriptorScriptPubKeyMan`: Key management

## Historical Note
- Major wallet structure changes: Descriptor wallets introduced in v0.21.0 (2021)
- Legacy wallets use `wallet.dat` (Berkeley DB); descriptor wallets use `wallet.dat` + descriptors

## Exercise
- Create a new wallet on testnet:
  ```powershell
  .\bitcoin-cli.exe -testnet createwallet "testwallet"
  ```
- List wallet addresses and generate a new one.

## Research
- What are the formats and lengths of private/public keys? Where are they stored?
- How does wallet encryption (e.g., ChaCha) work?

[Next: util/README.md](../util/README.md)
