# primitives/

## Purpose
Defines the fundamental data types used throughout Bitcoin Core, such as blocks, transactions, and cryptographic primitives. These types are the building blocks for all higher-level logic in the system.

## Key Classes
- `CBlock`, `CBlockHeader`: Block structure and metadata
- `CTransaction`, `COutPoint`, `CTxIn`, `CTxOut`: Transaction structure and inputs/outputs
- `uint256`, `arith_uint256`: 256-bit integers for hashes and arithmetic

## Class Table
| Class         | Description                                 |
|--------------|---------------------------------------------|
| CBlock       | Represents a block, contains header & txs    |
| CBlockHeader | Metadata for a block (version, prev, merkle) |
| CTransaction | Represents a transaction                     |
| COutPoint    | Reference to a previous output               |
| CTxIn        | Transaction input                            |
| CTxOut       | Transaction output                           |
| uint256      | 256-bit hash value                           |
| arith_uint256| 256-bit arithmetic value                     |

## Serialization
All primitives support custom serialization for efficient disk and network encoding. See `serialize.h` for details.

## Cryptographic Primitives
- Used for block and transaction hashes, signatures, and Merkle trees
- Security relies on SHA256, secp256k1, and other standards

## Exercise
- Locate and read the definitions of `CBlock` and `CTransaction` in the codebase.
- Write a short summary of how a Bitcoin block is structured.
- Parse a raw block and extract its transactions using the primitives.

[Next: consensus](../consensus/README.md)
