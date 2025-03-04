# 4-bit Microcontroller Simulator

This is a playful project—a 4-bit microcontroller simulator built using HTML, CSS, and JavaScript. It provides an interactive environment to explore the fundamentals of microcontroller programming with a simplified instruction set and a visual memory map.

## 🔹 Overview

The simulator mimics a simple 4-bit microcontroller with a limited set of instructions, including:
- **MOV, ADD, SUB, AND, OR** – Basic arithmetic and data movement.
- **CMP** – Compare a register with zero.
- **JMP, JZ, JNZ** – Unconditional and conditional jumps.
- **LOAD & STORE** – Read from and write to a simulated RAM (16 memory cells).

A **Fibonacci example (6 iterations)** demonstrates how the simulator works.

## ✨ Features

✔️ **Interactive Code Editor** – Write and edit microcontroller assembly code.  
✔️ **Visual Debugging** – View registers, flags, and memory changes in real time.  
✔️ **Step-by-Step Execution** – Run code instruction by instruction or continuously.  
✔️ **Built-in Examples** – Quickly load pre-written programs via a combobox.  
✔️ **Memory Map** – Simulated RAM (16 cells) for LOAD and STORE operations.  

### 🖥️ Try it live:  
🔗 [**4-bit Microcontroller Simulator**](https://brunovmcastanho.github.io/uC-Simulator/uC.html)

## 🚀 Getting Started

### 1️⃣ Run the Simulator  
No installation needed! Open the live demo or download and run locally.

### 2️⃣ Local Installation  
Clone the repository and open `uC.html` in your browser:

```bash
git clone https://github.com/brunovmcastanho/uC-Simulator.git
cd uC-Simulator
open uC.html  # (or manually open in your browser)
```

## 🛠️ Instruction Set

- **MOV Rd, Rs** – Move data between registers.  
- **MOV Rd, #n** – Load an immediate value (0-15) into a register.  
- **ADD Rd, Rs** – Add the value from one register to another.  
- **SUB Rd, Rs** – Subtract the value of one register from another.  
- **AND Rd, Rs / OR Rd, Rs** – Perform bitwise operations.  
- **CMP Rs** – Compare a register's value with zero (sets the ZERO flag).  
- **JMP label** – Unconditional jump to a label.  
- **JZ label / JNZ label** – Conditional jumps based on the ZERO flag.  
- **LOAD Rd, #n** – Load a value from memory cell `n` into register `Rd`.  
- **STORE Rs, #n** – Store a value from register `Rs` into memory cell `n`.  

## 🏗️ Example: Fibonacci Program (6 Iterations)

The **Fibonacci example** initializes registers with the first two Fibonacci numbers (0 and 1) and calculates subsequent numbers for **6 iterations**.  
Each new Fibonacci number is **stored in memory cell 0 using `STORE`**, and the memory map updates in real time.

```assembly
MOV R0, #0         ; F0 = 0
MOV R1, #1         ; F1 = 1
MOV R3, #6         ; Loop counter (6 iterations)
STORE R1, #0       ; Store F1 in memory cell 0
LOOP:
  MOV R2, R0       ; Copy F(n-2) into R2
  ADD R2, R1       ; R2 = R0 + R1 -> New Fibonacci number
  MOV R0, R1       ; Shift values: F(n-1) → F(n-2)
  MOV R1, R2       ; Shift values: F(n) → F(n-1)
  STORE R1, #0     ; Store new Fibonacci number in memory cell 0
  MOV R2, #1       ; Constant 1
  SUB R3, R2       ; Decrement loop counter
  CMP R3           ; Check if counter reached zero
  JNZ LOOP         ; Repeat if R3 ≠ 0
```

## 🏆 Contributing

Contributions and suggestions are welcome! Feel free to fork the repository and submit a pull request.  

## 📜 License

This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for details.

---

🎯 **Built for fun and learning!** If you have any questions or feedback, feel free to reach out. 🚀  

