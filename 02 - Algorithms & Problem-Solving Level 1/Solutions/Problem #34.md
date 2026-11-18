## 🧠 Deep Problem Deconstruction & Engineering Vision

Every algorithm designed in this course directly reflects the 5 core functionalities of a computer system:

1️⃣ **Input Data:** Taking raw data in.  
2️⃣ **Store Data:** Retaining data/instructions in memory.  
3️⃣ **Process Data:** Converting raw inputs into structured information.  
4️⃣ **Output Information:** Presenting calculated results.  
5️⃣ **Control:** Coordinating and directing sequence and execution flow.

---

### 🟢 Problem #34: Commission Percentage

> **Problem Statement:**  
> Write a program to ask the user to enter:  
> • `TotalSales`  
> The commission is calculated as `Percentage * TotalSales`. Decide which percentage tier to apply based on the following brackets:  
> • `> 1,000,000` ==>> Percentage is `1%` (`0.01`)  
> • `> 500K to 1M` ==>> Percentage is `2%` (`0.02`)  
> • `> 100K – 500K` ==>> Percentage is `3%` (`0.03`)  
> • `> 50K to 100K` ==>> Percentage is `5%` (`0.05`)  
> • Otherwise ==>> Percentage is `0%` (`0.00`)  
> *Example Input:* `110000`  
> *Output:* `3300` *(since 110,000$ * 0.03 = 3,300$)*

#### 🎯 Deep Analysis & Creator’s Reflection:
* **The Creator's Intent:** As the programmer, I am instructing the computer to read a continuous financial figure (`TotalSales`), classify it into a **tiered commission rate (`Percentage`)** via a cascading decision structure, and separate **policy selection** (determining `Percentage`) from **arithmetic execution** (`TotalCommission = Percentage * TotalSales`).
* **Core Concepts Introduced:** 
  1. **Separation of Decision & Calculation (DRY Principle):** Instead of duplicating `TotalCommission = TotalSales * 0.01`, `TotalCommission = TotalSales * 0.02`, etc., inside every `If` branch, each branch simply assigns the state variable `Percentage`, and a **single** calculation statement (`TotalCommission = Percentage * TotalSales`) runs at the bottom after the decision block!
  2. **Strict Boundary Precision (`>` vs. `>=`):** Notice that `1,000,000` belongs to the `2%` tier (`> 500K to 1M`), whereas `1,000,001` belongs to the `1%` tier (`> 1,000,000`). Getting strict (`>`) vs. inclusive (`<=`) inequalities right at bracket edges prevents costly financial off-by-one bugs!

#### ⚙️ Computer Functionality Mapping:
* 📥 **Input Data:** Receives a single numeric financial amount: `TotalSales`.
* 💾 **Store Data:** Allocates floating-point memory variables for `TotalSales`, `Percentage`, and `TotalCommission`.
* ⚙️ **Process Data:** 
  1. Evaluates tiered sales brackets to assign `Percentage` (`0.01`, `0.02`, `0.03`, `0.05`, or `0.00`).
  2. Multiplies `TotalCommission = Percentage * TotalSales`.
* 📤 **Output Information:** Displays the calculated `TotalCommission` on the monitor screen.
* 🎮 **Control:** Multi-branch cascading selection (`If / Else If / Else`) that converges back into a single sequential multiplication and output step.

---

#### 🛠️ Multiple Algorithmic & Architectural Solutions Explored:

Can tiered commission calculation be structured in different ways? **Yes!** Here are four clean engineering approaches:

1. **Solution 1: Descending Threshold Ladder + Unified Calculation (Clean Flowchart Approach)**
   * **Logic:** Check tiers from highest to lowest so each `Else If` implicitly knows the upper bound has already been ruled out:  
     `Read TotalSales`  
     `If TotalSales > 1000000 Then Percentage = 0.01`  
     `Else If TotalSales > 500000 Then Percentage = 0.02`  
     `Else If TotalSales > 100000 Then Percentage = 0.03`  
     `Else If TotalSales > 50000 Then Percentage = 0.05`  
     `Else Percentage = 0.00`  
     `End If`  
     `TotalCommission = Percentage * TotalSales`  
     `Print TotalCommission`
   * **Pros:** Zero redundant range checks, avoids floating-point boundary gaps (e.g., `100000.50`), and computes the commission in one single place.

2. **Solution 2: Explicit Closed-Interval Checks (Order-Independent Approach)**
   * **Logic:** Explicitly check both lower and upper bounds in each branch:  
     `If (TotalSales > 1000000) Then Percentage = 0.01`  
     `Else If (TotalSales > 500000 AND TotalSales <= 1000000) Then Percentage = 0.02`  
     `Else If (TotalSales > 100000 AND TotalSales <= 500000) Then Percentage = 0.03`  
     `Else If (TotalSales > 50000 AND TotalSales <= 100000) Then Percentage = 0.05`  
     `Else Percentage = 0.00`  
     `End If`
   * **Pros:** Every branch is self-documenting and immune to accidental reordering of `Else If` blocks.

3. **Solution 3: Modular Function Decomposition (`GetCommissionPercentage` + `CalculateTotalCommission`)**
   * **Logic:** Split rate lookup and commission calculation into two dedicated functions:  
     `Function GetCommissionPercentage(TotalSales)` -> returns `0.01`..`0.00`  
     `Function CalculateTotalCommission(TotalSales) -> Return GetCommissionPercentage(TotalSales) * TotalSales`
   * **Pros:** Separates *business policy lookup* from *financial calculation* (Single Responsibility Principle), making unit testing effortless.

4. **Solution 4: Data-Driven Bracket Table (Enterprise Scalable Architecture)**
   * **Logic:** Store threshold minimums `[1000000, 500000, 100000, 50000]` and rates `[0.01, 0.02, 0.03, 0.05]` in parallel arrays:  
     `MinSales = [1000000, 500000, 100000, 50000]`  
     `Rates    = [0.01, 0.02, 0.03, 0.05]`  
     `Percentage = 0.00`  
     `For i = 0 To 3`  
     `    If TotalSales > MinSales[i] Then`  
     `        Percentage = Rates[i]`  
     `        Break`  
     `    End If`  
     `End For`
   * **Pros:** Decouples business rules from control flow—allowing finance teams to add new brackets or adjust percentages without modifying code logic!

---
