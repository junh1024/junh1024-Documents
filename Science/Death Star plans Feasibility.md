# Death Star plans Feasibility

Introduction
---
So in Rogue One, Jyn steals the Death Star plans, broadcasts them to a ship, then it's transferred to a memory card. There are a few reasons why I think it's quite unfeasible, unless there are some changes.

Amount
---
We are led to believe that the thing that Jyn steals contains the development archive for something Gaelen Erso worked on for "so much" of his life. So we assume at least 20-ish years of engineering work, I'll make up a number, 2TB. It might be bigger than this, but i'll use this number.

Medium
---
The movie says it's a tape, but Jyn steals something that looks like a hard disk, but then it's broadcast to a ship (we assume it's (partially) buffered in RAM), then copied to something that looks like a giant [smartmedia](https://en.wikipedia.org/wiki/SmartMedia) card (only cuz it has the biggest gold contacts, and the card in the movie looks quite gold). Can these media store 2TB? Yes, with conditions.

- Tape: 3TB (compressed) [in 2010](https://en.wikipedia.org/wiki/Linear_Tape-Open#Generations) , or more now.
- Hard Disk: 2TB drives became common in 2010s
- RAM: supercomputers might have 2TB of RAM in 2010s, but it's certainly not common at home, and I wouldn't expect spaceship main computers to have >128GB RAM
- SmartMedia card: while it flopped & stored nowhere near 2TB, 2TB SSDs were available 2015-ish. They're both flash memory.

Broadcast
---
While the above media can store 2TB, it's quite unbelievable to have them read, and then broadcast 2TB in a few seconds. The console shows 4 progress meters. The full spectrum can't be used, because there must be frequencies reserved for other things, like ground to ship communications. So let's take an example that we have now, digital OTA TV. The bandwidth of a station (not channel), might be 50Mbps. , or 6MBps.

"But the future will have better technologies!!!"

Yes, but you can't get around the laws of physics. If you increase the frequency, the data rate can increase, but the range will decrease. You can increase the power to compensate, but there might be health or interference effects. Broadcasting technology hasn't really made big strides recently, but reception technology (especially for weak signals) has improved due to building bigger & more antennas, and better computers to analyse the data. Read about it on the [Event Horizon Telescope website](https://eventhorizontelescope.org) 

Note on data reduction. Given a 3D model, you can reduce the data size requirements, by reducing the level of detail (LOD). But you need to be careful. Like, if you have a 160km Death Star, but you sample it at 10m, a cruicial 2m [thermal ventilation shaft](https://starwars.fandom.com/wiki/Thermal_exhaust_port) might disappear. Also, it depends on how detailed it is. Having lots of blank space isn't necessarily helpful for data reduction, cuz the blank space that's DS-2 is quite detailed.

I am fairly certain that the data that was actually broadcast is in the 20-200MB range. This makes everything so much more feasible. After all, you need to copy the data very quickly, when Darth Vader is coming.

I believe what's broadcast was only that size, or only what was needed. You could think of other ways of storing more, but broadcasting less, like the broadcasting only some thing(s), but if you put the HD in a proper reader you can see all the files, but I don't think the production particularly cared about this aspect of feasibility.