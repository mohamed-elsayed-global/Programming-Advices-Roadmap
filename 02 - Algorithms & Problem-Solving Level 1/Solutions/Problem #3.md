## 🧠 Deep Problem Deconstruction & Engineering Vision

Every algorithm designed in this course directly reflects the 5 core functionalities of a computer system:

1️⃣ **Input Data:** Taking raw data in.  
2️⃣ **Store Data:** Retaining data/instructions in memory.  
3️⃣ **Process Data:** Converting raw inputs into structured information.  
4️⃣ **Output Information:** Presenting calculated results.  
5️⃣ **Control:** Coordinating and directing sequence and execution flow.

---

### 🟣 Problem #3: Check Odd or Even Number

> **Problem Statement:**  
> Write a program to ask the user to enter a number, then print "ODD" if it's odd, or "Even" if it's even.

#### 🎯 Deep Analysis & Creator’s Reflection:
* **The Creator's Intent:** I am instructing the computer to receive numerical data, store it, run a specific logic evaluation process (parity check), and utilize control structures to branch execution dynamically based on the outcome.

#### ⚙️ Computer Functionality Mapping:
* 📥 **Input Data:** Receives integer input `Num` from the user.
* 💾 **Store Data:** Stores `Num` and intermediate calculation state `Result` in memory.
* ⚙️ **Process Data:** Converts raw input into parity information via arithmetic logic unit (ALU) or string pattern matching.
* 📤 **Output Information:** Displays `"EVEN"` or `"ODD"` based on the evaluated outcome.
* 🎮 **Control:** Decision structure (`Result == 0?`) actively directs execution flow down one of two mutually exclusive paths (**Yes** branch or **No** branch).

#### 🛠️ Multiple Algorithmic Solutions Explored:

1. **Solution 1: Modulo Arithmetic (Standard Mathematical Process)**
   * **Process & Control:** `Result = Num mod 2`. If `Result == 0` ==>> Even, If Not ==>> Odd.
   * **Pros:** Highly efficient, hardware-aligned integer division remainder check.

2. **Solution 2: Whole Division & Fractional Check (Trial & Error / Visual Process)**
   * **Process & Control:** Divide `Num / 2`. Check if the result is a pure whole integer or contains a fraction.
   * **Pros:** Mimics visual human calculation without strictly relying on modulo operators.

3. **Solution 3: Last Digit Inspection (Pattern Recognition / Text Process)**
   * **Process & Control:** Read input as a string, extract the rightmost digit, and test against the set of even numbers \{0, 2, 4, 6, 8\}.
   * **Pros:** Pure structural pattern recognition that handles arbitrarily large numbers beyond standard hardware integer limits.

---
