## 🧠 Deep Problem Deconstruction & Engineering Vision

Every algorithm designed in this course directly reflects the 5 core functionalities of a computer system:

1️⃣ **Input Data:** Taking raw data in.  
2️⃣ **Store Data:** Retaining data/instructions in memory.  
3️⃣ **Process Data:** Converting raw inputs into structured information.  
4️⃣ **Output Information:** Presenting calculated results.  
5️⃣ **Control:** Coordinating and directing sequence and execution flow.

---

### 🟢 Problem #38: Is Prime Number?

> **Problem Statement:**  
> Write a program to read a number and check if it is a prime number or not.  
> *Note:* A prime number is a positive integer greater than 1 that has no positive divisors other than 1 and itself.  
> *Example Inputs:* `5`, `6`, `3`  
> *Outputs:*  
> `Prime`  
> `Not Prime`  
> `Prime`

#### 🎯 Deep Analysis & Creator’s Reflection:
* **The Creator's Intent:** As the programmer, I am instructing the computer to read a number `N`, test whether it can be evenly divided by any integer from `2` up to `N - 1` (or more efficiently, up to √N), and determine its prime status using a loop combined with a decision flag.
* **Core Concepts Introduced:** 
  1. **Prime Primality Testing & Divisibility Checking:** Utilizing the modulo operator (`N mod i == 0`) inside a loop to detect factor pairs. If any divisor is found between `2` and `N - 1`, the number is composite (`Not Prime`).
  2. **Early Exit Optimization (O(√N) Square Root Limit):** Recognizing that a composite number N must have a factor less than or equal to √N (e.g., for N = 36, divisors are tested up to √36 = 6), which drastically accelerates the computation for large numbers.

#### ⚙️ Computer Functionality Mapping:
* 📥 **Input Data:** Receives a single integer value: `N`.
* 💾 **Store Data:** Allocates memory for input `N`, loop counter `i`, and a boolean flag `IsPrime` (initialized to `True`).
* ⚙️ **Process Data:** 
  1. Guard edge cases (N <= 1 are not prime).
  2. Loop i from `2` to `N / 2` (or √N).
  3. If `N mod i == 0`, set `IsPrime = False` and exit/break early.
* 📤 **Output Information:** Displays `"Prime"` or `"Not Prime"` on the monitor screen.
* 🎮 **Control:** Counter-controlled loop with conditional early exit (`Break`) based on a divisibility test.

---

#### 🛠️ Multiple Algorithmic & Architectural Solutions Explored:

Can checking if a number is prime be structured in different ways? **Yes!** Here are five clean engineering approaches:

1. **Solution 1: Sequential Loop up to `N - 1` (Full-Range Approach)**
   * **Logic:**  
      `Read N`  
      `If N > 0 Then`  
      `    Counter = 2`  
      `    If N <= Counter Then`  
      `        Print "Prime"`  
      `    Else`  
      `        Loop:`  
      `            If (N Mod Counter == 0) Then`  
      `                Print "Not Prime"`  
      `            Else`  
      `                If Counter == N - 1 Then`  
      `                    Print "Prime"`  
      `                Else`  
      `                    Counter = Counter + 1`  
      `                    Repeat Loop`  
      `                End If`  
      `            End If`  
      `    End If`  
      ` Else`  
      `     Print "Number must be >0"`  
      `     // Loops back to Read N as shown in the flowchart`  
      ` End If`
   * **Pros:** Very intuitive and directly models the foundational definition of prime numbers by sequentially testing all potential divisors below N; includes robust input validation for non-positive numbers.
   * **Cons:** Highly inefficient with a linear time complexity of O(N) that makes it entirely impractical for large numbers; contains redundant computations by checking every single integer up to N - 1 instead of stopping at the square root; acts as a major performance bottleneck by failing to leverage basic mathematical optimizations and wasting valuable CPU cycles on unnecessary divisions.

2. **Solution 2: Half-Range Loop up to `N / 2` (Standard Educational Approach)**
   * **Logic:**  
     `Read N`  
     `If N <= 1 Then Print "Not Prime" (Exit)`  
     `IsPrime = True`  
     `For i = 2 To floor(N / 2)` // for integer division.  
     `    If (N mod i == 0) Then`  
     `        IsPrime = False`  
     `        Break`  
     `    End If`  
     `End For`  
     `If IsPrime Then Print "Prime" Else Print "Not Prime"`
   * **Pros:** Simple to understand; since no number greater than N/2 can evenly divide N (except N itself), looping up to N/2 cuts unnecessary iterations in half.

3. **Solution 3: Square Root Optimization (`√N`) (High-Performance Approach)**
   * **Logic:** Loop only up to the integer square root of N (`SquareRoot = Integer(SquareRoot(N))`), making large prime checks lightning-fast:  
     `Read N`  
     `If N <= 1 Then Print "Not Prime" (Exit)`  
     `IsPrime = True`  
     `Limit = Integer(SquareRoot(N))`  
     `For i = 2 To Limit`  
     `    If (N mod i == 0) Then`  
     `        IsPrime = False`  
     `        Break`  
     `    End If`  
     `End For`
   * **Pros:** Reduces time complexity from O(N) down to O((√N)), which is essential when testing large numbers (e.g., N = 1,000,000).

4. **Solution 4: Boolean Function Decomposition (`CheckIsPrime(N)`)**
   * **Logic:** Encapsulate the primality test into a reusable function returning `True` or `False`:  
     `Function CheckIsPrime(N) -> Returns Boolean`  
     `Main: Read N -> If CheckIsPrime(N) Then Print "Prime" Else Print "Not Prime"`
   * **Pros:** Follows the Single Responsibility Principle and allows checking prime status anywhere in a larger program without rewriting loops.

5. **Solution 5: Pre-computed Prime Sieve (For Range Analysis)**
   * **Logic:** If checking multiple numbers up to a maximum limit K, use the **Sieve of Eratosthenes** instead of individual trial divisions.
   * **Pros:** Highly efficient for bulk prime generation and testing across a range of numbers.

---
