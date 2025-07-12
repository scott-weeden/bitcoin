# Bitcoin Core integration/staging tree

## Overview
Bitcoin Core is the reference implementation of the Bitcoin protocol. It connects to the peer-to-peer network, validates blocks and transactions, and provides a wallet and graphical user interface. The project is organized into several major subsystems:
- **Kernel:** Validation, block processing, chainstate management
- **Consensus:** Block and transaction rules
- **Wallet:** Key management, address generation, transaction signing
- **Node:** Node state and network logic
- **Policy:** Local relay and mempool rules
- **Util:** Utility functions (hashing, encoding, logging)
- **Index:** Indexers for fast lookup (txindex, address index)
- **Primitives:** Fundamental data types (blocks, transactions)

## Node Types
- **Full Node:** Stores and validates the entire blockchain
- **Pruned Node:** Stores only recent blocks, discards old ones
- **Lightweight Client:** Relies on full nodes for validation

## Security Best Practices
- Always verify binaries and signatures
- Keep your node software up to date
- Use strong passwords and encrypted wallets
- Run nodes on secure, dedicated hardware

## Testing
Bitcoin Core uses unit, functional, integration, and fuzz tests. See `/src/test/README.md` and `/test` for details. CI runs on Windows, Linux, and macOS.

## Community & Support
- [bitcoincore.org](https://bitcoincore.org)
- [BitcoinTalk Forum](https://bitcointalk.org)
- [IRC #bitcoin-core-dev](https://webchat.freenode.net/?channels=bitcoin-core-dev)
- [Transifex](https://explore.transifex.com/bitcoin/bitcoin/)

## License
Released under the MIT license. See [COPYING](COPYING).

For an immediately usable, binary version of the Bitcoin Core software, see
https://bitcoincore.org/en/download/.

What is Bitcoin Core?
---------------------

Bitcoin Core connects to the Bitcoin peer-to-peer network to download and fully
validate blocks and transactions. It also includes a wallet and graphical user
interface, which can be optionally built.

Further information about Bitcoin Core is available in the [doc folder](/doc).

Development Process
-------------------

The `master` branch is regularly built (see `doc/build-*.md` for instructions) and tested, but it is not guaranteed to be
completely stable. [Tags](https://github.com/bitcoin/bitcoin/tags) are created
regularly from release branches to indicate new official, stable release versions of Bitcoin Core.

The https://github.com/bitcoin-core/gui repository is used exclusively for the
development of the GUI. Its master branch is identical in all monotree
repositories. Release branches and tags do not exist, so please do not fork
that repository unless it is for development reasons.

The contribution workflow is described in [CONTRIBUTING.md](CONTRIBUTING.md)
and useful hints for developers can be found in [doc/developer-notes.md](doc/developer-notes.md).

Testing
-------

Testing and code review is the bottleneck for development; we get more pull
requests than we can review and test on short notice. Please be patient and help out by testing
other people's pull requests, and remember this is a security-critical project where any mistake might cost people
lots of money.

### Automated Testing

Developers are strongly encouraged to write [unit tests](src/test/README.md) for new code, and to
submit new unit tests for old code. Unit tests can be compiled and run
(assuming they weren't disabled during the generation of the build system) with: `ctest`. Further details on running
and extending unit tests can be found in [/src/test/README.md](/src/test/README.md).

There are also [regression and integration tests](/test), written
in Python.
These tests can be run (if the [test dependencies](/test) are installed) with: `build/test/functional/test_runner.py`
(assuming `build` is your build directory).

The CI (Continuous Integration) systems make sure that every pull request is tested on Windows, Linux, and macOS.
The CI must pass on all commits before merge to avoid unrelated CI failures on new pull requests.

### Manual Quality Assurance (QA) Testing

Changes should be tested by somebody other than the developer who wrote the
code. This is especially important for large or high-risk changes. It is useful
to add a test plan to the pull request description if testing the changes is
not straightforward.

Translations
------------

Changes to translations as well as new translations can be submitted to
[Bitcoin Core's Transifex page](https://explore.transifex.com/bitcoin/bitcoin/).

Translations are periodically pulled from Transifex and merged into the git repository. See the
[translation process](doc/translation_process.md) for details on how this works.

**Important**: We do not accept translation changes as GitHub pull requests because the next
pull from Transifex would automatically overwrite them again.
