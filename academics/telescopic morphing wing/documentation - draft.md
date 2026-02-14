## load collector and load step in hypermesh 2024

### 1. What is a Load Collector?

A **Load Collector** is a container (like a folder) that holds specific types of entities like forces, constraints (SPCs), or solver settings (EIGRL).

- **It is a grouping tool:** You use them to organize your model so you can keep your "Fixed Root" constraints separate from your "Engine Weight" forces.
- **Card Images:** Every collector can have a "Card Image." For your wing modal analysis, one collector has the `EIGR` card image (the solver instructions), while another has no card image because it just holds nodes you fixed (SPCs).
- **Visual Management:** You can turn collectors on or off in the graphics area to see exactly where your loads or constraints are applied.

### 2. What is a Load Step?

A **Load Step** (called a **SUBCASE** in Nastran) is the actual "Instruction Manual" that tells the solver what to do with the collectors you created.

- **It defines the analysis type:** This is where you tell HyperMesh, "Perform a **Normal Modes** analysis" rather than a "Static" analysis.
- **It links collectors to the solver:** A load step is essentially a list of pointers. You tell the Load Step to:
    - Use the **Constraints** collector for the boundary conditions (SPC slot).
    - Use the **EIGRL/EIGR** collector for the vibration settings (METHOD slot).
- **Multiple Load Steps:** You can have multiple load steps in one file. For example, `Load Step 1` could be a modal analysis of the wing, and `Load Step 2` could be a static check of the wing under lift.

---

### Comparison Table

|**Feature**|**Load Collector**|**Load Step (Subcase)**|
|---|---|---|
|**Analogy**|A box of specific items (bolts, weights, settings).|The instruction to "Build a Wing" using those items.|
|**Contents**|Forces, Moments, SPCs, or EIGR cards.|References to specific Load Collectors.|
|**Purpose**|To store and organize data.|To define the type of simulation and execute it.|
|**Nastran Term**|Bulk Data Entry (SPC, FORCE, EIGRL).|Subcase Control (SUBCASE 1).|

---

### Material Specifications

**For Aluminum**

| **Field** | **Property**    | **Value to Enter** | **Units (Implicit)**      |
| --------- | --------------- | ------------------ | ------------------------- |
| **E**     | Young's Modulus | **71000**          | $MPa$ (which is $N/mm^2$) |
| **G**     | Shear Modulus   | **26000**          | $MPa$                     |
| **NU**    | Poisson's Ratio | **0.33**           | Unitless                  |
| **RHO**   | Density         | **2.7e-9**         | $Tonne/mm^3$              |

---

## how NASTRAN-95 solver works

The **NASA NASTRAN-95** repository is the official "open-source" ancestor of modern solvers like MSC Nastran and NX Nastran. Since modern versions are proprietary, this 1995 release is the most complete version available for public study.

The repository is written almost entirely in **Fortran** (99.7%) and follows a highly modular architecture designed in the 1960s to handle massive structural problems on limited computer memory.

### 1. Repository Directory Structure

Here is a breakdown of the key folders found in the [nasa/NASTRAN-95](https://github.com/nasa/NASTRAN-95) repo:

- **`/mis` (Main Source):** This is the "brain" of the solver. It contains the core Fortran subroutines for matrix operations, element formulations (like CBAR, CHEXA), and the executive system that manages data flow.
- **`/mds` (Module Source):** Contains functional modules. In Nastran, a "Module" is a self-contained program unit that performs a specific task (e.g., assembling a stiffness matrix or solving an eigenvalue problem).
- **`/um` (User Manual):** Contains the text files for the original documentation.
    - `EXEC.TXT`: Explains the Executive Control Deck.
    - `CASE.TXT`: Explains the Case Control Deck (loads, constraints, output requests).
- **`/bin`:** Contains the executable scripts (like the `nastran` shell script) used to initiate a run, assign file buffers, and manage system memory.
- **`/inp`:** Sample input files (.dat or .bdf) used to test the solver.
- **`/demoout`:** Expected output files (.f06) for the demo problems, which you can use to verify if your own builds are working correctly.

---

### 2. How the Solver Code Works (The "Three Decks")

The code is organized to process your input file in three distinct stages, which is reflected in how the subroutines are called:

1. **Executive Control (The Traffic Cop):** Found primarily in `/mis`, this code manages the "Solution Sequence" (SOL). It allocates memory and decides which modules to call. It uses a specialized internal language called **DMAP** (Direct Matrix Abstraction Program) to string modules together.
2. **Case Control:** This part of the code interprets your requests for specific results (like `STRESS` or `DISPLACEMENT`) and selects which "sets" of loads and constraints to apply for each subcase.
3. **Bulk Data (The Physics):** This contains the actual geometry. The code in the element library (within `/mis`) reads your `GRID` points and `ELEMENT` connections to build the local stiffness matrices ($k$) which are then "assembled" into the global matrix ($K$).

---

### 3. Critical Parts for Your Current Issue

Since you are dealing with a **modal frequency analysis (SOL 103)** that is crashing on a coarse mesh, the following code areas are the most relevant:

- **The Eigensolver:** Look in `/mis` for subroutines related to "EIG" (like `EIGR` or `LANCZOS`). This is where the solver calculates the natural frequencies. If the coarse mesh has "bad" element shapes (high aspect ratios), the math here will fail, causing a crash.
- **Matrix Assembly:** The code that takes your coarse elements and builds the stiffness matrix. If an element is so distorted that its volume/area becomes zero or negative in the math, the solver will "divide by zero" and crash.
- **Constraint Processor:** The code that applies your `SPC` (Single Point Constraints). If your coarse mesh isn't properly constrained, it creates "Rigid Body Modes," which can sometimes crash older solvers if not handled by a `PARAM, BAILOUT`.

### Summary of Documentation Files in Repo:

- **NASTRAN Programmers Manual.pdf:** This is the most important file for you. It explains how the code is structured, how to add new elements, and how the memory (GINO - General Input/Output) is managed.
- **NASTRAN Users Manual.pdf:** Essential for understanding the syntax of the input cards you are using in your BDF files.

---

## what is FORTRAN? it's Perks

**Fortran** (which stands for **For**mula **Tran**slation) is the world's first high-level programming language. Created by IBM in the 1950s, it was designed specifically for scientists and engineers to perform complex mathematical calculations without having to write in tedious machine code.

Even though it’s over 70 years old, it remains the "gold standard" for high-performance computing (HPC) and heavy-duty engineering simulations like the Nastran solver you're looking into.

---

### 1. Why is it still used?

You might wonder why engineers haven't just switched to Python or C++. There are three main reasons:

- **Raw Speed:** When it comes to "crunching" massive matrices (like a wing's structural mesh), Fortran is often faster than almost any other language. It is designed to talk to the computer's processor in a way that prioritizes math execution.
- **Legacy (The "If it ain't broke" rule):** Huge libraries of verified, "battle-tested" engineering code (like Nastran or weather prediction models) were written in Fortran. Re-writing them would be incredibly expensive and risky.
- **Array Handling:** Fortran treats matrices and arrays as "first-class citizens." In many languages, you have to do extra work to handle math on a grid of numbers; in Fortran, it’s built into the syntax.

---

### 2. How it looks and feels

If you look at the NASTRAN-95 source code, you’ll notice a few distinct characteristics:

- **Case Insensitivity:** Modern Fortran doesn't care if you write `PRINT` or `print`.
- **Column-Based (Older Versions):** Early Fortran (like Fortran 77) was designed for punch cards. You had to start your code in specific columns (e.g., column 7 for the actual instruction).
- **Math-Heavy Syntax:** It looks very similar to how you would write an equation on a chalkboard.

---

### 3. Key Differences from Modern Languages

Compared to a language like Python, Fortran is **Compiled**, not **Interpreted**.

|**Feature**|**Fortran**|**Python**|
|---|---|---|
|**Execution**|Needs a compiler (turns code into an .exe).|Runs line-by-line via an interpreter.|
|**Data Types**|You must strictly declare if a number is an Integer or Real.|Very flexible; handles types for you.|
|**Purpose**|Heavy math, fluid dynamics, structural analysis.|Web apps, AI, automation, general use.|
|**Speed**|Extremely fast for math operations.|Slower (often uses Fortran libraries in the background!).|

---

## about MATLAB & it's source

MATLAB has a fascinating "origin story" that connects directly to the Fortran world you've been exploring. It wasn't originally intended to be a commercial product; it was created as a teaching tool to make engineering math easier.

### 1. The Origin: A "Wrapper" for Fortran

In the late 1970s, **Cleve Moler**, a professor at the University of New Mexico, wanted his students to use powerful linear algebra libraries (called **LINPACK** and **EISPACK**) without having to learn Fortran.

At the time, using those libraries required writing a full Fortran program, compiling it, and linking it—a tedious process for students who just wanted to solve a matrix equation. Moler wrote **MATLAB** (short for **MAT**rix **LAB**oratory) as an interactive "command-line" interface that would call those Fortran subroutines in the background.

### 2. What is the source code made of?

While the original 1970s version was almost entirely Fortran, modern MATLAB is a sophisticated multi-language machine.

The source code is primarily composed of three layers:

- **C and C++ (The Engine):** Most of the modern MATLAB engine, including the desktop interface, the graphics system (handle graphics), and the "Just-In-Time" (JIT) compiler, is written in C++. This provides the speed and memory management needed for professional software.
- **Fortran (The Math Backbone):** To this day, the heaviest mathematical lifting (like solving huge systems of linear equations) is still done by highly optimized Fortran libraries like **LAPACK** and **BLAS**. When you type `A \ b` in MATLAB, you are likely triggering a Fortran routine under the hood.
- **MATLAB itself (The Toolboxes):** A huge portion of MATLAB is actually written in `.m` files (MATLAB's own language). Most of the "Toolboxes" (Signal Processing, Optimization, etc.) are built using MATLAB code that runs on top of the C++/Fortran engine.
- **Java:** The Graphical User Interface (GUI) and the desktop environment traditionally used Java for cross-platform compatibility.

### 3. Comparing the "DNA" of Solvers

Since you are looking at both **Nastran** and **MATLAB**, it's helpful to see how their "source code" philosophies differ:

|**Feature**|**Nastran (Historical)**|**MATLAB (Modern)**|
|---|---|---|
|**Primary Language**|Fortran|C++|
|**Philosophy**|A single-purpose "Black Box" solver.|A general-purpose "Sandbox" for math.|
|**Extension**|Write a Fortran Subroutine or DMAP.|Write a `.m` script or C++ "MEX" file.|
|**User Interface**|Text-based (Input Deck).|Visual/Interactive (Command Window).|

---

### Why this matters for your Wing Analysis

When you use a tool like **HyperMesh**, it acts as a bridge. HyperMesh creates the BDF file (the "text" input) that the **Fortran-based Nastran** understands. If you were to take the results from Nastran and plot them or perform further data analysis, you would likely use **MATLAB** to "crunch" those numbers.

---

