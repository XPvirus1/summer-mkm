Below is a **starter playbook** you and Jackson can copy‑paste into a shared doc, Trello board, or GitHub project. It turns Dr Getman’s e‑mail into concrete tasks, ordered roughly by date, with quick links and “definition‑of‑done” (DoD) notes so he always knows what “finished” looks like. Feel free to tweak the schedule; the goal is simply to hit Milestone 1 (replicating the original results) during his first two internship weeks.



------





## **0 · Laptop & Tooling (🗓 May 31 – Jun 3)**



| **Task**                                                     | **Link**                                                     | **DoD**                                                      |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| ✅ Install VS Code + extensions (Remote WSL, Julia, GitLens, Docker) | https://code.visualstudio.com                                | VS Code launches; **Ctrl + Shift + P → “Remote‑WSL: New Window”** opens a WSL session |
| ✅ Enable WSL 2 & Ubuntu 22.04                                | https://learn.microsoft.com/windows/wsl/install              | wsl --version shows *Version 2*                              |
| ✅ Install Docker Desktop (integrated with WSL)               | https://www.docker.com/products/docker-desktop               | docker run hello-world prints the welcome message            |
| ✅ Install Julia 1.10 LTS (Windows .exe OR inside WSL)        | https://julialang.org/downloads/                             | julia --version returns *1.10.x*                             |
| ✅ Install Git + GitHub CLI                                   | https://git-scm.com/book/en/v2/Getting-Started-Installing-Git | git --version returns version ≥ 2.40                         |

> **Tip**: Put everything in WSL unless a package truly needs Windows. It avoids path headaches when compiling C++ later.



------





## **1 · Orientation (🗓 Jun 3 – Jun 6)**



| **Task**                                                     | **Link**                                                     | **DoD**                                                      |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Skim Dr Getman’s full microkinetic‑modeling review           | https://pubs.acs.org/doi/full/10.1021/acs.chemrev.0c00394    | A bulleted list of 5‑7 key concepts in your notes            |
| Skim “terrace aqueous” model paper (focus on Supplementary Info) | https://www.sciencedirect.com/science/article/pii/S0021951724002756#appSB | Identify which figures/tables you must reproduce             |
| Watch playlist videos 10, 11, 23, 24, 54‑66                  | https://youtube.com/playlist?list=PLSV5Smmq7NIA_Zml1k0b7CALucgmVm1LR | Write a one‑paragraph summary of “Why microkinetic vs simple rate laws?” |
| Work through **one** Julia intro (choose video or text)      | https://julialang.org/learning/                              | Complete the “90 Minute Julia Tutorial” or equivalent and push a *hello‑julia.ipynb* to GitHub |



------





## **2 · Milestone 1 — Reproduce mkmcxx Results (🗓 Jun 9 – Jun 20)**



| **Task**                                                     | **Link**              | **DoD**                                                      |
| ------------------------------------------------------------ | --------------------- | ------------------------------------------------------------ |
| Clone & build **mkmcxx** inside WSL                          | https://www.mkmcxx.nl | mkmcxx --version runs without error                          |
| Collect input files for the *terrace aqueous* model (supplementary ZIP) | paper’s SI            | All input files live in a project repo: mkmcxx‑terrace       |
| Run baseline simulation                                      | —                     | Raw output files match author’s reported conversion & rate trends (within ±5 %) |
| Generate comparable plots (Python/Jupyter ok)                | —                     | PDF/PNG plots committed to results folder                    |
| Write **README.md** describing exact command line, parameters, & checksums | —                     | Graduate student can reproduce results in ≤10 min            |



------





## **3 · Milestone 2 — Understand Julia Reference Model (🗓 Jun 23 – Jul 3)**



| **Task**                                                     | **Link**                                          | **DoD**                                        |
| ------------------------------------------------------------ | ------------------------------------------------- | ---------------------------------------------- |
| Fork & clone **ProgrammableOER**                             | https://github.com/srgathmann/ProgrammableOER     | Repo builds; static model runs (julia main.jl) |
| Map C++ → Julia concept table (species, reactions, ODE solver, thermodynamics) | —                                                 | Markdown table committed (mapping.md)          |
| Re‑run static model; verify outputs vs paper                 | https://chemrxiv.org/.../65af381d66c13817290d5404 | Replicated key figure within ±5 %              |



------





## **4 · Milestone 3 — Port** 

## **Terrace Aqueous**

##  **Model to Julia (🗓 Jul 7 – Aug 2)**



| **Task**                                               | **DoD**                                                  |
| ------------------------------------------------------ | -------------------------------------------------------- |
| Sketch architecture (data structures, solver choice)   | design.md includes diagrams                              |
| Translate kinetic parameters & species list            | Julia structs & CSV inputs compile                       |
| Implement ODE system & test small timesteps            | Unit tests passing                                       |
| Compare Julia results against original mkmcxx baseline | Plots overlay with <10 % deviation                       |
| Optimize (vectorize, use StaticArrays, etc.)           | 2× speed‑up over naïve version                           |
| Prepare final presentation notebook                    | Executable Jupyter/Pluto notebook with narrative + plots |



------





## **Daily Workflow & Support**





1. **15/30 Rule** — try solving solo for 15‑30 min, then ask.

2. Keep a **lab notebook** (paper or Notion) logging:

   

   - Commands run & SHA of commit
   - Environment details (julia --version, commit hashes)
   - Observations & next steps

   

3. Push to GitHub **daily**; open a draft PR each Friday for feedback.

4. Meet grad‑student mentor on Slack/Teams for stand‑up (5 min) if Dr Getman is away.





------





### **Nice‑to‑Have Extras**





- Install the Julia VS Code extension and enable **Plots pane** for quick visualization.
- Set up **Docker images** with the entire toolchain so the group can reuse your environment (Dockerfile in repo root).
- Explore **GitHub Copilot** to speed up Julia boilerplate—but always review generated math!





------





### **Quick Reference Links (Handy Bookmark Folder)**





- Microkinetic modeling review (Chem Rev 2020)
- Terrace aqueous model paper (J. Catal. 2024)
- mkmcxx official docs
- ProgrammableOER GitHub repo
- Julia learning resources
- Dr Getman’s playlist timestamps (start at 10)





------



**Next Step for You, Dad:**

Share this checklist with Jackson, help him knock out Section 0 this weekend, and make sure Git + GitHub are working so he can start committing by Monday. After that, he can largely run with the plan and ping his grad‑student mentor when he hits a blocker.