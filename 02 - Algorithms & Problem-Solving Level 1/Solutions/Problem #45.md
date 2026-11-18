## 🧠 Deep Problem Deconstruction & Engineering Vision

Every algorithm designed in this course directly reflects the 5 core functionalities of a computer system:

1️⃣ **Input Data:** Taking raw data in.  
2️⃣ **Store Data:** Retaining data/instructions in memory.  
3️⃣ **Process Data:** Converting raw inputs into structured information.  
4️⃣ **Output Information:** Presenting calculated results.  
5️⃣ **Control:** Coordinating and directing sequence and execution flow.

---

### 🟢 Problem #45: Month Of Year

> **Problem Statement:**  
> Write a program to ask the user to enter:  
> • `Month` (an integer from `1` to `12`)  
> Then print the corresponding month of the year as follows:  
> • `1` ==>> Print `January`  
> • `2` ==>> Print `February`  
> • `3` ==>> Print `March`  
> • `4` ==>> Print `April`  
> • `5` ==>> Print `May`  
> • `6` ==>> Print `June`  
> • `7` ==>> Print `July`  
> • `8` ==>> Print `August`  
> • `9` ==>> Print `September`  
> • `10` ==>> Print `October`  
> • `11` ==>> Print `November`  
> • `12` ==>> Print `December`  
> • Otherwise ==>> Print `"Wrong Month"` and ask the user to enter the month again.  
> *Example Input:* `11`  
> *Output:* `November`

#### 🎯 Deep Analysis & Creator’s Reflection:
* **The Creator's Intent:** As the programmer, I am generalizing Problem #44 (7-way weekday lookup) to a **12-way calendar month lookup**. By pairing a **pre-validation boundary loop** (`Month < 1` or `Month > 12`) with a **multi-branch dispatch or O(1) lookup table**, I guarantee that invalid month numbers are rejected immediately and only valid integers `[1..12]` proceed to string resolution.
* **Core Concepts Introduced:** 
  1. **Scaling Multi-Way Branching (`12` Cases vs. Data-Driven Arrays):** As discrete case counts grow from 7 (days) to 12 (months) or 50 (states), long `If / Else If` chains become verbose and harder to maintain—highlighting why `Switch` jump tables, `Enum` types, and **O(1) array lookup tables** are preferred in production engineering.
  2. **Reusable Range-Validation Abstraction (`ReadNumberInRange(1, 12)`):** Notice that the validation logic for Problem #44 (`[1..7]`) and Problem #45 (`[1..12]`) is identical except for the upper bound—demonstrating the power of parameterized helper functions!

#### ⚙️ Computer Functionality Mapping:
* 📥 **Input Data:** Repeatedly reads an integer `Month` until a valid value in `[1..12]` is entered.
* 💾 **Store Data:** Allocates integer memory for `Month` (and optional enum/string variable `MonthName`).
* ⚙️ **Process Data:** 
  1. Validates `1 <= Month <= 12` (printing `"Wrong Month"` and looping on invalid inputs).
  2. Maps the validated `Month` index `[1..12]` to its corresponding calendar month name.
* 📤 **Output Information:** Displays the matching month name (e.g., `"November"`) on the monitor screen.
* 🎮 **Control:** Input validation loop (`Do-While`) followed by a 12-way discrete selection (`Switch` / `If-Else If` / Array index) leading to `End`.

---

#### 🛠️ Multiple Algorithmic & Architectural Solutions Explored:

Can mapping a validated month number `[1..12]` to a month name be structured in different ways? **Yes!** Here are three clean engineering approaches:

1. **Solution 1: Validation Loop + `Switch` Statement (Clean Idiomatic Approach)**
   * **Logic:** Validate `[1..12]` first, then dispatch through a 12-case `Switch` block:  
     `Do`  
     `    Read Month`  
     `    If (Month < 1 OR Month > 12) Then Print "Wrong Month"`  
     `While (Month < 1 OR Month > 12)`  
     `Switch (Month)`  
     `    Case 1:  Print "January"`  
     `    Case 2:  Print "February"`  
     `    Case 3:  Print "March"`  
     `    Case 4:  Print "April"`  
     `    Case 5:  Print "May"`  
     `    Case 6:  Print "June"`  
     `    Case 7:  Print "July"`  
     `    Case 8:  Print "August"`  
     `    Case 9:  Print "September"`  
     `    Case 10: Print "October"`  
     `    Case 11: Print "November"`  
     `    Case 12: Print "December"`  
     `End Switch`
   * **Pros:** Cleanly separates range validation from case mapping and compiles into a fast O(1) jump table.

2. **Solution 2: Cascading `If / Else If` with Loopback (Flowchart Approach)**
   * **Logic:** Directly mirrors sequential decision diamonds where the final `Else` prints `"Wrong Month"` and loops back to `Read Month`:  
     `Label ReadInput:`  
     `Read Month`  
     `If Month == 1 Then Print "January"`  
     `Else If Month == 2 Then Print "February"`  
     `...`  
     `Else If Month == 12 Then Print "December"`  
     `Else`  
     `    Print "Wrong Month"`  
     `    GoTo ReadInput`  
     `End If`
   * **Pros:** Maps 1-to-1 to basic flowchart diamonds without needing a separate range check.

3. **Solution 3: O(1) Array Lookup Table (Data-Driven Architecture)**
   * **Logic:** Store the 12 month names in a constant array and index directly with `Month - 1` after validation:  
     `Months = ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"]`  
     `Month = ReadNumberInRange(1, 12)`  
     `Print Months[Month - 1]`
   * **Pros:** Compresses 12 conditional branches into a single line of O(1) memory lookup and makes internationalization effortless!

---
