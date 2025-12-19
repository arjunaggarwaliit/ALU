# 8-bit Integer ALU (Gate-Level Implementation)

This project implements an **8-bit Integer Arithmetic Logic Unit (ALU)** using **basic logic gates** in the **Digital** logic simulator by Helmut Neemann.

The ALU is designed as part of **CS207 – Foundations of Computer Systems** and extends the functionality of a basic ALU to support arithmetic, logical, comparison, multiplication, and division operations, strictly following the given specifications.

Repository Link:
[https://github.com/arjunaggarwaliit/ALU](https://github.com/arjunaggarwaliit/ALU)

---

## 🔧 Tool Used

* **Digital – Logic Designer and Simulator**
  [https://github.com/hneemann/Digital](https://github.com/hneemann/Digital)

All components (adders, multiplexers, comparators, etc.) are built **from logic gates**, except where explicitly allowed by the lab instructions.

---

## 📌 Supported ALU Operations

The ALU supports the following operations:

1. Addition
2. Subtraction
3. Bitwise NOT (of one selected input)
4. Bitwise AND
5. Bitwise OR
6. Bitwise XOR
7. Magnitude Comparison
8. Multiplication
9. Division

---

## 🧾 Inputs to the ALU

### 1. Operand Inputs

* **Input A**: 8-bit signed number (2’s complement)
* **Input B**: 8-bit signed number (2’s complement)

### 2. Control Inputs

| Signal Name | Width  | Description                               |
| ----------- | ------ | ----------------------------------------- |
| `Carry_in`  | 1 bit  | Carry input for addition                  |
| `InputID`   | 1 bit  | Selects operand for NOT / divisor for DIV |
| `OpCode`    | 4 bits | Selects the ALU operation                 |

---

### 🔹 InputID Usage

* **NOT operation**

  * `0` → NOT(Input A)
  * `1` → NOT(Input B)

* **Division operation**

  * `0` → Input A is divisor
  * `1` → Input B is divisor

---

## 🧠 Operation Selection (OpCode)

The 4-bit `OpCode` determines which operation is performed.

| OpCode | Operation            |
| ------ | -------------------- |
| `0000` | Addition             |
| `0001` | Subtraction          |
| `0010` | Bitwise NOT          |
| `0011` | Bitwise AND          |
| `0100` | Bitwise OR           |
| `0101` | Bitwise XOR          |
| `0110` | Magnitude Comparison |
| `0111` | Multiplication       |
| `1000` | Division             |

(Extra opcodes are reserved for future extensions.)

---

## 📤 Outputs from the ALU

### 1. Main Outputs

| Output    | Width  | Description                        |
| --------- | ------ | ---------------------------------- |
| `Output0` | 8 bits | Primary ALU result                 |
| `Output1` | 8 bits | Secondary result (used in MUL/DIV) |

#### Output Interpretation:

* **Addition / Subtraction**

  * Result → `Output0`
* **Multiplication**

  * 16-bit result → `Output1:Output0`
* **Division**

  * Quotient → `Output0`
  * Remainder → `Output1`

---

### 2. Status Flags

| Flag        | Description                               |
| ----------- | ----------------------------------------- |
| `Carry_out` | Carry generated from addition/subtraction |
| `Overflow`  | Signed overflow / underflow               |
| `A = B`     | High if Input A equals Input B            |
| `A > B`     | High if Input A greater than Input B      |
| `A < B`     | High if Input A less than Input B         |
| `DivByZero` | High if division by zero is attempted     |

---

## 🏗️ Internal Design Overview

The ALU is composed of the following gate-level modules:

* **Full Adder** (built using logic gates and reused for 8-bit addition)
* **Adder/Subtractor Unit**
* **Bitwise Logic Unit (AND, OR, XOR, NOT)**
* **Magnitude Comparator**
* **Multiplier Unit**
* **Divider Unit**
* **Multiplexers / Demultiplexers**
* **Control Logic (Decoder for OpCode)**

All modules are designed manually using **basic logic gates**, following lab constraints.

---

## ▶️ How to Run the Project

1. Install **Digital** simulator from:
   [https://github.com/hneemann/Digital](https://github.com/hneemann/Digital)

2. Clone the repository:

   ```bash
   git clone https://github.com/arjunaggarwaliit/ALU.git
   ```

3. Open the `.dig` file in Digital.

4. Set:

   * Input A and Input B (8-bit switches)
   * OpCode (4-bit control)
   * Carry_in and InputID

5. Observe:

   * Output0, Output1
   * Status flags

---

## 📚 Notes

* All numbers are represented in **2’s complement**.
* Overflow is detected for signed arithmetic.
* Division by zero is safely handled using a dedicated flag.

---

## 👤 Author

**Arjun Aggarwal**
B.Tech, Artificial Intelligence & Data Engineering
IIT Ropar

---

## 📜 License

This project is intended for **academic and educational use only**.
