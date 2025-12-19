# 8-Bit Arithmetic Logic Unit (ALU)  
**Designed Using Logic Gates in Digital Simulator**

**Author:** Arjun Aggarwal  
**GitHub Repository:** https://github.com/arjunaggarwaliit/ALU  
**Tool Used:** Digital – Logic Design and Simulation Tool (by Helmut Neemann)

---

## 📌 Project Overview

This project implements a **fully functional 8-bit Arithmetic Logic Unit (ALU)** built **entirely from basic digital logic gates** using the **Digital logic simulator**.  
No HDL (Verilog/VHDL) or high-level blocks are used — every operation is constructed from fundamental components such as **AND, OR, XOR, NOT gates, multiplexers, adders, and control logic**.

The objective of this project is to gain **low-level understanding of processor design**, digital arithmetic, and logical computation by manually constructing the ALU datapath and control selection logic.

---

## 🧠 What is an ALU?

An **Arithmetic Logic Unit (ALU)** is a core component of a CPU responsible for executing:
- Arithmetic operations (addition, subtraction)
- Logical operations (AND, OR, XOR, NOT)
- Bitwise operations

This ALU operates on **two 8-bit inputs** and produces an **8-bit output**, along with optional status signals.

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|-----|--------|
| **Digital Simulator** | Designing and simulating logic circuits |
| Logic Gates | AND, OR, XOR, NOT |
| Combinational Circuits | Adders, multiplexers |
| Bus Structures | 8-bit wide data paths |


---

## 🔧 ALU Architecture

### Inputs
- **A[7:0]** – First 8-bit operand
- **B[7:0]** – Second 8-bit operand
- **Opcode[3:0]** – Operation select signal

### Outputs
- **Result[7:0]** – Operation result
- **Carry Out** – Carry from MSB (for arithmetic ops)
- **Zero Flag** – Set if output is zero

---

## ⚙️ Supported Operations

| Opcode | Operation |
|------|----------|
| 0000 | A + B (Addition) |
| 0001 | A − B (Subtraction) |
| 0010 | A AND B |
| 0011 | A OR B |
| 0100 | A XOR B |
| 0101 | NOT A |
| 0110 | A NAND B |
| 0111 | A NOR B |

> Operation selection is implemented using **multiplexers** driven by the opcode bits.

---

## 🧩 Implementation Details

### 🔹 Arithmetic Unit
- Built using **8 full adders** in ripple-carry configuration
- Subtraction implemented using **2’s complement**
  - B is inverted
  - Carry-in set to 1

### 🔹 Logic Unit
- Parallel execution of:
  - AND
  - OR
  - XOR
  - NOT
- Outputs routed to MUX

### 🔹 Control Unit
- Opcode bits select final output
- Ensures only one operation drives the result bus

---

## ▶️ How to Run the Project

### Step 1: Install Digital Simulator
Download from:  
https://github.com/hneemann/Digital

### Step 2: Open the Project
1. Launch **Digital**
2. Go to **File → Open**
3. Load `circuits/ALU_8bit.dig`

### Step 3: Simulate
- Set input values using switches
- Choose opcode
- Observe output LEDs and flags

---

## 🧪 Testing

- Separate test circuits provided in the `tests/` directory
- Each operation is verified independently
- Edge cases such as overflow and zero output tested

---

## 🎯 Learning Outcomes

- Deep understanding of **ALU internals**
- Practical experience with:
  - Combinational logic design
  - Bus-based architectures
  - Control signal routing
- Foundation for building:
  - Simple CPU
  - Instruction decoder
  - Datapath architecture

---

## 🚀 Possible Extensions

- Add **shift operations** (LSL, LSR, ASR)
- Implement **signed overflow detection**
- Integrate with a **register file**
- Build a complete **8-bit CPU**

---

## 📜 License

This project is licensed under the **MIT License**.  
You are free to use, modify, and distribute it.

---

## 📬 Contact

**Arjun Aggarwal**  
B.Tech – Artificial Intelligence & Data Engineering 
IIT Ropar  
GitHub: https://github.com/arjunaggarwaliit

---
