## 🧠 Deep Problem Deconstruction & Engineering Vision

Every algorithm designed in this course directly reflects the 5 core functionalities of a computer system:

1️⃣ **Input Data:** Taking raw data in.  
2️⃣ **Store Data:** Retaining data/instructions in memory.  
3️⃣ **Process Data:** Converting raw inputs into structured information.  
4️⃣ **Output Information:** Presenting calculated results.  
5️⃣ **Control:** Coordinating and directing sequence and execution flow.

---

### 🟢 Problem #7: Half Number (Calculation & Formatted Output)

> **Problem Statement:**  
> Write a program to ask the user to enter a **Number**.  
> Then print the result in the format:  
> `"Half of the <Number> is <???>"`  
> *Example Inputs:* `60` | `50`  
> *Outputs:*  
> `Half of 60 is 30`  
> `Half of 50 is 25`

#### 🎯 Deep Analysis & Creator’s Reflection:
* **The Creator's Intent:** As the programmer, I am instructing the computer to receive a numeric input, perform a fundamental mathematical division (`Number / 2`), store the resulting value, and dynamically inject both the original input variable and the calculated result into a formatted output string template.
* **Core Concepts Introduced:** 
  1. **Arithmetic Division Processing** (`/`).
  2. **String Interpolation / Variable Binding** (embedding dynamic runtime values inside a text message template rather than printing static text).

#### ⚙️ Computer Functionality Mapping:
* 📥 **Input Data:** Receives a numeric scalar (`Num`) from the user.
* 💾 **Store Data:** Allocates memory variables for `Num` and the computed `Half`.
* ⚙️ **Process Data:** Executes mathematical division: `Half = Num / 2`.
* 📤 **Output Information:** Combines string literals with dynamic memory variables to render a formatted sentence onto the monitor.
* 🎮 **Control:** Linear sequential execution flow (`Start` ==>> `Read` ==>> `Compute` ==>> `Print` ==>> `End`).

---

#### 🛠️ Multiple Algorithmic & Implementation Solutions Explored:

Can this problem be implemented in different ways? **Yes!** While the logic is straightforward, how we handle the memory allocation and formatting varies:

1. **Solution 1: Two-Variable Explicit Storage (Standard Approach)**
   * **Logic:** 
     1. Read `Num`.
     2. Calculate `Half = Num / 2`.
     3. Print `"Half of " + Num + " is " + Half`.
   * **Pros:** Highly readable, explicit, keeps computation separate from presentation.

2. **Solution 2: On-the-Fly Inline Calculation (Memory Optimization Approach)**
   * **Logic:** 
     1. Read `Num`.
     2. Print `"Half of " + Num + " is " + (Num / 2)` directly without creating a separate `Half` variable.
   * **Pros:** Reduces memory overhead by omitting an intermediate variable buffer.
   * **Cons:** Slightly less readable if the mathematical expression gets complex.

3. **Solution 3: Data Type Handling Consideration (Integer vs. Float Division)**
   * **Logic:** Depending on whether the user enters an even or odd number (e.g., entering `5` yielding `2.5`), the algorithm must handle **Floating-Point Division** rather than strict Integer Division to ensure precision when the result contains fractions especially in Solution 1.
---
