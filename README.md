# 3-Stage-pipeline-Risc_V-architecture

## Overview
This repository contains the Verilog implementation of a three-stage pipelined architecture for a RISC-V processor. The design aims to balance simplicity and performance, making it suitable for educational purposes and providing a foundation for understanding pipelined processor architectures.

## Pipeline Stages
### 1. Instruction Fetch (IF)
**Responsibilities:**
- Fetches instructions from the instruction memory (Inst_mem).
- Manages the program counter (PC) for sequential instruction retrieval.

### 2. Instruction Decode and Execute (ID-EX)
**Responsibilities:**
- Decodes instructions and executes arithmetic/logic operations using the ALU.
- Determines branching conditions with the Brn_cond unit.
- Manages control signals for multiplexers and other control-related modules.
**Data Flow:**
- Forwards results from execution to write-back and memory stages.
- Updates the program counter for the next instruction in the instruction fetch stage.
**Control Signals:**
- Manages control signals for synchronization and pipeline control.

### 3. Write Back and Memory (WB-MEM)
**Responsibilities:**
- Completes the instruction execution cycle by writing back results to the register file (Reg_file).
- Manages control signals for write-back and memory access operations.

## Interaction between Stages
**Data Dependency Handling:**
- Implements data forwarding between stages to mitigate data hazards.
- Utilizes stall and flush signals to handle dependencies and maintain data consistency.

**Control Signal Propagation:**
- Propagates control signals through the pipeline stages for coordinated instruction execution.
- Ensures synchronization to maintain proper sequencing of operations.

## Conclusion
This three-stage pipelined RISC-V processor provides an educational and insightful exploration into pipelined processor design. 

## Usage
- Simulate the design using appropriate tools.
- Use the following commands to run the code:
  - vlog *.sv
  -vsim -c -voptargs=+acc tb_processor -do "run -all"
