**Amplifiers**
 
Amplifiers rely upon the phenomenon of optically stimulated emission. In this process, an existing photon with a given frequency, polarisation and direction of travel interacts with an already-excited electron. This causes the electron to drop to a lower energy state, and hence release stored energy as a photon. This new photon will inherit the aforementioned characteristics, thereby 'amplifying' the original light. Since one photon can interact with many electrons, this results in a functional amplification of a given photon.
 ![Exported image](Exported%20image%2020241010164035-0.png)  

A common example of an optical amplifier employs erbium. In this case, erbium exists in its ground state, and is then exposed to pump laser light. After the erbium's electrons are excited, they relax back down to a 'metastable state; the very state useful for optical amplification. Once an incident photon interacts with the metastable erbium, a duplicate photon is created, which travels in tandem with the original photon as seen in the figure above.
 ![Exported image](Exported%20image%2020241010164037-1.png)  

Most optical amplifiers operate in the 17dB-25dB range, resulting in an associated gain. The maximum output power of an optical amplifier depends on the pump laser being used to excite the erbium.
 
Amplifiers always introduce a degree of noise to the original signal. Since some excited electrons will emit their own light rather than amplifying the desired photon's characteristics (which, in turn, becomes amplified by the amplifier itself), it is important to consider how much signal noise is being introduced by an amplifier.
 ![Exported image](Exported%20image%2020241010164039-2.png)  

The above figure displays the power of an input signal (solid red line) and output of the subsequent amplified signal (green line). Additionally, the component of the amplified signal that is desired is shown in dotted red lines. Hence, the actual total output power is greater than the components contributed by the original photon's characteristics; this discrepancy indicates that noise is present in the amplified signal.
 
The gain of a signal (_G_) can be expressed as a function of the output power (_P__out_), power of the amplified spontaneous emission (_P__ASE_), and input power (_P__in_), as such:
 ![Exported image](Exported%20image%2020241010164042-3.png)  

_P__ASE_ can be most simply expressed as the interpolated background level (_P__ipt_) subtracted by the gain multiplied by the amplified spontaneous source emission (_P__SSE_).
 ![Exported image](Exported%20image%2020241010164044-4.png)  

This equation holds up, unless the gain is relatively small and _P__SSE_ is relatively large.
 
Hence, the noise figure of an amplifier can be expressed as a function of _P__ASE_, gain, Planck's constant, frequency and the bandwidth of the optical signal amplifier (_B__0_).
 ![Exported image](Exported%20image%2020241010164048-5.png)  

In the case of an erbium amplifier, the gain is dependent on the heat of the material. Hence, erbium amplifiers are typically accompanied by a heater to achieve the desired gain amount. As temperature increases, gain decreases depending on wavelength, as seen below:
 ![Exported image](Exported%20image%2020241010164050-6.png)     

**Lasers**
 
Amplifiers construct the foundation of how lasers function, and understanding how they work is vital to understanding how lasers work.
 
At face value, lasers run into a fundamental issue; at thermal equilibrium, the likelihood for a metastable electron to emit a light induced by optically stimulated emission is equal to the probability that the incoming photon is simply absorbed by an electron at a lower energy state. This can be seen in the following equation:
 ![Exported image](Exported%20image%2020241010164052-7.png)  

That is, the ratio of the number of electrons in energy state _E__1_ (_N__1_) and energy state _E__2_ (_N__2_) can be expressed with the above equation. Thus, in equilibrium, if _E__1_ > _E__2_, then _N__1_ can never be equal to or greater than _N__2_. Furthermore, at equilibrium, more electrons are in the lower state, meaning that on average there will be more photons absorbed than emitted. For a laser system, This Simply Won't Do™.
 
This issue can be overcome by creating a **population inversion**. In the state of a population inversion_, N__2_ _> N__1_. This would allow the photon to be duplicated indefinitely, without running the risk of all input photons ultimately being absorbed. This can be done in a number of ways, which are outlined below.
 
1. _Optical Pumping_

This refers to the process of illuminating the material (such as erbium) with a wavelength known to excite the material's electrons (see above diagram on amplifiers for more info). This causes the material to emit a phonon (vibration energy), which preps the electron into the metastable state useful for amplification.
 
1. _Electrical Pumping_

This process is similar to optical pumping, except a flow of electrons is injected directly into the excited conduction band.
 
1. _Collision Pumping_

This entails exciting the electrons within the desired material by colliding another excited atom with it (radiation?)
 
1. _Chemical Reaction_

Some chemical reactions can cause atoms to excite in a predictable way. For instance, when H2 reacts with F2, HF is formed. This is how a HF laser works (who knew!)
 
All of these methods are used to tackle a similar issue. Fundamentally, it is problematic that electrons within the chosen material do not remain in the desirable excited state for long enough to guarantee a cascade effect of infinite photon duplication. To remedy this, all these methods elevate the electron to an excitation state beyond the desired level, resulting in the emission of heat and de-excitation _to the desired state_, in which it becomes **metastable**. In a metastable state, electrons remain excited for thousands of times longer than during regular excitation.
 ![Exported image](Exported%20image%2020241010164054-8.png)  

**A Quick Detour on Semiconductors**
 
Semiconductors are materials which exhibit properties of both conductors and non-conductors. The mechanism through which semiconductors is comprised of two main bands of electrons; the **valence band**, which is where electrons reside at equilibrium, and the **conduction band**, which is a region capable of moving electricity. As the temperature of a semiconductor increases, electrons emigrate from the valence band to the conduction band, thereby increasing its conductivity. This means that semiconductors can use temperature as a means to regulate their inherent conductivity.
 ![Exported image](Exported%20image%2020241010164055-9.png)  

Electrons which move from the valence band to the conduction band are called **free electrons**. These electrons are capable of transferring charge by traditional means. The regions in the valence band which were once occupied by these electrons are called **holes**, which are also capable of transferring electricity. Taking advantage of these characteristics allows semiconductors to be transient in their conductivity.
 
Semiconductors' conductivity can be altered further by **doping** using either pentavalent atoms (atoms with five valence electrons) or trivalent atoms (atoms with three valence electrons). Pentavalent atoms introduce extra free electrons into a semiconductor, which is referred to as an **N-type semiconductor**. Conversely, trivalent atoms introduce extra holes into the valence band, creating **P-type semiconductors**. A semiconductor that has not been doped is called an **intrinsic semiconductor**, whereas a semiconductor that has been doped in any way is called an **extrinsic semiconductor**.
 
One way of deliberately moving an electron from the conduction band to the valence band is using photons. Some semiconductors exhibit a **direct band gap**; when the lowest possible energy in the conduction band has equal momentum to the highest energy states in the valence band. In this circumstance, it is possible to use a photon to stimulate an electron to move from the conduction band to the valence band.
 ![Exported image](Exported%20image%2020241010164057-10.png)  

Naturally, electrons within the conduction band tend to reside at the lowest possible energy state with the band. Conversely, electrons within the valence band tend to reside at the highest possible energy state. When a photon with energy equal to the band gap is exposed to a semiconductor, an electron in the conduction band can use the photon to transition down to the valence band. This movement results in the release of energy from the electron which moves; the very amount of energy in the band gap. In other words, a photon of identical characteristics to the photon which enabled the electron to move is produced.
 
![[Clarke_Optics For Telecommunications - Theroy and Engineering.pdf]]