> [!caution] This page contained a drawing which was not converted.   

**Chapter 2 - The Signal Power Budget for Intersatellite Links**
 
This chapter touches on some of the challenges involved with establishing laser communications between two satellites in nonatmospheric conditions.
 
In generalised laser signal power budget (SPB) calculations, it's common to assume that a transmitter satellite and receiver satellite maintain uninterrupted communication with one another. In reality, it is quite difficult to perfect the acquisition, tracking and pointing (ATP) of a laser link system. Factors as simple as vibrations in either satellite can result in a temporary disruption of communication, and thus a loss of ATP.
 
One critical difference of establishing a laser SPB compared to an RF SPB is the signal units; laser SPBs calculate number of photons per cycle (or bit), whereas RF SPBs utilise watts per cycle (or bit). The energy per photon is expressed as _hν_, where _h_ represents Planck's constant and _ν_ represents the frequency of light measured in Hz. Hence:
      

That is to say, if you take the received optical power in watts _P_, and divide it by _hν_ multiplied by the signal data rate _f_ (which is in bits per second), you receive the number of photons per bit, _n_. This is the most reliable way of calculating the number of photons per bit received at the receiver satellite.
 
Receivers are typically accompanied by photoelectric devices such as Avalanche Photo Diodes (APD) or P-Intrinsic (PIN) photodiodes, as well as photomultiplier tubes and electronic filters, which are used to separate signal photoelectrons from noise photoelectrons.
 
**Calculating the Signal Power Budget**
 
The generalised equation to calculate the power received by the receiver satellite can be expressed as:
       
where:
 
- PR represents power received
- PT represents power transmitted
- ΩR represents the solid angle of the receiver
- ΩT represents the solid angle of the transmitter.
 
The solid angle of the receiver, ΩR, can be calculated as:
         

where:
 
- aR represents the radius of the receiver aperture
- R represents the distance between the transmitter and receiver optics.
 
Finally, the solid angle of the transmitter, ΩT, can be calculated as:
         

where:
 
- aT represents the radius of the transmitter aperture.
 
Using all these equations, we can make some substitutions to estimate the power received based on the physical characteristics of the laser link system:
             
Additionally, the number of signal photoelectrons _n'_ can be determined as such:
            

where:
 
- Q is the _quantum efficiency_ of the photoelectron detector.
 
We can develop a more robust calculation for _n'_ by introducing some extra factors:
             
where:
 
- F is the combined efficiencies of the Tx and Rx subsystems
- M is the margin (huh?)
- θ is the optical beamwidth of the transmitter.
 
A summary of the above equations is detailed below (page 19)
 ![Exported image](Exported%20image%2020241010164210-0.png)  

**Numerical Example 1**
 
In this example, we will be considering a Nd:YAG laser from a transmitter satellite, which emits light with a wavelength of **1.064μm**. This system also requires **40 photoelectrons per bit**. The detector has a quantum efficiency of **30%**. Let's start by determining the power received by the receiver.
 
Firstly, if the required receive rate is 40 electrophotons per bit, and the receiver itself has a quantum efficiency of only 30%, a substantially higher transmission rate is required.
      

Hence, the transmission rate must be **133.33 photoelectrons per bit**.
 
When performing calculations, it is useful to convert these units to dB. To do this, simply take 10log10() of the photoelectrons per bit. Let's convert our 133.33 photoelectrons per bit into dB:
       
Hence, we have re-expressed our transmitted number of photoelectrons per bit into **21.2dB**.
 
Now, we have been provided with the wavelength of **1.064μm**, which we can convert to frequency with:
         

This gives us a frequency of **3 x 10****14****Hz**. We can use this to calculate hν, since h is Planck's constant and ν is the frequency. Thus:
                        

Converting to dB:
       
Thus, **hν = -187.2dB**. This can be re-expressed as -187.2 joules per photon.
 
Now we know that the required number of photons is 21.2dB (photons per bit), and hν (energy per photon) is -187.2dB (joules per photon). Thus, we can simply add these values together as such:
            

This gives us a value of **-166dB (joules per bit)**. This can also be re-expressed as -166 watt-sec per bit. Now, let's assume a transmission rate of **1Gbps (10****9** **bit/sec)**. We can now convert the transmission rate into dB, and add it to our previous value to find watts per bit.
                  

This gives us a value of **-76dbW**. Converting this into watts per bit:
                            
Given all this information, we can construct our link budget as such:
 
|   |   |   |
|---|---|---|
||Value|dB|
|Required Photoelectrons/BIT|40|16|
|Detector Quantum Efficiency|30%|5.2|
|Required Photons/BIT|133|21.2|
|hν (watt-sec/photon)||-184.2|
|Joules per bit||-163|
|Bit rate|109|90|
|Watts required at detector|5x10-8W|-73|
 
This example makes several assumptions. First of all, it's not accounting for any atmospheric conditions or other disruptions, since it is just considering two satellites in free space. Furthermore, it assumes 100% ATP efficiency, which is not realistic. This is simply an exercise to show the basic method of devising a link budget.
 
**Numerical Example 2**
 
Here is a similar example to the previous scenario, except a GaAlAs diode laser is used instead of a Nd:YAG laser. In this case, the wavelength output is **0.780μm**, and the detector quantum efficiency is **27%**, with a required **40 photoelectrons per bit**. In this case, the transmission rate will be **12.6Mbps**.
                                                                                          

Constructing the full link budget for the GaAlAs diode laser:
 
|   |   |   |
|---|---|---|
||Value|dB|
|Required Photoelectrons/BIT|40|16|
|Detector Quantum Efficiency|27%|5.7|
|Required Photons/BIT|148|21.7|
|hν (watt-sec/photon)||-185|
|Joules per bit||-163.3|
|Bit rate (bits per second)|12.6x106|71|
|Watts required at detector|5.89x10-10W|-92.3|
 
**Power Budget Expression**
 
A comprehensive expression which represents the entire power budget system for two satellites communicating with each other through free space can be seen below:
 ![Exported image](Exported%20image%2020241010164212-1.png) ![Exported image](Exported%20image%2020241010164217-2.png) ![Exported image](Exported%20image%2020241010164219-3.png)  

Most terms are self-explanatory. LP-T and LP-R are typically characterised by vibrations in the platforms of both the transmitting and receiving satellites. Small vibrations can have a profound effect on the laser link system, causing either the transmitter or receiver to be momentarily pointing in the wrong direction, resulting in bit error rate (BER). This effect is amplified over short distances, since small vibrations can drastically alter the relative pointing direction of the transmitter/receiver.
 
**Bit Error Rate Analysis**
 
One common modulation method used in satellite laser communications is Pulse-Gated Binary Modulation (PGBM). This is a one-bit-per-pulse stream which transmits data using simple binary laser pulses, as seen below.
 ![Exported image](Exported%20image%2020241010164221-4.png)  

The _extinction ratio_ E describes the ratio between the number of signal photoelectrons detected by the receiver satellite (when a pulse is desired), and the total number of photoelectrons received when no pulse is desired. The cumulative probability of error can thus be expressed as:
          
where:
 
- p is the probability of transmitting a pulse
- (1 - p) is the probability of not transmitting a pulse
- Pnd is the probability of no detection of a transmitted pulse by the Rx
- Pfd is the probability of a false positive pulse detection at the Rx.
 
I don't really get the maths described on page 23, but here's a graph which shows some of the applications:
 ![Exported image](Exported%20image%2020241010164222-5.png)  

where:
 
- E is the extinction ratio
- m - B is the mean number of noise photoelectrons per decision period
- m - s is the mean number of signal photoelectrons per decision period
 
Simply put, for a given extinction ratio, the probability of error decreases rapidly in low-noise, high number of signal photoelectron environments. Increasing the number of noise photoelectrons even slightly results in a large probability of error, even in high number of signal photoelectron conditions.
 
**Background Noise Considerations**
 
The main source of background photons in a satellite-based laser communication system is obviously solar radiance. Other sources of photonic noise include the moon, stars, Earth's atmosphere and earthshine. To determine the amount of expected background noise at a receiver, the product between the following parameters can be examined:
                                                      

m -

m - B

m - s