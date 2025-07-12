# index/

## Purpose
Provides indexers for blockchain data (e.g., address index, txindex, block filter index) to speed up lookups and enable advanced queries. Indexes are optional but improve performance for certain RPCs and wallet operations.

## Key Classes
- `BaseIndex`: Abstract base class for all indexes
- `TxIndex`: Indexes transactions by txid for fast lookup
- `BlockFilterIndex`: Indexes block filters for compact block filtering

## How Indexes Work
- Indexes are built during initial sync and updated as new blocks arrive
- Queries use indexes for O(1) or O(log n) lookup instead of linear scans
- Indexes require extra disk space and maintenance

## Trade-offs
- Faster queries (e.g., `getrawtransaction`, `getblockfilter`)
- Increased disk usage and longer initial sync
- Potential for index corruption if not maintained

## Performance Note
- Indexes improve lookup speed (O(1) or O(log n)), but require extra storage and maintenance.
- Recovery tools are available for rebuilding indexes if needed

## Exercise
- Enable `txindex` in your testnet node and query a transaction by txid.
- What are the trade-offs of enabling indexes?
- Benchmark query speed with and without indexes.
- Simulate index corruption and use recovery tools.

[Next: kernel/README.md](../kernel/README.md)
