# index/

## Purpose
Provides indexers for blockchain data (e.g., address index, txindex) to speed up lookups.

## Key Classes
- `BaseIndex`: Base class for indexes
- `TxIndex`, `BlockFilterIndex`: Specific index types

## Performance Note
- Indexes improve lookup speed (O(1) or O(log n)), but require extra storage and maintenance.

## Exercise
- Enable `txindex` in your testnet node and query a transaction by txid.
- What are the trade-offs of enabling indexes?

[Next: kernel/README.md](../kernel/README.md)
