# Access Sui Data

---

### What Is Sui Network Data?

- **Sui Network Data** includes information such as:
  - **Transactions:** Records of every action on the network.
  - **Checkpoints:** Snapshots of the network’s state at different times.
  - **Objects & Events:** Details about assets, tokens, or other activities on the network.

You can use this information to build applications, analyze network behavior, or audit the network.

---

### How Can You Access This Data?

There are three main ways:

1. **Direct Connection (JSON-RPC):**
   - **What It Is:**  
     Connect directly to Sui Full nodes using a JSON-RPC interface to request data (like transaction details) in real-time or from history.
   - **Important Note:**  
     The amount of historical data available depends on how each node is set up. Sometimes, old data might not be kept for very long.

2. **Custom Indexer:**
   - **What It Is:**  
     Set up your own service (or use one provided by others) that constantly collects Sui data and stores it in a relational database (like Postgres).
   - **Why Use It:**  
     This method gives you more control:
     - You decide which data to store.
     - You can choose how long the data remains available.
     - You can optimize queries for your specific needs.
   - **Remember:**  
     Running your own indexer means you’re also managing and paying for the required infrastructure.

3. **Future Data Access Interfaces (Beta/Alpha Stages):**
   - **gRPC API:**  
     - **What It Will Do:**  
       Provide a faster and more reliable way to stream data in real time without frequent polling (repeatedly asking for data).
     - **Status:**  
       Currently in beta (testing stage) and will eventually replace JSON-RPC.
   - **GraphQL RPC:**  
     - **What It Will Do:**  
       Allow you to fetch data using GraphQL, which is especially handy for web apps since it lets you combine data from different sources in one go.
     - **Status:**  
       Available in alpha (early testing) and built on a new version of the indexing system (Indexer 2.0).

---

### When to Use Which Method?

- **For Simple Data Needs:**  
  JSON-RPC might be enough if you only need basic real-time or recent data.
- **For Advanced or Custom Requirements:**  
  A custom indexer lets you tailor data storage and queries exactly to your application’s needs.
- **For Future-Proofing or Real-Time Streams:**  
  The gRPC API or GraphQL RPC will eventually offer better performance and flexibility, especially if you need live updates or complex data queries.

---

### Summary Timeline for Future Interfaces:

- **gRPC API:**  
  - Beta testing starts soon.
  - Will fully replace JSON-RPC within the next couple of years.
- **GraphQL RPC:**  
  - Expected to mature from alpha to a more stable version by late 2025.
- **JSON-RPC:**  
  - Currently available but planned to be phased out in favor of the newer methods.

---

This simplified guide should help you understand the basic ways to access data on the Sui network and decide which method might work best for your project or application. Enjoy exploring Sui data!
