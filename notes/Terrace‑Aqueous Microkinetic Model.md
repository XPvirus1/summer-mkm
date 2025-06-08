### **Terrace‑Aqueous Microkinetic Model**





*(Pt‑(111) terrace surface, 500 K, bulk = 10 % CH₃OH | 90 % H₂O)*

| **#** | **Elementary step (forward)** | **ΔGrxn(eV, aq)** | **ΔG‡(eV, aq)** | **k0** **(s⁻¹ site⁻¹)** | **Notes / status**                  |
| ----- | ----------------------------- | ----------------- | --------------- | ----------------------- | ----------------------------------- |
| 1     | CH₃OH + * ⇌ CH₃OH*            | −0.62             | 0 (HK)          | Hertz‑Knudsen           | Adsorption only; no barrier         |
| 3     | CH₃OH* + * ⇌ CH₂OH* + H*      | −0.77             | 0.79            | 1 × 10¹³                | Included                            |
| 4     | CH₂OH* + * ⇌ CHOH* + H*       | −0.14             | 0.73            | 1 × 10¹³                | Included                            |
| 5     | CHOH* + * ⇌ COH* + H*         | −1.10             | 0.41            | 1 × 10¹³                | Included                            |
| 6     | COH* + * ⇌ CO* + H*           | −0.08             | 1.39            | 1 × 10¹³                | Included                            |
| 7     | COH* + H₂O ⇌ COH‑H₂O*         | +0.28             | **0**           | 1.43 × 10¹⁰             | H₂O‑assisted step; barrier set to 0 |
| 8     | COH‑H₂O* + * → CO* + H* + H₂O | −0.36             | **0**           | krev=1.25 × 10⁹         | Completes H₂O‑mediated de‑H         |
| 12    | CHO* + * ⇌ CO* + H*           | −1.07             | 0.43            | 1 × 10¹³                | Included                            |
| 14    | CHOH* + * ⇌ CHO* + H*         | −0.10             | 0.45            | 1 × 10¹³                | Included                            |
| 15    | CO* ⇌ CO + *                  | ΔGrxn(gas)=2.19†  | 0 (HK)          | Hertz‑Knudsen           | CO desorption kept (rate‑limiting)  |
| 16    | H* ⇌ ½ H₂ + *                 | 0.65              | 0 (HK)          | Hertz‑Knudsen           | H₂ desorption                       |

† Gas‑phase value used because solvation destabilisation would unrealistically speed CO desorption .



**Steps omitted**



- Water adsorption (*H₂O + \* ⇌ H₂O*): intentionally **excluded**—H₂O binds much weaker than CH₃OH on Pt(111) so the terrace surface is assumed dry .
- Reactions whose aqueous ΔGrxn > +0.30 eV (e.g., CH₃O* pathway, CH₂OH* → CH₂O*, etc.) are not present in the terrace model .





------





#### **Kinetic constants and conventions**





- **Surface reactions:** Afw = 1 × 10¹³ s⁻¹ site⁻¹, ν = 1.
- **Step 7 forward / Step 8 reverse:** special pre‑exponentials (1.43 × 10¹⁰ s⁻¹ site⁻¹ and 1.25 × 10⁹ s⁻¹ site⁻¹, respectively) because proton transfers are barrier‑less in the H‑bonded network .
- **Adsorption/desorption** (steps 1, 15, 16) use Hertz–Knudsen collision theory; adsorption barriers set to 0.
- The model is run at 500 K until coverages change < 1 × 10⁻¹² ML between iterations (MKMCXX default) .





------





#### **Dominant aqueous‑terrace mechanism & rate control**





1  CH₃OH → CH₂OH* → CHOH*

2  CHOH* → **COH*** (preferred)

3  COH* → COH‑H₂O* → CO*

4  CO* → CO(g) (desorption)



- **Degree‑of‑rate‑control (DRC)**:

  

  - CO* desorption ≈ +1.00
  - H* desorption ≈ +0.27
  - CH₃OH* → CH₂OH* ≈ −0.27 

  





These statistics mean the terrace‑aqueous rate is chiefly throttled by CO* removal; speeding H₂ evolution or modestly slowing the first de‑H step would also raise throughput.



------





### **How to port this into Julia**





1. **Species & site list**: :vac, :CH3OH, :CH3OH_star, :CH2OH_star, :CHOH_star, :COH_star, :COH_H2O_star, :CHO_star, :CO_star, :H_star.
2. **Reactions**: encode the 11 active steps above with forward/reverse Arrhenius parameters (use 500 K values or E‑A + pre‑exponential).
3. **Rate law template** (pseudo‑Julia):



```
r[i] = kf[i]*Π(θ_j^ν_ij) - kb[i]*Π(θ_j^ν'_ij)   # MKM mass‑action
```



1. **Surface balance**: one site type; θ_vac = 1 – Σθ_ads.
2. **Integration**: stiff ODE solver (e.g., CVODE_BDF) until steady‑state criterion above.
3. **Validation**: confirm DRCs replicate CO*‑limited behaviour and match Fig. 4b fluxes.





With this table and notes Jackson can translate each elementary step directly into Julia (e.g., using Catalyst.jl or custom ODEs) and begin benchmarking against the published MKMCXX results.