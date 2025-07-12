# policy/

## Purpose
Defines policies for transaction relay, fee estimation, and mempool acceptance. These are local node rules, not global consensus rules. Policy modules allow node operators to tune transaction relay, mempool size, and fee estimation for their specific use case.

## Key Modules & Classes
- `PolicyEstimator`: Fee estimation and dynamic fee calculation
- `MempoolPolicy`: Mempool acceptance and transaction filtering
- `EphemeralPolicy`, `RBFPolicy`, `TrucPolicy`: Specialized policies for ephemeral transactions, replace-by-fee, and topologically restricted transactions

## Policy vs Consensus
- **Consensus:** Global rules all nodes must follow (e.g., block validity)
- **Policy:** Local rules for transaction relay and mempool (e.g., minimum fee, RBF opt-in)

## Tuning Policy
- Adjust mempool size, expiry, and relay fee for different node roles (mining, archival, privacy)
- Enable/disable RBF, ephemeral, or truc policies for custom transaction handling

## Exercise
- What is the difference between consensus and policy?
- What does "ephemeral" mean in the context of policy?
- Simulate changing the minimum relay fee and observe which transactions are accepted or rejected.
- Enable/disable RBF and observe mempool behavior.

[Next: index](../index/README.md)
