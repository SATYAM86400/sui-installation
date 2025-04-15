# Get Sui Tokens

- **What is a Sui Address?**
  - It uniquely identifies your account on the Sui blockchain.
  - It’s used to store and spend SUI tokens.
  - A Sui address is 32 bytes long and usually shown in hexadecimal (e.g., starting with "0x").
  - You can create and manage multiple Sui addresses.

- **How to Get a Sui Address**

  1. **Using the Sui Wallet (Browser Extension)**
     - Install the Sui Wallet Chrome extension.
     - Open the extension and choose one of these options:
       - **ZkLogin:** Use your Gmail, Twitch, or Facebook account.
       - **New Passphrase Account:** Select “More Options” then “Create a new passphrase account” and follow the prompts.
     - Your Sui Wallet will generate a unique address for you.
  
  2. **Using the Command Line Interface (CLI)**
     - When you first run the Sui CLI, it will prompt you to set up your local wallet.
     - The CLI automatically generates a new Sui address along with a secret recovery phrase.
       - **Important:** Write down and securely store the secret recovery phrase.
     - To manually generate a new address, run:
       ```
       sui client new-address ed25519
       ```
     - To view all generated addresses in your local wallet, use:
       ```
       sui keytool list
       ```
     - Note that your private keys are saved locally in the file:
       ```
       ~/.sui/sui_config/sui.keystore
       ```
       - Keep this file secure to prevent unauthorized access to your account.

This guide should help you quickly understand how to obtain a Sui address either through the browser wallet or the CLI.
