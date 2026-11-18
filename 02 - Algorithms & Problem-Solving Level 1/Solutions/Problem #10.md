## 🧠 Deep Problem Deconstruction & Engineering Vision

Every algorithm designed in this course directly reflects the 5 core functionalities of a computer system:

1️⃣ **Input Data:** Taking raw data in.  
2️⃣ **Store Data:** Retaining data/instructions in memory.  
3️⃣ **Process Data:** Converting raw inputs into structured information.  
4️⃣ **Output Information:** Presenting calculated results.  
5️⃣ **Control:** Coordinating and directing sequence and execution flow.

---

### 🟢 Problem #10: Average of Three Marks Calculation

> **Problem Statement:**  
> Write a program to ask the user to enter three marks:  
> • Mark1, Mark2, Mark3  
> Then print the average of the entered marks.  
> *Example Inputs:* `90`, `80`, `70`  
> *Output:* `80`

#### 🎯 Deep Analysis & Creator’s Reflection:
* **The Creator's Intent:** As the programmer, I am instructing the computer to read multiple numeric inputs, execute a **two-stage arithmetic computation** (first summing the operands, then dividing by the count of operands), and output the resulting floating-point or integer average.
* **Core Concepts Introduced:** 
  1. **Order of Operations (Operator Precedence):** The importance of using parentheses `(Mark1 + Mark2 + Mark3) / 3` to ensure addition happens *before* division.
  2. **Statistical Aggregation Processing** (Moving from simple summation to computing central tendency).

#### ⚙️ Computer Functionality Mapping:
* 📥 **Input Data:** Receives three separate numeric marks: `Mark1`, `Mark2`, and `Mark3`.
* 💾 **Store Data:** Allocates memory variables for each input mark, the intermediate `Sum`, and the final `Average`.
* ⚙️ **Process Data:** 
  1. Cumulative addition: `Sum = Mark1 + Mark2 + Mark3`
  2. Division by count: `Average = Sum / 3`
* 📤 **Output Information:** Displays the calculated average value onto the monitor screen.
* 🎮 **Control:** Linear sequential flow (`Start` ==>> `Read Marks` ==>> `Compute Sum` ==>> `Compute Average` ==>> `Print Average` ==>> `End`).

---

#### 🛠️ Multiple Algorithmic & Implementation Solutions Explored:

Can this average calculation be approached differently? **Yes!** 

1. **Solution 1: Direct Compound Expression (Standard Approach)**
   * **Logic:** `Average = (Mark1 + Mark2 + Mark3) / 3`, followed by printing `Average`.
   * **Pros:** Compact, highly readable, encapsulates the entire formula in a single mathematical statement.

2. **Solution 2: Two-Step Explicit Pipeline (Step-by-Step Approach)**
   * **Logic:** 
     
```text
     TotalSum = Mark1 + Mark2 + Mark3
     Average = TotalSum / 3
     Print Average
```
**Pros:** Enhances readability and debugging by breaking down the logic into discrete, named semantic steps (`TotalSum` then `Average`), which is cleaner when dealing with complex formulas.

---
