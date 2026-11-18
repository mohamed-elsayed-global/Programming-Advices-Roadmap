## 🧠 Deep Problem Deconstruction & Engineering Vision

Every algorithm designed in this course directly reflects the 5 core functionalities of a computer system:

1️⃣ **Input Data:** Taking raw data in.  
2️⃣ **Store Data:** Retaining data/instructions in memory.  
3️⃣ **Process Data:** Converting raw inputs into structured information.  
4️⃣ **Output Information:** Presenting calculated results.  
5️⃣ **Control:** Coordinating and directing sequence and execution flow.

---

### 🟢 Problem #44: Day Of Week

> **Problem Statement:**  
> Write a program to ask the user to enter:  
> • `Day` (an integer from `1` to `7`)  
> Then print the corresponding day of the week as follows:  
> • `1` ==>> Print `Sunday`  
> • `2` ==>> Print `Monday`  
> • `3` ==>> Print `Tuesday`  
> • `4` ==>> Print `Wednesday`  
> • `5` ==>> Print `Thursday`  
> • `6` ==>> Print `Friday`  
> • `7` ==>> Print `Saturday`  
> • Otherwise ==>> Print `"Wrong Day"` and ask the user to enter the day again.  
> *Example Input:* `6`  
> *Output:* `Its Friday`

#### 🎯 Deep Analysis & Creator’s Reflection:
* **The Creator's Intent:** As the programmer, I am combining **input range validation** (`Day < 1` or `Day > 7`) with a **7-way discrete value lookup** (`Switch` or `Else If` ladder) so that the computer rejects out-of-range numbers, prompts the user until a valid integer `[1..7]` is supplied, and maps that numeric index to its human-readable weekday string.
* **Core Concepts Introduced:** 
  1. **Validated Discrete Enumeration Mapping:** Real-world software often stores categorical concepts (days, months, statuses) as compact integers (`1..7` or `Enum`) in memory/databases and translates them to display strings only at the UI layer.
  2. **Pre-Validation Guard Loop (`Do-While`):** Wrapping `Read Day` inside a `Do ... While (Day < 1 OR Day > 7)` loop guarantees that by the time execution reaches the `Switch` / `If` block, `Day` is **100% guaranteed** to be a valid integer between `1` and `7`.

#### ⚙️ Computer Functionality Mapping:
* 📥 **Input Data:** Repeatedly reads an integer `Day` until a valid value in `[1..7]` is entered.
* 💾 **Store Data:** Allocates integer memory for `Day` (and optional string/enum variable `DayName`).
* ⚙️ **Process Data:** 
  1. Validates `1 <= Day <= 7` (re-prompting with `"Wrong Day"` on invalid inputs).
  2. Dispatches `Day` through a 7-branch lookup to resolve the matching weekday name.
* 📤 **Output Information:** Displays `"Its <DayName>"` (e.g., `"Its Friday"`) on the monitor screen.
* 🎮 **Control:** Input validation loop (`Do-While`) followed by a multi-way discrete selection (`Switch` / `If-Else If`) leading to `End`.

---

#### 🛠️ Multiple Algorithmic & Architectural Solutions Explored:

Can mapping a validated day number `[1..7]` to a weekday name be structured in different ways? **Yes!** Here are three clean engineering approaches:

1. **Solution 1: Validation Loop + `Switch` Statement (Clean Idiomatic Approach)**
   * **Logic:** Validate the range first, then use a jump-table `Switch` statement:  
     `Do`  
     `    Read Day`  
     `    If (Day < 1 OR Day > 7) Then Print "Wrong Day"`  
     `While (Day < 1 OR Day > 7)`  
     `Switch (Day)`  
     `    Case 1: Print "Its Sunday"`  
     `    Case 2: Print "Its Monday"`  
     `    Case 3: Print "Its Tuesday"`  
     `    Case 4: Print "Its Wednesday"`  
     `    Case 5: Print "Its Thursday"`  
     `    Case 6: Print "Its Friday"`  
     `    Case 7: Print "Its Saturday"`  
     `End Switch`
   * **Pros:** Separates input validation from value mapping, avoids repeating `Day ==` seven times, and compiles into an efficient O(1) jump table.

2. **Solution 2: Cascading `If / Else If` with Loopback (Flowchart Approach)**
   * **Logic:** Directly mirrors sequential decision diamonds where the final `Else` prints `"Wrong Day"` and jumps back to `Read Day`:  
     `Label ReadInput:`  
     `Read Day`  
     `If Day == 1 Then Print "Its Sunday"`  
     `Else If Day == 2 Then Print "Its Monday"`  
     `Else If Day == 3 Then Print "Its Tuesday"`  
     `Else If Day == 4 Then Print "Its Wednesday"`  
     `Else If Day == 5 Then Print "Its Thursday"`  
     `Else If Day == 6 Then Print "Its Friday"`  
     `Else If Day == 7 Then Print "Its Saturday"`  
     `Else`  
     `    Print "Wrong Day"`  
     `    GoTo ReadInput`  
     `End If`
   * **Pros:** Maps 1-to-1 to basic flowchart diamonds without needing a separate range-check condition.

3. **Solution 3: O(1) Array Lookup Table (Data-Driven Architecture)**
   * **Logic:** Store the 7 weekday names in an array and index directly using `Day - 1` after validating `1 <= Day <= 7`:  
     `Days = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"]`  
     `Day = ReadNumberInRange(1, 7)`  
     `Print "Its " + Days[Day - 1]`
   * **Pros:** Replaces 7 conditional branches with a single O(1) array lookup—making localization to other languages (e.g., Arabic or Spanish) as simple as swapping the array!

---
