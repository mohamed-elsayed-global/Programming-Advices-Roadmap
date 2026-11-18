## 🧠 Deep Problem Deconstruction & Engineering Vision

Every algorithm designed in this course directly reflects the 5 core functionalities of a computer system:

1️⃣ **Input Data:** Taking raw data in.  
2️⃣ **Store Data:** Retaining data/instructions in memory.  
3️⃣ **Process Data:** Converting raw inputs into structured information.  
4️⃣ **Output Information:** Presenting calculated results.  
5️⃣ **Control:** Coordinating and directing sequence and execution flow.

---

### 🟢 Problem #25: Read Until Age Between 18 and 45

> **Problem Statement:**  
> Write a program to ask the user to enter:  
> • `Age`  
> If `Age` is between `18` and `45`, print **"Valid Age"**; otherwise print **"Invalid Age"** and re-ask the user to enter a valid age.  
> *Note:* You should keep asking the user to enter a valid age until he/she enters it.

#### 🎯 Deep Analysis & Creator’s Reflection:
* **The Creator's Intent:** As the programmer, I am upgrading Problem #24 from a passive one-shot validator into an **active input-enforcement loop**. Instead of terminating on bad input, I instruct the computer to trap execution inside an iterative validation cycle (`While` / `Do-While`) that continuously prompts the user until `Age` satisfies the closed interval 18 <= Age <=  45.
* **Core Concepts Introduced:** 
  1. **Input Validation Loops (Iterative Guarding):** Preventing corrupted or out-of-range user data from ever reaching downstream business logic by refusing to exit the input loop until valid data is supplied.
  2. **Loop Continuation vs. Termination Conditions (De Morgan's Law):** Notice the logical inversion! We want to **stop** when `Age >= 18 AND Age <= 45`, which means the `While` loop must **continue** while `NOT (Age >= 18 AND Age <= 45)`—equivalent to `Age < 18 OR Age > 45`.
  3. **Infinite Loop Prevention:** Ensuring the `Read Age` statement is placed *inside* the loop body so the state variable `Age` can mutate on every iteration toward the exit condition.

#### ⚙️ Computer Functionality Mapping:
* 📥 **Input Data:** Repeatedly receives numeric `Age` inputs from the user until a valid value is entered.
* 💾 **Store Data:** Allocates dynamic memory for the `Age` variable (overwritten on each retry iteration).
* ⚙️ **Process Data:** Evaluates loop exit/continuation condition: `(Age >= 18 AND Age <= 45)` ==>> Boolean (`True` / `False`).
* 📤 **Output Information:** Displays `"Invalid Age"` on failed attempts, and `"Valid Age"` once a valid input breaks the loop.
* 🎮 **Control:** Backward-jumping **looping control flow** that routes execution back to the input prompt on `False` and exits forward on `True`.

---

#### 🛠️ Multiple Algorithmic & Architectural Solutions Explored:

Can iterative input validation be structured in different ways? **Yes!** Here are four clean engineering approaches:

1. **Solution 1: Pre-Test `While` Loop with Initial Read (Standard Flowchart Approach)**
   * **Logic:** Perform an initial `Read Age` before the loop, then loop while the age is out of range:  
     `Read Age`  
     `While (Age < 18 OR Age > 45)`  
     `    Print "Invalid Age"`  
     `    Read Age`  
     `End While`  
     `Print "Valid Age"`
   * **Pros:** Avoids printing `"Invalid Age"` before the user has even entered their first guess, and guarantees `Age` is initialized before evaluation.

2. **Solution 2: Post-Test `Do-While` Loop (Single-Read Entry Approach)**
   * **Logic:** Execute the prompt at least once, then repeat while invalid:  
     `Do`  
     `    Read Age`  
     `    If (Age < 18 OR Age > 45) Then Print "Invalid Age"`  
     `While (Age < 18 OR Age > 45)`  
     `Print "Valid Age"`
   * **Pros:** Eliminates duplicating the `Read Age` prompt outside and inside the loop (DRY principle), though it evaluates the range condition twice on invalid attempts.

3. **Solution 3: Modular `ReadAgeInRange(From, To)` Function (Scalable Architecture)**
   * **Logic:** Encapsulate the entire retry loop inside a reusable function `ReadNumberInRange(18, 45)` (combining Problem #24's `ValidateNumberInRange` helper with a loop):  
     `Function ReadNumberInRange(From, To)`  
     `    Read Num`  
     `    While NOT ValidateNumberInRange(Num, From, To)`  
     `        Print "Invalid Number, try again:"`  
     `        Read Num`  
     `    End While`  
     `    Return Num`  
     `End Function`
   * **Pros:** Production-grade software engineering—any future program needing validated numeric input (e.g., menu choices `1..5`, grades `0..100`) simply calls `ReadNumberInRange(From, To)`!

4. **Solution 4: Infinite Loop with Explicit `Break` Guard (`While True`)**
   * **Logic:** Use a single exit point inside the loop body to avoid repeating either the prompt or the condition:  
     `While True`  
     `    Read Age`  
     `    If (Age >= 18 AND Age <= 45) Then Break`  
     `    Print "Invalid Age"`  
     `End While`  
     `Print "Valid Age"`
   * **Pros:** Zero code duplication (both `Read Age` and the range condition appear only once) and reads naturally as "loop until valid."

---
