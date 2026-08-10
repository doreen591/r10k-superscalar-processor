# R10K-Style Out-of-Order Superscalar Processor

A Verilog implementation of an out-of-order superscalar processor
inspired by the MIPS R10000 architecture.

## 🚀 Features

- Register renaming
- Reservation stations
- 64-entry Reorder Buffer (ROB)
- Common Data Bus (CDB)
- Out-of-order execution
- In-order retirement
- Branch misprediction recovery
- Precise exceptions
- RAW/WAR/WAW dependency handling

## 🏗️ Architecture

The processor follows an out-of-order execution pipeline:

Fetch → Decode → Rename → Dispatch → Execute → Complete → Retire

Register renaming removes false dependencies, while the ROB ensures that
instructions commit in program order and architectural state remains precise.

## 🔍 Key Design Challenges

### Register Renaming
Used physical/register mapping to eliminate WAR and WAW hazards while
preserving true RAW dependencies.

### Reorder Buffer
Designed a ROB to track speculative instructions and guarantee in-order retirement.

### Branch Recovery
Implemented recovery mechanisms to restore architectural state after
branch mispredictions.

### Precise Exceptions
Exceptions are committed only when the corresponding instruction reaches
the head of the ROB.

## 🧪 Verification

The design was tested using:

- Directed instruction sequences
- Data-dependency tests
- Branch misprediction scenarios
- ROB recovery tests
- Exception-handling tests

## 🛠️ Technologies

`SystemVerilog` `Computer Architecture` `RTL Design` `RISC-V` `Python`

## 📚 Background

Developed as part of graduate-level computer architecture work at
Columbia University.
