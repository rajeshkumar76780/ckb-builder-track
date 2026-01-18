# Week 07  
**Date:** 11th Jan - 18th Jan, 2026  

## Topics Studied

### CKB Basic Practical Operation Course  
- Completed the **CKB Basic Practical Operation** course on CKB Academy using the **CKB Testnet**.
- Learned how to connect a wallet (MetaMask) to CKB and interact with on-chain data.
- Understood that a wallet’s CKB balance represents the **sum of capacities of all live cells** the wallet can unlock.
- Explored live cells, blocks, and transactions, and inspected their details in JSON format.

### Understanding Transactions  
- Learned that a CKB transaction fundamentally:
  - consumes existing **live cells** as inputs  
  - creates new cells as outputs  
- Understood the concept of **off-chain computing, on-chain verification** by manually constructing transactions.
- Gained clarity on transaction structure, including:
  - `inputs` (outpoints referencing live cells)  
  - `outputs` and `outputs_data`  
  - `cell_deps` for script dependencies  
  - miner fees as the capacity difference between inputs and outputs  

### Manual Transaction Construction & Signing  
- Practiced manually assembling a transaction using JSON format.
- Learned how:
  - input cells reference previous outputs  
  - outputs define new cells with capacity and lock scripts  
  - witnesses provide signatures and proofs  
- Understood the role of **WitnessArgs**, especially the `lock` field used by lock scripts for verification.
- Completed the process of:
  - generating a transaction hash in advance  
  - signing the transaction using the connected wallet  
  - inserting the signature into witnesses  
  - sending the finalized transaction to the CKB testnet  

