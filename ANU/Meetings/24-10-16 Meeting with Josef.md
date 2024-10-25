
This meeting with Josef is to discuss the implications of lunar dust and its attenuation on FSOC lasers.

**Quick reminder on the actual mechanism that causes the lunar dust levitation, and how frequently it occurs**

- Electrons deposit from solar wind on the surface of the moon
- Incident photons then exercise an amount of energy on the electrons which exceed their work function, causing them to leap
- This leaves behind a positively charged ground region; 'patch charging'
- 'Supercharging' can also occur when the lunar terminator gets involved; surface remains negatively charged on the dark side so the electrons get caught up in the resulting electric field and "fuck right off"







**What is lunar dust physically made of - especially the mock-up dust you're using?**

- Sized of lunar dust particles are 1 - 10$\mu m$
- Particles which are a similar size to the wavelength usually result in forward scattering anyway
- To be honest, the lunar dust scattering might not even be an issue






**What kind of densities of lunar dust kicking around above the surface of the moon are typical?**

- It varies; a lot more dense just above the surface
- 100 particles per cubic metre at 3km, up to 10$^{-3}$ per cubic metre at 100km




**Would it be feasible to shoot an optical laser through your current setup to investigate attenuation?**

- It could be possible
- The window might block out infrared
- But the windows can conceivably be swapped out for better windows
- Josef finishes his PhD in February, and is planning to stick around a while longer (perhaps until the end of the year), so it would be nice if we could get an experiment done before he leaves





**Are there any prevention methods to stop levitating lunar dust from obfuscating a lens / receiver?**

- The idea is you hit the lens that has collected on your surface with UV to make it jump
- Basically replicating the process that made the dust jump at the first place
- UV is >100mW per square centimetre for Josef's work
- Not sure whether that might damage the lens, etc. I'm pretty sure as long as the lens has a narrowband filter it wouldn't be a problem though




**Are there any regions of the moon that the levitating dust is observed more frequently at (i.e. poles, etc.?)**

- Supercharged dust cloud likely lags the terminator
- This means there's usually a big cloud of dust that's hovering above the surface that is slightly behind the terminator as it moves across the moon




**What wavelengths of light are most commonly reflected by lunar dust?**

- People in QLD who are working on lunar regolith simulators that are optically high fidelity







- Equation for shooting a beam through a material - what's the likelihood of it hitting a particle? 
- "Mean free path", "collision frequency"

Here's some napkin maths calculating the mean free path for photons through the field of lunar dust:

**Assumptions**:

- 100 particles per cubic metre at 3km altitude
- 1$\mu m$ radius of dust particles
- 1000nm photon wavelength
- Lunar dust refractivity $\approx$ silicates $\approx$ 1.5

First, determine the size parameter

$\huge x = \frac{2\pi r}{\lambda}$

- $r$ $\approx$ 1$\mu m$
- $\lambda \approx$ 1$\mu m$

Thus, x $\approx$ 6.28

This implies that [[Mie Scattering]] is occurring, since x $\approx$ 1 rather than x $<<$ 1. For [[Mie Scattering]] of non-metallic particles, the scattering efficiency factory $Q$ $\approx$ 2.

Mean free path formula:

$\huge \lambda = \frac{1}{n\sigma}$

where

$\huge \sigma = Q\pi r^2$

Thus:

$\huge \sigma \approx 6.28 \times 10^{-12}m^2$

$n$ = 100 particles per cubic metre

$\huge \lambda = \frac{1}{100 \times 6.28 \times 10^{-12}m^2}$

$\huge \lambda \approx 1.6 \times 10^9m$

This implies that photons in the SIR wavelength range can travel $\approx$ 10$^9$m before they are likely to collide with a lunar dust particle (quite unlikely to affect signal attenuation whatsoever).



