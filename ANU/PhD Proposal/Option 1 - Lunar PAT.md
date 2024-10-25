
**Brief**

Pointing, Acquisition and Tracking (PAT) is a critical process when establishing a FSOC link. It typically involves both the satellite and ground station sending artificial beacon signals to one another in order to establish a robust link. This means that all satellites must be equipped with dedicated architecture to produce beacon signals, which drives up SWaP. For deep space communications, it is common to instead rely on celestial bodies as natural beacons, eliminating the need for artificial beacons. This is difficult to do for regular Earth-orbiting satellites due to the rapidly shifting environment and the nature of parallax. It is, however, conceivable that we could use features of the lunar surface to act as beacons for lunar-based FSOC systems. This study would entail researching the current methods of establishing PAT for both static lunar modules (i.e. terminals and buildings) and moving lunar modules (i.e. lunar rovers and transport vessels).

There may be room to develop an adaptive optics system to work for this very purpose. This could include an experimental aspect of the study, in which the QOGS is used to prove the feasibility of using the lunar surface as a beacon. Furthermore, this study could be enhanced with AI-based convolutional neural networks which excel at feature recognition. The end goal of the study is to prove, experimentally, that it can be done. 

**Background Context**

- Lunar gateway would massively benefit from a FSOC module
- Gateway will also deploy rovers, transport vessels, etc.
- Static lunar FSOC terminals will eventually be established on the lunar surface
- Reducing SWaP for all of these components is critical
- The lunar surface is rich with optically identifiable and distinct features (mares, craters, etc.)
- It may be possible to forgo traditional powered, artificial beacons in lieu of using the lunar surface itself AS a beacon
- Unique challenges are introduced for tracking moving objects on the moon, such as lunar rovers (Cam suggests using RF to give a rough position before using natural surface feature beacons)
- Fuck it, in the long term just set up RF beacons in a network around the moon that can triangulate the position of a moving object, then just point the laser at it by using the natural surface beacon method
- It could be possible to use AI for surface feature identification, I should ask Dave what he reckons about that

**Key Skills**

- Operating the telescope to take direct observations of the moon
- Implementing convolutional neural networks (CNNs) for image processing
- Programming and implementing FPGAs

**Points to Clarify**

Will the phase of the moon affect observations? Were we to employ terrestrial telescopes to establish uplink, there may be significant amount of time where the moon's surface isn't receiving enough light from the sun, such as during a new moon. Furthermore, boundaries drawn by naturally waning / waxing crescents may interrupt surface feature identification and result in the inability to establish uplink with a terminal that is close to the boundary layer.

Is there going to be too much background noise in NIR wavelengths because the moon is gay?

**Jamie's Considerations**

Jamie thinks it may be possible to use the moon's surface features as beacons, but to his knowledge nobody has mapped the moon to a great enough extent that it would be a simple task. He showed me pictures that the Stromlo telescope has taken of the moon, of relatively high quality and detail.

It might be possible for me to use the telescope to create my own map if I really wanted. Perhaps I could focus on a small area, and see if there are enough distinct features to reliably identify a given position. This is where the AI Dave was using may come particularly in handy, due to its high performance in pattern recognition. The idea would be taking several images of the studied region(s) in different lighting conditions, time of day, moon phases, etc. and seeing if the AI can identify the region. I may be cooking.

**References**

- [[Kaushal Review]]
- 
