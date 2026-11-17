# 🧠 02 - Algorithms & Problem Solving - Level 1

This directory contains my algorithmic analyses, step-by-step logic designs, flowcharts, and personal reflections for **[02 - Algorithms & Problem Solving - Level 1](https://programmingadvices.com/p/00316b1)** by **Dr. Mohammed Abu-Hadhoud**.

---

## 📂 Subfolder Structure

* `README.md` – Course analysis, difficulty progression, Course 1 conceptual mappings, and deep-dive reflections on challenging problems.
* `Certificate Of Completion.pdf` – Official verified certificate of completion for this course.
* `Solutions/` – Individual numbered Markdown files (`Problem #1.md` to `Problem #50.md`) containing step-by-step algorithmic solutions and flowcharts for all 50 problems.

---

## 📜 Course Summary & Personal Competencies

> **Course Completion Statement:**  
> Upon successfully completing the **Algorithms & Problem Solving – Level 1** course administered by **Dr. Mohammed Abu-Hadhoud** (*Programming Advices*), I have mastered the foundational discipline of computational thinking independent of any programming language syntax. Through this course, I am able to:
>
> * **Separate Thinking from Coding:** Analyze requirements, define inputs/processes/outputs (IPO), and design bug-free logic before touching a single line of code.
> * **Design Visual Flowcharts:** Translate abstract problem statements into standardized flowchart symbols (Terminals, Input/Output parallelograms, Process rectangles, Decision diamonds, and Flowlines).
> * **Construct Deterministic Algorithms:** Write clear, unambiguous, step-by-step instructions that handle edge cases, validation loops, and state mutations reliably.
> * **Apply Boolean & Relational Logic:** Structure complex multi-branch decision trees (`AND`, `OR`, `NOT`, nested conditions) to control execution flow accurately.
> * **Engineer Iterative Loops & Accumulators:** Design counter-controlled and condition-controlled loops (`While` / `Do-While` patterns) using accumulators (`Sum`, `Counter`, `Factorial`) and sentinel values.
> * **Bridge Theory to Implementation:** Map theoretical computer science concepts from *Course 01* (memory states, arithmetic operations, parity, primality, and data types) directly into algorithmic workflows, preparing for **Course 03 (Introduction to Programming with C++ – Level 1)**.

---

## 🎯 Course Objectives & Conceptual Architecture

The core philosophy of this course is simple yet transformative: **Programming is not a programming language; a language is merely a tool to express an algorithm.**

### Core Concepts Presented
1. **Input ==>> Process ==>> Output (IPO Model):** Every problem is broken down into what data enters the system, how it is transformed in memory, and what result is delivered.
2. **Sequential Execution:** Understanding that instructions execute top-to-bottom in a strict deterministic order unless redirected.
3. **Selection (Decision Making):** Branching execution paths based on boolean evaluations (`True`/`False`).
4. **Iteration (Repetition):** Automating repetitive tasks using loop invariants, counters, and termination conditions to prevent infinite loops.
5. **Input Validation & Defensive Logic:** Ensuring algorithms verify constraints (e.g., positive numbers, valid age ranges, non-zero divisors) before processing.

---

## 📈 Gradation of Problem Levels (The 50-Problem Roadmap)

The 50 problems are carefully engineered with a smooth, deliberate **gradation in cognitive load**, transitioning from linear mechanics to multi-layered algorithmic state tracking:

| Tier | Problem Range | Cognitive Focus | Algorithmic Mechanics |
| :--- | :--- | :--- | :--- |
| **Level 1: Linear Foundations** | `#01` – `#06` | **I/O & Basic Sequencing** | Reading user inputs, string concatenation, and displaying formatted outputs without branching. |
| **Level 2: Arithmetic & State** | `#07` – `#23` | **Mathematical Modeling** | Applying formulas (areas, averages, swapping variables using a `Temp` memory slot) and basic `If/Else` checks. |
| **Level 3: Decision & Validation** | `#24` – `#25` | **Defensive Looping** | Introducing `Read Until` validation loops to trap invalid inputs until conditions are satisfied. |
| **Level 4: Iterative Loops & Accumulators** | `#26` – `#35` | **Counters & Series** | Mastering `Counter` increments/decrements, summation accumulators, factorials, and power calculations. |
| **Level 5: Sentinels & Nested Logic** | `#36` – `#43` | **Complex State & Primality** | Sentinel-controlled loops (`-99`), multi-way switch logic, primality testing, and financial/time breakdowns. |
| **Level 6: Modular Decomposition** | `#44` – `#50` | **Real-World Systems** | Lookup mappings (days/months), character generation, ATM PIN authentication with retry limits, and loan calculators. |

---

## 🔥 Deep-Dive: Most Challenging Problems & Personal Reflections

While every problem reinforced structured thinking, **8 specific problems** stood out as the most intellectually demanding, requiring careful flowchart tracing, edge-case handling, and state management:

### 1. Problem `#27`: Print Numbers from N to 1
* **The Challenge:** Reversing the standard counting direction required shifting from an upward counter (`Counter = Counter + 1`) to a downward state mutation (`Counter = N`, `Counter = Counter - 1`).
* **Key Breakthrough:** Realizing that loop initialization (`Counter = N`) and termination (`Counter < 1` or `Counter == 0`) must mirror each other precisely to avoid off-by-one errors.

### 2. Problem `#28`: Sum Odd Numbers from 1 to N
* **The Challenge:** Combining **iteration** with **conditional filtering** inside the same loop while maintaining a running `Sum` accumulator.
* **Key Breakthrough:** Learning to initialize `Sum = 0` *before* the loop begins (if placed inside, it resets every iteration) and checking parity (`Counter mod 2 != 0`) before accumulating.

### 3. Problem `#29`: Sum Even Numbers from 1 to N
* **The Challenge:** Building on `#28`, ensuring accurate boundary inclusion when N itself is even versus odd, and optimizing step increments vs. modulo checks.
* **Key Breakthrough:** Reinforcing the concept that `0` is the additive identity for summation accumulators and understanding the two valid algorithmic approaches (step-by-1 with modulo check vs. step-by-2).

### 4. Problem `#30`: Factorial of N!
* **The Challenge:** Switching from an **additive accumulator** (`Sum = 0`) to a **multiplicative accumulator** (`Factorial = 1`), alongside handling negative inputs and the edge case of 0! = 1.
* **Key Breakthrough:** Initializing `Factorial = 0` would collapse the entire multiplication to zero. Combined with a validation loop for N < 0, this taught me how mathematical identities dictate variable initialization.

### 5. Problem `#32`: Power of M (N^M)
* **The Challenge:** Computing exponents iteratively without relying on built-in math functions, especially handling the universal edge case where M = 0 (where any number raised to 0 equals 1).
* **Key Breakthrough:** Designing an early-exit decision diamond (`If M == 0 -> Print 1`) before entering the multiplication loop (`P = P * N` repeated M times).

### 6. Problem `#38`: Is Prime Number?
* **The Challenge:** Translating the mathematical definition of primality into an efficient, deterministic, guarded loop that handles and validates positive and non-positive edge cases (N = 1, N = 2, N < 1), tracks the primality state via a boolean flag (`IsPrime`), and eliminates redundant O(N) iterations and exits early upon finding a divisor.
* **Key Breakthrough:** Evolving from a naive full-range search (N - 1) to half-range (floor(N / 2)) and finally to the square root bound (√N)—recognizing that checking divisibility up to (√N) is sufficient (since no integer greater than √N can divide N evenly without a corresponding factor less than or equal to √N), thereby reducing time complexity to O(√N)—combined with an immediate `Break` exit upon detecting the first divisor (N mod i == 0) and utilizing a `Counter` vs. early `Return "Not Prime"` exit strategy.

### 7. Problem `#43`: Seconds to Days, Hours, Minutes, Seconds
* **The Challenge:** Decomposing a single large integer into four cascading time units without losing precision or corrupting the remaining seconds.
* **Key Breakthrough:** Mastering sequential integer division (div) and remainder extraction (mod), updating `Remainder` after each tier (`Days` ==>> `Hours` ==>> `Minutes` ==>> `Seconds`).

### 8. Problem `#46`: Print Letters from `A` to `Z`
* **The Challenge:** Treating characters not as abstract symbols, but as sequential numeric values in memory.
* **Key Breakthrough:** Directly applying **ASCII encoding knowledge from Course 01**—looping an integer counter from `65` (`'A'`) to `90` (`'Z'`) and converting each numeric code back into its character representation.

---

## 🔗 Complete Mapping: Course 02 Problems ↔ Course 01 Foundations

Every algorithm in this course relies directly on the theoretical computer science concepts established in **01 - Programming Foundations - Level 1**:

| # | Problem Title | Core Algorithmic Pattern | Course 01 Foundation Relevance |
| :-: | :--- | :--- | :--- |
| **01** | Print Your Name | Direct Output | **DIKW Hierarchy:** Delivering processed *Information* to the output stream. |
| **02** | Read Name & Print It | Input ==>> Output | **Memory & I/O:** Allocating RAM space to store string input and retrieving it. |
| **03** | Check Odd or Even | Modulo (`mod 2`) & Branching | **Binary Parity:** Least Significant Bit (`2^0`) determines even (`0`) vs. odd (`1`). |
| **04** | Hire a Driver (Case 1) | Compound `AND` Condition | **Boolean Logic:** Both `Age > 21` AND `HasDriverLicense` are necessary; neither alone is sufficient. |
| **05** | Hire a Driver (Case 2) | `OR` Precedence (`HasRec OR (Age > 21 AND License)`) | **Boolean Logic & Truth Tables:** `OR` makes `HasRecommendation` sufficient on its own to bypass other rules. |
| **06** | Full Name | String Concatenation | **Text Encoding (ASCII/UTF-8):** Combining character arrays in memory with a delimiter (`" "`). |
| **07** | Half Number | Arithmetic Division (`/ 2`) | **CPU ALU Operations:** Performing floating-point/integer division inside the Arithmetic Logic Unit. |
| **08** | Pass / Fail | Single Relational Comparison (`>= 50`) | **Boolean Evaluation:** Reducing a numeric score into a 1-bit `True`/`False` state. |
| **09** | Sum of 3 Numbers | Multi-Input Addition | **Memory & Registers:** Holding 3 distinct variables in RAM and summing them sequentially. |
| **10** | Average of 3 Marks | Sequential Arithmetic (`Sum / 3`) | **Operator Precedence & Data Types:** Avoiding integer truncation during division. |
| **11** | Average Pass / Fail | Chained Processing + Decision | **Data Pipeline:** Transforming raw data (marks) ==>> information (average) ==>> decision (pass/fail). |
| **12** | Max of 2 Numbers | Binary Comparison (`A > B`) | **CPU Comparator Circuits:** Evaluating magnitude between two memory addresses. |
| **13** | Max of 3 Numbers | Nested Decision Tree | **Control Flow Branching:** Isolating the maximum value through hierarchical comparisons. |
| **14** | Swap Numbers | Temporary Variable (`Temp`) | **RAM Overwrite Mechanics:** Understanding that assigning `A = B` destroys `A`'s previous value unless backed up in `Temp`. |
| **15** | Rectangle Area | Multiplication (`A * B`) | **Data Sizing & Overflow Awareness:** Ensuring variable types (`DWORD`/`QWORD`) can hold product magnitudes. |
| **16** | Rectangle Area (Diagonal & Side) | Square Root & Power (`A * sqrt(D^2 - A^2)`) | **Algorithmic Decomposition:** Breaking complex mathematical expressions into deterministic steps. |
| **17** | Triangle Area | Floating-Point Scaling (`0.5 * A * H`) | **Numeric Representation:** Handling fractional constants (`0.5`) alongside integer inputs. |
| **18** | Circle Area | Constant pi Multiplication (pi * R^2) | **Constants vs. Variables:** Storing immutable values (pi) vs. dynamic user inputs (R). |
| **19** | Circle Area Through Diameter | Derived Formula (pi * D^2 / 4) | **Logical vs. Syntax Errors:** Preventing operator precedence bugs (`D^2 / 4` vs. `(D/2)^2`). |
| **20** | Circle Area Inscribed in Square | Geometric Substitution (pi * A^2 / 4) | **Problem Analysis:** Translating geometric constraints into algebraic expressions before execution. |
| **21** | Circle Area Along Circumference | Inverse Formula (L^2 / (4 * pi)) | **Execution Order:** Grouping denominator `(4 * PI)` so the CPU doesn't divide by `4` and multiply by `PI`. |
| **22** | Circle Area Inscribed in Isosceles Triangle | Multi-Variable Formula | **Complex Expression Evaluation:** Managing multiple arithmetic operators cleanly to prevent logical errors. |
| **23** | Circle Described Around Arbitrary Triangle | Heron's Semi-Perimeter (P = (A+B+C)/2) | **Intermediate State Storage:** Caching intermediate results (`P`) in memory rather than recomputing them. |
| **24** | Validate Age Between 18 and 45 | Range Check (`Age >= 18 AND Age <= 45`) | **Boolean Range Logic:** Combining lower and upper boundary checks with `AND`. |
| **25** | Read Until Age Between 18 and 45 | Validation Loop (`While Not Valid`) | **Defensive Execution:** Preventing invalid data from corrupting downstream processing. |
| **26** | Print Numbers from 1 to N | Upward Counter Loop | **Instruction Pointer & Loops:** Repeating a block of CPU instructions until a counter threshold is reached. |
| **27** | Print Numbers from N to 1 🔥 | Downward Counter Loop | **Memory State Mutation:** Decrementing a register/variable (`N - 1`) down to a lower bound. |
| **28** | Sum Odd Numbers from 1 to N 🔥 | Loop + Modulo Filter + Accumulator | **Binary Parity + Accumulation:** Filtering odd numbers (LSB = `1`) into a running memory total. |
| **29** | Sum Even Numbers from 1 to N 🔥 | Loop + Even Filter + Accumulator | **Binary Parity + Accumulation:** Filtering even numbers (LSB = `0`) into a running memory total. |
| **30** | Factorial of N! 🔥 | Input Validation + Multiplicative Loop | **Integer Overflow & Sizing:** Factorials grow rapidly, highlighting `BYTE`/`WORD`/`DWORD`/`QWORD` memory limits. |
| **31** | Power of 2, 3, 4 | Sequential Multiplication | **Powers of 2 & CPU Efficiency:** Understanding how powers are computed via repeated multiplication. |
| **32** | Power of M (N^M) 🔥 | Iterative Exponentiation + Zero Edge Case | **Edge-Case Determinism:** Handling mathematical identities (N^0 = 1) to prevent logical errors. |
| **33** | Grade (`A, B, C, D, E, F`) | Multi-Branch `Else-If` Ladder | **Mutually Exclusive Branching:** Ordering conditions from highest to lowest so only one branch executes. |
| **34** | Commission Percentage | Tiered Threshold Lookup | **Business Logic Modeling:** Mapping continuous numeric ranges into discrete percentage multipliers. |
| **35** | Piggy Bank Calculator | Weighted Summation (`Pennies..Dollars`) | **Unit Normalization:** Converting multi-unit inputs into a single base unit (total pennies) before scaling to dollars. |
| **36** | Simple Calculator | Operation Dispatch (`+, -, *, /`) | **ALU Instruction Decoding:** Mimicking how a CPU decodes an opcode (`+`, `-`, `*`, `/`) to select an operation. |
| **37** | Sum Until `-99` | Sentinel-Controlled Loop | **Sentinel Values & Control Flow:** Using a special out-of-band value (`-99`) to terminate input reading before adding. |
| **38** | Is Prime Number? 🔥 | Divisor Search Loop (`2` to `N/2`) | **Number Theory (Course 01):** Applying prime vs. composite number properties (e.g., `2` is the only even prime). |
| **39** | Pay Remainder | Subtraction (`CashPaid - TotalBill`) | **Signed Arithmetic:** Handling positive change vs. negative balance owed. |
| **40** | Service Fee & Sales Tax | Compound Percentage (`Bill * 1.1 * 1.16`) | **Sequential State Transformation:** Applying cascading multipliers in strict order. |
| **41** | Weeks and Days | Floating-Point Division (`Hours / 24`, `/ 7`) | **Unit Conversion:** Scaling base time units upward using exact divisors. |
| **42** | Task Duration in Seconds | Multi-Unit Aggregation | **Base Conversion Mechanics:** Similar to positional number systems, multiplying each tier by its base weight (`60`, `3600`, `86400`). |
| **43** | Seconds to Days, Hours, Minutes, Seconds 🔥 | Cascading `Div` & `Mod` Extraction | **Positional Decomposition:** Extracting quotients and remainders step-by-step, mirroring Decimal-to-Base-N conversion. |
| **44** | Day of Week | Validated Lookup (`1..7`) | **Lookup Tables & Validation:** Ensuring index bounds (`1..7`) before mapping integers to text labels. |
| **45** | Month of Year | Validated Lookup (`1..12`) | **Deterministic Mapping:** Transforming numeric codes into human-readable strings without ambiguity. |
| **46** | Print Letters from `A` to `Z` 🔥 | Numeric Loop over Character Codes | **ASCII Encoding Standard:** Leveraging the fact that `'A'`–`'Z'` are stored sequentially as `65`–`90` (1 Byte each). |
| **47** | Loan Installment Months | Division (`LoanAmount / MonthlyPayment`) | **Financial Modeling:** Computing duration required to deplete a balance to zero. |
| **48** | Monthly Loan Installment | Division (`LoanAmount / Months`) | **Inverse Modeling:** Solving for rate/installment given total principal and time. |
| **49** | ATM PIN | Conditional Authentication | **Security & Comparison:** Matching stored credential state against user input. |
| **50** | ATM PIN (3 Tries) | Counter-Limited Authentication Loop | **Compound Loop Termination:** Exiting when *either* `PIN == Valid` (Success) *or* `Counter == 3` (Card Locked). |

---

## 💡 Key Takeaways & Philosophical Insights

### 1. Thinking Precedes Syntax
* *Jumping directly into a programming language without designing the algorithm first leads to trial-and-error coding and hidden logical bugs.*
* Flowcharts expose missing edge cases (like division by zero, negative factorials, or M=0) visually before a single line of code is written.

### 2. Accumulator & Loop Discipline
* **Initialization Matters:** Additive accumulators (`Sum`) must start at `0`; multiplicative accumulators (`Factorial`, `Power`) must start at `1`.
* **Loop Invariants:** Every loop must have a clear initialization, a strict termination condition, and a step that actively moves the state toward termination.

### 3. Computer Science Foundations Are Practical
* Concepts from **Course 01**—such as ASCII character codes (`65`–`90`), binary parity (`mod 2`), prime properties, and positional remainder extraction—are not just academic theory; they are the exact building blocks of everyday algorithms.

---

## 🧪 Algorithmic Solutions & Flowcharts

All 50 step-by-step written algorithms are organized inside the `Solutions/` directory:

* 📁 **Folder:** `Solutions/`
* 📝 **Contents:** Structured problem breakdowns (`Input`, `Process`, `Output`), step-by-step pseudocode and algorithms for Problems `01` through `50`.

---

## 📌 Core Quote

> *"Programming is not a programming language; a programming language is only a tool. Great programmers are great thinkers first."*
