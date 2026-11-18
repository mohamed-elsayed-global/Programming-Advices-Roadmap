## 🧠 Deep Problem Deconstruction & Engineering Vision

Every algorithm designed in this course directly reflects the 5 core functionalities of a computer system:

1️⃣ **Input Data:** Taking raw data in.  
2️⃣ **Store Data:** Retaining data/instructions in memory.  
3️⃣ **Process Data:** Converting raw inputs into structured information.  
4️⃣ **Output Information:** Presenting calculated results.  
5️⃣ **Control:** Coordinating and directing sequence and execution flow.

---

### 🟢 Problem #35: Piggy Bank Calculator

> **Problem Statement:**  
> Write a program to ask the user to enter:  
> • `Pennies`, `Nickels`, `Dimes`, `Quarters`, `Dollars`  
> Then calculate the **Total Pennies** and **Total Dollars** and print them on the screen, given that:  
> • `Penny = 1`  
> • `Nickel = 5`  
> • `Dime = 10`  
> • `Quarter = 25`  
> • `Dollar = 100`  
> *Example Inputs:* `5, 5, 5, 5, 5`  
> *Outputs:*  
> `705 Pennies`  
> `7.05 Dollars`

#### 🎯 Deep Analysis & Creator’s Reflection:
* **The Creator's Intent:** As the programmer, I am instructing the computer to read five distinct currency denomination counts, normalize them into a **single atomic base unit** (`TotalPennies`) using weighted linear combination, and then derive the macroscopic unit (`TotalDollars = TotalPennies / 100.0`) before displaying both representations.
* **Core Concepts Introduced:** 
  1. **Base-Unit Normalization (Avoiding Floating-Point Currency Bugs):** In financial software engineering, summing coins directly as dollars (`0.01 + 0.05 + 0.10 + 0.25`) causes binary floating-point rounding errors (e.g., `0.1 + 0.2 = 0.30000000000000004`!). Computing everything in **integer cents (`TotalPennies`)** first guarantees 100% exact arithmetic, converting to dollars only at the final display step.
  2. **Integer Division Trap (`TotalPennies / 100` vs. `TotalPennies / 100.0`):** In strongly typed languages like C++, writing `705 / 100` performs integer truncation and outputs `7` instead of `7.05`! Dividing by a floating-point literal (`100.0`) or casting `(float)TotalPennies / 100` is mandatory to preserve the `.05` cents.

#### ⚙️ Computer Functionality Mapping:
* 📥 **Input Data:** Receives five integer coin/bill quantities: `Pennies`, `Nickels`, `Dimes`, `Quarters`, and `Dollars`.
* 💾 **Store Data:** Allocates integer memory for the five denomination counts plus `TotalPennies`, and floating-point memory for `TotalDollars`.
* ⚙️ **Process Data:** 
  1. Weighted Sum: `TotalPennies = (Pennies * 1) + (Nickels * 5) + (Dimes * 10) + (Quarters * 25) + (Dollars * 100)`
  2. Unit Conversion: `TotalDollars = TotalPennies / 100.0`
* 📤 **Output Information:** Displays `TotalPennies` and `TotalDollars` sequentially on the monitor screen.
* 🎮 **Control:** Linear sequential execution flow (`Start` ==>> `Read 5 Inputs` ==>> `Compute TotalPennies` ==>> `Compute TotalDollars` ==>> `Print Both` ==>> `End`).

---

#### 🛠️ Multiple Algorithmic & Architectural Solutions Explored:

Can a multi-denomination currency calculator be structured in different ways? **Yes!** Here are four clean engineering approaches:

1. **Solution 1: Direct Weighted Linear Combination (Flowchart Approach)**
   * **Logic:**  
     `Read Pennies, Nickels, Dimes, Quarters, Dollars`  
     `TotalPennies = Pennies * 1 + Nickels * 5 + Dimes * 10 + Quarters * 25 + Dollars * 100`  
     `TotalDollars = TotalPennies / 100.0`  
     `Print TotalPennies`  
     `Print TotalDollars`
   * **Pros:** Transparent, maps 1-to-1 to basic flowchart symbols, and performs exact integer arithmetic before a single final division.

2. **Solution 2: Named Constants for Denominations (Clean Code / Self-Documenting Approach)**
   * **Logic:** Eliminate "magic numbers" (`5, 10, 25, 100`) by declaring named constants:  
     `Const PENNY_VAL = 1, NICKEL_VAL = 5, DIME_VAL = 10, QUARTER_VAL = 25, DOLLAR_VAL = 100`  
     `TotalPennies = (Pennies * PENNY_VAL) + (Nickels * NICKEL_VAL) + (Dimes * DIME_VAL) + (Quarters * QUARTER_VAL) + (Dollars * DOLLAR_VAL)`  
     `TotalDollars = TotalPennies / DOLLAR_VAL` *(with float cast)*
   * **Pros:** Dramatically improves readability and makes adapting the calculator to another currency (e.g., Euros/Cents or Pounds/Pence) trivial.

3. **Solution 3: Structured Record / `struct stPiggyBankContent` (Modular Architecture)**
   * **Logic:** Group the five related inputs into a single cohesive data structure passed to a pure calculation function `CalculateTotalPennies(PiggyBank)`:  
     `Struct stPiggyBank { Pennies, Nickels, Dimes, Quarters, Dollars }`  
     `Function CalculateTotalPennies(Bank) -> Returns integer sum`  
     `Main: Bank = ReadPiggyBank() -> Pennies = CalculateTotalPennies(Bank) -> Print Pennies, Pennies / 100.0`
   * **Pros:** Prevents parameter-order bugs (accidentally swapping `Dimes` and `Nickels` when calling a 5-parameter function!) and encapsulates domain data cleanly.

4. **Solution 4: Data-Driven Parallel Arrays (Scalable Currency Engine)**
   * **Logic:** Store denomination weights `[1, 5, 10, 25, 100]` and user counts in arrays and compute the dot product in a loop:  
     `Weights = [1, 5, 10, 25, 100]`  
     `Counts  = [Pennies, Nickels, Dimes, Quarters, Dollars]`  
     `TotalPennies = 0`  
     `For i = 0 To 4`  
     `    TotalPennies = TotalPennies + (Counts[i] * Weights[i])`  
     `End For`
   * **Pros:** Scales effortlessly if additional denominations (half-dollars `50`, five-dollar bills `500`, twenty-dollar bills `2000`) are added later without changing the core loop logic!

---
