# Week 03  
**Date:** 8th Dec – 15th Dec, 2025

## Topics Studied

### Completed CKB Basic Theory Course  
- Completed the remaining sections of the **CKB Basic Theory** course on CKB Academy.  
- Previously covered **Summary 1** in Week 2 and skimmed it again for revision.  
- Finished the course with **Summary 2**, completing the full theoretical module.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e0417ad9-9e3a-4bc1-86f6-d347f2c91537" />

### Where Is the Code Actually Located?  
- Script code is not stored directly in transactions.
- Code is stored in separate **dep cells** and referenced using:
  - `code_hash`
  - `hash_type`
- The CKB-VM locates and loads the required code at runtime using these references.

### What If the Lock Code Is Lost?  
- If the code cell containing the lock script is lost or unavailable:
  - All cells referencing that code become **unspendable**.
  - Locked funds are permanently frozen.
- This highlights the importance of reliable script code management.

### What Is a Transaction?  
- A transaction fundamentally:
  - consumes existing cells
  - creates new cells
- Transactions represent state changes by destroying old cells and generating new ones.
- Lock scripts run for all input cells, while type scripts run for both inputs and outputs.

### Role of the Type Script  
- Each cell can carry two scripts:
  - **Lock Script** (mandatory): protects ownership
  - **Type Script** (optional): enforces cell transformation rules
- Differences in execution:
  - Lock scripts validate ownership.
  - Type scripts define how cells may be created or transformed.
- This separation enables flexible smart contract design.

