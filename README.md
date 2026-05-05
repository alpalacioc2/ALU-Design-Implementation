#  32-bit ALU Design & Implementation (Logisim)

##  Overview
This project implements a fully functional **32-bit Arithmetic Logic Unit (ALU)** using Logisim. The design supports arithmetic, logical, shift, and comparison operations controlled by a 4-bit opcode.

The ALU integrates multiple submodules including adders, shifters, comparators, and multiplexers to produce a 32-bit result along with an overflow flag when applicable.

---

##  Features
- 32-bit arithmetic operations (Addition, Subtraction)
- Logical operations (AND, OR, XOR, NOR)
- Shift operations (Logical & Arithmetic)
- Comparison operations (Equal, Not Equal, Greater Than, Less or Equal)
- Overflow detection for signed arithmetic

---

##  System Architecture

###  LeftShift32
- Performs 32-bit left shift operations  
- Uses a 5-stage multiplexer structure (1, 2, 4, 8, 16 shifts)  
- Supports shift amounts from 0–31  

###  Add32
- Hierarchical design:
  - 1-bit Full Adders → 4-bit → 16-bit → 32-bit  
- Includes overflow detection logic based on MSB conditions  

###  ALU32
- Central unit combining all operations  
- Uses a multiplexer to select output based on opcode  
- Overflow signal enabled only for arithmetic operations  

---

##  Supported Operations

| Opcode | Operation |
|-------|----------|
| 000x  | Shift Left |
| 001x  | Addition |
| 0100  | Logical Right Shift |
| 0101  | Arithmetic Right Shift |
| 011x  | Subtraction |
| 1000  | AND |
| 1001  | Equal |
| 1010  | OR |
| 1011  | Not Equal |
| 1100  | XOR |
| 1101  | Greater Than |
| 1110  | NOR |
| 1111  | Less or Equal |

---

##  Performance
- Critical path dominated by the **32-bit ripple-carry adder**
- Estimated delay: ~65 gate delays  
  - 64 from carry propagation  
  - +1 from output multiplexer  

---

##  Testing
All modules were tested individually and integrated into the final ALU system.  
The design successfully passed all test cases with correct output behavior.

---

##  Key Takeaways
- Reinforced understanding of hierarchical digital design  
- Explored trade-offs of ripple-carry adders vs performance  
- Gained experience with modular circuit design in Logisim  

---

##  Tools Used
- Logisim  
- Digital Logic Design Principles  

---
