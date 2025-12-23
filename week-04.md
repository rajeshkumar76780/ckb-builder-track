# Week 04  
**Date:** 16th Dec – 23rd Dec, 2025

## Topics Studied

### CKB Quick Start (Overview)  
- Went through the **CKB Quick Start** guide from the official Nervos documentation.  
- Gained a high-level understanding of how to:
  - set up a local CKB development environment  
  - run a devnet  
  - interact with CKB using basic tools  
- This served as an introduction before moving deeper into hands-on development.

### OffCKB Tooling  
- Learned about **OffCKB**, a developer tool that simplifies local CKB development.  
- Understood how OffCKB:
  - spins up a local devnet with pre-funded accounts  
  - provides built-in scripts and configuration  
  - reduces setup complexity for beginners  
- Reviewed basic commands for starting, resetting, and debugging a local chain.

### CKB Glossary & Core Concepts (In-depth)  
- Spent significant time studying the **CKB Glossary** to strengthen foundational understanding.  
- Clarified the meaning and purpose of core concepts, including:
  - **Cell**: the fundamental unit of state and storage on CKB  
  - **Capacity**: storage value measured in bytes (1 CKB = 1 Byte)  
  - **Lock Script**: enforces ownership and authorization  
  - **Type Script**: defines rules for how a cell can be used or transformed  
  - **Transaction**: consumes live cells and creates new ones  
  - **Inputs / Outputs**: represent destroyed and newly created cells  
  - **Cell Dependencies (Deps)**: allow scripts to reference external code cells  
  - **CKB-VM**: RISC-V based virtual machine that executes scripts  
  - **Cycles**: measure computational cost of script execution  
- This glossary review helped connect theoretical concepts from the Basic Theory course with practical development terminology.

### Transaction Validation & Debugging Concepts  
- Reviewed how CKB validates transactions through:
  - lock script execution for inputs  
  - type script execution for inputs and outputs  
- Understood how failures occur when:
  - scripts return non-zero values  
  - capacity or structure rules are violated  
- Learned how debugging tools help inspect script execution and cycle usage.

## Summary  
- Strengthened conceptual clarity by deeply reviewing the CKB Glossary.  
- Connected theory (cells, scripts, transactions) with tooling and real-world development flow.  
- Built a stronger foundation for upcoming hands-on smart contract development.
