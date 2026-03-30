# blackparrot-uvm-gsoc2026
GSoC 2026 proposal — UVM Testbenches for BlackParrot RISC-V Multicore |  Verilator UVM exploration across ALU, BHT, and CCE modules with findings  and wishlist for Verilator UVM feature development.   
#gsoc2026 uvm systemverilog verilator blackparrot risc-v verification  formal-verification open-source-hardware fossi.


# BlackParrot UVM Testbenches — GSoC 2026

**Organization:** FOSSi Foundation  
**Project:** BlackParrot UVM Testbenches  
**Mentor:** Dan Ruelas-Petrisko  
**Applicant:** Harshitha  
**Duration:** 175 hours (Medium)  

---

## Project Overview

BlackParrot is an open-source Linux-capable RISC-V multicore processor.
Verilator has newly added UVM support. This project develops UVM 
testbenches for key BlackParrot modules and compiles a wishlist of 
new UVM features needed in Verilator.

---

## Target Modules

### Module 1 — Integer ALU (bp_be_pipe_int)
- Starter module, simple interface, proof of concept
- UVM components: Sequence, Driver, Monitor, Scoreboard, Coverage

### Module 2 — Branch History Table (bp_fe_bht)  
- Stateful module, GSELECT algorithm
- 4 test sequences: always-taken, always-not-taken, alternating, random

### Module 3 — Cache Coherence Engine (bp_cce_wrapper)
- Primary target, BedRock protocol, multi-agent environment
- LCE agent + Memory agent + Scoreboard for coherence rule checking

---

## Verilator UVM Findings

| # | Finding | Impact |
|---|---------|--------|
| 1 | `--uvm` flag not supported → manual library path config required | Setup complexity |
| 2 | `` `uvm_component_utils ``, `` `uvm_fatal ``, `repeat()` not recognized | Core UVM macros broken |
| 3 | Coverpoint bin specifications silently ignored (COVERIGN warning) | Coverage unreliable |

These 3 findings form the **Verilator UVM Wishlist** — a core deliverable.

---

## Timeline

| Weeks | Tasks |
|-------|-------|
| 1-2 | ALU testbench + Verilator UVM exploration + findings |
| 3-8 | CCE testbench — LCE agent, memory model, BedRock scoreboard |
| 9-12 | BHT testbench — 4 sequences, prediction accuracy, final docs |

---

## Diagrams
See `/diagrams` folder for UVM component block diagrams.

---

## Skills
SystemVerilog, Verilator, UVM, RISC-V, Computer Architecture
