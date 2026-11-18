## 🧠 Deep Problem Deconstruction & Engineering Vision

Every algorithm designed in this course directly reflects the 5 core functionalities of a computer system:

1️⃣ **Input Data:** Taking raw data in.  
2️⃣ **Store Data:** Retaining data/instructions in memory.  
3️⃣ **Process Data:** Converting raw inputs into structured information.  
4️⃣ **Output Information:** Presenting calculated results.  
5️⃣ **Control:** Coordinating and directing sequence and execution flow.

---

### 🟢 Problem #26: Print Numbers from 1 to N

> **Problem Statement:**  
> Write a program to print numbers from `1` to `N`.  
> *Example Input:* `10`  
> *Outputs:*  
> `1`  
> `2`  
> `3`  
> `4`  
> `5`  
> `6`  
> `7`  
> `8`  
> `9`  
> `10`

#### 🎯 Deep Analysis & Creator’s Reflection:
* **The Creator's Intent:** As the programmer, I am instructing the computer to read a dynamic upper-bound integer `N`, initialize an **iterative loop counter** (`Counter = 1`), and execute a deterministic repetition cycle that prints the current counter value and increments it (`Counter = Counter + 1`) until `Counter` exceeds `N`.
* **Core Concepts Introduced:** 
  1. **Counter-Controlled Iteration (`For` vs. `While`):** Unlike Problem #25 (an event/sentinel-controlled loop that waits for valid user input), printing `1` to `N` is a **definite loop** where the exact number of iterations (`N`) is known before the loop starts.
  2. **The Three Pillars of Every Loop:** Every counter-controlled loop requires: (1) **Initialization** (`Counter = 1`), (2) **Boundary Condition** (`Counter <= N`), and (3) **State Progression** (`Counter = Counter + 1`) to guarantee termination.

#### ⚙️ Computer Functionality Mapping:
* 📥 **Input Data:** Receives a single integer upper limit: `N`.
* 💾 **Store Data:** Allocates dynamic memory variables for `N` and the loop state variable `Counter`.
* ⚙️ **Process Data:** Repeatedly increments `Counter` by `1` and evaluates the boundary condition `Counter <= N` ==>> Boolean (`True` / `False`).
* 📤 **Output Information:** Prints the current integer value of `Counter` on each active iteration.
* 🎮 **Control:** Backward-jumping **counter-controlled loop** that repeats `Print Counter` and `Counter++` while `Counter <= N`, exiting once `Counter > N`.

---

#### 🛠️ Multiple Algorithmic & Architectural Solutions Explored:

Can printing a sequence from `1` to `N` be structured in different ways? **Yes!** Here are four clean engineering approaches:

1. **Solution 1: Deterministic `For` Loop (Standard Idiomatic Approach)**
   * **Logic:**  
     `Read N`  
     `For Counter = 1 To N Step 1`  
     `    Print Counter`  
     `End For`
   * **Pros:** Encapsulates initialization, condition checking, and incrementing into a single compact header—eliminating the risk of forgetting `Counter = Counter + 1`.

2. **Solution 2: Explicit Pre-Test `While` Loop (Flowchart / State-Machine Approach)**
   * **Logic:** Manage the counter variable explicitly across three distinct steps:  
     `Read N`  
     `Counter = 1` `(OR Counter = 0)`  
     `While (Counter <= N)` `(OR While (Counter < N))`  
     `    Counter = Counter + 1`  
     `    Print Counter`  
     `End While`
   * **Pros:** Directly maps 1-to-1 to basic flowchart symbols (`Rectangle` ==>> `Diamond` ==>> `Parallelogram` ==>> `Rectangle`) and gracefully skips printing entirely if `N < 1`.

3. **Solution 3: Post-Test `Do-While` Loop (With Boundary Guard)**
   * **Logic:** Execute the body first and check `Counter <= N` at the bottom (requires guarding `N >= 1` first so `N = 0` doesn't erroneously print `1`):  
     `Read N`  
     `If N >= 1 Then`  
     `    Counter = 1`  
     `    Do`  
     `        Print Counter`  
     `        Counter = Counter + 1`  
     `    While (Counter <= N)`  
     `End If`
   * **Pros:** Demonstrates the crucial edge-case difference between pre-test (`While`) and post-test (`Do-While`) loops when `N <= 0`.

4. **Solution 4: Recursive Call Stack (Functional Programming Approach)**
   * **Logic:** Replace explicit loops with a self-calling function `PrintRange(Current, N)` (or head recursion `PrintFrom1ToN(N)`):  
     `Procedure PrintFrom1ToN(N)`  
     `    If N < 1 Then Return`  
     `    PrintFrom1ToN(N - 1)`  
     `    Print N`  
     `End Procedure`
   * **Pros:** Purely stateless functional elegance (prints `1` through `N` as the call stack unwinds), though limited by stack memory depth for massive values of `N` (e.g., `N = 1,000,000`).

---
