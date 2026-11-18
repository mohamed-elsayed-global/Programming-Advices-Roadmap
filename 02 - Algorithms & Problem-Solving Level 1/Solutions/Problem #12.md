## 🧠 Deep Problem Deconstruction & Engineering Vision

Every algorithm designed in this course directly reflects the 5 core functionalities of a computer system:

1️⃣ **Input Data:** Taking raw data in.  
2️⃣ **Store Data:** Retaining data/instructions in memory.  
3️⃣ **Process Data:** Converting raw inputs into structured information.  
4️⃣ **Output Information:** Presenting calculated results.  
5️⃣ **Control:** Coordinating and directing sequence and execution flow.

---

### 🟢 Problem #12: Maximum of Two Numbers

> **Problem Statement:**  
> Write a program to ask the user to enter two numbers:  
> • Number1, Number2  
> Then print the **Max Number**.  
> *Example Inputs:* `10`, `20`  
> *Output:* `20`

#### 🎯 Deep Analysis & Creator’s Reflection:
* **The Creator's Intent:** As the programmer, I am instructing the computer to read two dynamic scalar inputs (`Num1` and `Num2`), execute a **relative magnitude comparison** (`>`), and use a conditional branching structure to select and output whichever memory variable holds the greater value.
* **Core Concepts Introduced:** 
  1. **Relative Value Comparison:** Comparing two dynamic variables against each other (`Num1 > Num2`) rather than comparing a variable against a fixed constant threshold.
  2. **Edge-Case Equality Handling:** Understanding what happens when `Num1 == Num2` (both paths yield the exact same numeric output, making `>` and `>=` functionally equivalent here).

#### ⚙️ Computer Functionality Mapping:
* 📥 **Input Data:** Receives two numeric scalars: `Num1` and `Num2`.
* 💾 **Store Data:** Allocates dynamic memory variables for `Num1` and `Num2` (and optionally a `Max` tracker variable).
* ⚙️ **Process Data:** Evaluates relational comparison: `Num1 > Num2` $\rightarrow$ Boolean (`True` / `False`).
* 📤 **Output Information:** Displays the value stored in whichever variable holds the maximum magnitude.
* 🎮 **Control:** A decision structure branches execution down the `Print Num1` path if `True`, or the `Print Num2` path if `False`.

---

#### 🛠️ Multiple Algorithmic & Architectural Solutions Explored:

Can finding the maximum of two numbers be designed in different ways? **Yes!** Here are four distinct engineering approaches:

1. **Solution 1: Direct Branching Print (Standard Approach)**
   * **Logic:**  
     `Read Num1, Num2`  
     `If Num1 > Num2 Then Print Num1 Else Print Num2`
   * **Pros:** Minimal memory footprint (no extra `Max` variable needed), clean and direct control flow.

2. **Solution 2: State Tracker Variable / "King of the Hill" Pattern (Scalable Approach)**
   * **Logic:** Assume the first input is the maximum, then challenge it against subsequent inputs:  
     `Read Num1, Num2`  
     `Max = Num1`  
     `If Num2 > Max Then Max = Num2`  
     `Print Max`
   * **Pros:** This is the foundational algorithm used in computer science to find the maximum across **3, 10, or 1,000,000 numbers** (arrays/loops) without writing complex nested `If-Else` trees!

3. **Solution 3: Explicit Three-Way Equality Handling (Strict Clarity Approach)**
   * **Logic:** Explicitly separate the `Equal` edge case from `Greater` and `Less`:  
     `If Num1 > Num2 Then Print Num1`  
     `Else If Num2 > Num1 Then Print Num2`  
     `Else Print Num1 (or "Numbers are Equal")`
   * **Pros:** Makes edge-case behavior explicit if business requirements later demand a custom message when both numbers are identical.

4. **Solution 4: Pure Mathematical Formula (Branchless / No `If` Statement)**
   * **Logic:** Using absolute difference arithmetic to compute the maximum without any conditional branching:  
     `Max = (Num1 + Num2 + Abs(Num1 - Num2)) / 2`  
     `Print Max`
   * **Pros:** Eliminates CPU branch prediction penalties in low-level systems programming—pure arithmetic execution!

---
