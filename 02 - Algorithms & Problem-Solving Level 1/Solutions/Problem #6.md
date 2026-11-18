## 🧠 Deep Problem Deconstruction & Engineering Vision

Every algorithm designed in this course directly reflects the 5 core functionalities of a computer system:

1️⃣ **Input Data:** Taking raw data in.  
2️⃣ **Store Data:** Retaining data/instructions in memory.  
3️⃣ **Process Data:** Converting raw inputs into structured information.  
4️⃣ **Output Information:** Presenting calculated results.  
5️⃣ **Control:** Coordinating and directing sequence and execution flow.

---

### 🟢 Problem #6: Full Name (Concatenation)

> **Problem Statement:**  
> Write a program to ask the user to enter:  
> • First Name  
> • Last Name  
> Then Print Full Name on screen.  
> *Example Input:*  
Mohammed  
Abu-Hadhoud  
> *Output:* Mohammed Abu-Hadhoud

#### 🎯 Deep Analysis & Creator’s Reflection:
* **The Creator's Intent:** As the programmer, I am instructing the computer to read **multiple discrete string inputs**, allocate distinct memory addresses for each, execute a string processing operation (**Concatenation** with a whitespace separator), and output the combined result as a unified entity.
* **Core Concept Introduced:** String manipulation and data bonding without arithmetic calculations.

#### ⚙️ Computer Functionality Mapping:
* 📥 **Input Data:** Receives two separate string streams: `FirstName` and `LastName`.
* 💾 **Store Data:** Allocates dynamic memory buffers for both input strings and the resulting concatenated string.
* ⚙️ **Process Data:** Joins `FirstName` + `" "` + `LastName` into a single memory buffer (String Concatenation).
* 📤 **Output Information:** Displays the combined `FullName` string onto the monitor screen.
* 🎮 **Control:** Linear sequential flow from input acquisition to memory concatenation and final output.

---

#### 🛠️ Multiple Algorithmic Solutions Explored:

1. **Solution 1: Direct On-the-Fly Concatenation (Standard Approach)**
   * **Logic:** `FullName = FirstName + " " + LastName`, followed by printing `FullName`.
   * **Pros:** Clean, highly readable, standard practice across all programming languages.

2. **Solution 2: Immediate Print Stream (Memory Saving Approach)**
   * **Logic:** Print `FirstName` directly, print a space `" "`, then print `LastName` directly without storing the combined string in a temporary `FullName` variable.
   * **Pros:** Saves memory allocation by avoiding an extra variable buffer for intermediate state.
   * **Cons:** Less reusable if the full name needs to be referenced multiple times later in the program.

---
