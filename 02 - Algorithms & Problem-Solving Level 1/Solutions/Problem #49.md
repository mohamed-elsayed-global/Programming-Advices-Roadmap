## 🧠 Deep Problem Deconstruction & Engineering Vision

Every algorithm designed in this course directly reflects the 5 core functionalities of a computer system:

1️⃣ **Input Data:** Taking raw data in.  
2️⃣ **Store Data:** Retaining data/instructions in memory.  
3️⃣ **Process Data:** Converting raw inputs into structured information.  
4️⃣ **Output Information:** Presenting calculated results.  
5️⃣ **Control:** Coordinating and directing sequence and execution flow.

---

### 🟢 Problem #49: ATM PIN

> **Problem Statement:**  
> Write a program to read the ATM `PIN` code from the user, then check if `PIN == 1234`.  
> • If valid (`1234`), display the user's balance (`Your Balance is: 7500`).  
> • Otherwise, print `"Wrong PIN"` and ask the user to enter the PIN again.  
> *(Assume User Balance is `7500`)*  
> *Example Inputs:* `1234` ==>> `Your Balance is: 7500` | `5151` ==>> `Wrong PIN` *(and prompts again)*

#### 🎯 Deep Analysis & Creator’s Reflection:
* **The Creator's Intent:** As the programmer, I am instructing the computer to implement an **authentication gatekeeper loop**—the foundational pattern behind login screens, ATM terminals, and password prompts. Instead of exiting after a failed check, the program uses a validation loop (`Do-While` or `While`) to trap execution until the exact secret credential (`1234`) is matched, only unlocking the sensitive account state (`Balance = 7500`) once authentication succeeds.
* **Core Concepts Introduced:** 
  1. **Authentication Gatekeeper Pattern (`Do-While` Credential Loop):** Separating **credential verification** (`Login()` returning `true` when `PIN == "1234"`) from **protected resource access** (`ShowBalance()`). In this unlimited-attempt variant (contrasted with Problem #50's 3-attempt lockout), the loop continues indefinitely until `PIN == 1234`.
  2. **String vs. Integer PIN Representation:** While introductory flowcharts store `PIN` as an integer (`1234`), real-world banking systems store PINs as strings (`"0123"` vs. `123`) so leading zeros are never stripped by numeric parsing!

#### ⚙️ Computer Functionality Mapping:
* 📥 **Input Data:** Repeatedly reads `PIN` from the user until `"1234"` (`1234`) is entered.
* 💾 **Store Data:** Allocates memory for user input `PIN`, expected secret `VALID_PIN = 1234`, and account balance `Balance = 7500`.
* ⚙️ **Process Data:** Compares `PIN == 1234`; if false, outputs `"Wrong PIN"` and repeats input acquisition; if true, exits the validation loop.
* 📤 **Output Information:** Displays `"Your Balance is: 7500"` upon successful authentication.
* 🎮 **Control:** Indefinite **post-test validation loop (`Do-While`)** guarding the final sequential balance output.

---

#### 🛠️ Multiple Algorithmic & Architectural Solutions Explored:

Can an ATM PIN authentication loop be structured in different ways? **Yes!** Here are three clean engineering approaches:

1. **Solution 1: Post-Test `Do-While` Validation Loop (Clean Idiomatic Approach)**
   * **Logic:** Read the PIN at least once, display `"Wrong PIN"` if it fails, and repeat while `PIN != 1234`:  
     `Do`  
     `    Read PIN`  
     `    If (PIN != 1234) Then`  
     `        Print "Wrong PIN"`  
     `    End If`  
     `While (PIN != 1234)`  
     `Print "Your Balance is: 7500"`
   * **Pros:** Zero duplicate `Read PIN` statements (DRY principle) and guarantees `"Your Balance is: 7500"` is unreachable until `PIN == 1234`.

2. **Solution 2: Flowchart Loopback Structure (Flowchart Approach)**
   * **Logic:** Directly mirrors decision diamond where the `No` branch prints `"Wrong PIN"` and jumps back to `Read PIN`:  
     `Label ReadInput:`  
     `Read PIN`  
     `If (PIN == 1234) Then`  
     `    Print "Your Balance is: 7500"`  
     `Else`  
     `    Print "Wrong PIN"`  
     `    GoTo ReadInput`  
     `End If`
   * **Pros:** Maps 1-to-1 to basic flowchart diamonds and arrows.

3. **Solution 3: String-Based PIN Storage + Named Constants**
   * **Logic:** Store `Const VALID_PIN = "1234"` and `Const USER_BALANCE = 7500` as named constants using `string` comparison instead of integer comparison.
   * **Pros:** Preserves leading zeros (e.g., `"0042"`), avoids input stream crashes if a user accidentally types letters, and eliminates magic numbers.

---
