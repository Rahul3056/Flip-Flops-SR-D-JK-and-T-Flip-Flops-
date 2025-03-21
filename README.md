 Flip-Flops (SR, D, JK, and T Flip-Flops) - Theory, Design & Implementation 

#### **Concept Overview**  
Flip-flops are sequential logic circuits that store one bit of data and change state based on a clock signal. They are the basic building blocks of memory elements in digital systems.

---

## **1️⃣ SR Flip-Flop (Set-Reset)**
- **Definition:** A simple bistable circuit with two inputs: `S` (Set) and `R` (Reset).  
- **Functionality:**  
  - `S = 1, R = 0 → Q = 1` (Set)  
  - `S = 0, R = 1 → Q = 0` (Reset)  
  - `S = 0, R = 0 → No change` (Hold)  
  - `S = 1, R = 1 → Invalid (undefined output)`  

### **Truth Table**
| S | R | Q (Next State) |
|---|---|---------------|
| 0 | 0 | Q (No change) |
| 0 | 1 | 0 (Reset) |
| 1 | 0 | 1 (Set) |
| 1 | 1 | Undefined |

---

## **2️⃣ D Flip-Flop (Data Flip-Flop)**
- **Definition:** A flip-flop that captures the input `D` on the rising edge of the clock.
- **Functionality:**  
  - `D = 0 → Q = 0`  
  - `D = 1 → Q = 1`  

### **Truth Table**
| D | Q (Next State) |
|---|---------------|
| 0 | 0 |
| 1 | 1 |

---

## **3️⃣ JK Flip-Flop**
- **Definition:** An improved version of the SR flip-flop where `J = 1, K = 1` results in toggling the output.
- **Functionality:**  
  - `J = 0, K = 0 → No change`  
  - `J = 0, K = 1 → Reset (Q = 0)`  
  - `J = 1, K = 0 → Set (Q = 1)`  
  - `J = 1, K = 1 → Toggle (Q changes state)`  

### **Truth Table**
| J | K | Q (Next State) |
|---|---|---------------|
| 0 | 0 | Q (No change) |
| 0 | 1 | 0 (Reset) |
| 1 | 0 | 1 (Set) |
| 1 | 1 | Q' (Toggle) |

---

## **4️⃣ T Flip-Flop (Toggle Flip-Flop)**
- **Definition:** A flip-flop that toggles the output on each clock pulse when `T = 1`.
- **Functionality:**  
  - `T = 0 → No change`  
  - `T = 1 → Toggle`  

### **Truth Table**
| T | Q (Next State) |
|---|---------------|
| 0 | Q (No change) |
| 1 | Q' (Toggle) |

### **Code Explanation**
1. **Each flip-flop is implemented as a separate module.**
2. **All designs use an always block triggered on the positive edge (`posedge clk`).**
3. **The testbench initializes clock (`clk`) and applies various input conditions.**
4. **The `$finish` command stops the simulation after testing all conditions.**

---

### **Execution Steps**
1. Copy the Verilog code into a simulator (ModelSim, Xilinx Vivado, etc.).
2. Compile and run the code.
3. Observe the flip-flop behavior for different input conditions.

---

### **Real-World Application**
- **D Flip-Flop** is used in shift registers and memory elements.
- **JK Flip-Flop** is commonly used in counters and control circuits.
- **T Flip-Flop** is the foundation of frequency dividers.
