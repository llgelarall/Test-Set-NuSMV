# Test&Set Registers Implementation and Analysis

## Introduction

This repository contains an implementation of Test&Set registers using the NuSMV model checker. Test&Set registers are fundamental in concurrent programming, providing mutual exclusion and synchronization for shared resources among multiple processes.

The primary objective of this implementation is to demonstrate how Test&Set registers can be utilized to address the mutual exclusion problem in a concurrent system. This report outlines the implementation, describes the modules and processes, and illustrates the application of NuSMV for model checking and property verification.

## Implementation Overview

The implementation consists of two main modules: `main` and `user`. The `main` module represents the overall system, involving multiple processes (`proc1`, `proc2`, and `proc3`) interacting with a shared Test&Set register (`regTS`). The `user` module models the behavior of an individual process and its interactions with the Test&Set register.

### `main` Module

In the `main` module, three processes (`proc1`, `proc2`, and `proc3`) are defined alongside a shared Test&Set register (`regTS`). The initial value of the register is set to `FALSE`, representing an available critical section. An invariant is specified to ensure that all three processes cannot simultaneously be in the critical state (`critState`).

### `user` Module

The `user` module simulates an individual process interacting with the shared Test&Set register. Each process maintains a `state` variable that tracks its current state: `idleState`, `tryState`, or `critState`. Transitions between states are defined based on the current state and the value of the shared register.

### Model Checking and Verification

To verify the correctness of the implementation, the NuSMV model checker is used. The provided commands include simulation (`simulate`) and model checking (`check_invar_bmc`) to analyze system behavior and verify properties. For example, the invariant is checked to ensure that processes do not enter the critical state simultaneously.

## Usage

To run the implementation and perform verification using NuSMV, follow these steps:

1. Install NuSMV (if not installed).
2. Clone this repository and navigate to its directory.
3. Run NuSMV interactively: `./NuSMV -int models/TestAndSet.smv`
4. Execute commands inside NuSMV to simulate, check invariants, and analyze behavior.

## Conclusion

This repository showcases the implementation of Test&Set registers using NuSMV. By modeling concurrent processes and shared resources, mutual exclusion and synchronization are achieved. Formal methods like model checking ensure system correctness and safety, enhancing reliability in real-world applications.

Explore the code and experiment with different scenarios to gain insights into concurrent programming and formal verification techniques.
