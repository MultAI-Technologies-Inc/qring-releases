# QRing Network Releases

Official binaries for the QRing Network Rust implementation.

## Latest Release: v0.2.0.4-rust_pure

This release features the first 100% pure-Rust build of the QRing daemon, featuring:
- **Pure Rust Consensus**: RandomX and CryptonightR ported to native Rust.
- **Post-Quantum Security**: Integrated ML-KEM and ML-DSA via PQClean.rs and Lantern.rs.
- **Optimized P2P**: Full Levin protocol implementation.
- **Thread-Safe Storage**: High-performance RocksDB backend.

## Installation Instructions

### Linux (x64)

1. **Download the binary**:
   Download `qring-daemon-linux-x64` from the [Releases](https://github.com/MultAI-Technologies-Inc/qring-releases/releases) page.

2. **Make it executable**:
   ```bash
   chmod +x qring-daemon-linux-x64
   ```

3. **Run the daemon**:

   **For Stagenet (Recommended for testing):**
   ```bash
   ./qring-daemon-linux-x64 --stagenet
   ```

   **For Mainnet:**
   ```bash
   ./qring-daemon-linux-x64 --mainnet
   ```

4. **Configuration**:
   The daemon will automatically connect to `seeds.qring.io` and begin synchronization. Data will be stored in `qring_data_stagenet` (for stagenet) or `qring_data` (for mainnet).

### Prerequisites
- **GLIBC 2.31+**: Most modern Linux distributions (Ubuntu 20.04+, Debian 11+, etc.) are supported.
- **AVX2/AVX-512 Support**: The daemon automatically detects and utilizes hardware acceleration for PQC primitives.

### Firewall Settings
Ensure the following ports are open for incoming connections:
- **Mainnet**: 18080 (P2P), 18081 (RPC)
- **Stagenet**: 38080 (P2P), 38081 (RPC)
- **Testnet**: 28080 (P2P), 28081 (RPC)
