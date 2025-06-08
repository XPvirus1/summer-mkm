\### Your Very First Moves (next 2‑3 days)



> **Goal:** be fully tooled‑up and ready to hit “Run” on the *terrace‑aqueous* simulation the moment the internship clock starts.

| **#** | **Action**                                                   | **Why it’s first**                                           | **How long?**                     |
| ----- | ------------------------------------------------------------ | ------------------------------------------------------------ | --------------------------------- |
| 1     | **Create your “internship” folder** on the new laptop (~/summer‑mkm/) with sub‑folders: code/, data/, papers/, notes/. | Keeps every download & script in one place from Day 1.       | 5 min                             |
| 2     | **Install the toolchain inside WSL 2 Ubuntu 22.04**  • VS Code + Remote‑WSL extension  • Git + GitHub CLI  • Docker Desktop (linked to WSL)  • Julia 1.10 LTS (sudo snap install julia --classic) | You can’t compile / run anything until these are working. Everything else depends on it. | 1–2 hrs (most of it is downloads) |
| 3     | **Spin up a “hello project” repo on GitHub**git init code/terrace‑mkm && gh repo create | Daily commits start **today**; no lost work later.           | 10 min                            |
| 4     | **Download & drop the key PDFs** into papers/:  • Terrace‑aqueous methanol paper  • Micro‑kinetic review PDF | You’ll refer to them constantly; keep local copies so you’re not hunting links offline/on flights. | 5 min                             |
| 5     | **Skim just two things** (no deep dive yet):  • Abstract + Fig 4 of the terrace paper (see what you must replicate).  • Playlist video #10 (8 min) for the big‑picture idea of micro‑kinetics. | Gives you context without drowning you; you’ll read deeper **after** the toolchain works. | 30–40 min                         |
| 6     | **Clone & build mkmcxx** in WSL:git clone https://gitlab.com/mkmcxx/mkmcxx.gitcd mkmcxx && mkdir build && cd build && cmake .. && make -j$(nproc) | Verifies your C++ toolchain and shows you can run the legacy code before porting to Julia. | 30 min                            |
| 7     | **Grab the terrace‑aqueous input files** from the paper’s Supplementary ZIP; drop in data/terrace‑mkmcxx/. | Needed for Step 8; keeps inputs version‑controlled.          | 10 min                            |
| 8     | **Run the baseline simulation**./mkmcxx terrace.inp (example) and make sure it finishes and writes output. | Confirms you can reproduce Ricardo’s original numbers—the internship’s first milestone. | Variable (seconds → minutes)      |



------





#### **What to Put Off** 

#### **for Now**





- **Julia scripting** – wait until after you have the C++ baseline; then you’ll know what output you’re aiming for.
- **Deep thermodynamics reading** – skim as you go; don’t stall on theory before you can actually run code.
- **Dockerising everything** – handy later, but not a blocker for first‑runs.





------



\### Checkpoint



If by the end of these steps you can:



1. Open VS Code in WSL and run julia at the terminal prompt,
2. Execute ./mkmcxx on the terrace input file without errors, and
3. See an output file (rates, coverages, etc.) in your results folder,





…then you’re perfectly positioned for Day 1 (June 9) – even while Dr Getman is at her conference.



Keep that momentum: commit your README.md with exact commands and any troubleshooting tips you hit along the way. That documentation habit will impress the grad‑student mentor from the very start.



*You’ve got this—start with the toolbox, run the legacy model, and everything else builds on that foundation.*