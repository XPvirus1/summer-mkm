### **Microkinetic Modeling in Plain English**





*(A friendly tour of the review paper “Microkinetic Modeling: A Tool for Rational Catalyst Design” so you can follow Jackson’s internship reading list without getting buried in equations.)*



------





#### **1. What problem does microkinetic modeling solve?**





Think of a catalytic surface as an airport runway at rush‑hour. Molecules land, taxi through many checkpoints (adsorb, break bonds, swap atoms), and finally take off again as new products. **Microkinetic modeling is simply a detailed flight‑schedule**: it lists every tiny “step” that can happen, assigns a speed to each one, and lets a computer juggle millions of those steps per second to predict the overall traffic flow.



Why bother? Because **seeing the bottlenecks**—which checkpoint is really slowing everyone down—lets chemists redesign the runway (catalyst) instead of just guessing and testing. The review opens by stressing that modern catalyst design “relies on understanding the fundamental surface kinetics that controls catalyst performance” okinetic Modeling A Tool for Rational Catalyst Design.pdf](file-service://file-XS2qSiP6bJuoJrXtSfHt5q).



------





#### **2. From curve‑fitting to first principles**





Classic reactor models fit experimental data to a single, empirical rate law. Useful, but you learn very little about *why* a catalyst works—we’re back to guessing. Twenty‑five years ago Michel Boudart predicted a “revolution” where rate constants would come from computation and surface science instead of curve‑fits; the introduction notes we’re now living that future kinetic Modeling A Tool for Rational Catalyst Design.pdf](file-service://file-XS2qSiP6bJuoJrXtSfHt5q).



------





#### **3. The microkinetic workflow (in five human‑readable steps)**



| **Step**                                           | **In plain language**                                        | **Where the paper explains it**                              |
| -------------------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **1. Draft the roadmap**                           | List every plausible elementary reaction on the surface, but keep only those you can actually measure or estimate. | Section 2.1 “Formulation of a Reaction Mechanism” okinetic Modeling A Tool for Rational Catalyst Design.pdf](file-service://file-XS2qSiP6bJuoJrXtSfHt5q) |
| **2. Check your math with thermodynamics**         | Make sure all these little steps, when added up, equal the overall reaction and obey energy conservation. | Section 2.2–2.4 “Stoichiometric & Thermodynamic Consistency” okinetic Modeling A Tool for Rational Catalyst Design.pdf](file-service://file-XS2qSiP6bJuoJrXtSfHt5q) |
| **3. Give each step a speed**                      | Estimate rate constants from quantum‑chemistry (DFT), semi‑empirical shortcuts (UBI‑QEP), or lab data. | Section 2.5 “Rate Constant Estimation” okinetic Modeling A Tool for Rational Catalyst Design.pdf](file-service://file-XS2qSiP6bJuoJrXtSfHt5q) |
| **4. Let the computer run the traffic simulation** | Solve a stiff set of differential equations until surface coverages stop changing—this is steady state. | Section 2.6–2.7 “Model Development & Numerical Solution” okinetic Modeling A Tool for Rational Catalyst Design.pdf](file-service://file-XS2qSiP6bJuoJrXtSfHt5q) |
| **5. Extract insight**                             | Use tools like **degree of rate control**, sensitivity, and selectivity analysis to find the true bottlenecks. | Section 3 “Analysis after Model Development” okinetic Modeling A Tool for Rational Catalyst Design.pdf](file-service://file-XS2qSiP6bJuoJrXtSfHt5q) |



------





#### **4. Key analysis ideas without the math**





- **Degree of Rate Control (DRC)** – If you could magically lower the energy of one transition state by a tiny amount, DRC tells you how much the overall rate would change. A DRC of 1 means that step is *the* throttle; a value near 0 means it hardly matters okinetic Modeling A Tool for Rational Catalyst Design.pdf](file-service://file-XS2qSiP6bJuoJrXtSfHt5q).
- **Sensitivity Analysis** – Nudges each rate constant up or down to see which ones move the needle okinetic Modeling A Tool for Rational Catalyst Design.pdf](file-service://file-XS2qSiP6bJuoJrXtSfHt5q).
- **BEP & Scaling Relationships** – Shortcuts that relate a step’s barrier to its reaction enthalpy. They let you screen whole catalyst families quickly and explain those famous “volcano” plots (activity peaks at just‑right binding strength) okinetic Modeling A Tool for Rational Catalyst Design.pdf](file-service://file-XS2qSiP6bJuoJrXtSfHt5q).





------





#### **5. Why it matters for Jackson’s project**





- **Mechanism clarity:** He’ll know exactly *which* C‑H or O‑H break limits aqueous methanol dehydrogenation instead of blindly tweaking the model.
- **Reproducibility:** Anyone in Dr Getman’s group can rerun his Julia code with different metals or temperatures because the model is grounded in first‑principles parameters, not lab‑specific curve fits.
- **Design leverage:** Once the Julia port reproduces published results, Jackson can play “what‑if” games—e.g., *What if CO sticks a little less?*—and instantly see predicted rate gains.





------





#### **6. Big take‑aways (no equations required)**





1. **Microkinetic models are digital wind‑tunnels for catalysts.** They predict performance before you ever mix chemicals.
2. **Most steps are spectators.** Tools like DRC pinpoint the handful that truly control the rate or selectivity.
3. **Thermodynamic bookkeeping keeps you honest.** If the little steps don’t add up to the overall energy change, something’s wrong.
4. **Modern computing + surface science make it practical.** What looked impossible two decades ago is now routine thanks to DFT and smarter algorithms.
5. **The review is a field guide.** It walks through best practices, common pitfalls, and even how machine learning is joining the party rokinetic Modeling A Tool for Rational Catalyst Design.pdf](file-service://file-XS2qSiP6bJuoJrXtSfHt5q).





------



**If you skim only one part of the paper:** read the Abstract and the first half of Section 2. Together they give you the “why” and the “how” in just a few pages . After that, dip into Section 3’s analysis tools whenever Jackson starts asking *“Which step is rate‑limiting in my code?”* – you’ll be ready.	