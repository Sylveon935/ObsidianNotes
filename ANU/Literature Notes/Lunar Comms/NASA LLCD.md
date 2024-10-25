The following notes regard NASA's 2013 Lunar Laser Communications Demonstration (LLCD) event, in which NASA demonstrated the world's longest laser link system including satellites, the Lunar Atmosphere and Dust Environment Explorer (LADEE) and Earth ground stations.
 
The greatest consideration to be made regarding the physical architecture of laser link systems is **Size, Weight and Power** (SWaP). Minimising all three of these parameters is critical to the development of laser link systems for obvious reasons.
 
The LLCD's main terminals consist of:
 
- Lunar Lasercom Space Terminal (LLST)
- Lunar Lasercom Ground Terminal (LLGT)  
The LLST was stationed on the LADEE spacecraft, and the LLGT was stationed at White Sands, New Mexico. Due to the nature of laser communications, unobscured and direct LoS between terminals is required, and so two alternative ground stations also existed as redundancies:
 
- Lunar Lasercom OCTL Terminal (LLOT)
- Lunar Lasercom Optical Ground System (LLOGS)
 
LLOT was stationed at JPL's Optical Communications Telescope Laboratory in California, and LLOGS was stationed at ESA's Optical Ground Station on the Canary Islands.
 
Since we don't have enough acronyms already, here's another one. The operations of all the space and ground terminals was coordinated from the Lunar Lasercom Operations Centre (LLOC), which was found at the MIT Lincoln Laboratory in Massachusetts.
 
Here are some basic specs regarding the LLCD laser link system:
 
- 1.5μm band
- 4PPM uplinks at 10/20Mbps
- 16PPM downlinks at 39Mbps-622Mbps
- Uplink acquisition signal square-wave, modulated at 1 Khz
 
The LLST consists of the following components:
 
- Optical module (10cm telescope, ~15 μrad beam)
- Modem
- Controller Electronics (CE)
 
The optical module and modem were coupled using a fibre optic cable. The CE was responsible for controlling the optical module and modem, as well as telecommand and telemetry.
 
The LLGT was characterised by the following components:
 
- Array of four 15-cm uplink telescopes (10W)
- Array of four 40-cm downlink telescopes
- Superconducting nanowire single photon detectors
- Gimballing system
- Nearby control room
 
The LLGT's uplink telescopes delivered signals using single-mode fibre, whereas the downlink telescopes were coupled with multi-mode, polarisation-maintaining fibre to the SNSPDs. Being a transportable system, it was tested at Lincoln Laboratory before being transferred to White Sands for nominal operations. Further specifications for the alternative ground stations such as the LLOT and LLOGS can be found in the paper on page 2.
 
The LLOC was basically an array of desktop computers which were used in tandem to oversee operations. This included telecommand/telemetry, performance monitoring, weather monitoring, etc.
 
For details regarding the testing and deployment logistics of the LADEE satellite, read page 2 of the paper.
 
The LADEE spacecraft also ported several other scientific payload on board other than the LLCD, and so the LLST was intermittently powered down to allow other experiments to gather data. To achieve this, two operators (one in California and one in Massachusetts) coordinated in two overlapping, 10-hour shifts. Several other operators monitored other nominal proceedings, including signal health and ground terminal switchboarding.
 
The LADEE spacecraft was able to allocate 39 watt-hours per orbit of energy usage for the LLST, since it was constrained by its battery life. After each orbit, the solar panels were only able to replenish roughly half of the power used before the LLST needed to be activated again.
 
Optically, the LADEE spacecraft had an unobstructed view of the Earth for one hour per orbit. The 39 watt-hours meant that the LLST could operate for only 20-25 minutes at a time. Thus, that window could be placed anywhere within the one hour timeframe per orbit. For more information regarding protocols and planning for transmission windows, read page 3 of the paper.
 
The LLCD has to play by the rules of the United States' Air Force Laser Clearing House (LCH); an authority which controlled laser emissions from the US. The LCH would instruct the LLOC regarding when lasers would have to be shut off (usually for a few seconds at a time). Due to the aforementioned flexibility in 25-minute blocks, the LLCD was usually able to plan a window in which the laser comms would not be disrupted. However, when necessary, the system did shut off the laser for the few required seconds, before re-establishing laser link almost instantaneously.
 
The pointing, acquisition and tracking (PAT) system of the LLCD was optimised by ensuring that most of the work was done by the ground stations, to reduce the SWaP of the LADEE spacecraft. Ground terminals would lock on to LADEE several minutes before the LLST was powered up, with an uplink beam spread between 45-100 urad depending on the ground terminal. The wavelength of the acquisition signal was square-wave modulated at 1 KHz; this provided background noise resistance.
 
At this point I'm a little shaky on how the exact communications functions worked, but no time like the present to figure this shit out!
 
From my understanding, there is a precarious balancing act between data transfer rate and data error rate. Error in data transmission can come from a variety of sources, including atmospheric turbulence and encoding/decoding inconsistencies.
 
Signals transmitted during the LLCD were multiplexed, meaning multiple different signals were combined into a single signal to transmit. This allows for robust and succinct signal transmission without the fear of any individual signal being lost, creating interference, etc. In this process, different subchannels were combined into a single 'transfer frame', resulting in a single time-division multiplexed (TDM) frame.
 
Before this process, the data bits within each subchannel are appended with several identifiers and redundancies. This includes a Cyclic Redundancy Check (CRC). A CRC is much like the final line on a barcode; to ensure that the signal hasn't damaged during the transmission process, several logical checks involving polynomial division are conducted to assign a _check value_ to the data bit. After transmission, if the _check value_ (calculated by logical mathematical operations on the output data) doesn't match the check value, the data has been corrupted. Usually, several data recovery steps can be taken to correct for corrupted data, but this process isn't too relevant.
 
Many data bits were combined to form a 7560-bit block of data. This data was then encoded using a 1/2 serially concatenated turbo code.
 
During transmission (especially in space), two main types of bit errors can occur; burst errors (in which several sequential bits are flipped), and random bit errors (in which a single, isolated bit is flipped). Both types of errors corrupt data, and it is important that they are corrected for. In space, several processes such as solar weather, thermal temperatures and incident radiation can be responsible for both burst and random bit errors.
 
Concatenated encoding is a multi-step process involving an 'inner' and 'outer' coder and decoder, which provide extra redundancy. Typically, the outer coder is used to protect against burst errors (i.e. Reed-Solomon coding). This involves grouping bits into blocks, and intermittently placing 'parity symbols' into each block based on mathematical operations performed on individual bits within each block. If data is corrupted during transmission, the outer decoder will pick up on it (since the parity symbols don't match the expected values of the bits within each block), and can typically correct for it.
 
Similarly, the inner coder works by placing parity bits within each byte at reserved positions in an effort to combat random bit errors. This is performed by adding the parity bits in before transmission, then after transmission the inner decoder can be used to determine the integrity of the data (in a similar way to the aforementioned outer decoder), after which the parity bits are removed and the signal is passed on.
 
Using a two-step concatenated process is efficient, since it mimics the data retention rate of more sophisticated encoding methods while reducing computational demand. This is especially important considering missions like the LADEE satellite, which very much want to reduce SWaP where possible.
 
The data then undergoes a **convolutional interleaving** process. This involves breaking up the blocks of data and 'scrambling' the bits within to be physically transmitted in a different order than the original order. This means that, when a burst error does occur, once the data is de-interleaved at the receiver, the burst error resolves into several, isolated single bit errors in most cases. This is useful because it's much easier to deal with a random bit error than a burst error.
 
Finally, the data went through a Frame Alignment Sequence (FAS). This is a process that involves putting an arbitrary, known bit at the beginning of the transmitted data block as an identifier that a new block has begun. This enables the decoder to apply the appropriate processes in the correct order to correctly identified blocks of data.
 
In order to uplink data to the LLST, a 4-level Pulse Position Modulation (PPM) system was used, which multiplexed either 8 or 16 channels. The 4PPM signal could carry either 10Mbps or 20Mbps. The receiver aboard the LLST utilised a Fibre Bragg Grating (FBG) near-matched filter. This kind of filter works by using a fibre optic cable that has periodically varying refractive indices, allowing only resonant wavelengths to pass through. Hence, FBG filter can be configured in such a way that it only allows the desired laser wavelengths through, eliminating noise.
 
Once the uplink signals reached the LLST, the onboard modem was used to both demodulate and decode the transmission. Telecommand was then sent to the CE, which controlled the rest of the payload.
 
The downlink signal from the LLST utilised a 16PPM architecture, which operated between 311 MHz to 5 GHz. This enabled a per-channel data rate of 38.55 Mbps, and the full link rate could transmit up to 622 Mbps. The downlink TDM could support up to 16 subchannels, with subchannel 0 reserved for the LLST telemetry stream.
 
At the ground stations, laser signals were received and fed into multi-mode fibre optic cables, before being processed by single photon detectors. The LLGT was equipped to decode four selectable subchannels in real time using an FPGA, whereas the backup stations used off-line processing.
 
For more information regarding logistics of when and how the LLST was powered up, read page 5.
 
**Operational Results**
 
It was found that the LLST could transmit at data rates up to 311 Mbps with only 0.25 W of power. It was also able to approach the 622 Mbps transfer rate on 0.25 W, though the team usually increased the power to 0.5 W for these transmissions. All stations demonstrated very good lock-on times, downlink performance and error-free data transfer.