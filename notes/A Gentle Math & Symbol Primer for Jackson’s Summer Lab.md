## **A Gentle Math & Symbol Primer for Jackson’s Summer Lab**





**Good news:** the math behind micro‑kinetic modeling isn’t much harder than Algebra 2 once you see how the pieces fit. Below is a quick‑start guide you can keep beside you while coding in Julia or reading the papers.



------





### **1. Core “Math Moves” You’ll Re‑Use**



| **Concept**             | **What It Means**                                            | **Quick Refresher**                                       |
| ----------------------- | ------------------------------------------------------------ | --------------------------------------------------------- |
| **Exponentials & ln**   | Reaction speeds follow the Arrhenius form k = A · e^(–Eₐ/RT)—same e from Algebra 2, just with negative exponents. | Review natural logs & base‑e rules (ln ab = ln a + ln b). |
| **Scientific notation** | Energies & rate constants span 10¹³ – 10⁻¹⁰. 1.4 × 10¹³ simply means move the decimal 13 places. | Khan Academy: “Intro to scientific notation”.             |
| **Derivatives (d/dt)**  | dθ/dt reads “how fast the surface coverage θ changes in time”. You won’t solve them by hand; Julia’s ODE solver does it. | Visualize as the slope of a curve at each point.          |
| **Steady State**        | When dθ/dt ≈ 0 for every species, the system stops changing—your simulation goal. | Think “cruise control” speed: no net acceleration.        |
| **Matrix notation**     | Stoichiometry often packed into a matrix ν so the ODEs look like dθ/dt = ν·r. | If you know how to multiply A·x, you’re set.              |



------





### **2. Symbols & Greek Letters You’ll Meet**



| **Symbol** | **Spoken**               | **What It Tracks**                   | **Typical Units**           |
| ---------- | ------------------------ | ------------------------------------ | --------------------------- |
| *          | “star”                   | An empty platinum surface site       | —                           |
| θ          | “theta”                  | Fraction of surface covered (0 – 1)  | dimensionless               |
| ΔG         | “delta G”                | Free‑energy change of a step         | **eV** (1 eV ≈ 96 kJ mol⁻¹) |
| ΔG‡        | “delta G double‑dagger”  | Activation barrier (“hurdle”)        | eV                          |
| k          | “k”                      | Rate constant for a step             | s⁻¹ or (s⁻¹ site⁻¹)         |
| A          | “A” or “pre‑exponential” | Max attempt frequency in Arrhenius   | same as k                   |
| R          | “gas constant”           | 8.314 J mol⁻¹ K⁻¹ (also 0.008314 kJ) | —                           |
| T          | “temperature”            | Kelvin (K)                           | K                           |
| e          | “Euler’s e”              | 2.718 …                              | —                           |

*(Tip: in Julia, type* *\Delta* *+ TAB to insert Δ.)*



------





### **3. How the Pieces Fit in a Micro‑Kinetic Step**





Take one elementary reaction from the terrace model:

```
CH3OH*  +  *   →   CH2OH*  +  H*
```

1. **Identify reactants/products.**

| **Species** | **Coverage symbol** |
| ----------- | ------------------- |
| CH₃OH*      | θ₁                  |
| * (vacant)  | θ_vac               |
| CH₂OH*      | θ₂                  |
| H*          | θ_H                 |

2. **Write the rate law (mass action):**

```
r_forward = k_forward × θ1 × θ_vac
r_reverse = k_reverse × θ2 × θ_H
```

3. **Compose the Arrhenius rates:**

```
k_f = A * exp( -ΔG‡ / (R*T) )     # forward
k_r = A * exp( -(ΔG‡ - ΔG_rxn) / (R*T) )  # reverse
```

> **All you really need:** multiplying numbers, natural exp, and tracking units.



4. **Plug into the ODE for each surface species:**

```
dθ1_dt = - r_forward + r_reverse
dθ2_dt = + r_forward - r_reverse
dθ_vac_dt = - r_forward + r_reverse        # because a vacant site is used, then freed
dθ_H_dt   = + r_forward - r_reverse
```

Julia’s DifferentialEquations.jl handles the integration until every dθ_dt ≈ 0.



------





### **4. Mini‑Cheat Sheet: Constants Jackson Will Copy‑Paste**



```
const kB = 1.380649e-23      # J K^-1
const h  = 6.62607015e-34    # J s
const R  = 8.314462618       # J mol^-1 K^-1
const eV = 1.602176634e-19   # J
# conversion helper
kj_per_mol(E_eV) = E_eV * 96.485    # kJ mol^-1
```



------





### **5. “Must‑Know” Definitions in One Sentence Each**



| **Term**                         | **Single‑Sentence Meaning**                                  |
| -------------------------------- | ------------------------------------------------------------ |
| **Adsorption**                   | When a molecule sticks to the metal surface (star).          |
| **Coverage (θ)**                 | The percentage of surface sites occupied by a given species. |
| **Activation Energy / Barrier**  | The energetic hill a reaction must climb before it rolls downhill. |
| **Arrhenius Equation**           | Converts a barrier height into a reaction speed via an exponential. |
| **Steady State**                 | The point where coverages stop changing (model output).      |
| **Degree of Rate Control (DRC)** | A sensitivity score telling which step throttles the whole pathway. |



------





### **6. Quick Path to Confidence**





1. **Refresh exponent rules & natural logs** – 30 min on Khan Academy.
2. **Practice unit conversions** – how many kJ mol⁻¹ is 0.75 eV? (Answer: ≈ 72 kJ mol⁻¹.)
3. **Type a tiny Julia script** that prints k for ΔG‡ = 0.8 eV at 500 K; verify it changes properly with T.
4. **Skim Section 2 of the review paper**—now the symbols will look familiar.





You now have 90 % of the math you’ll need. The rest is coding practice and asking questions when stuck for that extra 10 %!