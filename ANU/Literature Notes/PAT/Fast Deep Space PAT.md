[Access the article here](C:\ANU\Papers\Deep Space Beacon - Star Tracking\Quick acquisition and recognition method for the beacon in deep space optical communications.html)

This paper suggests a novel method of PAT for deep space FSOC systems without relying on traditional beacon methods.

The paper suggests that the two main ways the acquisition time for a traditional beacon system can be reduced is by selecting a narrowband filter, or increasing the beacon's power. Increasing beacon power can become problematic due to the inherently added architectural and thermal control requirements. Software-based solutions also struggle when dynamic noise within CCDs prevent traditional tracking methods such as frame substitution from being employed.

Ahh I'll talk about the maths when I can be fucked slogging through it.

The crux of the methodology is this - a satellite in deep space can establish an optical downlink with the Earth by taking a photo of it, then comparing that image to a reference image. Once it finds the Earth (which itself serves as a beacon due to beam divergence over deep space), the satellite can point its laser in the correct direction.

To test this, the authors simulated images that would be taken of the Earth from a deep space telescope in MATLAB. After cutting down the collecting image and honing in on the Earth, they were eventually able to locate the Earth in the collecting image. The following images show the process of refining the Earth image.

![[Pasted image 20241015122602.png]]

![[Pasted image 20241015122619.png]]
![[Pasted image 20241015122637.png]]
![[Pasted image 20241015122648.png]]
![[Pasted image 20241015122659.png]]

**Physical Implementation**

The hardware implementation of this process is facilitated using an FPGA system. The processing system of the FPGA (using several modules) can be seen below:

![[Pasted image 20241015134224.png]]

For information for the specific models and grades of hardware implemented, look below Figure 6 in the paper.

Below shows the original reference image (left) compared to the catching result of the hardware, after it has been put though the FPGA (right).

![[Pasted image 20241015134351.png]]

The result was an acquisition time of around 8 seconds. The experiment was repeated for suboptimal conditions such as lower Earth reflectivity and cloudy conditions, with similar acquisition times.

**Personal Analysis**

I think the paper has its merits, but is somewhat limited in its scope. Obviously the use of simulated images is suboptimal, but it's not exactly like we have a bounty of real images of Earth taken from this distance with the variety needed to perform a real experiment. I like the methodology, but it is also limited to downlink, with no real application processes for uplink.

There is definitely some scope that could allow uplink to be possible using this methodology. If a satellite is orbiting Jupiter, for instance, it could be possible to use Jupiter as the reference beacon, and offsetting the resulting uplink beam by a known angular and spatial displacement in accordance with the satellite's relative position to Jupiter. Whether this could be achieved at a sub-microradian level may not be likely.

Some of the methods used here could be useful for establishing uplink to a small object on the moon. The system has promise in its simplicity and acquisition times, and the moon has no lack of distinct features to support a similar surface map. The difference is that, whilst the deep space satellite only needs to use the Earth itself as a beacon, we would be looking for a needle in a haystack when trying to identify a rover, for instance. 