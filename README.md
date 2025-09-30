ITSME Coin - Privacy-Enhanced Cryptocurrency
=====================================
https://bitcoincore.org

For an immediately usable, binary version of the ITSME Coin software, see
https://bitcoincore.org/en/download/.

What is ITSME Coin?
---------------------

ITSME Coin is a privacy-focused cryptocurrency based on Bitcoin Core technology. It connects to the peer-to-peer network to download and fully validate blocks and transactions. It also includes a wallet and graphical user interface, which can be optionally built.

**Enhanced Privacy Features:**

ITSME Coin is committed to providing users with enhanced privacy and anonymity features:

- **Planned Tor Integration**: Native support for routing transactions through the Tor network to protect user IP addresses and enhance anonymity
- **Planned CoinJoin Support**: Implementation of CoinJoin protocol to break the link between transaction inputs and outputs, making it harder to trace fund flows
- **Future Privacy Upgrades**: Ongoing research into additional privacy technologies to ensure maximum user protection

Further information about ITSME Coin is available in the [doc folder](/doc).

## Privacy Roadmap

### Short-term Goals (Q1-Q2 2026)

- Complete Tor network integration for all node communications
- Implement basic CoinJoin mixing protocol
- Add privacy-focused RPC commands
- Develop user documentation for privacy features

### Medium-term Goals (Q3-Q4 2026)

- Enhanced CoinJoin with multi-party coordination
- Privacy metrics and analysis tools
- Integration with privacy-focused wallets
- Stealth address support

### Long-term Vision (2027 and beyond)

- Research and potential implementation of zero-knowledge proofs
- Cross-chain privacy bridges
- Advanced cryptographic privacy enhancements
- Quantum-resistant privacy features

## Rewards and Incentives for Privacy Contributors

ITSME Coin recognizes that privacy is a community effort. We welcome and reward contributors who help us build and strengthen our privacy features.

### Bug Bounty Program

We maintain an active bug bounty program for security and privacy vulnerabilities:

- **Critical Privacy Vulnerabilities**: Up to 10,000 ITSME
- **High-Severity Issues**: Up to 5,000 ITSME
- **Medium-Severity Issues**: Up to 2,000 ITSME
- **Low-Severity Issues**: Up to 500 ITSME

All vulnerability reports should be submitted confidentially through our [SECURITY.md](SECURITY.md) process.

### Development Grants

We offer grants for contributors working on significant privacy enhancements:

- **Major Feature Implementation**: Grants for implementing complete privacy features from our roadmap
- **Research Contributions**: Funding for original research into privacy-enhancing technologies
- **Documentation & Education**: Rewards for comprehensive privacy documentation and educational materials

### Open Collaboration

We believe in open collaboration and encourage community participation:

- Regular Community Calls: Join our monthly privacy development meetings
- Mentorship Program: Experienced developers available to guide new contributors
- Recognition: Top contributors featured in release notes and project documentation

### Have an Idea?

We invite the community to propose innovative ideas for privacy upgrades!

- Submit Enhancement Proposals: Open an issue with the "privacy-enhancement" label
- Join the Discussion: Participate in our [Discussions](/discussions) to share your ideas
- Collaborate on RFCs: Help shape the future of ITSME Coin privacy through Request for Comments

Whether you're a cryptography expert, a privacy advocate, or a developer passionate about financial freedom, your contributions are valued. Together, we can build the most privacy-respecting cryptocurrency ecosystem.

For more information on how to contribute, see [CONTRIBUTING.md](CONTRIBUTING.md).

## Repository Structure

Understanding the repository structure is essential for effective contribution. This section outlines the fundamental folders and files, along with recommendations for keeping the repository clean and focused.

### Core Folders and Files

These are the essential components of the ITSME Coin repository:

- **`src/`** - Contains all source code for the ITSME Coin core implementation
  - This is where the main cryptocurrency logic, network protocol, consensus rules, and wallet functionality reside
  - Contributors should focus their development efforts here for core features

- **`doc/`** - Complete documentation for ITSME Coin
  - Build instructions, API documentation, release notes, and technical specifications
  - Essential reading for both users and developers

- **`share/`** - Platform-specific resources
  - Icons, desktop files, and other resources for GUI applications
  - Important for user-facing application deployment

- **`CMakeLists.txt`** - Main build configuration file
  - Defines how the project is compiled and built
  - Required for building the software from source

- **`README.md`** - This file - project overview and quick start guide

- **`CONTRIBUTING.md`** - Guidelines for contributing to the project

- **`COPYING`** - MIT License terms

- **`INSTALL.md`** - Installation instructions

### Optional/Legacy Folders

The following folders may not be necessary for all development workflows:

- **`test/`** - Integration and functional tests
  - While testing is important, extensive test suites may not be needed for all forks
  - Consider if your project requires the full test suite

- **`contrib/`** - Community contributed tools and utilities
  - Contains various helper scripts and tools
  - May include tools not relevant to your specific fork

- **`.tx/`** - Transifex translation configuration
  - Used for managing translations through the Transifex platform
  - Not needed if you're not actively managing translations

- **`ci/`** - Continuous Integration scripts
  - GitHub Actions and CI/CD configurations
  - May need customization for your specific workflow

### Repository Cleanup Recommendations

**For Contributors**: We encourage contributors to focus their efforts on the core functionality:

- **Primary Focus Areas**: `src/`, `doc/`, `share/`, build files (`CMakeLists.txt`)
- **Documentation**: Always update relevant documentation in `doc/` when modifying core features
- **Testing**: While `test/` exists, focus on testing code changes in `src/` directly

**Repository Maintenance Notes**:

If you're maintaining your own fork and want a leaner repository:

1. **Consider Manual Removal** of unused directories:
   - If not using Transifex: Remove `.tx/`
   - If not maintaining the full test suite: Consider removing or minimizing `test/`
   - If not using contributed tools: Review and possibly remove `contrib/`

2. **Before Removing**, consider:
   - Do you need the CI/CD pipeline? (`.github/`, `ci/`)
   - Will you maintain compatibility with upstream Bitcoin Core?
   - Do you need the full test coverage for your fork?

3. **Cleaning Process**:
   ```bash
   # Example commands (use with caution):
   git rm -r .tx/          # Remove Transifex configuration
   git rm -r contrib/      # Remove contributed tools
   git commit -m "Clean up unused directories"
   ```

**Important**: Before removing any directories, ensure they're not required by your build system or dependencies. Some folders may be referenced in CMake or other configuration files.

### Focus Areas for ITSME Coin

For ITSME Coin specifically, contributors should concentrate on:

- **Privacy features** in `src/` - Tor integration, CoinJoin implementation
- **Privacy documentation** in `doc/` - User guides and technical specifications
- **Core consensus** and network protocol modifications for privacy
- **Wallet enhancements** for privacy-preserving transactions

By maintaining focus on these core areas, we can build a robust privacy-focused cryptocurrency while keeping the repository manageable and contributor-friendly.

License
-------

ITSME Coin is released under the terms of the MIT license. See [COPYING](COPYING) for more
information or see https://opensource.org/license/MIT.

Development Process
-------------------

The `master` branch is regularly built (see `doc/build-*.md` for instructions) and tested, but it is not guaranteed to be
completely stable. [Tags](https://github.com/bitcoin/bitcoin/tags) are created
regularly from release branches to indicate new official, stable release versions of ITSME Coin.

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
These tests can be run (if the [test dependencies](/test) are installed) with: `build/test/functional/test_runner.py` (assuming build is your build directory).

The CI (Continuous Integration) systems make sure that every pull request is tested on Windows, Linux, and macOS. The CI must pass on all commits before merge to avoid unrelated CI failures on new pull requests.

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
