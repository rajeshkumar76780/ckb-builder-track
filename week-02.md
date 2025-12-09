# Week 02  
**Date:** 1st Dec – 7th Dec, 2025

## Topics Studied

### Started CKB Basic Theory Course  
- I began the Basic Theory course on the official CKB Academy.  
- Completed content up through **Summary 1**.
<img width="1920" height="1080" alt="CKB Basic Theory Course" src="https://github.com/user-attachments/assets/8e909f45-83b6-4202-bc6e-887c01e31f13" />

### What is CKB?  
- CKB is fundamentally a system built on **cells** and **cell transformations**.  
- A **Cell** is the basic unit of CKB, similar to a biological cell or a Bitcoin UTXO.  
- All blockchain state is represented through cells.  
- Transactions simply **spend existing cells** and **create new ones**, regardless of complexity.  
- Unspent cells are **live cells**; spent ones are **dead cells**.  
- Cells store arbitrary data in the `data` field, such as:
  - hashes  
  - text  
  - dates  
  - binary data  
  - executable smart-contract code for CKB-VM  

### What Does a Cell Contain?  
A Cell consists of:
```ts
Cell {
capacity: HexString;
lock: Script;
type: Script;
data: HexString;
}
```

- `capacity` (in bytes; 1 CKB = 1 Byte of storage)  
- `lock` script (default lock controlling ownership)  
- `type` script (optional lock controlling usage rules)  
- `data` (arbitrary bytes)  

Additional details:  
- The total storage used (all four fields) must not exceed the `capacity`.  
- Storage is valuable — large data requires many CKB tokens.  

### How Ownership Works  
Ownership is enforced through scripts (lock / type).  
A script has this structure:
```ts
Script {
code_hash: HexString;
args: HexString;
hash_type: 0 | 1 | 2;
}
```

- `code_hash` identifies which code will run.  
- `args` are parameters (e.g. a public-key hash).  
- When spending a cell, the script executes via CKB-VM:  
  - If it returns `0`, the lock is unlocked → you own/control the cell  
  - Else → unlocking fails  

This allows for cryptographic proof of ownership (public key + signature verification).  
