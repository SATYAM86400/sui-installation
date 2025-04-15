# Connect to Sui Network

- **Networks Available:**
  - **Mainnet:** Production network (no faucet tokens).
  - **Devnet & Testnet:** Test networks for experimenting.  
  - **Localnet:** A local Sui network for development.

- **Connecting via RPC:**
  - Sui nodes use an RPC endpoint in this format:  
    `https://fullnode.<NETWORK-VERSION>.sui.io:443`  
    (Replace `<NETWORK-VERSION>` with devnet or testnet as needed.)

- **Getting Test Tokens:**
  - **Devnet/Testnet:**  
    - Join the respective faucet channels on Discord (devnet-faucet or testnet-faucet) to request free test tokens.
  - **Localnet:**  
    - Use a cURL command to request tokens from your local faucet.
  - *Note: Test tokens have no real financial value.*

- **Using the Sui Command Line Interface (CLI):**
  - **Check Installation:**  
    - Run `which sui` in your terminal.  
    - If installed, it shows the Sui binary path; if not, it gives “sui not found”.
  - **Launch the Sui Client:**  
    - Run the command `sui client` to start configuring the connection.
    - If no configuration file exists, you’ll see a prompt like:  
      `"Config file [<PATH>/client.yaml] doesn't exist, do you want to connect to a Sui Full node server [y/N]?"`  
      - Press **y** and hit **Enter**.
    - When prompted, input the RPC server URL:
      - Press **Enter** to use the default Sui Testnet, or type in another endpoint (for Devnet or custom servers).
    - Next, set an alias for this connection and choose a key scheme (for example, press **0** for ed25519).

- **Customizing Your Connection:**
  - **View Current Environments:**  
    - Run `sui client envs` to see the list of defined networks.
  - **Add a New RPC Endpoint:**  
    - Use:  
      `sui client new-env --alias <ALIAS> --rpc <RPC-SERVER-URL>`
  - **Switch Between Networks:**  
    - Run:  
      `sui client switch --env <ALIAS>`
  - *Tip: If you run into issues, try deleting the configuration directory (`~/.sui/sui_config`) and reinstall the latest Sui binaries.*

