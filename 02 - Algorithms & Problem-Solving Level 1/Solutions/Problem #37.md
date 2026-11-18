## 🧠 Deep Problem Deconstruction & Engineering Vision

Every algorithm designed in this course directly reflects the 5 core functionalities of a computer system:

1️⃣ **Input Data:** Taking raw data in.  
2️⃣ **Store Data:** Retaining data/instructions in memory.  
3️⃣ **Process Data:** Converting raw inputs into structured information.  
4️⃣ **Output Information:** Presenting calculated results.  
5️⃣ **Control:** Coordinating and directing sequence and execution flow.

---

### 🟢 Problem #37: Sum Until `-99` (Sentinel-Controlled Loop)

> **Problem Statement:**  
> Write a program to read numbers from the user and sum them. Keep reading until the user enters `-99`, then print the total **Sum** on the screen.  
> *Example Inputs:* `10`, `20`, `30`, `40`, `-99`  
> *Output:* `100` *(since 10 + 20 + 30 + 40 = 100)*

#### 🎯 Deep Analysis & Creator’s Reflection:
* **The Creator's Intent:** As the programmer, I am introducing a fundamental pattern in software engineering: the **Sentinel-Controlled Loop**. Unlike counter-controlled loops (where the number of iterations is known in advance, like Problems #26–#30), a sentinel loop runs indefinitely until the user inputs a specific stopping flag value (the sentinel, `-99`), which terminates the accumulation sequence.
* **Core Concepts Introduced:** 
  1. **The Sentinel Pattern & Accumulation:** Combining an accumulator (`Sum = 0`) with an indefinite loop (`While` or `Do-While`) that inspects every incoming number before deciding whether to add it to the total or break out of the loop.
  2. **The Sentinel Pollution Trap (`-99` Bug):** A classic beginner bug is adding the sentinel value (`-99`) directly into the accumulator! Checking `If (Number != -99)` *before* adding it to `Sum` is mandatory.

#### ⚙️ Computer Functionality Mapping:
* 📥 **Input Data:** Repeatedly receives numeric values from the user until `-99` is entered.
* 💾 **Store Data:** Allocates memory variables for the current input `Number` and the accumulator `Sum` (initialized to `0`).
* ⚙️ **Process Data:** 
  1. Reads `Number`.
  2. Checks if `Number != -99`. If true, updates `Sum = Sum + Number`.
  3. Repeats until `Number == -99`.
* 📤 **Output Information:** Displays the final accumulated `Sum` on the monitor screen.
* 🎮 **Control:** Indefinite backward-jumping **sentinel-controlled loop** that breaks out upon encountering the termination flag.

---

#### 🛠️ Multiple Algorithmic & Architectural Solutions Explored:

Can a sentinel-controlled summation loop be structured in different ways? **Yes!** Here are four clean engineering approaches:

1. **Solution 1: Pre-Test `While` Loop with Priming Read (Standard Approach)**
   * **Logic:**  
     `Sum = 0`  
     `Read Number`  
     `While (Number != -99)`  
     `    Sum = Sum + Number`  
     `    Read Number`  
     `End While`  
     `Print Sum`
   * **Pros:** The priming read ensures that if the user enters `-99` immediately on the first prompt, `Sum` correctly outputs `0` without running the loop body.

2. **Solution 2: Post-Test `Do-While` Loop with Sentinel Guard**
   * **Logic:** Read inside the loop and guard the addition so `-99` is never added to the sum:  
     `Sum = 0`  
     `Do`  
     `    Read Number`  
     `    If (Number != -99) Then`  
     `        Sum = Sum + Number`  
     `    End If`  
     `While (Number != -99)`  
     `Print Sum`
   * **Pros:** Eliminates duplicating the `Read Number` statement outside and inside the loop (DRY principle).

3. **Solution 3: Infinite Loop with Explicit Break (`While True`)**
   * **Logic:** Run an infinite loop, read input, check for the sentinel to break, otherwise accumulate:  
     `Sum = 0`  
     `While True`  
     `    Read Number`  
     `    If (Number == -99) Then Break`  
     `    Sum = Sum + Number`  
     `End While`  
     `Print Sum`
   * **Pros:** Extremely readable flow ("read number, if sentinel exit, else add") with zero code duplication.

4. **Solution 4: Configurable Sentinel Constant (`Const SENTINEL = -99`)**
   * **Logic:** Replace hardcoded `-99` literals with a named constant so the sentinel flag can be changed easily (e.g., `-1` or `0`):  
     `Const SENTINEL = -99`  
     `While (Number != SENTINEL)`  
     `    ...`  
   * **Pros:** Adheres to clean code principles by eliminating magic numbers and improving maintainability.

---
