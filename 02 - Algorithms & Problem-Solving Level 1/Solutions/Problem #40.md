## 🧠 Deep Problem Deconstruction & Engineering Vision

Every algorithm designed in this course directly reflects the 5 core functionalities of a computer system:

1️⃣ **Input Data:** Taking raw data in.  
2️⃣ **Store Data:** Retaining data/instructions in memory.  
3️⃣ **Process Data:** Converting raw inputs into structured information.  
4️⃣ **Output Information:** Presenting calculated results.  
5️⃣ **Control:** Coordinating and directing sequence and execution flow.

---

### 🟢 Problem #40: Service Fee and Sales Tax

> **Problem Statement:**  
> A restaurant charges a `10%` service fee and a `16%` sales tax.  
> Write a program to read a `BillValue`, add the service fee and sales tax to it, and print the final `TotalBill` on the screen.  
> *Example Input:* `100`  
> *Output:* `127.6` *(Calculation: 100 + (100 * 0.10) + (110 * 0.16) = 100 + 10 + 17.6 = 127.6, or applied sequentially: 100 * 1.10 = 110, then 110 * 1.16 = 127.6)*

#### 🎯 Deep Analysis & Creator’s Reflection:
* **The Creator's Intent:** As the programmer, I am instructing the computer to read an initial financial baseline (`BillValue`), apply two successive percentage increments (service fee followed by sales tax), and compute the final composite retail total.
* **Core Concepts Introduced:** 
  1. **Successive vs. Combined Percentage Markup:** Understanding the order of financial operations: restaurants typically calculate sales tax on the subtotal *after* the service fee has been added (Bill * 1.10) * 1.16 rather than adding 26\% to the original base (10\% + 16\% = 26\% ==>> 126), which yields a lower total (126) due to compounding!
  2. **Floating-Point Precision in Financial Calculations:** Ensuring monetary values are processed using floating-point types (`float` or `double`) to preserve decimals like `.6`.

#### ⚙️ Computer Functionality Mapping:
* 📥 **Input Data:** Receives a single numeric bill value: `BillValue`.
* 💾 **Store Data:** Allocates floating-point memory variables for `BillValue`, intermediate totals, and final `TotalBill`.
* ⚙️ **Process Data:** 
  1. Add service fee: `Total = BillValue * 1.10`
  2. Add sales tax on top of service fee: `Total = Total * 1.16`
* 📤 **Output Information:** Displays the final `TotalBill` on the monitor screen.
* 🎮 **Control:** Sequential execution flow (`Start` ==>> `Read BillValue` ==>> `Compute Service Fee & Tax` ==>> `Print TotalBill` ==>> `End`).

---

#### 🛠️ Multiple Algorithmic & Architectural Solutions Explored:

Can calculating restaurant service fees and sales tax be structured in different ways? **Yes!** Here are four clean engineering approaches:

1. **Solution 1: Successive Multiplicative Markup (Standard Approach)**
   * **Logic:**  
     `Read BillValue`  
     `TotalBill = BillValue * 1.10` *(adds 10% service fee)*  
     `TotalBill = TotalBill * 1.16` *(adds 16% sales tax on the new total)*  
     `Print TotalBill`
   * **Pros:** Mirrors exact real-world restaurant billing software logic where tax applies to the service-inclusive subtotal.

2. **Solution 2: Explicit Separate Calculation Variables**
   * **Logic:** Compute fees and tax explicitly in separate steps for transparency:  
     `Read BillValue`  
     `TotalBill = BillValue`  
     `TotalBill = TotalBill + (TotalBill * 0.10)`  
     `TotalBill = TotalBill + (TotalBill * 0.16)`  
     `Print TotalBill`
   * **Pros:** Highly readable and self-documenting; easy for auditors or junior developers to inspect step-by-step arithmetic.

3. **Solution 3: Named Constants for Rates (`Const SERVICE_FEE = 0.10`)**
   * **Logic:** Replace hardcoded multipliers with named constants so tax policy changes can be updated instantly:  
     `Const float SERVICE_FEE = 0.10`  
     `Const float SALES_TAX = 0.16`  
     `TotalBill = BillValue * (1 + SERVICE_FEE) * (1 + SALES_TAX)`  
     `Print TotalBill`
   * **Pros:** Eliminates magic numbers and makes tax adjustments effortless when government tax laws change.

4. **Solution 4: Modular Function Composition (`CalculateTotalBill(BillValue)`)**
   * **Logic:** Encapsulate the pricing logic into a pure function:  
     `Function CalculateTotalBill(BillValue) -> Returns float`  
     `    Return BillValue * 1.10 * 1.16`  
     `End Function`
   * **Pros:** Promotes separation of concerns, allowing point-of-sale systems or mobile checkout apps to reuse the calculation logic cleanly.

---
