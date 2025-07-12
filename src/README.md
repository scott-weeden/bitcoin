# src

Main source code for Bitcoin Core. Contains all core logic, networking, consensus, wallet, and RPC code.

## Subfolders
- `consensus/`: Implements consensus rules for block and transaction validation
- `kernel/`: Core validation, block processing, chainstate management
- `wallet/`: Key management, address generation, transaction signing
- `policy/`: Local relay and mempool rules
- `util/`: Utility functions (hashing, encoding, logging)
- `index/`: Indexers for fast lookup (txindex, address index)
- `primitives/`: Fundamental data types (blocks, transactions)
- `node/`: Node state and network logic

## Entry Points
- `main.cpp`: Application startup
- `validation.cpp`: Block and transaction validation

## Navigation Tips
- Start with `main.cpp` and follow initialization
- Use README.md in each subfolder for details
- See `doc/` for build and usage instructions
