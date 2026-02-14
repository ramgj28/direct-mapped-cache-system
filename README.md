# Direct-Mapped Cache Memory System (Verilog)

## Overview

This project implements a **Direct-Mapped Cache Memory System** in Verilog HDL. The design models a simplified memory hierarchy consisting of:

- 8-line cache memory  
- Tag memory with valid bits  
- 64-byte main memory  
- Hit/Miss detection logic  
- Write-allocate behavior on cache miss  

The controller performs tag comparison for each read request and automatically updates the cache on a miss. The architecture demonstrates key hardware concepts used in processor cache design, including address decomposition, block indexing, tag validation, and memory synchronization.

### Architecture Summary

- **Address Width:** 6 bits  
- **Cache Lines:** 8  
- **Data Width:** 8 bits  
- **Main Memory Size:** 64 bytes  
- **Mapping Policy:** Direct-Mapped  
- **Write Policy:** Write-Allocate  

### Address Breakdown

| Bits  | Field  |
|--------|--------|
| [5:3] | Tag    |
| [2:0] | Index  |


##  Module Descriptions

- **`direct_cmem`** – Top-level direct-mapped cache controller that integrates tag memory, cache memory, and main memory to perform hit/miss detection and data selection.

- **`cache_mem`** – 8-line data storage array that holds cached data indexed by address for fast access.

- **`main_mem`** – 64-byte backing memory that serves as the lower-level storage for cache refills and write operations.

- **`tag_mem`** – Tag array with valid bits used to compare incoming address tags and generate cache hit or miss signals.
 
