## 🧠 Deep Problem Deconstruction & Engineering Vision

Every algorithm designed in this course directly reflects the 5 core functionalities of a computer system:

1️⃣ **Input Data:** Taking raw data in.  
2️⃣ **Store Data:** Retaining data/instructions in memory.  
3️⃣ **Process Data:** Converting raw inputs into structured information.  
4️⃣ **Output Information:** Presenting calculated results.  
5️⃣ **Control:** Coordinating and directing sequence and execution flow.

---

### 🟢 Problem #36: Simple Calculator

> **Problem Statement:**  
> Write a program to ask the user to enter:  
> • `Number1`  
> • `Number2`  
> • `OperationType` (`+`, `-`, `*`, `/`)  
> Then perform the calculation according to the `OperationType` as follows:  
> • `"+"` : Add the two numbers (`Number1 + Number2`).  
> • `"-"` : Subtract the two numbers (`Number1 - Number2`).  
> • `"*"` : Multiply the two numbers (`Number1 * Number2`).  
> • `"/"` : Divide the two numbers (`Number1 / Number2`).  
> *Example Inputs:* `10`, `20`, `*`  
> *Output:* `200`

#### 🎯 Deep Analysis & Creator’s Reflection:
* **The Creator's Intent:** As the programmer, I am instructing the computer to read two numeric operands (`Number1`, `Number2`) alongside a **symbolic operator character** (`OperationType`), use a **multi-way dispatch structure (`If / Else If` or `Switch`)** to route execution to the matching arithmetic instruction, and output the computed result (or handle invalid operators / division by zero gracefully).
* **Core Concepts Introduced:** 
  1. **Control-Flow Dispatching (`Switch` vs. `If / Else If`):** Choosing between sequential boolean comparisons (`If OperationType == '+'`) and an indexed discrete value jump table (`Switch (OperationType)`), which cleanly expresses single-variable equality branching.
  2. **Runtime Edge-Case Guarding (Division by Zero & Invalid Operators):** In arithmetic dispatching, division (`'/'`) introduces a critical runtime hazard when `Number2 == 0`, while unrecognized characters (e.g., `'%'` or `'?'`) require a `Default` / `Else` fallback branch so the program never fails silently with uninitialized output.

#### ⚙️ Computer Functionality Mapping:
* 📥 **Input Data:** Receives two numbers (`Number1`, `Number2`) and one character/string operator (`OperationType`).
* 💾 **Store Data:** Allocates floating-point memory for `Number1`, `Number2`, and `Result`, plus character memory for `OperationType`.
* ⚙️ **Process Data:** Matches `OperationType` against `'+'`, `'-'`, `'*'`, or `'/'` and executes the corresponding ALU arithmetic operation.
* 📤 **Output Information:** Displays the calculated `Result` (or an error message for invalid operations) on the monitor screen.
* 🎮 **Control:** Multi-branch discrete selection (`Switch` or `If / Else If / Else`) routing execution to exactly one arithmetic path before `End`.

---

#### 🛠️ Multiple Algorithmic & Architectural Solutions Explored:

Can a four-function calculator be structured in different ways? **Yes!** Here are four clean engineering approaches:

1. **Solution 1: Discrete `Switch` Statement Dispatch (Standard Clean Approach)**
   * **Logic:**  
     `Read Number1, Number2, OperationType`  
     `Switch (OperationType)`  
     `    Case '+': Print (Number1 + Number2)`  
     `    Case '-': Print (Number1 - Number2)`  
     `    Case '*': Print (Number1 * Number2)`  
     `    Case '/': Print (Number1 / Number2)`  
     `    Default:  Print "Wrong Operation"`  
     `End Switch`
   * **Pros:** Idiomatic, avoids repeating `OperationType ==` four times, and scales cleanly if new operators (like `'%'` or `'^'`) are added later.

2. **Solution 2: Cascading `If / Else If / Else` Ladder (Flowchart Approach)**
   * **Logic:** Directly maps to sequential diamond decision nodes in basic flowcharts:  
     `Read Number1, Number2, OperationType`  
     `If OperationType == '+' Then Print (Number1 + Number2)`  
     `Else If OperationType == '-' Then Print (Number1 - Number2)`  
     `Else If OperationType == '*' Then Print (Number1 * Number2)`  
     `Else If OperationType == '/' Then Print (Number1 / Number2)`  
     `Else Print "Wrong Operation"`  
     `End If`
   * **Pros:** Works universally even in languages or string types where `Switch` statements are restricted to integer/character primitives.

3. **Solution 3: Defensive Division-by-Zero & `Enum` Type Safety**
   * **Logic:** Represent valid operations as a strongly typed `Enum enOperationType { Add = '+', Subtract = '-', Multiply = '*', Divide = '/' }` and guard against `Number2 == 0` before dividing:  
     `Case enOperationType.Divide:`  
     `    If Number2 == 0 Then Print "Error: Cannot divide by zero"`  
     `    Else Return Number1 / Number2`
   * **Pros:** Eliminates magic character literals across the codebase and prevents runtime crashes or `Infinity`/`NaN` output when dividing by zero.

4. **Solution 4: Pure Calculation Function (`Calculate(Num1, Num2, OpType)`)**
   * **Logic:** Decouple user I/O from arithmetic computation by returning the result from a dedicated function:  
     `Function Calculate(Number1, Number2, OpType) -> Returns float`  
     `Main: Read inputs -> Result = Calculate(Number1, Number2, OperationType) -> Print Result`
   * **Pros:** Follows the Single Responsibility Principle—the calculator engine can be reused in GUI apps, web APIs, or unit tests without console dependencies.

---
