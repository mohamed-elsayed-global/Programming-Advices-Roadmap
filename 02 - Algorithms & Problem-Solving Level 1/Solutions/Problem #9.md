## 🧠 Deep Problem Deconstruction & Engineering Vision

Every algorithm designed in this course directly reflects the 5 core functionalities of a computer system:

1️⃣ **Input Data:** Taking raw data in.  
2️⃣ **Store Data:** Retaining data/instructions in memory.  
3️⃣ **Process Data:** Converting raw inputs into structured information.  
4️⃣ **Output Information:** Presenting calculated results.  
5️⃣ **Control:** Coordinating and directing sequence and execution flow.

---

### 🟢 Problem #9: Sum of Three Numbers

> **Problem Statement:**  
> Write a program to ask the user to enter three numbers:  
> • Number1, Number2, Number3  
> Then print the sum of the entered numbers.  
> *Example Inputs:* `10`, `20`, `30`  
> *Output:* `60`

#### 🎯 Deep Analysis & Creator’s Reflection:
* **The Creator's Intent:** As the programmer, I am instructing the computer to receive **multiple sequential inputs**, allocate distinct memory addresses for each numerical variable, execute an arithmetic addition operation across all operands, store the aggregated total, and output the result.
* **Core Concepts Introduced:** 
  1. **Multi-Input reading Pipeline** (Handling sequential data entry).
  2. **Cumulative Arithmetic Accumulation** (Summation across n variables).

#### ⚙️ Computer Functionality Mapping:
* 📥 **Input Data:** Receives three separate numeric values: `Num1`, `Num2`, and `Num3`.
* 💾 **Store Data:** Allocates dynamic memory variables for each input scalar and the resulting `TotalSum`.
* ⚙️ **Process Data:** Executes cumulative arithmetic addition: `TotalSum = Num1 + Num2 + Num3`.
* 📤 **Output Information:** Displays the calculated numeric sum onto the monitor screen.
* 🎮 **Control:** Sequential linear execution flow (`Start` ==>> `Read Num1` ==>> `Read Num2` ==>> `Read Num3` ==>> `Compute Sum` ==>> `Print Sum` ==>> `End`).

---

#### 🛠️ Multiple Algorithmic & Implementation Solutions Explored:

1. **Solution 1: Direct Multi-Operand Addition (Standard Approach)**
   * **Logic:** Calculating `TotalSum = Num1 + Num2 + Num3`, followed by printing `TotalSum`, or printing `Num1 + Num2 + Num3` directly.
   * **Pros:** Highly intuitive, clean, and directly mirrors basic human addition.

2. **Solution 2: Iterative Accumulator / Running Total (Scalable Approach)**
   * **Logic:** 
     
```text
     Sum = 0
     Read Num1 -> Sum = Sum + Num1
     Read Num2 -> Sum = Sum + Num2
     Read Num3 -> Sum = Sum + Num3
     Print Sum
```
**Pros:** Introduces the Accumulator Pattern (Sum = Sum + CurrentValue), which is foundational for handling loops, arrays, and summing hundreds or thousands of inputs later in programming.

---
