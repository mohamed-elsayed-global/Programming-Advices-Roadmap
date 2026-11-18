## 🧠 Deep Problem Deconstruction & Engineering Vision

Every algorithm designed in this course directly reflects the 5 core functionalities of a computer system:

1️⃣ **Input Data:** Taking raw data in.  
2️⃣ **Store Data:** Retaining data/instructions in memory.  
3️⃣ **Process Data:** Converting raw inputs into structured information.  
4️⃣ **Output Information:** Presenting calculated results.  
5️⃣ **Control:** Coordinating and directing sequence and execution flow.

---

### 🟢 Problem #23: Circle Area Described Around an Arbitrary Triangle

> **Problem Statement:**  
> Write a program to calculate a **circle's area described around (circumscribing) an arbitrary triangle**, then print it on the screen.  
> The user should enter:  
> • Side `a`  
> • Side `b`  
> • Side `c`  
> *Example Inputs:* `5`, `6`, `7`  
> *Output:* `40.088`

#### 🎯 Deep Analysis & Creator’s Reflection:
* **The Creator's Intent:** As the programmer, I am instructing the computer to read the three side lengths (`a`, `b`, `c`) of any arbitrary triangle, compute its semi-perimeter p = (a + b + c)/2, apply **Heron's Formula** alongside the **Circumradius Theorem**:
  R = (a * b * c)/(4 √((p(p - a)(p - b)(p - c))))
  square that circumradius, and multiply by pi (Area = pi * R^2) to output the area of the circumscribed circle passing through all three vertices of the triangle.
* **Core Concepts Introduced:** 
  1. **Multi-Stage Formula Decomposition:** Unlike earlier problems with a single direct formula, attempting to write this entire equation on one line creates unreadable code prone to parenthesis mismatches. Breaking it into intermediate semantic variables (`p`, `R`, `Area`) is essential software engineering practice.
  2. **Integer Division Trap in Semi-Perimeter (`p`):** If `a`, `b`, and `c` are entered as integers whose sum is odd (e.g., `5 + 6 + 6 = 17`), writing `(a + b + c) / 2` truncates `8.5` down to `8`! Always divide by `2.0` (`p = (a + b + c) / 2.0`) to preserve floating-point precision.

#### ⚙️ Computer Functionality Mapping:
* 📥 **Input Data:** Receives three numeric side lengths: `a`, `b`, and `c`.
* 💾 **Store Data:** Allocates constant memory for `PI` and floating-point memory variables for `a`, `b`, `c`, intermediate `p` and `R`, and final `Area`.
* ⚙️ **Process Data:** 
  1. Semi-Perimeter: `p = (a + b + c) / 2.0`
  2. Circumradius: `R = (a * b * c) / (4.0 * Sqrt(p * (p - a) * (p - b) * (p - c)))`
  3. Circle Area: `Area = PI * R * R`
* 📤 **Output Information:** Displays the calculated floating-point `Area` onto the monitor screen.
* 🎮 **Control:** Linear sequential execution flow (`Start` ==>> `Read a, b, c` ==>> `Compute p` ==>> `Compute R` ==>> `Compute Area` ==>> `Print Area` ==>> `End`).

---

#### 🛠️ Multiple Algorithmic & Architectural Solutions Explored:

Can calculating the circumcircle area of an arbitrary triangle be structured in different ways? **Yes!** Here are four clean engineering approaches:

1. **Solution 1: Decomposed Multi-Step Pipeline (Standard Clean Code Approach)**
   * **Logic:** Compute semi-perimeter `p` and circumradius `R` explicitly, then delegate to `CircleAreaByRadius(R)` from Problem #18:  
     `Const PI = 3.14159265`  
     `Read a, b, c`  
     `p = (a + b + c) / 2.0`  
     `R = (a * b * c) / (4.0 * Sqrt(p * (p - a) * (p - b) * (p - c)))`  
     `Area = PI * R * R`  
     `Print Area`
   * **Pros:** Crystal-clear readability, isolates each mathematical stage for effortless debugging, and reuses the `PI * R * R` circle area building block.

2. **Solution 2: Algebraic Cancellation of `Sqrt` (Precision & Speed Optimization)**
   * **Logic:** Notice that R has a square root in its denominator, and we immediately square R in Area = pi * R^2! Squaring cancels the `Sqrt` entirely:
     Area = pi * ((a * b * c)^2)/(16 * p(p - a)(p - b)(p - c))

     `p = (a + b + c) / 2.0`  
     `Numerator = (a * b * c) * (a * b * c)`  
     `Denominator = 16.0 * p * (p - a) * (p - b) * (p - c)`  
     `Area = PI * (Numerator / Denominator)`
   * **Pros:** Eliminates an expensive `Sqrt()` CPU call and avoids floating-point square-root rounding inaccuracies!

3. **Solution 3: Modular Separation via Heron's Triangle Area Function**
   * **Logic:** Encapsulate Heron's formula into a reusable helper `TriangleArea(a, b, c) = Sqrt(p * (p - a) * (p - b) * (p - c))`, then compute R = (a * b * c)/(4 * TriangleArea):  
     `K = TriangleArea(a, b, c)`  
     `R = (a * b * c) / (4.0 * K)`  
     `Area = CircleAreaByRadius(R)`
   * **Pros:** Demonstrates high-level software modularity—creating a reusable general triangle area function for future geometry problems.

4. **Solution 4: Triangle Inequality Guard (Domain Constraint Validation)**
   * **Logic:** Three side lengths form a valid triangle if and only if the sum of any two sides strictly exceeds the third (a + b > c, a + c > b, and b + c > a); otherwise, `p * (p - a) * (p - b) * (p - c) <= 0` causes a division-by-zero or imaginary square root crash:  
     `If (a + b <= c OR a + c <= b OR b + c <= a) Then Print "Invalid Triangle"`  
     `Else Compute and Print Area`
   * **Pros:** Protects the program from crashing or outputting `NaN` / `Infinity` on impossible side lengths (like `1, 2, 10`).

---
