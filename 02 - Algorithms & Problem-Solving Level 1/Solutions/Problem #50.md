## 🧠 Deep Problem Deconstruction & Engineering Vision

Every algorithm designed in this course directly reflects the 5 core functionalities of a computer system:

1️⃣ **Input Data:** Taking raw data in.  
2️⃣ **Store Data:** Retaining data/instructions in memory.  
3️⃣ **Process Data:** Converting raw inputs into structured information.  
4️⃣ **Output Information:** Presenting calculated results.  
5️⃣ **Control:** Coordinating and directing sequence and execution flow.

---

### 🟢 Problem #50: ATM PIN 3 Times (Capstone Problem)

> **Problem Statement:**  
> Write a program to read the ATM `PIN` code from the user, then check if `PIN == 1234`.  
> • If valid (`1234`), display the user's balance (`Your Balance is: 7500`).  
> • Otherwise, print `"Wrong PIN"` and ask the user to enter the PIN again.  
> • **Only allow the user to enter the PIN 3 times**; if all 3 attempts fail, print `"Card is locked!"`.  
> *(Assume User Balance is `7500`)*  
> *Example Inputs:* `1234` ==>> `Your Balance is: 7500` | `5151` (3 times) ==>> `Wrong PIN` ... `Card is locked!`

#### 🎯 Deep Analysis & Creator’s Reflection:
* **The Creator's Intent:** As the programmer, I am upgrading Problem #49's unlimited login loop into a **bounded-attempt security gatekeeper**—synthesizing **input validation**, **compound loop termination conditions (`PIN != 1234 AND Counter < 3`)**, and **post-loop state disambiguation** (determining *why* the loop exited: did the user succeed on attempt #3, or did they exhaust all 3 tries?).
* **Core Concepts Introduced:** 
  1. **Dual-Exit Loop Disambiguation (The "3rd Attempt Success" Edge Case):** A classic security bug occurs when a user enters the *correct* PIN (`1234`) on their **3rd and final attempt**: `Counter` reaches `3`, so the loop terminates! If the code naively checks `If Counter == 3 Then Print "Card is locked!"`, it will lock out a valid user! Checking `If PIN == 1234` (or returning `true` immediately from `Login()`) avoids this critical off-by-one state bug.
  2. **Compound Termination Conditions (`AND` / `OR` De Morgan's Law):** Keeping a retry loop alive requires *both* conditions to hold: the user hasn't succeeded yet (`PIN != 1234`) **AND** they still have remaining attempts (`Counter < 3`).

#### ⚙️ Computer Functionality Mapping:
* 📥 **Input Data:** Reads up to 3 `PIN` attempts from the user.
* 💾 **Store Data:** Allocates memory for `PIN`, attempt counter `Counter` (initialized to `0` or `3`), secret `VALID_PIN = 1234`, and `Balance = 7500`.
* ⚙️ **Process Data:** 
  1. Loops while `Counter < 3` and `PIN != 1234`.
  2. Increments attempt counter on each try; prints `"Wrong PIN"` if `PIN != 1234`.
  3. After loop exit, checks whether `PIN == 1234` (authenticated) or `Counter == 3` (locked out).
* 📤 **Output Information:** Displays either `"Your Balance is: 7500"` or `"Card is locked!"` on screen.
* 🎮 **Control:** Bounded **counter-and-condition loop** followed by a binary post-loop decision branch (`PIN == 1234?`) leading to `End`.

---

#### 🛠️ Multiple Algorithmic & Architectural Solutions Explored:

Can a 3-attempt ATM PIN security lock be structured in different ways? **Yes!** Here are four clean engineering approaches:

1. **Solution 1: Flowchart Loopback with `FailedAttempts` Counter (Flowchart Approach)**
   * **Logic:** Directly mirrors flowchart where `Counter` starts at `0`, increments on wrong PIN, checks `Counter == 3?`, and either locks the card or loops back:  
     `Counter = 0`  
     `Label ReadInput:`  
     `Read PIN`  
     `If (PIN == 1234) Then`  
     `    Print "Your Balance is: 7500"`  
     `Else`  
     `    Counter = Counter + 1`  
     `    Print "Wrong PIN"`  
     `    If (Counter < 3) Then GoTo ReadInput`  
     `    Else Print "Card is locked!"`  
     `End If`
   * **Pros:** Maps 1-to-1 to basic flowchart diamonds and arrows.

2. **Solution 2: Structured `For` Loop (`Attempt = 1 To 3`) with Early Exit**
   * **Logic:** Express the maximum retry bound directly via a deterministic `For` loop:  
     `For Attempt = 1 To 3`  
     `    Read PIN`  
     `    If (PIN == 1234) Then`  
     `        Print "Your Balance is: 7500"`  
     `        Exit Program`  
     `    End If`  
     `    Print "Wrong PIN"`  
     `End For`  
     `Print "Card is locked!"`
   * **Pros:** Ultra-concise; if the loop finishes all 3 iterations naturally without hitting `Exit`, execution falls straight through to `"Card is locked!"`.

3. **Solution 3: Configurable Security Policy Constants (`Const MAX_ATTEMPTS = 3`)**
   * **Logic:** Extract `Const VALID_PIN = "1234"`, `Const MAX_ATTEMPTS = 3`, and `Const ACCOUNT_BALANCE = 7500` into named constants.
   * **Pros:** Adheres to enterprise security best practices—allowing security administrators to adjust lockout thresholds (e.g., 3 vs. 5 attempts) without touching control-flow logic.

---
