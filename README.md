# 16-Bit Arithmetic Logic Unit (ALU)

A comprehensive implementation of a 16-bit **Arithmetic Logic Unit (ALU)** written in Verilog. This project demonstrates the core computational engine of a processor, capable of performing arithmetic, logical, and comparison operations.

---

## 🚀 Project Overview

The ALU is a fundamental component of the Central Processing Unit (CPU). This specific implementation takes two 16-bit inputs and processes them based on a 4-bit selection code (`ALU_Sel`). It is designed to be synthesizable for FPGA deployment and includes a robust testbench for functional verification.

### Key Features
* **16-bit Data Path:** Processes two 16-bit operands ($A$ and $B$).
* **16 Operations:** Includes standard arithmetic, bitwise logic, shifts, and comparisons.
* **Status Flags:** Real-time monitoring of result states:
    * **CarryOut:** Indicates an overflow in arithmetic operations.
    * **Zero:** High if the result is exactly $0$.
    * **Negative:** High if the most significant bit (MSB) is $1$.

---

## 🛠 Supported Operations

The ALU behavior is controlled by the `ALU_Sel` input:

| ALU_Sel | Operation | Description |
| :--- | :--- | :--- |
| **0000** | **Addition** | $A + B$ |
| **0001** | **Subtraction** | $A - B$ |
| **0010** | **Multiplication** | $A \times B$ |
| **0011** | **Division** | $A / B$ |
| **0100** | **Left Shift** | $A \ll 1$ |
| **0101** | **Right Shift** | $A \gg 1$ |
| **0110** | **Rotate Left** | Circular shift left |
| **0111** | **Rotate Right** | Circular shift right |
| **1000** | **AND** | Bitwise AND |
| **1001** | **OR** | Bitwise OR |
| **1010** | **XOR** | Bitwise XOR |
| **1011** | **NOR** | Bitwise NOR |
| **1100** | **NAND** | Bitwise NAND |
| **1101** | **XNOR** | Bitwise XNOR |
| **1110** | **Greater Than** | $1$ if $A > B$, else $0$ |
| **1111** | **Equal** | $1$ if $A == B$, else $0$ |

---

## 📂 Repository Structure

* `ALU.v`: The main hardware module containing the combinational logic.
* `testbench.v`: A test script that applies stimulus to the ALU and monitors outputs.
* `README.md`: Project documentation.

---

## 💻 Getting Started

### Prerequisites
You will need an HDL simulator. Popular choices include:
* **Icarus Verilog** (Open Source)
* **ModelSim / QuestaSim**
* **Vivado Design Suite**

### How to Run (Icarus Verilog)

1.  **Clone the Repo:**
    ```bash
    git clone [https://github.com/arjunaggarwaliit/ALU.git](https://github.com/arjunaggarwaliit/ALU.git)
    cd ALU
    ```

2.  **Compile:**
    ```bash
    iverilog -o alu_sim ALU.v testbench.v
    ```

3.  **Simulate:**
    ```bash
    vvp alu_sim
    ```

4.  **Visualize:**
    If your testbench generates a `.vcd` file, open it in GTKWave:
    ```bash
    gtkwave dump.vcd
    ```

---

## 📈 Future Enhancements
- [ ] Expand data width to 32-bit or 64-bit.
- [ ] Implement Floating Point Unit (FPU) support.
- [ ] Add signed/unsigned arithmetic toggle.

---

## 👤 Author
**Arjun Aggarwal**
* GitHub: [@arjunaggarwaliit](https://github.com/arjunaggarwaliit)

## 📜 License
This project is open-source and available under the [MIT License](LICENSE).
