# Galvanic Corrosion

Galvanic corrosion occurs when two different metals are electrically connected in the **presence of an electrolyte**.

Under this situation, the *more anodic* (i.e., less noble) metal will transfer its electrons to the more noble metal, corroding in the process.

The **Standard Reduction Potential** (SRP) is   and be reduced in an electrochemical reaction.

- A *higher* (more positive) SRP indicates a stronger tendency for the metal to be *reduced* (act as a cathode, gain electrons). This will be the "more noble" metal.
- A *lower* (more negative) SRP indicates a stronger tendency for the metal to be *oxidized* (act as an anode, loose electrons). This will be the "less noble" metal.

The SRP is somewhat related to the ionization energy of a metal. It is in units of volts and quantifies the tendency for either metal to gain or loose electrons. If you were to bring two metals together under an electrolyte, they would pass electrons between each other; this is a **galvanic cell battery**, which is what we see in *lemon batteries*. The lemon juice and its citric acid acts as an electrolyte, and the two metals with a difference in SRP create an *electric potential*. This electric potential, for a galvanic cell, can be expressed with:

$$E_{cell} = E_{cathode} - E_{annode}$$
so, for copper (SRP = +0.34 V) and zinc (SRP = -0.76 V), the cell would have an voltage potential of:

$$ E_{cell} = 0.34V−(−0.76V)=1.10V $$

> I still don't understand the complete driving force of this reaction. It makes sense as to why the entropy of the system would increase with this process, but I feel like there's a piece of the puzzle missing. I think Gibb's free energy can explain this, but that goes above my head.


This electric potential explains the issue; underwater (in an electrolyte), the metals create a potential between themselves and turn into a sort of battery, passing electrons between each other. As electrons deplete on the anode, it's oxidized within; imagine a bolt rusting inside-out—you can see how this would compromise the material.

### Preventing Galvanic Corrosion (Cathodic Protection)

You can use **Sacrificial Anode** to prevent the corrosion of a material that would otherwise be corroding the primary material. By adding a thin layer of Zinc or another material with *a lower SRP*, you ensure that this material will oxidize instead of the primary material.

Eventually, the sacrificial anode will entirely corrode, after it has given all of it's electrons to the cathode; however, in this time, you have ensured that all the oxidation only occurs at the sacrificial anode—instead of jeopardizing the integrity of the actual part.