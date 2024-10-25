This document will outline a potential project which takes advantage of geostationary satellites to provide a relay system for lunar FSOC applications. This idea was suggested by Francis via email in October 2024, following his overseas conference trip.

"There is quite a bit of interest in lunar communications with optical at this conference, one thing we should definitely look at is how we could do this from a GEO satellite to enable data relay - for example from the Moon to a GEO then via EDRS to where it needs to get to. A couple of GEO would then mean you have continuous coverage of the Moon. It would be interesting if existing hardware could make this work e.g. the Tesat SCOT135."

**EDRS**

The European Data Relay System (EDRS) is a constellation of two satellites (EDRS-A and EDRS-C) which facilitates high speed laser communications through space. The EDRS was established by ESA in collaboration with Airbus Defence & Space, and has established over 75,000 satellite links during its operations since 2016.

The EDRS makes use of three ground stations; one in Germany, one in Belgium and one in the U.K. It is capable of ~2 gigabit speeds, and was designed to enhance the quality and transfer speeds of data in real-time scenarios, such as emergency workers who need access to high resolution satellite imagery instantaneously.

The EDRS itself does not make direct observations, but rather facilitates high speed data transfer between other satellites; most commonly those in LEO. Although most LEO satellites are only equipped with RF communication capabilities, the EDRS can dramatically reduce the delay in data transfer due to line-of-sight restrictions.

The laser terminals equipped on both EDRS payloads make it an obvious choice for handling FSOC lunar data transfer. There are a few things I need to confirm to determine whether the EDRS would be suitable for robust and reliable lunar data transfer, including:

- is the EDRS capable of establishing simultaneous links with several different satellites?
- can the EDRS be oriented to point toward the moon, or are its attitude control systems only configured to be Earth-facing?
- can the EDRS satellites actually receive optical uplink, or only RF uplink?
- are there any significant LoS issues associated with the moon's orbit?

There are a few ways we could implements the actual communications scheme, i.e.:

- Lunar terminal -> EDRS -> Earth
- Lunar terminal -> Dedicated GEO satellite -> EDRS -> Earth
- Lunar terminal -> EDRS-like dedicated constellation(?) -> Earth

**Tesat SCOT135**

![[Pasted image 20241023141332.png]]

![[Pasted image 20241023141345.png]]

https://www.tesat.de/images/tesat/products/240306_DataSheet_SCOT135_A4.pdf

The SCOT135 is an optical communication terminal (OCT) developed by German company Tesat. It is intended to be placed on satellites (usually GEO) to facilitate high-speed data transfer. The SCOT135 can transfer at a data rate up to 100Gbps at 30,000km, making it very desirable for a satellite handling multiple data channels.

My assumption would be that the SCOT135 would be placed on a satellite which acts as a relay for several other transmitters sending data from the moon. This would enable several gigabit-speed links to a single relay satellite, which could then beam all channels down to Earth.

If we incorporate a system which makes use of the EDRS as Francis suggested, there would certainly be a bottleneck, since the EDRS is only capable of ~1.8Gbps data transfer. 