## 🧠 Deep Problem Deconstruction & Engineering Vision

Every algorithm designed in this course directly reflects the 5 core functionalities of a computer system:

1️⃣ **Input Data:** Taking raw data in.  
2️⃣ **Store Data:** Retaining data/instructions in memory.  
3️⃣ **Process Data:** Converting raw inputs into structured information.  
4️⃣ **Output Information:** Presenting calculated results.  
5️⃣ **Control:** Coordinating and directing sequence and execution flow.

---

### 🟢 Problem #31: Power of 2, 3, 4

> **Problem Statement:**  
> Write a program to ask the user to enter:  
> • `Number`  
> Then print Number^2, Number^3, and Number^4.  
> *Example Input:* `3`  
> *Outputs:*  
> `9`  
> `27`  
> `81`

#### 🎯 Deep Analysis & Creator’s Reflection:
* **The Creator's Intent:** As the programmer, I am instructing the computer to read a single base integer (`Number`), compute three successive integer powers (N^2, N^3, and N^4), and output each result sequentially onto the screen.
* **Core Concepts Introduced:** 
  1. **Incremental Multiplication (Strength Reduction):** Instead of recomputing from scratch for every power (`N*N`, `N*N*N`, `N*N*N*N` — 6 multiplications total), we can reuse the previous result (`a = N * N`, `b = a * N`, `c = b * N` — only **3 multiplications total**!), cutting CPU arithmetic operations in half!
  2. **Direct Arithmetic vs. Math Library (`Pow`):** Built-in `Pow(base, exp)` functions operate on floating-point numbers (`double`), which are slower and can introduce tiny floating-point precision inaccuracies for large integers. Explicit integer multiplication is faster and 100% exact.

#### ⚙️ Computer Functionality Mapping:
* 📥 **Input Data:** Receives a single numeric base value: `Number`.
* 💾 **Store Data:** Allocates dynamic memory variables for `Number` and the three computed power results (`a`, `b`, `c`).
* ⚙️ **Process Data:** Computes sequential powers via multiplication:  
  `a = Number * Number`  
  `b = Number * Number * Number` *(or `a * Number`)*  
  `c = Number * Number * Number * Number` *(or `b * Number`)*
* 📤 **Output Information:** Displays `a`, `b`, and `c` sequentially on the monitor screen.
* 🎮 **Control:** Linear sequential execution flow (`Start` ==>> `Read Number` ==>> `Compute Powers` ==>> `Print a, b, c` ==>> `End`).

---

#### 🛠️ Multiple Algorithmic & Architectural Solutions Explored:

Can computing the 2nd, 3rd, and 4th powers of a number be structured in different ways? **Yes!** Here are four clean engineering approaches:

1. **Solution 1: Direct Explicit Multiplication (Standard Approach)**
   * **Logic:**  
     `Read Number`  
     `a = Number * Number`  
     `b = Number * Number * Number`  
     `c = Number * Number * Number * Number`  
     `Print a`  
     `Print b`  
     `Print c`
   * **Pros:** Transparent, maps 1-to-1 to basic flowchart boxes, and avoids floating-point conversion overhead.

2. **Solution 2: Chained Incremental Multiplication (CPU Strength Reduction)**
   * **Logic:** Reuse each computed power as the input to the next multiplication:  
     `Read Number`  
     `Power2 = Number * Number`  
     `Power3 = Power2 * Number`  
     `Power4 = Power3 * Number`  
     `Print Power2, Power3, Power4`
   * **Pros:** Reduces total multiplications from **6 down to 3** (50\% fewer CPU instructions) while remaining 100% integer-exact.

3. **Solution 3: Iterative Accumulator Loop (Scalable to Any Exponent M)**
   * **Logic:** Maintain a running product `Result = Number` and multiply by `Number` across a loop for exponents `2` through `4`:  
     `Read Number`  
     `Result = Number`  
     `For Exponent = 2 To 4`  
     `    Result = Result * Number`  
     `    Print Result`  
     `End For`
   * **Pros:** Easily scales if future requirements change from "powers 2, 3, 4" to "powers 2 through 100" without duplicating lines of code!

4. **Solution 4: Built-in `Pow()` Math Library Function**
   * **Logic:** Delegate exponentiation to standard language math libraries:  
     `Read Number`  
     `Print Pow(Number, 2)`  
     `Print Pow(Number, 3)`  
     `Print Pow(Number, 4)`
   * **Pros:** Concise and readable, though best reserved for floating-point or fractional exponents since `Pow()` carries floating-point casting overhead.

---
