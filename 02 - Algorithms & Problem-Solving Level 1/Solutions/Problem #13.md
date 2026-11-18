## 🧠 Deep Problem Deconstruction & Engineering Vision

Every algorithm designed in this course directly reflects the 5 core functionalities of a computer system:

1️⃣ **Input Data:** Taking raw data in.  
2️⃣ **Store Data:** Retaining data/instructions in memory.  
3️⃣ **Process Data:** Converting raw inputs into structured information.  
4️⃣ **Output Information:** Presenting calculated results.  
5️⃣ **Control:** Coordinating and directing sequence and execution flow.

---

### 🟢 Problem #13: Maximum of Three Numbers

> **Problem Statement:**  
> Write a program to ask the user to enter 3 numbers:  
> • A  
> • B  
> • C  
> Then print the **Max Number**.  
> *Example Inputs:* `30`, `10`, `20`  
> *Output:* `30`

#### 🎯 Deep Analysis & Creator’s Reflection:
* **The Creator's Intent:** As the programmer, I am instructing the computer to read **three scalar inputs** (`A`, `B`, `C`), evaluate their relative magnitudes through multi-stage relational comparisons, and determine the single greatest value among the three candidates.
* **Core Concepts Introduced:** 
  1. **Multi-Operand Decision Trees vs. Sequential Elimination:** Moving beyond a simple two-way branch (`If-Else`) into nested branching or iterative state tracking.
  2. **Algorithmic Scalability:** Recognizing why the "King of the Hill" state variable pattern scales effortlessly from 2 inputs to 3 (and beyond), whereas nested decision trees grow exponentially in complexity.

#### ⚙️ Computer Functionality Mapping:
* 📥 **Input Data:** Receives three numeric scalars: `A`, `B`, and `C`.
* 💾 **Store Data:** Allocates dynamic memory variables for `A`, `B`, `C` (and an optional `Max` tracker variable).
* ⚙️ **Process Data:** Executes sequential or compound relational comparisons (`A > B`, `A > C`, `B > C`) to isolate the maximum magnitude.
* 📤 **Output Information:** Displays the winning maximum number onto the monitor screen.
* 🎮 **Control:** Multi-branching decision structure or sequential state-update checks directing execution to output the single highest value.

---

#### 🛠️ Multiple Algorithmic & Architectural Solutions Explored:

Can finding the maximum of three numbers be engineered in different ways? **Yes!** Here are four distinct algorithmic approaches:

1. **Solution 1: Nested Decision Tree / Binary Elimination (Standard Flowchart Approach)**
   * **Logic:**  
     `If A > B Then`  
     `    If A > C Then Print A Else Print C`  
     `Else`  
     `    If B > C Then Print B Else Print C`  
     `End If`
   * **Pros:** Performs the exact mathematical minimum number of comparisons (always **2 comparisons** regardless of input order!).

2. **Solution 2: "King of the Hill" State Tracker (Scalable Pattern Approach)**
   * **Logic:** Assume `A` is the champion, then let `B` and `C` challenge it sequentially:  
     `Max = A`  
     `If B > Max Then Max = B`  
     `If C > Max Then Max = C`  
     `Print Max`
   * **Pros:** Zero nested `If-Else` complexity! Adding a 4th or 5th variable requires only a single extra `If` line, making this the foundational pattern for arrays and loops.

3. **Solution 3: Compound Logical Operators (`AND` / `Else-If` Ladder)**
   * **Logic:** Evaluate each candidate's supremacy explicitly using compound `AND` conditions:  
     `If (A >= B AND A >= C) Then Print A`  
     `Else If (B >= A AND B >= C) Then Print B`  
     `Else Print C`
   * **Pros:** Reads like plain English specifications; note the use of `>=` instead of `>` to properly handle edge cases where two numbers are tied for the maximum (e.g., `30, 30, 10`).

4. **Solution 4: Functional Composition / Divide & Conquer (Reusing Problem #12)**
   * **Logic:** Decompose the 3-number problem into two calls of our existing `MaxOf2(x, y)` algorithm from Problem #12:  
     `Max = MaxOf2(MaxOf2(A, B), C)`  
     `Print Max`
   * **Pros:** Demonstrates **abstraction and code reuse**—solving a harder problem by composing smaller, already-proven algorithmic building blocks!

---
