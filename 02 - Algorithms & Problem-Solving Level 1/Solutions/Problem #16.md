## 🧠 Deep Problem Deconstruction & Engineering Vision

Every algorithm designed in this course directly reflects the 5 core functionalities of a computer system:

1️⃣ **Input Data:** Taking raw data in.  
2️⃣ **Store Data:** Retaining data/instructions in memory.  
3️⃣ **Process Data:** Converting raw inputs into structured information.  
4️⃣ **Output Information:** Presenting calculated results.  
5️⃣ **Control:** Coordinating and directing sequence and execution flow.

---

### 🟢 Problem #16: Rectangle Area Through Diagonal & Side

> **Problem Statement:**  
> Write a program to calculate a **rectangle's area** using its diagonal and one side, and print it on the screen.  
> The user should enter:  
> • Side `a`  
> • Diagonal `d`  
> *Example Inputs:* `5`, `40`  
> *Output:* `198.431`

#### 🎯 Deep Analysis & Creator’s Reflection:
* **The Creator's Intent:** As the programmer, I am instructing the computer to read two partial geometric measurements (`a` and `d`), apply the **Pythagorean Theorem** to derive the missing perpendicular side (b = sqrt(d^2 - a^2)), multiply it by the known side a to obtain the area (Area = a * sqrt(d^2 - a^2)), and output the floating-point result.
* **Core Concepts Introduced:** 
  1. **Indirect Measurement / Mathematical Derivation:** Real-world systems often lack direct inputs (like both width and height) and must compute hidden variables first using domain geometry before solving the target equation.
  2. **Built-in Mathematical Functions (`Sqrt`):** Moving beyond basic arithmetic operators (`+`, `-`, `*`, `/`) to invoke square-root functions (`Sqrt()`) and exponentiation (d^2, a^2).
  3. **Floating-Point Precision:** Because square roots of non-perfect squares produce irrational decimals, the output variable must support floating-point data types (`Float` / `Double`).

#### ⚙️ Computer Functionality Mapping:
* 📥 **Input Data:** Receives two numeric measurements: side `a` and diagonal `d`.
* 💾 **Store Data:** Allocates floating-point memory variables for `a`, `d`, and the computed `Area`.
* ⚙️ **Process Data:** Executes the geometric formula: `Area = a * Sqrt(d^2 - a^2)`.
* 📤 **Output Information:** Displays the calculated floating-point `Area` onto the monitor screen.
* 🎮 **Control:** Linear sequential execution flow (`Start` ==>> `Read a, d` ==>> `Compute Area` ==>> `Print Area` ==>> `End`).

---

#### 🛠️ Multiple Algorithmic & Architectural Solutions Explored:

Can this geometric derivation be structured in different ways? **Yes!** Here are four clean engineering approaches:

1. **Solution 1: Direct Single-Formula Evaluation (Standard Approach)**
   * **Logic:**  
     `Read a, d`  
     `Area = a * Sqrt((d * d) - (a * a))`  
     `Print Area`
   * **Pros:** Compact, uses minimal variables, and uses direct multiplication (`d * d`) instead of a heavy `Pow(d, 2)` function call for faster CPU execution.

2. **Solution 2: Two-Step Decomposed Calculation (Reusing Problem #15)**
   * **Logic:** Explicitly compute the missing side `b` first, then delegate to the standard rectangle area formula (`a * b`):  
     `Read a, d`  
     `b = Sqrt((d * d) - (a * a))`  
     `Area = a * b`  
     `Print Area`
   * **Pros:** High semantic clarity—separates **finding the missing dimension** from **calculating the area**, making debugging effortless.

3. **Solution 3: Difference of Squares Algebraic Optimization**
   * **Logic:** Using the algebraic identity d^2 - a^2 = (d - a)(d + a):  
     `Area = a * Sqrt((d - a) * (d + a))`
   * **Pros:** Prevents intermediate numeric overflow when `d` is very large (since `d * d` could exceed maximum number limits before subtraction occurs, whereas `(d - a) * (d + a)` stays bounded!).

4. **Solution 4: Defensive Input Validation (Edge-Case Guard)**
   * **Logic:** In geometry, a rectangle's diagonal `d` must strictly be greater than either side `a` (d > a > 0); otherwise, d^2 - a^2 <= 0 causes a domain error (`NaN` / imaginary square root):  
     `If d <= a OR a <= 0 Then Print "Invalid Dimensions"`  
     `Else Compute and Print Area`
   * **Pros:** Protects the program from crashing or producing invalid `NaN` (Not a Number) outputs on impossible user inputs.

---
