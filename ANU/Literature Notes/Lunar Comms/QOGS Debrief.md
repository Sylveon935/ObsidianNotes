**QOGS Summary and Functions**
 
- The Quantum Optical Ground Station (QOGS) at ANU is the telescope installation atop Mount Stromlo. We plan for this station to be equipped with a beacon and receiver in order to establish optical communications with Optical to Orion (O2O) to support the Artemis II missions. - Optical communications are superior to RF communications due to better inherent Size, Weight and Power (SWaP) characteristics. Furthermore, since optical wavelengths are far shorter than radio wavelengths, there is less associated beam divergence. This means that less power is required to transmit optical signals, especially over long distances.
   

- There are some associated downsides with optical communications over RF. During poor weather / turbulence conditions, signals can become distorted and broken. The inherently low beam divergence also means that signals must be much more precise than RF signals.
 
- Optical signals in free space must be optimised to account for the low photon count. The QOGS will use Pulse Position Modulation (PPM); a form of High Photon Efficiency (HPE) communication which encodes information within temporal packets.
 
**QOGS Specs**
 
- 70cm diameter
- Planewave Instruments RC700 Ritchey-Chrétien design
- 6.5m dome diameter
- Two Nasmyth ports (135kg capacity) will be used to install beacon + receiver in the future
 
**Design for the Receiver**
 ![Exported image](Exported%20image%2020241010164109-0.png)  

Firstly, light collected by the telescope will be redirected to the Nasmyth port and into a [[Fold Mirror]], orienting the light in the correct plane to be processed. The light then travels through an iris, which reduces any off-angle light entering the system; a form of noise reduction. A second [[Fold Mirror]] is then used to redirect the beam, before it is collimated through a lens to sharpen the image. A fast steering mirror (FSM) is then used to optimise the shape of the beam for fibre coupling.
 
Different spacecraft utilise distinct uplink systems, so it is important to be able to tailor the system to the appropriate system when necessary. To facilitate this, two motorised filter wheels will be used to select the correct lens based on the satellite's uplink system. This includes a filter selection system based on the downlink wavelength.
 
Finally, the light travels through a beamsplitter. 98% of the light is sent to the fibre coupling for detection purposes, and the remaining 2% is sent to a tracking camera, used to control the FSM in a closed loop.
 
**Receiver Fibre Specs**
 
- [[Few Mode Fibre]] (FMF) system
- Graded index core of 20-30μm
- Superconducting Nanowire Single Photon Detector (SNSPD) [16x1 array, 16x16μm in size)
- Demodulated using an FPGA receiver
 
**Transmitter Beacon**
 
The beacon will be mounted atop the QOGS telescope, and will facilitate communication with the satellite. It will take advantage of four distinct channels, slightly separated to mitigate the effects of atmospheric scintillation. Each channel of the beacon will transmit up to 10W of optical power. An amplifier will be used in conjunction with the beacon, meaning some signal filler will need to be added by modulating the beacon with a 7kHz square wave (sometimes the amplifiers get upset if they don't think they see constant power, as per Francis). The design of the beacon system can be seen below.
 ![Exported image](Exported%20image%2020241010164110-1.png)  

**Transmit Optical Assembly Configuration**
 
Once the beacon's light is amplified, a fibre is used to couple it into free space, where it is collimated. This beam will then travel through a dichroic beamsplitter, before being reflected off a FSM. This FSM is what is used to ensure the beacon is always directed toward the spacecraft, and is capable of applying corrections. After passing through a telescope to expand the beam to around 12cm, it is sent towards the spacecraft. A negative lens is used to control the divergence angle, which is aimed to increase to around 100 μrad for acquisition.
 ![Exported image](Exported%20image%2020241010164113-2.png)  

As seen above, the beacon system is also used to collect the satellite's downlink signal. After striking the telescope lens, the beam is resized and sent back through the system to the FSM. It is then reflected off the beamsplitter, before passing through a filter and an imaging lens toward a camera which is used to control the FSM.
 
During the alignment process, the beamsplitter will be used to co-align the uplink and downlink beams. During this team, a shutter will be opened which allows a portion of the beam to reflect off the retroreflector. This will allow the uplink beam to enter the path of the tracking camera. Each channel of the beacon can be pointed at a star, allowing the uplink beam to overlap with the image of the star, hence achieving co-alignment.
 
![[SPIEPW2024-Paper-MichaelCopeland.pdf]]