# Bitcoin Core Two-Week Hands-On Course

Welcome to the Bitcoin Core hands-on course! This program is designed for programmers (junior to senior) to learn Bitcoin’s architecture, codebase, and testnet experimentation through guided markdowns, diagrams, and exercises.

## Prerequisites
- Basic C++ and command-line experience
- Git and build tools (CMake, MSVC/GCC/Clang)
- Curiosity and willingness to experiment

## Syllabus Overview

### **Week 1: Foundations & Core Concepts**
- **Day 1:** Project structure, build, and run on testnet
- **Day 2:** Data types and primitives (`primitives/`)
- **Day 3:** Consensus and block structure (`consensus/`, `CBlock`, `CBlockHeader`)
- **Day 4:** Wallets, key formats, and encryption (`wallet/`, `util/`)
- **Day 5:** Networking and P2P (`net/`, `policy/`)

### **Week 2: Advanced Topics & Experiments**
- **Day 6:** Scripting, transactions, and Merkle roots (`script/`, `CTransaction`)
- **Day 7:** Indexes, performance, and database schemas (`index/`, `kernel/`)
- **Day 8:** Security, ephemeral keys, and ChaCha encryption (`secp256k1/`, `util/`)
- **Day 9:** Testing, debugging, and extending Bitcoin Core (`test/`, `univalue/`)
- **Day 10:** Capstone: Build, mine, and analyze blocks on testnet

## How to Use This Course
- Each folder contains a `README.md` with explanations, diagrams, and exercises.
- Follow the daily plan, complete exercises, and experiment on testnet.
- Use the provided diagrams (Mermaid/draw.io) for visualization.

## Final Project & Assessment
- On the last day, you’ll run a full node on testnet, mine blocks, inspect transactions, and answer a set of review questions.

---

**Start with Day 1 in the `README.md` of the project root, then follow the links to each folder’s guide.**

---

*For questions, see the [Bitcoin Developer Documentation](https://developer.bitcoin.org/devguide/) and [Bitcoin Core Docs](https://bitcoincore.org/en/doc/).*
