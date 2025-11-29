# Week 01  
**Date:** 24th Nov – 30th Nov, 2025

## Topics Studied

### What is CKB?
- CKB (Common Knowledge Base) is the Layer 1 blockchain of the Nervos Network.
- Core concept: cells and the transformation of cells.
- A **Cell** is the fundamental unit of storage (similar to Bitcoin UTXO).
- State is represented entirely through cells.
- Unspent cells are called **Live Cells**, spent ones are **Dead Cells**.
- Transactions consume old cells and create new ones.
- A cell's `data` field can store:
  - text  
  - hashes  
  - dates  
  - binary code  
  - on-chain executable smart contract code via CKB-VM

### What Does a Cell Contain?
A Cell includes:
- `capacity` in CKBytes (amount of storage)
- `lock script` (defines ownership)
- `type script` (optional logic/rules)
- `data` (arbitrary binary)

Cells are immutable. Updating requires:
1. Consuming the old cell  
2. Creating a new cell with modified data

### How Ownership Works
Ownership is enforced by a lock script.

Default lock script uses:
- secp256k1  
- Blake2b → Blake160  
- `sighash_all` signature scheme  

To spend a cell:
- The transaction must be signed with the corresponding private key.
- The Blake160 hash of the public key must match the `args` in the lock script.

### Where Is Script Code Stored?
- Script code lives in separate code cells.
- Scripts reference this code using:
  - `code_hash`
  - `hash_type`
- Code is loaded at runtime through CKB-VM syscalls.

### If Lock Code Is Lost
If the code cell containing script code is lost:
- Any cell referencing it becomes unspendable.
- Funds become permanently frozen.

### What Is a Transaction?
A transaction:
- consumes input cells
- creates output cells
- must satisfy all lock and type script rules
- requires a valid signature for locked inputs

Transaction lifecycle:
1. Create  
2. Sign  
3. Broadcast  
4. Validate  
5. Propagate (mempool)  
6. Confirm (included in a mined block)

### Role of the Type Script
Type scripts define how a cell can be used.

Examples:
- fungible token logic (UDT)
- NFT rules
- data validation
- custom contract behavior

### CKB-VM
- A RISC-V based virtual machine.
- Executes lock and type scripts.
- Uses syscalls such as:
  - `ckb_load_cell_data()`
  - `ckb_load_witness()`
- Execution result:
  - `0` → success  
  - non-zero → failure  

### Cycles
- Measure computational cost of script execution.
- Each instruction and syscall consumes cycles.
- CKB mainnet block limit: `3,500,000,000` cycles.
- No per-transaction cycle limit.

## Summary of Understanding
- CKB uses a cell-based state model.
- Everything is a cell; transactions transform cells.
- Scripts define ownership and behavior.
- CKB-VM executes low-level RISC-V code for validation.
- Cycles ensure fairness and prevent abuse.
