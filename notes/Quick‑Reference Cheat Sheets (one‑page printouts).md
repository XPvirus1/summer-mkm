Below is a “shopping list” of handy references you can **print, bookmark, or toss in a project folder** so that almost every question you’ll hit this summer is one click away. I’ve grouped them by purpose and flagged the items that are most useful at an Algebra‑2 / Geometry math level.



------





## **1 · Quick‑Reference Cheat Sheets (one‑page printouts)**



| **Sheet**                                                    | **Why It Helps**                                             | **Where to Grab It**                               |
| ------------------------------------------------------------ | ------------------------------------------------------------ | -------------------------------------------------- |
| **Physical‑constants placemat** (R, kB, h, eV↔kJ mol⁻¹, kcal↔kJ, Pa↔atm) | Saves hunting through papers while coding Arrhenius rates    | Cornell “Chem–E Constants” PDF or any CRC pull‑out |
| **Greek‑letter & math‑symbol key** (ΔG, ΔG‡, θ, ν)           | No more mixing up upsilon and nu                             | Copy the table from the primer I just gave you     |
| **Units & conversions wheel** (mbar↔Pa, Å↔nm, mol %↔ppm)     | Micro‑kinetic inputs often jump units                        | NIST “SI quick‑reference” card                     |
| **Git command cheat sheet**                                  | Daily commits w/ five commands (clone, add, commit, push, pull) | GitHub’s printable PDF                             |
| **VS Code keyboard shortcut card (Windows + WSL)**           | Opens terminal, search, split panes in a flash               | VS Code docs → “Keymaps” section                   |



------





## **2 · Core Concept Reading (20–40 min each)**



| **Title & Link**                                             | **What You’ll Learn**                                        | **Level** |
| ------------------------------------------------------------ | ------------------------------------------------------------ | --------- |
| **“Microkinetics for Beginners”** (6‑page tutorial by Dumesic & Campbell, Catalysis Letters 2019) | Walks through *one* surface reaction, shows how rate laws are built, introduces Degree of Rate Control with cartoons | ★☆☆       |
| **MIT OCW 10.626 – Fundamentals of Catalysis (Lecture 4 slides)** | Visual introduction to adsorption, rate constants, volcano plots | ★☆☆       |
| **Julia “SciML 101” notebook** (SciML docs)                  | Hands‑on DifferentialEquations.jl in <30 lines—exactly what you’ll do for coverages | ★★☆       |
| **“Getting Started with Catalyst.jl”**                       | A Julia DSL for reaction networks; lets you write @reaction_network and it auto‑builds the ODEs | ★★☆       |
| **“Practical Tips for Microkinetic Modeling”** (Catalysis Today 2020, short review) | Common pitfalls (bad thermodynamics, stiff solvers, units)   | ★★☆       |



------





## **3 · Math “Gap‑Bridgers”**



| **Resource**                                              | **Why It Fits Algebra 2**                                    | **How to Use**                                               |
| --------------------------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **Khan Academy – Natural Log & Exponent Practice**        | Arrhenius uses e^(–E/RT); 30 min of drills locks in log rules | Do one set, then code a quick Julia snippet to convert ΔG‡ to k |
| **Paul’s Online Notes – Intro ODEs §1–2**                 | Explains dθ/dt notation with slope diagrams—no calculus course needed | Skim diagrams; solver will do the heavy lifting              |
| **MIT “Mathematics for Chemistry” cheat sheet (2 pages)** | Lists derivatives, integrals, Greek letters, unit conversions | Print and keep on desk as “math dictionary”                  |



------





## **4 · Programming & Julia Essentials**



| **Item**                                                | **Why It Matters**                                           |
| ------------------------------------------------------- | ------------------------------------------------------------ |
| **Official Julia Manual §2–4 (“Basics” & “Functions”)** | 90 % of what you need: loops, functions, broadcasting (.)    |
| **Julia VS Code Extension docs**                        | Interactive Plots pane, inline profiler, variable explorer   |
| **Pluto.jl**                                            | Interactive notebooks for quick experiments—great for progress demos to grad mentor |



------





## **5 · Catalysis & Surface Science Background (optional deep dives)**





If the science bug bites and you want more than the project demands:



1. **“Heterogeneous Catalysis: Fundamentals and Applications”** by Jens Hagen – gentle textbook with pictures of adsorption geometries.
2. **“Microkinetics of Heterogeneous Catalysis”** by Nie & Schlögl – short, example‑driven monograph.
3. **DFT Illustrated YouTube Series (MaterialsProject)** – 5‑min videos demystifying how those ΔG and ΔG‡ numbers are computed.





------





## **6 · Lab Notebook & Project Management Aids**





- **Markdown template for daily log** – date, goal, commands, results, next steps.
- **Kanban board (Trello or GitHub Projects)** mirroring the milestone table we built—drag tasks across “To‑do → In Progress → Done”.
- **Pomodoro timer browser plugin** – keeps 25 min focus + 5 min breaks.





------





### **How to Curate (So You Don’t Get Overwhelmed)**





1. **Print the cheat sheets** in Section 1 and pin them near your monitor.
2. **Bookmark** one link from each sub‑section (⇧‑⌘‑D in Chrome). Create folders: *Math*, *Julia*, *Catalysis*.
3. **Schedule one reading per day** for the first week (20 min max each). Treat them like warm‑ups before coding.
4. **Archive the deep‑dives** until you’ve reproduced the mkmcxx results—then pull them out as curiosity snacks.





With this mini‑library in your backpack you’ll rarely hit a dead end—and when you do, you’ll know exactly which page or video to open. Happy modeling!