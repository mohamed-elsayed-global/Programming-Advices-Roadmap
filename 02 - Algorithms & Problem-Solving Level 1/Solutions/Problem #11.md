## 🧠 Deep Problem Deconstruction & Engineering Vision

Every algorithm designed in this course directly reflects the 5 core functionalities of a computer system:

1️⃣ **Input Data:** Taking raw data in.  
2️⃣ **Store Data:** Retaining data/instructions in memory.  
3️⃣ **Process Data:** Converting raw inputs into structured information.  
4️⃣ **Output Information:** Presenting calculated results.  
5️⃣ **Control:** Coordinating and directing sequence and execution flow.

---

### 🟢 Problem #11: Average Calculation & Conditional Pass / Fail

> **Problem Statement:**  
> Write a program to ask the user to enter three marks:  
> • Mark1, Mark2, Mark3  
> Then print the **Average** of the entered marks, and print **"PASS"** if `average >= 50`, otherwise print **"FAIL"**.  
> *Example Inputs:* `90`, `80`, `70`  
> *Outputs:*  
> `80`  
> `PASS`

#### 🎯 Deep Analysis & Creator’s Reflection:
* **The Creator's Intent:** As the programmer, I am instructing the computer to merge two distinct algorithmic phases into a single cohesive pipeline: first performing **Statistical Aggregation** (Problem #10) to compute the `Average`, and subsequently feeding that computed value into a **Binary Relational Decision** (Problem #8) to determine and output the academic status.
* **Core Concepts Introduced:** 
  1. **Chained Processing / Data Pipelining:** The output of one computational stage (`Average`) becomes the direct input for a subsequent logical evaluation stage (`Average >= 50`).
  2. **Multi-Stage Output:** Presenting both a quantitative metric (the numeric average) and a qualitative status (PASS/FAIL).

#### ⚙️ Computer Functionality Mapping:
* 📥 **Input Data:** Receives three numeric inputs: `Mark1`, `Mark2`, and `Mark3`.
* 💾 **Store Data:** Allocates dynamic memory variables for the three marks, the intermediate `Sum`, and the computed `Average`.
* ⚙️ **Process Data:** 
  1. Arithmetic Summation: `Sum = Mark1 + Mark2 + Mark3`
  2. Arithmetic Division: `Average = Sum / 3`
  3. Relational Evaluation: `Average >= 50` ==>> Boolean (`True` / `False`)
* 📤 **Output Information:** Prints the calculated `Average` first, followed by `"PASS"` (if True) or `"FAIL"` (if False).
* 🎮 **Control:** Linear sequence (`Input` ==>> `Compute Average` ==>> `Print Average`) transitioning into a conditional decision diamond (`Average >= 50?`) that branches execution into two mutually exclusive print paths before terminating.

---

#### 🛠️ Multiple Algorithmic & Architectural Solutions Explored:

Can this combined problem be structured in different ways? **Yes!** Here are three clean engineering approaches:

1. **Solution 1: Sequential Pipeline with Inline Decision (Standard Approach)**
   * **Logic:**  
     `Read Mark1, Mark2, Mark3`  
     `Average = (Mark1 + Mark2 + Mark3) / 3`  
     `Print Average`  
     `If Average >= 50 Then Print "PASS" Else Print "FAIL"`
   * **Pros:** Straightforward, minimal variables, directly reflects the sequential execution flow.

2. **Solution 2: Decomposed Step-by-Step Pipeline (Modular / Clean Code Approach)**
   * **Logic:** Break the calculation into explicit, readable intermediate states before decision-making:  
     `Sum = Mark1 + Mark2 + Mark3`  
     `Average = Sum / 3`  
     `Print Average`  
     `If Average >= 50 Then Print "PASS" Else Print "FAIL"`
   * **Pros:** Separates summation from division, making it easier to trace, debug, or extend (e.g., if you later want to print the `Sum` as well).

3. **Solution 3: Total Sum Threshold Shortcut (Mathematical Optimization Approach)**
   * **Logic:** Instead of comparing `Average >= 50`, notice that for 3 marks, having an average >= 50 is mathematically identical to having a total sum >= 150 (50 * 3):  
     `Sum = Mark1 + Mark2 + Mark3`  
     `Print (Sum / 3)`  
     `If Sum >= 150 Then Print "PASS" Else Print "FAIL"`
   * **Pros:** Eliminates floating-point precision rounding issues during the comparison step (e.g., if an average is `49.9999999` due to binary float representation, integer sum comparison `Sum >= 150` remains 100% exact!).

---
