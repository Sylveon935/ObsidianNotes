[Access the paper here](C:\ANU\Papers\FSOC\142.pdf) 

This JPL paper from 1999 discusses a baseline plan for a spacecraft designed to orbit Europa to collect data. It places a lot of focus on the data transmission methodology, suggesting a FSOC system to enable high speed data transfer. Here are some interesting implications found within the paper, and how they relate to the idea of a beaconless lunar terminal.

The paper suggests that an uplink beacon can be established in a number of ways:

- Using a powerful artificial beacon from Earth
- Using the sun-illuminated Earth itself as a beacon
- Using the moon or other bright stars as a beacon.

Two of these three suggested ideas implement a beacon-less approach from the ground station. Of course with an optical system, very precise PAT is required. However, due to the distance of a satellite which would orbit Europa, enough beam divergence occurs before the light arrives that Earth that it is viable to use the entire Earth itself as a beacon due to the large resulting spot size, and that's good enough. Obviously a much stronger communications laser would be required due to the divergence rate, and satellite vibrations and other disruptions would result in significant signal fade.

For a lunar-based FSOC system, using the entire Earth as a beacon isn't quite viable. A laser beamed from the moon would not diverge enough to result in a spot size big enough that precision can be reasonably neglected. This eliminated the possibility of using the Earth itself as a beacon. But then again, it's pretty easy to just make a high powered beacon from Earth and use that; I don't really see a reason not to.

To offset the fact that the desired 2kHz tracking rate does not seem possible using Europan geometry, the paper suggests that an inertia-based sensor could be employed. This doesn't seem very viable for a lunar terminal, since the inertia will remain relatively constant due to the moon's own inertial reference frame.

The paper never concludes with a solution to the PAT problem - it rather outlines a few methods of tracking and briefly discusses their associated pros and cons. The paper paints pretty broad strokes, but it's useful to think about some of these ideas nonetheless.



