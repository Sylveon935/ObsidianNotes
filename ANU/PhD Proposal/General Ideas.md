- Using TIE-GCM to predict / forecast atmospheric turbulence for laser systems. This could involve retrospectively looking at known turbulence values and seeing if TIE-GCM can replicate them at local levels.

- I wonder if all FSOC systems rely on exclusively solid state components. If not, there is room to reduce platform jitter and enhance PAT accuracy.

- I hate the fucking clouds I think it's so stupid. As if our whole operation grinds to a halt when there's a SINGLE CLOUD. As if that forces us to build a million different sites, all of which STILL have the potential to be thwarted by fucking GASEOUS WATER. There has to be a better way.

- Pointing, Acquisition and Tracking (PAT) is a critical process when establishing a FSOC link. It typically involves both the satellite and ground station sending artificial beacon signals to one another in order to establish a robust link. This means that all satellites must be equipped with dedicated architecture to produce beacon signals, which drives up SWaP. For deep space communications, it is common to instead rely on celestial bodies as natural beacons, eliminating the need for artificial beacons. This is difficult to do for regular satellites, however, due to the rapidly shifting environment and the nature of parallax. It is, however, conceivable that we could use features of the lunar surface to act as beacons for lunar-based FSOC systems. Following this lead would require a deep dive into how current plans to establish PAT with the moon have been proceeding. See reference [213] and [214] of [[Kaushal Review]] for more information.

- Assessing the impact of levitating lunar dust on the link budget of lunar-based FSOC modules. I know Joseph at ANU down at jet propulsion has been working on a plasma generator which is capable of levitating lunar dust in a fashion very similar to that observed on the moon. It might be possible to measure laser beam attenuation in this simulated environment to enhance our understanding of how lunar dust disrupts optical communications systems.

- Turns out Jamie is a smurf of a human being. He suggested that, rather than performing Earth-to-moon communications directly, that we use either:
  
  a) A large lunar ground station that facilitates communication from all manner of devices on the moon before establishing a link with the Earth
  
  b) One (or several) orbiting satellites which can establish laser links with devices around the moon, which then sends information to the Earth
  
  Both solutions would require investigating the link budgets for the proposed hardware, and determining whether it's even possible. Some considerations include:
  
  1. Is the period of a Low Lunar Orbit (LLO) suitable for establishing laser links?
  2. Will NASA's Lunar Gateway station have desirable characteristics for fulfilling this purpose?
  3. Would objects on the lunar surface require traditional beacons to establish uplink, or would the lack of atmosphere, satellite elevation, etc. alleviate this requirement?
     
    Jamie's advice was to look primarily at *what makes the moon different from Earth* in terms of FSOC requirements. Characteristics such as the smaller scale, lack of an atmosphere, etc. make the moon a desirable locale for FSOC operations; I should lean into this and make a solid case for why it's even worth using the moon in the first place.

- This idea is less fleshed out and I think it might be a little far-fetched: what if we establish a lunar laser communications system on the dark side of the moon? There's obviously far less solar irradiance there, meaning a higher SNR for deep space laser links. 
  
  My first thought is that any attempts to lase information back toward the Earth would inevitably introduce retroreflected sunlight, thereby ruining the entire point of having no direct sunlight on the sensor. But what if we just used like... a *really long* fibre optic cable:D

- I met with Josef down at jet propulsion on the main campus, and we had a chat about how levitating lunar dust can cause issues for lunar FSOC systems. There's definitely potential for this to occur, especially at lower elevations where the dust density is greater due to patch charging. Josef also has a working plasma chamber which emits the UV light required to induce jumps from the lunar dust, and he thinks it would be achievable to point a laser through the dust to test the attenuation rate.
  
  Josef is also working on technology to remove unwanted lunar dust from surfaces, such as the lens of an optic. This works by bombarding the surface with UV light. I'd have to look into whether or not this would harm the lens, but it's an interesting process nonetheless.
  

**Terrible Ideas that I Think are Funny**

- Crackhead idea: THERE AREN'T ENOUGH THINGS AT THE LAGRANGE POINTS LETS PUT MORE THINGS THERE!! BIG MIRROR!!! BIG FUCKING MIRROR TO FACILITATE OPTICAL COMMUNICATIONS ON THE DARK SIDE OF THE MOON YIPPEE!!!!

- If the atmosphere is such a problem, just put some satellites in space with FSOC capabilities and connect those to the moon, and downlink the data on to hard drives. Then we can fire those hard drives at Earth in little pods and it's probably still quicker than RF comms:D

- I haven't seen any mention of how special relativity affects laser comms yet. Maybe it's just genuinely not a problem, but surely it rears its head once in a while. I'm jotting this down as a bad idea not because it's stupid, but because I don't know if I have the mental fortitude to spend the next three years of my life bogged down in fucking special relativity.