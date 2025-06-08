### **A Gentle Walk‑Through of the “Terrace‑Aqueous” Microkinetic Model**





Below is a plain‑English guide to what that long table means, **why it matters**, and **how Jackson will use it**. No chemistry degree required.



------





## **1. The Big Picture — What’s Being Studied?**





- **Chemistry goal:** Turn liquid methanol (CH₃OH) into hydrogen gas (H₂) and carbon monoxide (CO) on a platinum catalyst.

- **“Terrace‑aqueous” setup:**

  

  - *Terrace* = a flat patch of platinum atoms arranged in a (111) crystal pattern (think of a billiard‑ball‑smooth metal tile).
  - *Aqueous* = the reaction happens in water, not in dry air.

  

- **Why model it?** Real experiments are slow and expensive; **micro‑kinetic modeling** breaks the reaction into Lego‑size steps, simulates them on a laptop, and predicts speed‑limits and bottlenecks. 





------





## **2. Micro‑Kinetic Modeling in One Sentence**





> *“Write down every tiny reaction step that could happen on the catalyst surface, give each step a speed, then let the computer juggle millions of tiny reactions per second until it reaches steady state.”*



That’s it. The table you saw is the *recipe* of those tiny steps (called **elementary steps**).



------





## **3. Decoding the Table Columns**



| **Column**          | **What It Means (simple)**                                   |
| ------------------- | ------------------------------------------------------------ |
| **Elementary step** | A single “move” a molecule can make on the surface (adsorb, lose an H, slide off, etc.). The asterisk (*) marks a vacant platinum site. |
| **ΔGrxn (eV)**      | Free‑energy change. Negative = step is downhill (favorable). |
| **ΔG‡ (eV)**        | Activation barrier: the hump the molecule must climb. Larger = slower. |
| **k₀**              | Pre‑exponential factor—the “attempt frequency.” Think of it as how many times per second the molecule *tries* to react. |
| **Notes / status**  | Why a step is kept, omitted, or treated specially (e.g., “water‑assisted, barrier ≈ 0”). |

*(You can ignore the exact eV numbers at first—just remember:* ***downhill good, big barrier slow\****).*



------





## **4. How Molecules March Across the Surface**





Imagine the platinum tile is a chessboard:



1. **Adsorption:** Methanol lands on an empty square (Step 1).
2. **De‑hydrogenation:** It loses one hydrogen at a time (Steps 3‑6/7‑8) while scooting to neighboring squares.
3. **Product release:** CO* finally lifts off into the liquid (Step 15); H* pairs up to leave as H₂ (Step 16).





The whole route is like peeling an onion—one H atom at a time—until you’re left with CO.



------





## **5. Why Some Steps Matter More Than Others**





The model reports **Degree of Rate Control (DRC)** numbers:



- *CO desorption (Step 15) DRC ≈ +1.0**

  

  - If you make this faster, overall production rises nearly 1‑for‑1.

  

- *H desorption DRC ≈ +0.27**

  

  - Helpful but second fiddle.

  

- **First C‑H break DRC ≈ −0.27**

  

  - Surprisingly *negative*: slowing this *increases* overall rate (it prevents the surface from clogging early).

  





DRC is like traffic analysis: which intersection, if widened, clears the jam fastest. 



------





## **6. What Jackson Will Actually Code**





1. **List of species** (empty site, CH₃OH*, CH₂OH*, …, CO*).
2. **Array of reactions** with parameters from the table.
3. **Rate equations**—mass‑action formulas that consume/react those species.
4. **Solver loop**—an ODE integrator that watches coverages until nothing changes.
5. **Validation**—confirm his Julia output reproduces the published curves from the original C++ code. 





Once it matches, he can tinker: test new catalysts, temperatures, or even add an electric field—*without ever stepping into a lab.*



------





## **7. Key Take‑Aways for Non‑Chemists**





- **Micro‑kinetic models are digital wind‑tunnels for chemistry.** They predict which step slows everything down.
- **Negative ΔG → thermodynamically downhill. Big ΔG‡ → kinetically slow.** Both matter.
- **CO‑poisoning is the villain.** Most of the catalyst’s “traffic jam” is stubborn CO* refusing to leave.
- **Porting to Julia** modernizes the toolchain—faster prototyping, easier collaboration, and integration with scientific packages.





If Jackson can replicate this model, he’ll not only learn Julia and scientific coding but also gain intuition about *how* chemists dissect complex reactions one atom‑shuffle at a time. That’s a huge win for a summer internship!



------





### **Still Feeling Lost?**





No worries. Skim Dr Getman’s 8‑minute playlist video #10 first—it walks through the same concepts with graphics. Then reread the table side‑by‑side with this cheat‑sheet. It will start to click.