The following paper is a huge review on the state of FSOC as of 2017. Some information and examples are slightly dated, but it's a good overview of some of the key facts regarding the state of FSOC.
    
FSOC has an advantage over RF systems in that a much lower SWaP is required. I expected it to be the other way around, but I guess it makes sense since all you really need is a laser and a modulator.
 
There is a trade-off regarding wavelength selection for FSOC systems. Antenna gain is **inversely proportional** to wavelength; for smaller wavelengths, greater antenna gain is observed. However, smaller wavelengths produce poorer link quality, and are more prone to fade outs.
 
Most FSOC systems opt to use NIR (750nm - 1450nm) or SIR (1400nm to 3000nm) wavelengths. These wavelengths strike a good balance between antenna gain and fade out likelihood, and are also common wavelengths used in fibre optic communications. This means that there are parts on the market readily available to adapt into a FSOC system.
 
Here are some common wavelengths used by FSOC space missions:

![[Pasted image 20241010165312.png]]

For ground-to-satellite communications, atmospheric turbulence presents a much greater challenge for uplink than downlink. This is because, when sending an uplink signal, the beam becomes disturbed from its point of origin. This means it expands outward as a spherical wavefront immediately, which carries over once it leaves the atmosphere.
 
Conversely, for a satellite-to-ground transmission, the beam travels as a plane wavefront until it reaches significant atmospheric distortion, after which it only travels a relatively short distance through turbulent conditions.
 
When an optical beam travels through the atmosphere, it encounters loss form a variety of sources. **Absorption and scattering loss** both occur when light travels through the atmospheric channel and interact with aerosols and gas molecules. The main offenders include water, carbon dioxide and ozone. Below is a table of some common FSOC wavelengths and their atmospheric absorption rates.
         

The main form of atmospheric scattering is **Rayleigh scattering**, which occurs for smaller wavelengths of light. For longer wavelengths >=NIR, Rayleigh scattering can functionally be neglected. In the IR range, [[Mie Scattering]] becomes the dominant form of light scattering. This process is usually caused by aerosols, fog and haze. Some geometric scattering due to large particles in the air, such as rain and snow, also exists.

Here is a list of references from Kaushal which look interesting:
 
[72] talks about mean temperature of the atmosphere as a function of altitude
 
[88] talks about FSOC modelling through the atmospheric channel in terms of signal loss
 
[98] talks about HAP interconnected optical links, whatever that means

![S.N0 Wavelength 550 690 850 1550 (nm) Molecular Absorption (dB/km) 0.13 0.01 0.41 0.01 ](Exported%20image%2020241010164240-3.png)

**Total Atmospheric Attenuation** **γ** can be described using the following formula:
 ![Exported image](Exported%20image%2020241010164243-4.png)  

Where:
 
- α$_m$ is the molecular absorption
- α$_a$ is the aerosol absorption
- β$_m$ is the molecular scattering coefficient
- β$_a$ is the aerosol scattering coefficient.
 
Atmospheric transmittance is also dependent on the transmission angle. At the zenith angle, where aerosol impact is lessened, the transmittance can be described as follows:
 ![чр(ч 'M)L OOOS— «[ТЭ (М) ](Exported%20image%2020241010164246-5.png)  

Where:
 
- γ is the atmospheric attenuation coefficient
- H is the vertical height of the atmospheric channel
- λ is the operating wavelength
- θ is the zenith angle.
 
The majority of atmospheric attenuation can be attributed to fog; in dense fog, loss up to 350dB/km can be experienced (astounding). It is possible to slightly offset the attenuation caused by fog by using high powered lasers around the 1550nm wavelength, however it remains a major issue. It is very difficult to model exactly how much attenuation is expected from a fog event, but the scattering due to fog can be roughly approximated via [[Mie Scattering]] using:
 ![(Bfog (λ) — 3.91 λ v 550 ](Exported%20image%2020241010164248-6.png)  

Where:
 
- V(km) is visibility range
- p is the size distribution coefficient of scattering.
 
In the above model, the value for p can be found using either the Kim or Kruse model [91], [92].
 
In NIR wavelengths, rain can produce attenuation loss up to 10dB/km. During low cloud, heavy rain events, attenuation loss is at its worst. It is possible to power through rain using very high power lasers, with a link budget margin of at least 30dB dedicated just for rain. Alternatively, HAP interconnected optical links at different locations can be used to bypass cloud coverage [98].
 
**THERE IS A MATHEMATICAL MODEL EXPLAINED FOR RAIN but it's pretty basic just go look at it if you want it it's on page 7.**
 
Snow can also be a source of attenuation loss, and in terms of severity is somewhat between fog and rain. In bad snow conditions, losses can approach the same 350dB/km that fog achieves. Dry snow and wet snow can affect signal loss differently, as explained by the formula:
 ![snow asb ](Exported%20image%2020241010164251-7.png)  

Where the parameters for _a_ and _b_ are dictated by whether the snow is wet or dry;
 ![Dry snow : Wet snow : a 5.42 x 10-5 + 5.49, 1 02 x 10-4+3.78, b = 1.38, b = 0.72. ](Exported%20image%2020241010164253-8.png)  

**Atmospheric turbulence** is the big boy. You know him, I know him, nobody likes him. Turbulence is caused by differentials in temperature at different layers of the atmosphere. This creates turbulent 'cells', or _eddies_. The eddies refract light and cause major attenuation in FSOC beams. There are three major types of atmospheric turbulence which can be identified.
 
**Turbulence-induced beam wander** occurs when a beam strikes an eddy that is larger than the beam. This most commonly occurs during uplink, due to the beam's wavefront properties. This process causes the beam to redirect in a random direction by up to several hundred metres, potentially resulting in link failure. Beam wander can be mathematically described as such:
 ![a BW 0.54 (H — ho) 2 sec2 (O) ](Exported%20image%2020241010164255-9.png)  

Where:
 
- H is the altitude of the satellite
- h$_0$ is the altitude of the transmitter
- r$_0$ is the atmospheric coherence length (Fried parameter)
- λ is the operating wavelength
- θ is the zenith angle
- W$_0$ is the initial beam size.
 
**Turbulence-induced beam spreading** occurs when the size of an eddy is smaller than the incident beam. This causes diffraction and scattering of different parts of the beam in different directions, resulting in a 'spread'.
 
**Turbulence-induced beam scintillation** occurs when a beam strikes an eddy roughly the same size as the beam. This causes the eddy to act like a lens, which can either focus or de-focus the beam. The result is an output beam with rapidly fluctuating irradiance and intensity, since eddies are not spatially and temporally static.
 
On a more general scale, atmospheric turbulence can induce signal loss by interrupting spatial coherence. A spatially coherent beam is one whose cross section shows a uniform phase state at a given space and time. However, due to turbulence, sometimes parts of the beam are disrupted, resulting in a change of phase across the beam's cross section.
 
The degree of coherence for a beam between two points can be expressed as:
 ![7 е.тр — 5/3 ро ](Exported%20image%2020241010164300-10.png)  

Where:
 
- ρ$_0$ is the spatial coherence length (Fried parameter)
- ρ$_1$ and ρ$_2$ are two position vectors in space.
 
This demonstrates that for values when ρ (|ρ$_1$ - ρ$_2$|) > ρ$_0$, the random phase angle (the amount the coherence has shifted) is greater than π. At this point, the wavefront has lost its spatial coherence, and the signal has been corrupted.
 
Atmospheric turbulence also has the potential to **depolarise** light which was initially polarised. This occurs because turbulence can create _birefringent_ pockets, through which light passes at a speed dependent on its polarisation. This can introduce complex phase shifts into the beam, and can cause power losses up to 160dB.
 
Downlink losses are mainly caused by:
 
- Beam spreading
- Scintillation
- Loss of spatial coherence.
 
Uplink losses are mainly caused be:
 
- Beam wander
- Fluctuations in angle of arrival at the receiver plane.
 
**Atmospheric Scintillation**
 
Atmospheric scintillation can be mathematically quantified by assigning a _scintillation index_. This is basically a measurement of the variance of intensity fluctuations induced by scintillation:
 ![Exported image](Exported%20image%2020241010164302-11.png)  

Where:
 
- _I_ is the irradiance of the beam at some point on the detector plane.
 
To put it simply, the scintillation index σ$^2_I$ is responsible for quantifying how much the intensity of the light fluctuates around its average value. Higher values of σ$^2_I$ imply a greater fluctuation around the mean value, and hence a less reliable signal.
 
Scintillation is also dependent on the refractive structure parameter, C$^2_n$, which attempts to quantify the amount of turbulence being experienced at a particular time and place. Close to the ground, C$^2_n$ tends to be relatively constant. During gentle turbulence, C$^2_n$ tends to take value around 10-17m-3/2, whereas strong turbulence can produce values around 10-13m-3/2.
 
C$^2_n$ is highly variable with altitude _h_. It can be said that C$^2_n$ increases roughly proportionately to _h_-4/3. When performing calculations, C$^2_n$ must be integrated over the entire atmospheric channel. This is done by integrating the path between the **height of the transmitter above sea level to the top of the atmosphere (around 40km)**.
 
**Page 10** has a lot of information on models used to calculate the value of C$^2_n$ as a function of elevation. If I ever need to calculate C$^2_n$, that's where I need to look.
 
Calculating the coherence length (Fried parameter) isn't actually as scary as it looks, and is dependent on whether we are considering a downlink or uplink scenario. For a downlink scenario (plane wave), we can calculate r$_0$ using the following equation:
 ![ho + L 0.423k2sec (0) c; (h) db ho —3/5 ](Exported%20image%2020241010164304-12.png)  

Where:
 
- k is the wavenumber (2π/λ)
- θ is the zenith angle
- h$_0$ is the height of the ground station antenna
- L is the height of the atmospheric channel (~40km) - h0
 
This equation is valid for the approximation of a plane wave, as is expected for a downlink since the signal originates in space before entering the turbulent atmosphere. Conversely, if we wanted to calculate the Fried parameter for an uplink signal, we would have to approximate the signal as a spherical wave, as such:
 ![Exported image](Exported%20image%2020241010164307-13.png)  

Time for a little mathematical proof to relate the dependence of r$_0$ on λ (update at home):
                            
This basically means that, as λ increases, r$_0$ decreases. Hence, greater wavelengths are less affected by turbulence. The Fried parameter is also good at predicting the size of the beam required. If the beam size is on the order of r$_0$, significant beam wander will occur.
 
When turbulence is weak, the scintillation index can be related to the refractive structure index parameter, as such:
 ![Exported image](Exported%20image%2020241010164309-14.png)  

Where:
 
- σ$^2_R$ is the Rytov variance
 
This assumption is valid for weak turbulence, small zenith angles and large wavelengths. In the case of moderate to strong turbulence, larger zenith angles and/or smaller wavelengths of light, a more complicated scintillation index can be calculated as such:
 ![Exported image](Exported%20image%2020241010164311-15.png)  

The Rytov variance itself is a whole thing, but for now here's the calculation for it (according to ChatGPT, I should double check this at some point):
 ![Exported image](Exported%20image%2020241010164313-16.png)  

There are several other models this paper references that can be used to approximate the scintillation index, which I will include here for SEO in my notes (see page 10):
 
- K model (or K distribution)
- I-K distribution
- Log-normal Rician distribution
- Rice-Nakagami statistics
- Gamma-gamma distribution
 
The following equations I will include here but not elaborate on, since I have neither the time nor inclination to figure out how they work.
 ![Exported image](Exported%20image%2020241010164318-17.png)  

The above equation is a probability density function for the irradiance of a signal through turbulence. I don't know what the gammas do, I don't know what the alpha or beta are, but I do know what the K is; a modified Bessel function of the second kind of order _a_. And no, I don't know what that means.
 
The paper then yaps about a few more models for turbulence which I will, once again, include here:
 
- Weibull distribution
- Double Generalised Gamma (Double GG)
- Exponentiated Weibull (EW)
 
**Beam Divergence Loss**

As a downlink beam enters the atmosphere and begins to interact with turbulence, it naturally diverges and spreads out over a larger surface area. Technically it is possible to still capture all the information by making a wide dish-like antenna, but in most cases some information is going to be lost. It is preferable to have narrow beams which don't diverge, however that means a more precise light capture method is required. Very narrow beams can still be captured with sophisticated PAT systems, but these systems are expensive and cumbersome.

**Background Noise and Sky Radiance**

The main sources of optical noise for a FSOC system are:

- Diffused atmospheric background noise
- The sun and other stars
- Scattered light collected by the receiver.

The easiest way to control background noise is to apply a filter which only permits certain wavelengths of light to the receiver. Commonly, a filter bandwidth of about 0.05nm is used in FSOC applications. However, a number of factors about the incoming signal must be considered in order to select the right kind of filter, including:

- Signal angle of arrival
- Potential for Doppler shift
- Temporal modes.

Another potential source of noise in a photon detector is **detector dark current**. This occurs when electrons receive enough thermal energy to jump from the valence band to the conduction band in a semiconductor. This causes a positive signal, even when no photon strikes the system.

Due to the quantum nature of photons, even in a steady beam of photons such as a laser beam, arrival time at the detector for each individual photon will slightly vary in accordance with a Poisson distribution. This introduces another source of noise called **shot noise**, which is predicated upon the random instabilities inherent in an optical signal.

Furthermore, detectors are unavoidably affected by thermal noise. Since electrons have some inherent thermal energy at temperatures above absolute zero, it is possible that the associated agitation creates a false positive in a detector, hence introducing another source of noise.

The solar irradiance spectrum ranges from 300 nm - 2000 nm with a peak at 500 nm. This means that using greater wavelengths of light closer to SIR is an effective way of filtering out sky radiance-induced background noise. Several factors can affect sky radiance, including the receiver's LOS sun angle, the receiver's altitude, aerosol concentration and cloud coverage. The sky radiance observed by a receiver can be quantified as such:

$\huge P_{sky} = S(\lambda,\theta,\phi)\frac{\pi D^2_R\Omega\Delta\lambda}{4}$

Where:
- $S$ is the sum of all scattering sources in all $N$ atmospheric layers
- $D_R$ is the receiver diameter
- $\Omega$ is the FOV of the receiver (steradians)
- $\Delta\lambda$ is the bandwidth of the narrow bandpass filter.

Page 11 talks about sky radiance and its major components at different viewing angles, some of it might be useful but for now I'm gonna brush over it.

**Misalignment and Pointing Loss**

The potential for pointing loss to occur in FSOC systems is inherent to two main factors about transmitters and receivers. Firstly, optical beams are narrow with little beam divergence, which means pointing must be very precise. Secondly, to reduce background noise, receiver FOV is very low. The combination of these two facts means that pointing and tracking must be extremely precise in FSOC systems in order to minimise loss.

Pointing loss is particularly tricky for satellite systems, since they are prone to many random, unpredictable movements including:

- Satellite vibration (see [145] - [151])
- Platform jitter
- Stress in mechanical devices.

Previously discussed phenomena such as atmospheric turbulence-induced beam wander can also result in pointing losses. Jitter losses are primarily compensated for in the engineering process, making sure that the assembly is free of vibrations. Further reading on misalignment and pointing error can be found in [160] - [162].

**The Fucking Clouds**

Clouds just fuck everything up they're the worst. One minute you have a 10Gbps optical link to the moon, the next your lunar Twitch stream randomly shuts off. And there's literally no counterplay; it's an opaque fucking object. You can't put a laser through it it's just not possible.

The best way to play around clouds is just with site diversity. Having multiple ground stations in different places lets us point our signals around the clouds, but personally I think it's stupid that we're scared of them. Caligula once attacked the ocean and lost. Now it's our turn to declare war on water. And this time, we will probably lose again but I'm willing to try.

**Atmospheric Seeing**

A concept that comes up a lot is that of *atmospheric seeing*. Seeing is calculated based on optical beam perturbations and the atmospheric coherence length (Fried parameter), $r_0$. In circumstances when $r_0$ is much smaller than the diameter of the receiver $D_R$, the received signal is blurred. This blurring effect is what we refer to as seeing, expressed by $\frac{\lambda}{r_0}$.

In an optimal optic collection system, we can express the spot size of a received signal in the focal plane of the receiver as $\frac{2.44F\lambda}{D_R}$, where $F$ is the focal length of the receiver. The spot size at the focal plane is increased by the ratio $\frac{D_R}{r_0}$.

**Angle-of-Arrival Fluctuations**

Unavoidable turbulence in the atmosphere can result in spot motion and/or image dancing; a consequence of angle-of-arrival fluctuations. Adaptive optics and [[Fast Steering Mirror (FSM)|fast steering mirrors]] can offset the issues introduced by angle-of-arrival fluctuations. The variance of angle-of-arrival fluctuations $<\beta^2>$ can be expressed by:

$\large <\beta^2 > = 2.91[\huge \int_{H}^{h_0} \large C^2_n(h) \,dh ]D_R^{-\frac{1}{3}}sec(\theta)$
This equation can be simplified further:

$\large <\beta^2> = 0.182(\frac{D_R}{r_0})^\frac{5}{3}(\frac{\lambda}{D_R})^2$

**Point-Ahead-Angle**

*Shoot where he's going, not where he's at!*

Point-ahead-angle (PAA) refers to the offset angle a transmitter must be pointed to account for the fact that light takes time to travel. When establishing an Earth-to-satellite or satellite-to-satellite link, one must account for the relative motion between the origin and the destination. For deep space communications, the PAA can be up to hundreds of microradians, whereas the PAA for a near space system would likely be in the tens of microradians.

This process is mostly self-explanatory, with the exception of PAA anisoplanatism. This occurs when the PAA exceeds the isoplanatic angle (the solid angle within which atmospheric turbulence can be assumed to be roughly uniform). In this case, the beacon path will encounter unpredictable turbulence and cause bit errors, or even total loss of signal.

The isoplanatic angle can be mathematically described using the following equation:

$\large\theta_0^{\frac{5}{3}}=2.91k^2\int_{0}^{L}h^{\frac{5}{3}}C^2_n(h),dh$

**Doppler Shift**

When establishing a FSOC link, it is important to account for the Doppler effect. For instance, if a LEO and GEO satellite must communicate, a Doppler shift on the order of $\pm$ 7.5GHz is observed.

To account for this, a common technique is to employ an optical phase-lock loop (OPLL) system. This involves sending a signal to a local oscillator (LO) laser, which produces a *beat signal*; the difference between the received laser and the LO laser caused by interference. The beat signal is then analysed before a phase shift-corrected beam is produced and sent over the FSOC system.

**Satellite Vibration and Tracking**

Maintaining PAT and LOS for a satellite can be made quite difficult due to inherent vibrations and noise produced by the satellite system. Examples of components that produce vibrational disturbances include:

- Solar panels
- Momentum wheels
- Gimbal packages
- Thrusters.

On-board laser systems produce various types of noise, including:

- Relative Intensity Noise (RIN)
- Thermal noise
- Dark current shot noise
- Signal shot noise
- Background shot noise.

Several tracking techniques can be used to mitigate these issues, including:

- DC tracking
- Pulse tracking
- Square law tracking
- Coherent tracking
- Tone tracking
- Feed-forward tracking
- Gimbal tracking.

Several of these tracking methods are briefly explained with sources on page 14.

**Background Noise Sources**

FSOC systems are subject to background noise from myriad sources, including:

- Detector bulk dark current
- Pre-amplifier noise
- Thermal noise
- Signal shot noise
- Stellar and celestial radiant fluxes
- Scattered light from optics structures

Page 15 goes into some funny maths about quantifying the noise experienced by a receiver.

**Pointing, Tracking and Acquisition (PAT)**

Since optical beams are so narrow, it can be challenging to establish initial uplink with a satellite. Firstly, the transmitter beacon must sweep a small uncertainty area, during which it (hopefully) acquires the signal of the satellite. To assist with this, the beacon uses high peak power, low pulse rate and large FOV. At this time, the receiver is undergoing a similar swathe search for the beacon signal.

Once the initial connection has been established, the receiving terminal is responsible for sending a new, steadier beacon signal toward the transmitter terminal (accounting for PAA). The receiver terminal processes this signal using telescope optics, and passes it off to a beam splitter which hands the beam off to communication detectors and PAT subsystems for accurate tracking. The incident beam is sent to a focal pixel array (FPA), which is used to detect changes in the satellite's position. 

Once this process is complete, the logic controller on the satellite begins to narrow its FOV until both the ground and space terminal have fully locked on to one another. This whole process usually only takes about a single second, as was seen in [[NASA LLCD]|NASA's LLCD]]. In the initial phases of acquisition, a coarse pointing mirror from the ground station is used. Once full acquisition has been established, this responsibility is delegated to a logic controller on the satellite, which commands a finer beam steering element to direct the signal straight to the detector at all times.

Several different technologies can be used as tracking sensors, including:

- Charge-coupled device (CCD) arrays
- Complementary Metal Oxide Semiconductors (CMOS)
- Quadrant Avalanche Photodiodes (QAPD).

Below is a figure showing a typical PAT system for a ground station:

![[Pasted image 20241014112047.png]]

In the case of deep space communications, it is not always possible to equip a satellite with an artificial beacon robust enough to enable PAT due inherent beam divergence. Thus, sometimes celestial bodies themselves are used as natural beacons [213], [214]. This is a very efficient way of initialising PAT, since no power or dedicated architecture for a beacon signal is required. It would be interesting to see if there were a reliable way to achieve this for lunar comms... maybe using features on the moon?



















