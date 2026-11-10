# 🚀 01 - Programming Foundations - Level 1

This directory contains my reflections, core computer science concepts, and exercises solutions for **[01 - Programming Foundations - Level 1](https://programmingadvices.com/p/00316b)** by **Dr. Mohammed Abu-Hadhoud**.

---

## 📂 Subfolder Structure

* `README.md` – Course summaries, conceptual takeaways, and error dynamics.
* `Solutions/` – Individual text files (`.txt`) containing activity and exercise answers for each lesson.

---

## 📜 Course Summary & Personal Competencies

> **Course Completion Statement:**  
> Upon successfully completing the **Programming Foundations – Level 1** course administered by **Dr. Mohammed Abu-Hadhoud** (*Programming Advices*), I have built a solid theoretical and practical computer science foundation. Through this course, I am able to:
>
> * **Apply the DIKW Hierarchy:** Differentiate between *Data, Information, Knowledge, and Wisdom*, mapping how raw inputs transform into meaningful outputs and actionable insights through systematic processing.
> * **Understand System & Execution Architecture:** Explain how software drives hardware, how the CPU handles instruction execution, how the memory hierarchy operates (Registers $\rightarrow$ Cache $\rightarrow$ RAM $\rightarrow$ Secondary Storage), and how general-purpose CPUs differ from massively parallel GPUs.
> * **Analyze Address Spaces & System Architectures:** Calculate memory addressing capacity and evaluate the performance and compatibility trade-offs between 32-bit ($x86$) and 64-bit ($x64$) architectures.
> * **Master Number Systems & Conversions:** Convert values fluidly between Binary (Base-2), Octal (Base-8), Decimal (Base-10), and Hexadecimal (Base-16) using both mathematical methods and fast direct nibble/3-bit mapping.
> * **Understand Text Encoding & Memory Units:** Differentiate between ASCII and multi-byte Unicode standards (UTF-8, UTF-16, UTF-32), and accurately measure data across storage units from Bits up to Exabytes.
> * **Utilize System & Developer Tools:** Inspect device specifications using Windows diagnostic utilities (`msinfo32`, `dxdiag`, CLI/PowerShell) and perform base-conversion testing with the Windows Programmer's Calculator across BYTE, WORD, DWORD, and QWORD sizes.
> * **Execute Computational & Boolean Logic:** Construct and evaluate truth tables (`AND`, `OR`, `NOT`), analyze binary number properties (such as parity and prime composition), and apply deterministic logic to algorithm design.
> * **Diagnose Execution Dynamics & Errors:** Evaluate language translation trade-offs (developer velocity vs. execution speed), understand compiler/interpreter build steps, and identify Syntax/Build, Runtime, and Logical errors.
> * **Explain Networking Fundamentals:** Explain local and wide-area network concepts (LAN vs. WAN), the roles of routers versus switches, and how devices communicate through wired (Ethernet) and wireless (Wi-Fi) protocols.

---

## 💡 Key Takeaways & Philosophical Insights

### 1. The Abstraction Trade-off
* *We trade raw execution speed for human readability and developer velocity.* 
* Language selection depends on the target objective and ecosystem rather than execution speed alone.

### 2. Logic Mechanics
* **AND Logic:** All conditions are necessary, but no single true condition alone is sufficient.
* **OR Logic:** Every condition is necessary and sufficient on its own to make the statement true.

### 3. Binary & ASCII Rules
* Standard ASCII characters fit within **1 Byte (8 bits) or less**.
* All powers of `2` (`1`, `2`, `4`, `8`...) are even numbers except for `1` (\(`2`^{`0`}\)), which occupies the rightmost position in binary. When a binary number ends in `0`, that `1` is excluded from the sum, guaranteeing the total value is even.
* All binary numbers are **composite (non-prime)**, except for `2`.

---

## 🧪 Exercises Solutions

The activity answers for all lessons are packed inside the `Solutions/` folder:

* 📄 **File:** `Solutions/`
* 📝 **Description:** Individual `.txt` files per lesson containing completed exercise solutions and lesson activities provided during the course.

---

## 📌 Core Quote

> *"Software drives hardware; CPU is designed for complex general-purpose tasks, while GPU excels at massive parallel execution."*
