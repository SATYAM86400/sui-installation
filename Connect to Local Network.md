# Connect to Local Network

- **Prerequisite:**  
  Ensure you have Sui CLI installed before proceeding.

- **Starting the Local Network:**  
  - Run this command to start your local network with a faucet and a brand-new genesis:  
    ```
    RUST_LOG="off,sui_node=info" sui start --with-faucet --force-regenesis
    ```  
    - **--with-faucet:** Starts the faucet service so you can request test SUI.  
    - **--force-regenesis:** Creates a new network state each time (no data persistence).  
    - The `RUST_LOG` flag controls logging—remove it if you prefer more detailed logs.

- **Persisting Data (Optional):**  
  - If you want to save your network's history between restarts, simply omit the `--force-regenesis` flag.  
  - By default, Sui looks for a config in `~/.sui/sui_config`; if it exists, it will continue using the existing genesis data.

- **Customizing Your Local Network:**  
  - You can add extra options, such as starting an indexer (`--with-indexer`) or a GraphQL server (`--with-graphql`).  
  - Some of these services may require additional software like PostgreSQL or libpq.

- **Accessing Your Local Full Node:**  
  - Test the connection by running a `curl` command:  
    ```
    curl --location --request POST 'http://127.0.0.1:9000' \
      --header 'Content-Type: application/json' \
      --data-raw '{
        "jsonrpc": "2.0",
        "id": 1,
        "method": "sui_getTotalTransactionBlocks",
        "params": []
      }'
    ```  
    - A successful response shows your current transaction count.

- **Connecting Sui CLI to the Local Network:**  
  - Create a new environment alias for your local network:  
    ```
    sui client new-env --alias local --rpc http://127.0.0.1:9000
    ```  
  - Switch to the new local environment:  
    ```
    sui client switch --env local
    ```  
    - Verify the active environment with:  
      ```
      sui client active-env
      ```  

- **Working with Your Local Address & Faucet:**  
  - Check your active address (the one used for transactions) by running:  
    ```
    sui client active-address
    ```  
  - Request test coins (gas) by executing:  
    ```
    sui client faucet
    ```  
    - Then, verify your gas coins with:  
      ```
      sui client gas
      ```

- **Optional: Generating Example Data:**  
  - To populate your local network with sample data, start the local network with extra options:  
    ```
    sui start --force-regenesis --with-faucet --with-indexer --with-graphql
    ```  
  - Then, from the Sui root folder, run:  
    ```
    pnpm --filter @mysten/sui test:e2e
    ```

- **Monitoring Your Network:**  
  - Use one of the network explorers (e.g., Polymedia Explorer, Sui Explorer, suoscan, SuiVision) locally or by setting your local RPC URL (http://127.0.0.1:9000).

- **Troubleshooting:**  
  - If you see an error like “fetch is not defined,” make sure you're running Node.js 18, as older versions may cause issues.

- **Note on the Sui TypeScript SDK:**  
  - If you plan to test your dApps with the SDK, double-check that you’re using the latest experimental version from the Sui NPM registry, as it might differ from the published version.

This guide should help you set up and connect to your local Sui network quickly and easily. Enjoy testing and building with Sui!
