#Install Sui
---
**Supported Operating Systems:**
- **Linux:** Ubuntu 20.04 (Bionic Beaver) or later
- **macOS:** macOS Monterey or later
- **Windows:** Windows 10 or 11

---

**Quickest Method – Using Package Managers:**

- **For macOS, Linux, or Windows Subsystem for Linux (Homebrew):**
  - Run this in your terminal:
    - `brew install sui`
  
- **For Windows (Chocolatey):**
  - Use the corresponding Chocolatey command to install Sui.

*Note: This quick install method is suitable for most users.*

---

**Using Pre-Built Binaries from GitHub:**

1. **Access the Repository:**
   - Visit [Sui on GitHub](https://github.com/MystenLabs/sui).

2. **Locate the Latest Release:**
   - In the right pane, find the **Releases** section and click on the release tagged **Latest**.

3. **Download the Correct File:**
   - Under Assets, choose the `.tgz` file for your operating system (Linux, macOS, or Windows).

4. **Extract and Prepare:**
   - Extract the files to a directory (e.g., `~/sui`).
   - The folder should include:
     - `sui`
     - `move-analyzer`
     - `sui-bridge`
     - `sui-data-ingestion`
     - `sui-faucet`
     - `sui-graphql-rpc`
     - `sui-node`
     - `sui-test-validator`
     - `sui-tool`
   
5. **Update Your PATH:**
   - Add the folder to your PATH. For example, add this line to your `~/.bashrc` or `~/.zshrc`:
     - `export PATH=$PATH:~/sui`
   - Restart your terminal or run `source ~/.bashrc` (or `source ~/.zshrc`).

6. **MacOS Security (if needed):**
   - If MacOS prevents the binaries from running, execute:
     - `xattr -d com.apple.quarantine ~/sui/*`

7. **Confirm the Installation:**
   - Run:
     - `sui --version`
   - You should see the Sui version displayed.

---

**Installing via Cargo (Rust’s Package Manager):**

1. **Pre-requisite:**
   - Ensure you have [Rust and Cargo](https://www.rust-lang.org/tools/install) installed.
   
2. **Run the Install Command:**
   - In your terminal, execute:
     - `cargo install --locked --git https://github.com/MystenLabs/sui.git --branch testnet sui --features tracing`
   - *Note:* The `tracing` feature is needed for Move test coverage and debugger support.
  
3. **Update Rust (if needed):**
   - Update to the latest stable version:
     - `rustup update stable`
   - This installs Sui binaries in the `~/.cargo/bin` folder.

---

**Building from Source:**

1. **Install Prerequisites:**
   - Ensure you have:
     - **Rust and Cargo**
     - **cURL** (to help install Rust on macOS or Linux)
     - **Homebrew** (for macOS)
     - **CMake**
     - **libpq** (only if using the indexer or GraphQL options)
     - **Git CLI**
     - **PostgreSQL** (if required)
  
2. **For macOS Users with Homebrew:**
   - Install prerequisites with:
     - `brew install curl cmake libpq git`

3. **Follow Build Instructions:**
   - Use the GitHub source and follow the provided instructions to compile and install Sui.

---

**Extra Developer Tools:**

- **VSCode Users:**
  - Install the **Move extension** for language server support, building, testing, and debugging Move code.
  - You can find it by searching `Mysten.move` in the VSCode extension marketplace.

This bullet-point guide should help simplify the installation process of Sui based on your needs and preferred method. Enjoy working with Sui!
