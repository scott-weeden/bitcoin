# kernel/

## Purpose
Contains kernel-level logic for validation, block processing, and chainstate management.

<TODO:  WHAT ARE MEMPOOLS?  WHAT IS A DISCONNECTED TRANSACTION.  WHAT ARE THE PROPERTIES AND CHARACTERISTICS OF A MEMPOOL?>

TODO: copilot - The kernel contains the most vital pieces of the software. For each header file describe the public, private and protected data structures, the data types, other kernel header includes files (in order to understand relationships between the kernel )

TODO: copilot - describe the lonely classes of the kernel. I.E. which of the c++ classes can be compiled by/ and of themselves, having no references to other classes or data types in the project?

## Key Classes
- `ChainstateManager`: Manages multiple chainstates
- `BlockManager`: Handles block storage and retrieval

## Classes and Asymptotic Analysis

### DisconnectedBlockTransactions
Manages transactions disconnected during blockchain reorganizations, storing them temporarily to efficiently re-add unconfirmed transactions to the mempool after a reorg.
- **Complexity:** All main methods (adding/removing transactions, memory limiting) are O(n) in the number of transactions. No nested loops or superlinear complexity. Master Theorem and backwards substitution confirm linearity.

### CCoinsStats / UTXO Stats
Tracks statistics about the UTXO set, including total coins, outputs, and serialized hashes. Used for snapshot validation and chainstate analysis.
- **Complexity:** Iterates over all UTXOs, O(N) where N is the number of UTXOs. No nested loops. Master Theorem confirms O(N).
- **Encryption:** Uses MuHash3072 (not a NIST standard; Bitcoin cryptography is generally based on NIST and IETF standards).

### CChainParams and Derived Classes
Defines network parameters for different Bitcoin networks, including consensus rules, genesis block, and address formats.
- **Complexity:** Initialization and snapshot height queries are O(n) in the number of config entries. No nested loops.

### CTxMemPoolEntry
Stores metadata about transactions in the mempool, including ancestor/descendant relationships, fees, and locktime information.
- **Complexity:** Updates are O(1) or O(log n) due to set operations. No nested loops.

### Notifications
Abstract base class for kernel event notifications, allowing the system to propagate warnings, progress, and errors to higher layers.
- **Complexity:** All notification methods are O(1).

### Warning, MemPoolRemovalReason, ChainstateRole
Enumerations for kernel warnings, mempool removal reasons, and chainstate roles. No algorithmic complexity.

### BlockManagerOpts, ChainstateManagerOpts, MemPoolOptions
Configuration structs for block manager, chainstate manager, and mempool. No algorithmic complexity.

---
## Dynamic Programming and Blockchain
Dynamic programming (DP) stores solutions to subproblems in a table to avoid redundant computation. The blockchain acts as a distributed, append-only DP table: each block contains the solution to the system state at a given time (e.g., UTXO set). Like DP tables, the blockchain allows fast lookup of previously solved states, speeding up validation and consensus.

---
## Standards Commentary
- **Encryption:** Bitcoin Core uses SHA256 (NIST, USA), secp256k1 (SECG, USA), and MuHash (not standardized).
- **Address formats:** Bech32 is managed by IETF/W3C for web standards; Bitcoin's use is community-driven.
- **Serialization:** Bitcoin uses custom serialization, not governed by external standards bodies.

## Exercise
- Trace the flow of block processing from network to disk.
- What is required for initialization in `init/`?

[Next: init](../init/README.md)
