# Get Sui Tokens

---

### Prerequisite
- **Have a Wallet Address:**  
  Make sure you already have a Sui wallet address (see “Get Sui Address” if you need to create one). This address is where your tokens will be sent.

---

### Methods to Request SUI Tokens

#### 1. **Online Faucet**
- **How to Use:**
  1. Visit [https://faucet.sui.io/](https://faucet.sui.io/).
  2. Connect your wallet or paste your wallet address in the field.
  3. Select the correct network (Devnet or Testnet) from the dropdown.
  4. Click the **Request SUI** button.
  5. If you need more tokens, refresh your browser and click the button again (note: requests are rate-limited).

- **Returning Unused Tokens (Testnet Only):**
  - To help keep tokens available for everyone, you can return unused tokens:
    - **Option 1:** Connect your wallet on the faucet page and click **Return tokens to faucet**, then approve the transaction.
    - **Option 2:** Copy the return address provided and send the tokens manually through a separate transaction.

---

#### 2. **Command Line Interface (CLI)**
- **Usage:**
  - Open your terminal and run:
    ```
    sui client faucet
    ```
  - This command uses your active network and active address (configured when you set up your Sui CLI).
  - You can also specify a different address with `--address` or a custom faucet endpoint with `--url`.

---

#### 3. **Discord**
- **Steps:**
  1. Join the Sui Discord server.
  2. Head to the **#devnet-faucet** or **#testnet-faucet** channel.
  3. Send a message formatted as:
     ```
     !faucet <YOUR SUI ADDRESS>
     ```
  - *Note:* New Discord accounts might need to wait for validation before you can use the faucet channels.

---

#### 4. **Using cURL**
- **Command:**
  - Run this command in your terminal (replace `<YOUR SUI ADDRESS>` with your wallet address):
    ```bash
    curl --location --request POST 'https://faucet.devnet.sui.io/v1/gas' \
    --header 'Content-Type: application/json' \
    --data-raw '{
        "FixedAmountRequest": {
            "recipient": "<YOUR SUI ADDRESS>"
        }
    }'
    ```
- **For a Local Network:**  
  Replace the URL with:
  - `http://127.0.0.1:5003/gas` if using **sui-faucet**, or  
  - `http://127.0.0.1:9123/gas` if using **sui**.

---

#### 5. **Using the Sui TypeScript SDK**
- **Example Code:**
  ```javascript
  import { getFaucetHost, requestSuiFromFaucetV0 } from '@mysten/sui/faucet';

  // Request tokens from the Devnet faucet
  await requestSuiFromFaucetV0({
      host: getFaucetHost('devnet'),
      recipient: '<YOUR SUI ADDRESS>',
  });
  ```

---

#### 6. **Local Network Faucet**
- **When Running a Local Sui Network:**  
  Follow the instructions in the “Connect to a Local Network” guide to request tokens from your local faucet.

---

This simplified guide should help you quickly understand and use the different methods available to request free test SUI tokens. Enjoy testing and building with Sui!
