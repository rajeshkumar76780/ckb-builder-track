# Week 06  
**Date:** 1st Jan - 7th Jan, 2026  

## Topics Studied

### Build DApp Tutorials (Hands-on)
This week, I completed and implemented all the **Build DApp** examples from the CKB documentation, gaining practical experience with cells, transactions, scripts, and full-stack dApp development.

#### 1. View and Transfer a CKB Balance  
- Understood CKB’s **UTXO-like Cell Model**, where each Cell’s `capacity` represents both balance and storage.
- Learned how balance transfers work by:
  - consuming live input cells  
  - creating new output cells for the receiver  
- Set up a local **Devnet** using OffCKB and ran the example dApp.
- Implemented balance transfer logic using the **CCC SDK**, including:
  - generating accounts from private keys  
  - constructing lock scripts (secp256k1 + Blake160)  
  - completing inputs and fees  
  - signing and broadcasting transactions  
- Learned that balances are calculated by summing the capacities of all cells sharing the same lock script.

#### 2. Store Data on a Cell  
- Learned how arbitrary data can be stored in a cell’s `data` field.
- Implemented a dApp that:
  - encodes a text message (e.g., `"Hello CKB!"`) into a hex string  
  - stores it on-chain inside a Cell  
  - retrieves and decodes the stored data back to the original text  
- Reinforced the idea that Cells can store any data format as long as it fits within capacity limits.

#### 3. Create a Fungible Token (xUDT)  
- Learned how CKB implements custom tokens using **User-Defined Tokens (UDTs)**.
- Understood the **xUDT** standard:
  - token balance stored in the cell’s `data` field  
  - token rules enforced via a Type Script  
  - issuer’s Lock Script hash acts as the unique token ID  
- Implemented issuing a fungible token using the pre-deployed xUDT script.

#### 4. Create a DOB (Spore Protocol)  
- Learned about **Spore**, an on-chain Digital Object (DOB) protocol.
- Understood how Spore Cells store assets fully on-chain using:
  - `content-type` and `content` in the data field  
  - immutable cell design  
- Built a dApp using the **Spore SDK** to convert a local image into an on-chain digital object.

#### 5. Build a Simple Lock Script  
- Built a full-stack dApp using a custom **hash_lock** script.
- Learned how:
  - lock scripts enforce ownership through script arguments  
  - unlocking requires providing a valid preimage matching a stored hash  
- Implemented both the on-chain script and a frontend interface to interact with it.
- Understood this as a learning example for lock script mechanics (non-production).
