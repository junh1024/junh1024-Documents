# Home Theater 3D Audio Formats Myths

## Introduction

There are many misconceptions about Home Theater 3D Audio formats on the internet. Here should be some common ones, some strange ones I've encountered, and some personal esoteric ones. You may see vague or flamboyant language to describe or misrepresent systems, which I will not do. I also do not have any commercial interest in the below systems, so there is no loss to attempt to tell the truth. I do have some interest in my own 15.1 system, but that is open-source & available for free.

- UBD = 4K UltraHD Blu-ray
- ps = bits per second
- DDP = Dolby Digital Plus
- DDP Atmos = Dolby Digital Plus JOC (Atmos)
- THD = TrueHD
- DTS-HD = DTS High Definition
- DTS-X = DTS:X
- ELL = ear-level layer. I won't call this the bottom layer since NHK 22.2 has 3 layers, including a bottom layer.

## Formats
- THD Atmos extends THD 7.1 (cinema version 2012 with Brave, consumer version introduced 2014 with Transformers)
- DDP Atmos extends DDP 5.1
- DTS-X extends DTS-HD and is fully compatible. (consumer version introduced 2015)
- Auro-3D embeds height channels within PCM, in a compatible manner. (introduced 2010)

These are the 3 contenders for 3D sound in the Home Theater arena. They are compatible with previous BD formats. The main purpose of the new formats is to store height. A secondary purpose of some is to be scalable to high speaker counts in a bitrate-efficient way, wether through the authoring with objects in the codec, or decoder.

Consumer Atmos has a legacy core + extension structure, to maintain compatibility with legacy devices. If you have no Atmos decoder, you get the legacy 5.1/7.1 presentation. If you have a Atmos decoder, the legacy 5.1/7.1 presentation disappears & you get the 3D Atmos presentation after a reconstruction process of 12-16 objects. DTS-X with legacy DTS-HD & DTS core functions in a similar way. Cinema versions of these codecs have more objects, but for home, the objects are reduced to a more managable number.

Since Auro-3D is backwards compatible with PCM, it has a legacy 5.1/7.1 PCM stream for older devices, and the 3D presentation is stored in the lower 6-8 bits of 24bit PCM. A Auro-3D decoder uses the lower bits to create a 3D presentation.

## General

### Atmos & DTS-X is only supported on UBD
FALSE. Atmos is an extension to TrueHD. TrueHD, while supported by many AVRs, is an optional codec on BD so may create compatibility problems in rare cases. Also, some labels like Sony may reserve the 3D audio presentations for UBD. Combined, may support this myth.

- Hobbit is 7.1 on BD, Atmos on UBD.

### Auro-3D is not supported on UBD
FALSE. As Auro-3D is carried in PCM, it can be supported on UBD through TrueHD & DTS-HD MA, too.

### THD cannot do height
FALSE. Dolby Media Producer allows several height layouts for THD and DDP, some of which DTS-HD also allows. I haven't tested this.

### DTS-HD cannot do height
FALSE. DTS Master Audio Suite allows several height layouts. [See here](https://frequenz.blogspot.com/2010/04/dts-surround-speaker-layout.html) for all supported layouts. But some layouts may not be correctly supported by older AVRs. It may appear as DTS-X on newer AVRs, but support is still flaky. You may need to choose the exact speaker layout & enable Neural-X DSP.

![DTSMAS](https://live.staticflickr.com/2690/4495882941_f4df7fcde9.jpg)

### DVD and SACD cannot do height
TRUE, MOSTLY. While the formats and codecs themselves have no height mapping, you can repurpose C &/ LFE for height content in a compatible way. Some DVDA and SACD releases do this. MDG uses the 2+2+2 system for some of their SACDs.

### THD Atmos is always superior to DDP Atmos
FALSE. Although THD is obviously lossless unlike DDP, many titles may have more spatial resolution/objects on a DDP release for streaming. Since THD Atmos is 12-14 elements about 75% of the time, and DDP Atmos is almost always 16 elements, this means DDP Atmos typically has better spatial resolution than THD Atmos. Example for Furious 9 (2021):

BD THD Atmos:

```
Commercial name : Dolby TrueHD with Dolby Atmos
...
Number of dynamic objects : 11
Bed channel count : 1 channel
```

Streaming DDP Atmos:
```
Commercial name : Dolby Digital Plus with Dolby Atmos
Number of dynamic objects : 15
Bed channel count : 1 channel
```

### DTS-X is always lossless
FALSE. DTS-X is available in DTS-X MA lossless for BD, DTS-X HR lossy for BD, and DTS-X lossy for streaming.

### Auro-3D is superior to Atmos
FALSE, MOSTLY. I'll split this up into 3 myths.

### Auro-3D codec is superior to Atmos
FALSE. Auro-3D must be stored at a full 24b since that's where the data is (the lower bits). Atmos and DTS-X can operate at lower bitdepths so they can have potentially lower bitrates. It is sensitive to mishandling if it's in PCM/FLAC rather than THD/DTS-HD MA, so bitstream may not work if the PCM is tampered with (aka some scenarios with KODI).

### Auro-3D upmix is superior to Atmos
FALSE. It uses a combination of [panning & reverb](https://www.avsforum.com/threads/the-official-dolby-atmos-thread-home-theater-version.1574386/page-3150#post-61232027) to create height, and isn't very discrete.


### Auro-3D speaker layout is superior to Atmos
FALSE, MOSTLY. Many A3D titles use the 11.1/5.1.6 layout. Hence, many people with legacy 7.1 speakers will get no benefit from A3D, unlike Atmos and DTS-X which are typically 7.1, since A3D 5.1.6 downmixes to 5.1. Also, In A3D 5.1.6, there is reduced rear & rear height resolution due to only 2 back speakers for each level. The layout is also uneven. This leads to noticeably un-smooth pans at the top/back, especially with larger spaces. A few newer A3D titles use 13.1/7.1.6, which rectifies problems with legacy systems & ELL back, but not height back.

[See here for diagrams](https://imgur.com/a/FYhUz)

### Auro-3D in practice is superior to Atmos
DEPENDS. This boils down to your preference for speaker layout & acoustics. Dolby recommends if your ceiling is low, that upfiring speakers be used instead of in-ceiling ones to create a better impression of space. The overhead/VOG speaker is the marketing point for A3D so Auro recommends one anyway. Some people prefer it. Some people dislike it.

Atmos cinema installations typically place ELL speakers are too high (about 40*), which ruins the contrast between ELL & height. OTOH, A3D places emphasis on their 3-layered approach, and have ELL placed much closer where it should be (about 10*).

### X system is better than Y system
DEPENDS. They all have their flaws, some are more flawed than others. No system is more natural, realistic, or emotional than others. That's just marketing collateral. But there are technical differences, and personal tastes.

## Beds and Objects

### Atmos Masters supports 128 elements
TRUE. Atmos Masters supports up to 128 elements. A maximum of 7.1.2 bed & 118 (dynamic) objects (DCP/IAB spec). Film mixers need to carefully plan their object allocation. [Frozen 2 sound interview](https://www.asoundeffect.com/frozen-2-sound/) .

### Atmos HE supports 128 elements
FALSE. The consumer version of Atmos, Atmos HE (Home Entertainment), has reduced objects to fit within limited bitrate & processing contraints available on consumer media & hardware. Spatial coding is applied to the Atmos Master to reduce the elements to 12-16, which is then encoded to THD or DDP. Bitrates for THD Atmos are typically 3-7mps, while DDP Atmos is usually 640-768kps as of 2021. You could claim [Atmos Gaming](https://docs.microsoft.com/en-us/windows/win32/coreaudio/spatial-sound) supports 128 elements, but that is only in 1 scenario, and it's debatable whether that counts since it's successively downmixed & rendered for headphones.

### DTS-X system is superior to Atmos system
TRUE. DTS-X Masters still supports 128 elements, but has a more flexible bed layout, including native support for 7.1.4 beds. But this is less used in practice since the IAB spec doesn't support this.

### DTS-X HE is superior to Atmos HE
DEPENDS. While you would think 16 objects in Atmos Home vs 7.1.4 + 5 objects in DTS-X Home are equivalent, there is the difference between channels & static objects so imaging may be different. Also, DTS software isn't as smart as Atmos software which automatically does spatial coding to reduce objects. Instead, you must manually choose which objects to channelize and others to keep as objects. What usually happens in practice is studios just skip this process and channelize everything to 7.1.4. Except for select past releases like Well Go's, "Ip man 3". [Ref2](https://www.avsforum.com/threads/trinnov-altitude.1516103/page-147#post-51314001). Thus, you need to carefully reformat your project to make maximum use of 7.1.4 + 5 objects.

For 7.1.4 systems, mixes in either codec should sound similar. But for more speakers, since DTS-X is channel-based, it might be better since it can upmix missing speakers. But Atmos will probably leave them blank most of the time. Which is why many AVR owners with many speakers install additional AVRs to upmix more speakers rather than native Atmos rendering.

### Channels and objects are equivalent
FALSE. Objects can move, and channels can't. This is what makes an OBA system superior. Objects can also be rendered at different volumes to have the correct pan law regardless of speakers. Same can't be said of channels.

### Channels & static objects are equivalent
FALSE. Objects can be partially imaged between multiple speakers. But channels usually have a 1-1 mapping to a speaker (except for C & LFE). This might be a problem with DTS-X 7.1.4 & non-7.1.4 speaker layouts


### There is no point to objects
FALSE. It's closer to what mixers have, it saves bitrate, it scales to whatever setup you have (within limits), and less volume artefacts. If you had a 24.1.10 channel mix but downmix, it would use an absurd amount of bitrate, and you would get modulation artefacts & wrong volumes due to [pan law](https://en.wikipedia.org/wiki/Panning_\(audio\)) being applied to speakers you don't have, more frequently. This is still an issue with 7.1 > 5.1 downmix, but it's less frequent.

### The distinction between beds and objects will be carried over to the home
FALSE. Spatial coding for Atmos HE converts everything to objects.

### Beds array at home
FALSE. While beds array at the cinema (that is, the LS channel of a 7.1 bed will address all speakers of the LS array), Due to spatial coding for consumer codecs of DA, DA beds are converted to point objects and don't array at home and bed channels only address individual speakers even if there are multiple LS speakers (unless every LS speaker is connected to the same amp output).

### Using beds only is fine since most users won't have more than a 7.1.2 system anyway
FALSE. Due to the geometry & panning of beds, bed can only use half of the available area. Objects can use all of the area. The effect of objects can be heard on:

- 5.1 & 7.1 systems (due to downmixing)
- 7.1 wide & 9.1 2D systems
- 7.1.4, 7.1.6 systems
- 9.1.2, 9.1.4, 9.1.6 systems
- **Headphone users** (due to 7.1.4 rendering)
- or >90% users.

The only users which won't hear the effect of objects are users with exactly 5.1.2 & 7.1.2 systems, or <10% users.

If you fail to use objects, not only will your mix fail to scale beyond 7.1.2, it will also fail to scale down to 7.1 & 5.1 as a result. Height may be constrained to 1 narrow line since 1 pair of overheads doesn't cover the whole ceiling space.

### Beds can address all available speakers
FALSE. There are some speakers that aren't a part of any array group so can't be addressed with beds, like WL WR, CL CR, SCRNL SCRNR, BC. You must use objects to address them.

### Beds can address all available area
FALSE. 7.1.2 beds can only use half the available area since 2 top speakers only cover a tiny area at the top.


### It is hard to decide whether a track should be bed or object
FALSE. Bed tracks will be sent to the speakers and may be arrayed. Objects will be pinpoint. In general, If something moves, or is at height, it should be an object. Since a 7.1.2 bed can't reproduce all height positions, and can't address all speakers.

### Atmos soundtracks will sound the same on all 5.1 systems
FALSE. Speaker panning will change depending on how old your AVR is.

### Side speakers will image halfway back on a 5.1 AVR
FALSE. On older AVRs, it may image all the way back. On Atmos AVRs, it will image about 2/3s back.

### If you have a 5.1.2 system, but have an object at height front, it will phantom image between front & height side speakers
FALSE. It may play back using height speakers only (Atmos), or ELL (DTS-X).

### 5.1.2 systems can reproduce all circular pans.
FALSE. If there is a circular pan @ 100% height, it will get all downmixed into HSL & HSR, transforming a circular movement into a LR movement. The only way to avoid this is to pan at partial height so you get some height depth. Ironically, it will sound OK on 2D 5.1 & 7.1 systems.

### Channels are always at ear-level and objects can only be at the top
FALSE. Atmos Masters Base is 7.1.2, 2 side height. Objects can also be at ELL.

### It doesn't matter how many spatial coding elements a Home soundtrack uses
FALSE. If it is set to 12 (lowest), then the soundtrack will be limited to 7.1.4 occupancy on busy scenes due to hitting the element limit. Hence I recommend setting it to 16 (highest), to preserve the maximum amount of objects, and hence 9.1.6 occupancy in the worst-case. This is more of a problem for THD Atmos on BDs where the default is 12-14, rather than DDP Atmos where the default is 16. 

## Technical

### THD Atmos is always worth 24 bits
FALSE. Most Atmos releases use bit-reduction, likely to save bitrate. Decode a THD Atmos through eac3to, and it may show something like this:

	Original audio track, L+R+LFE+BL+BR+SL: constant bit depth of 20 bits.
	Original audio track, C+SR: constant bit depth of 21 bits.

There may be an option to turn it off in some Dolby software.

### DTS-X is always worth 24 bits
FALSE. Some releases with DTS-X uses all 24b, but others use preconditioning, which reduces the bits.

### The Dolby Atmos extension is just metadata
FALSE. In addition to metadata of the object positions, it's not possible to describe audio in detail, unless you store something approaching audio.

* For TrueHD Atmos, as it is lossless, the Atmos extension does actually contain audio, but it's obviously not usable by itself. You can check this yourself. Re-encode a THD Atmos track to just 7.1, and the size will shrink by about 25-50% depending on element count and activity.
* For DDP Atmos, the Atmos extension contains a frequency-based approximation of how to extract the objects from the DDP core (ETSI 103 420 specification "object carriage using E-AC3"). It takes up about half the bitrate (Dolby 2017 Melbourne AES conference p50).

### The Atmos used in games is the same as the Atmos used on BDs
FALSE. Atmos for games uses Atmos MAT. This is different to TrueHD. Through HDMI EDID, the device can find out the AVR supports Atmos. It can then skip the AC3 core & legacy 7.1 downmix, and transmit Atmos MAT. Since no legacy material is needed, this leaves space for more objects.

### DDP Atmos always has a legacy 7.1 presentation
FALSE. Sometimes you can get 7.1, but for streaming unfortunately, the legacy presentation is 5.1, 7.1 & above is locked to Atmos AVRs.

### Only the 7.1 or 5.1 bed will get played for legacy devices
FALSE. There is no more bed for home mixes due to spatial coding. Also, if this were true, the audio from the objects would be missing. This is not the case, so the 7.1/5.1 core for legacy devices is a downmix. Play some files like a 7.1.4 test tone to confirm this happens.

### You can convert THD Atmos to DDP Atmos without the master file and get the same result
FALSE. If you don't have the master file, any recording-to-DDPA conversion would be different since the recording would be to a fixed CBA layout, but the master could have moving objects.

### THD Atmos uses a different master to DDP Atmos
FALSE (I think). You can create both types from the same masters. There are 2 master file types, DAMF, and ADM. They should be equivalent. But for streaming, DDP may have a different dialnorm which tells the decoder to change the volume, which contributes to this perception.

### You can separate THD core using FFMPEG
TRUE, PROBABLY. FFMPEG has a bitstream filter to remove the Atmos data from THD.

### You can separate DDP core using FFMPEG
FALSE. FFMPEG does not have a bitstream filter to remove the Atmos data from has a bitstream filter as of 2020. The DDP bitstream filter is for removing the 7.1 part.

### DDP in mp4 doesn't work all the time
TRUE. Depending on how it was muxed, it might not be compliant, and may fall back to AC3 decoding or may not work depending on what devices expect. You could use mkv or m2ts containers instead.

### You can store Atmos in FLAC
FALSE. Atmos for consumers is generally 12-16 channels or objects, but the FLAC codec only supports 8 fixed channels, so there's a problem. If you're able to "successfully" store Atmos in FLAC, you're prolly storing the legacy 7.1 presentation of THD Atmos.

### The Home rendering is the same as cinema rendering
FALSE. Home rendering may have decorrelation pre-applied to the objects depending on how big they are, and may have surround audio lowered.

## For Consumers

### There is only 1 version of the Atmos HE and DTS-X HE decoders
FALSE. Most AVRs implement only basic decoders, but not one for complex speaker layouts. The DTS-X one is called DTS-X Pro.

### Objects will be very dynamic on movies
FALSE. Unlike this [object visualizer](https://www.youtube.com/watch?v=lfpncHDYM6I) demo, movies usually have static music & ambience beds. Combined with an object limit, typically, the movement at ELL will be very restricted, and you may get a bit of movement at height.

### More speakers = more need for precise placement
FALSE, MOSTLY. As long as you are putting in some effort into positioning, multiple speakers in other spots can compensate for 1 speaker in a disallowed spot. Obviously we are far from a situation where you can "place your speakers anywhere" and the system will compensate unless you have expensive Trinnov AVRs. You can do this with Ambisonics but it's tricky & has other flaws.

### Upfiring Atmos speakers do not work.
FALSE, MOSTLY. I tested this in person, and if you're at a distance, sound will appear to come from above. Some people even have fake-mos speakers, like, regular speakers angled upwards to achieve this effect. I haven't tested this.

### TV and Device Atmos speakers do not work.
MAYBE. From my limited testing, TV Atmos speakers have a much reduced perception of direction, side is lumped in with back, and seems to employ the out-of-phase trick for rear sounds. Needs more testing.

### Atmos soundbars do not work.
I haven't tested this. At least some soundbars have detachable rears, and even upfiring drivers. Like the Samsung HW-Q930

### There is no benefit to an Atmos soundtrack if you don't have height speakers.
DEPENDS. If you have a 5.1 system, prolly no. If you have 7.1 speakers, maybe. Many older 5.1 titles have been reissued with a THD Atmos track which has a 7.1 mix. Most of them AFAIK aren't upmixes. So you get slightly increased resolution.

Another benefit is [height virtualization](https://hometheaterreview.com/marantz-sr6014-92-channel-av-receiver-reviewed/) . Dolby and DTS have DSPs you can apply to 3D mixes to give a small height effect on a 2D system. It can be useful to people that can't install height speakers, or find physical height speakers distracting. But restrictions apply, such as not being able to apply DTS Virtual X to an Atmos soundtrack due to Dolby's AVR Mandate of 2018 which prohibits some cross-vendor DSP applications.

## Atmos decoder state of THD Atmos dramatically affects the sound field on a 7.1 system
FALSE, probably. According to my tests, there is little difference between the legacy 7.1 decode & a Atmos decode.

## Atmos decoder state of DDP Atmos dramatically affects the sound field on a 7.1 system
TRUE, probably. There are 2 differences:
1. improved imaging due to 7.1 vs 5.1
2. (reversal) of a 90* phase shift for surround channels.

### There is little difference in theory between Heights vs Tops with AVR setup on Atmos
FALSE. Although Dolby recommends you put height speakers halfway up the wall between ELL & the ceiling, height speakers are actually [at the very top front](https://www.youtube.com/watch?v=-2cD9CPLMyo) of Dolby coordinate system, and Tops are actually 25% way inwards. So there is a small difference. 11.1.8 have [both](https://www.dolby.com/siteassets/about/support/guide/setup-guides/11.1.8-mounted-overhead-speakers-setup-guide/sell-sheet-11.1.8-mounted2.pdf) heights and tops.

https://manuals.denon.com/AVRX8500H/NA/EN/DRDZSYpvilxnds.php

### There is little difference in practice between Heights vs Tops with AVR setup on Atmos
TRUE. With only a max 25% difference, you might be unlikely to notice a difference with 7.1.4h vs 7.1.4t. Tops will be imaged 25% inwards on a height layout, and heights will be mapped to tops on a tops layout.

### It doesn't matter whether I choose Heights vs Tops for a given codec
FALSE. You may have no height activity depending on setting.

- Atmos: either works
- Auro: Heights
- DTS-X: Tops (top is mapped to height, most soundtracks are encoded to 7.1.4 height)

### THD Atmos may be 7.1.2
TRUE. 7.1.2 is due to the heavy reliance on the 7.1.2 bed, which is the maximum Atmos bed config for PT & the renderer. There are upmixers which can upmix to 7.1.2, so it could be an upmix. Or, the mixer forgot to use (more) objects inadvertently (object mixing is additional clicks in PT & needs to be connected to the renderer), or deliberately (7.1.2 file import). This flaw is hard to hear, as you need >=6 non-arrayed top speakers.

### THD Atmos may be 7.1.4
TRUE. Some studios choose 12 objects for Atmos THD or use a fixed 7.1.4 render. Supposedly this is easier/faster for authoring software such as Scenarist Ateme Titan or Sony Blu-print since it doesn't need a 2nd pass for spatial coding. Another benefit is reduced bitrate.

### Disney uses 7.1.4

TRUE, somewhat.

- BD: In the past only 712 was possible, converted to 714 for authoring. Now, mixes are rendered to 714 for BD.
- Streaming: A object mix with 16 elements could be heard, since streaming platforms [typically require]() ADM.

https://www.avsforum.com/threads/the-official-dolby-atmos-thread-home-theater-version.1574386/post-61202305 712 in 714

3.5 spclu 14 oct 2020
3.4 new 714 mar 2020

+mulan sparechange

### It doesn't matter what software they use to mix 3D
FALSE (imo). I believe if it's easier to use height, it will be used more. Most Atmos panners are cube-based. So if you want to use height, it's a separate control on top of ELL movement. There is a dome panner in DTS-X (and other suites like mine, and OBA suites) which makes 3D panning as easy as 2D panning by using the center of the circle for height. There is a dome panner for Atmos, but it's intended for VR use. ED: As of 2020, there is the Atmos Music panner with 2D to 3D panning.

![PT Panner](https://2.bp.blogspot.com/-2uXixotqXes/WVGaUr-5J_I/AAAAAAAABo8/4zR1nXzuC8oK4GC5ryCvv5vdySLP93_yACLcBGAs/s1600/pro-tools-hd-12-atmos.jpg "pleb Atmos Panner")
![DTS-X Panner](http://kyleclapman.com/wp-content/uploads/2017/12/mda_creator-dome.png "DTS-X Panner master race")

### Studios don't care about 9.1.6 users
MAYBE. Mixing software such as PT & Nuendo use a square panner which has L & R in the top corner. If you wanted to have consistent content in the width speakers, you would need to increase the diffusion of objects from L&R, or move them a bit back. Many studios also have 7.1.4 systems.

### Atmos mixers are lazy and don't care about height
MAYBE. There are several parts to this:
1. Many mixers are just used to panning in 2D. You can still get a great 2D mix, many still are.
2. Differing speaker placements and appropriateness. The Middle layer may be at screen level where the action is so sometimes it's not appropriate to pan sound upwards, even though there's a lot of action.
3. Some people don't like aggressive Atmos mixes (these people do exist), leading to conservative mixes being most agreeable subset
4. Not enough stem separation, especially for older movies. Though you can still move the whole bed up. Some reviewers may even hear things others don't
5. Effort. It needs to be a team effort from the start of the movie to use Atmos effectively, not an afterthought on one dude. Also, some people think consumers won't listen in Atmos. The result is some bad mixes, at least in part. Like "The Lion King" (1994) " Scar's Be Prepared in chapter eight is a scene that seems like an ideal time for some spacial adds to the top that never really materialize with any overhead prominence" in a review from [blu-ray](https://www.blu-ray.com/movies/The-Lion-King-4K-Blu-ray/217393/#Review), or Back to the Future [others have claimed](https://www.avsforum.com/threads/back-to-the-future-ultra-hd-blu-ray-review.3170351/#post-60174382) . But [John Wick 2](https://www.youtube.com/watch?v=Nx4vve3UGUg) and [Mission Impossible, I assume fallout](https://www.youtube.com/watch?v=pOI0T15d4R) are apparently examples of good mixes.
6. Cinema mixing rooms have all speakers above you, so the presence or absence of height activity is harder to detect.

### You will get the same experience at the cinema regardless of system
FALSE. As most movies are now mixed in Atmos, others may be conversions. The Dolby Atmos Renderer was limited to 7.1.2 in the past so other presentations such as DTS-X, Auro-3D, and IMAX will be inferior conversions. As of V3.5, it can now output 7.1.4 (and a few others) so a bit better, but still not perfect.

### If it was Atmos at the cinema it will be Atmos at home
FALSE. See start of this document. Also, there could be a case where a film was Atmos at a German cinema, but on the home release, the English track gets Atmos, but the German track only gets 5.1 due to the label wanting less versions of discs & space issues fitting in many languages. Said film may have German Atmos on streaming (but in lossy).

### It is easy to set up a cinema for Atmos
FALSE. There are many requirements like where you need to aim speakers at, height of speakers, amount of speakers, zones, consistency, etc. But easier than Auro-3D since for the latter you need to rebuild.

### It is best to listen to soundtracks with the same upmix system as the encoder
#### For example, DD soundtracks with DSU, and DTS soundtracks with DTS-X
FALSE. You can listen to any soundtrack with any upmixer. Some people prefer DSU, while others prefer Neural-X. Unless you have a AVR which has restrictions due to Dolby's AVR mandate of 2018, in which case you are restricted to vendor-only upmixing.

### 5.1.2 rear height is a valid setup and sounds fine
FALSE, at least on Denon AVRs. This setup is [not available](https://manuals.denon.com/AVRX2700H/NA/EN/DRDZSYpvilxnds.php) . Also, it will sound bad since many sounds will be above & behind you, not above or above front.


### Home theatre speaker locations are a subset of cinema speaker locations
FALSE. The Back Center speaker is unique to the Home layout.

## For Creators

### You need expensive hardware and Pro Tools to mix in Atmos
FALSE. The RMU is expensive, but the "Dolby Atmos Renderer" for mac is $300, and coupled with the free Atmos Music Panner, you can mix in Atmos in almost any DAW. DAR can encode to DDP in mp4.

### You need to use a Mac to mix in Atmos
FALSE. Atmos features are available in DaVinci Resolve studio, Cubase/Nuendo, Studio One, although Cubendo would be the one which is most music-oriented and has the most routing features.

### You need expensive software to encode Atmos
FALSE. Atmos encoding is available in cloud services such as Amazon.

### You need expensive hardware to encode DTS-X
FALSE. DTS has said that DTS-X is a purely software solution (but may need routing hax in PT). The DTS-X creator suite is a few $K, but the encoder suite is cheaper.

### You need expensive hardware to encode Auro-3D
FALSE. Again, Auro-3D is a software solution, but the software is still expensive.

### You must have object input to encode Atmos
FALSE. Some encoders allow 9.1.6 input. But that's about it. If you want other layouts, you must make static objects, or pad to 9.1.6.

### You must have object input to encode DTS-X
FALSE. DTS-X Encoder Suite is more flexible, and allows 5.1.2 up to 7.1.4 input for DTS-X, including weirdo layouts like 7.1.3. For more channels, you need to use objects or the DAW panner.

### You must use Dolby, DTS, or Auro-3D tools to mix for those formats.
FALSE. You can mix in other channel-based 3D surround formats using any tools. Such as [my Reaper-Surround suite](https://github.com/junh1024/Reaper-Surround#introduction), spatial PCM, or even ambisonics (but this is dispreferred). But you must use their encoder to ensure bitstream compliance.

### You can't convert between Atmos, DTS-X, and Auro-3D
FALSE.
- If you start with Atmos, you can export 7.1.4/9.1.6, setup a new project, and pan objects/channels in the appropriate positions.
- If you start with DTS-X, you can export 7.1.4 and do similar. If you only have an encoded bitstream, you can use DTS-X Bitstream tools to decode DTS-X to WAVs.
- If you start with Auro-3D, you can use channel exports. If you're using Nuendo, maybe you can convert Auro-3D panners to Atmos panners. If you only have an encoded bitstream, you can use the Auro-3D decoder in their suite.
- I haven't tested any of these.




### There is no way to avoid undesirable downmix behavior
FALSE. You can:
1. Adapt your mixing strategy (works across all DAWs)
2. Use zone masking
3. Change the downmix mode and trims

### I can use ADM from 3D OBA suite(s) with Dolby encoders
FALSE. Although this is the ideal situation, and the Dolby Atmos Conversion Tool can convert between DAMF and ADM formats, Dolby tools currently only accept ADM WAV files made by Dolby tools. This is due to cubular vs spherical coordinates, among other possible differences. So if you use other OBA suites such as [VISR](http://www.s3a-spatialaudio.org/plugins) or [EBU EAR](https://ear-production-suite.ebu.io/) suites and want to deliver for Dolby codecs, you're in for a bad time(tm). Unless you mix in CBA (which is what many people are doing anyway, including myself).

### I can use Dolby ADM with other suites
TURE. The EBU EAR suite (REAPER import) and Fraunhofer MPEG-H suite (converter) accept Dolby ADM.

### I can change the downmix trims of a Dolby ADM file using the Dolby Renderer
FALSE. You must [convert the file to DAMF](https://professionalsupport.dolby.com/s/article/Why-can-t-I-unlock-a-master-file-for-punch-ins-and-metadata-edits?language=en_US) using the Dolby Atmos Conversion Tool before the downmix trims are unlocked in the Dolby Renderer.

### It's hard to convert a legacy 5.1 project to an Atmos project
FALSE, MAYBE. In PT & Nuendo, maybe you can convert legacy projects to Atmos projects using scripts. PT 12.8 has a helpful "Auto-Height Overrides Height Automation" which generates height changes with existing 2D automation. Or you can export 5.1 stems and start a new project. I haven't tested any of these.

### It's hard to have consistent height content
FALSE. [Boom library](https://www.boomlibrary.com/shop/?swoof=1&pa_producttype=3d-surround) have released a few 3D surround libraries with room tones & weather FX recorded with a 8.0 mic array, which you can then expand to 7.1.4 or 9.1.4 using Penteo16.

### I can pan objects anywhere, and it won't matter
FALSE. It's advised to pan around the edges (like conventional surround) to sound stable. If you pan to the middle, in addition to sounding unstable, objects may be lower quality for streaming, since the Atmos reconstruction process needs to work harder to reconstruct those objects for playback. 

### I can make my Atmos mix as loud as I want with no consequence
FALSE. There is a [limiter](https://professionalsupport.dolby.com/s/question/0D54u000081G7hnCAC/soft-clip-limiter) on playback set before 0dB. Also, peaks will be increased slightly due to the lossy nature of DDP Atmos (as with most lossy codecs) so it's advised not to mix too loudly to avoid clipping. The Dolby Atmos Music Specification mandates -18 LUFS for music delivery (which means clipping rarely happens), and for TV & Film, there are usually targets of around -24 to -27 LUFS.

### A higher DDP Atmos bitrate always means higher audio quality
FALSE. DDP Atmos has technical & design limitations. There is a limit to the amount of frequency bands available for the Atmos reconstruction process. The number is chosen based on content & available bitrate. When it is hit, you will hear little improvement in audio quality if the bitrate is increased, even though there may still be audible artefacts. You will only get an improvement if you use a newer codec Dolby AC4 or MPEG-H (but those aren't mainstream yet). For most content, 640kps is quite sufficient. For simple content, maybe 448kps is enough. Please see the ETSI specification for more details.

### It's expensive to deliver Atmos content for cinema for independent creators
FALSE, probably. You can:
1. Convert your master with the Atmos Conversion Tool to IMF IAB, then use free software such as OpenDCP to make a package
2. Bring along a HDMI device which plugs into the projector. Cinema Atmos hardware can play back consumer formats such as DDP. NB: DDP has reduced objects.

I have tested neither workflow. Depending on budget or other factors, you may need to monitor on a Atmos-certified facility &/ use more standard workflows.

### DDP Atmos is the best way to deliver Atmos for cinema
FALSE. While it is efficient, you lose directionality since it's arrayed to 7.1.2. A regular DCP workflow would be better.

### DAMF, ADM, and IMF IAB are the same quality
FALSE, IMF IAB is reduced quality since the automation is quantized, and so IMF IAB (MXF) to ADM conversions should be avoided. 

"IMF IAB positional metadata is quantized to eight events per frame, an IMF IAB is considered a mezzanine rather than a master... it may be desirable to convert from the original master file rather than from the IMF IAB mezzanine" - Dolby Atmos Conversion Tool manual.

### If I create in Dolby Atmos, I need to render a 7.1.4 and use the DTS-X creative suite to create a specific DTS-X mix for DTS-X theaters 
FALSE. If you have produced IMF IAB, that is not Atmos-specific and will play back in DTS-X theaters fine.

### Dolby charges license fees per title

FALSE. "We have never charged content fees for our licensed technologies..." [ref](https://dolbyac4.com/uk/cost.php)

### DTS charges license fees per title
???

### Auro-3D charges license fees per title

Auro-3D charges an annual codec license. [ref.](https://www.auro-3d.com/buy/)

Special thanks to the individuals that have contributed to my understanding.

Date: Dec 2020 - Dec 2021 

BIN uses 7.1.4 https://professionalsupport.dolby.com/s/question/0D54u000081EnDzCAK/trim-and-downmix-controls?language=en_US

T: DDP compresion loud
TRUE

CR: As loud as I want OJK

FALSE . LUFS -18 integrated.	

I have done tests, and DDP comes out as a bit less dynamic on very loud sounds vs THD Atmos, otherwise very close.


https://professionalsupport.dolby.com/s/question/0D54u000081G7hnCAC/soft-clip-limiter?language=en_US


### Any Dolby Atmos will work for Dolby Atmos Headphone for Windows.
FALSE. It must be DDP Atmos. THD Atmos will not work and you may get the 5.1 core only. 

### Headphone Atmos is superior to speaker Atmos since the full vertical axis is virtualized on headphones.
FALSE. Dolby Atmos Headphone is decoded to 7.1.4 so still only half vertical axis. But there may be other implementations for Spatial audio that can virtualize a full height axis.

### Any app will work with Dolby Atmos Headphone. 
FALSE. windows spatial audio is restricted to Media Foundation or spatial aware apps. If it was available to any app, apps which already virtualize audio, will be double-virtualized, sounding very bad. Hence this is disallowed with requiring specific use of the API. Examples:
- Film & TV
- Netflix
- VLC from Microsoft Store
- Windows Media Player

### I need to pay for Dolby Access to enable Dolby Atmos Headphone
TRUE. You need to pay to enable it (after the end of the free trial). But there is Windows sonic which is free.

### I need to pay for Dolby Access to enable Dolby Atmos for Home Theater
FALSE. Bitstreaming Atmos to your AVR is always free.

### Every Dolby Atmos game will support Atmos on both Xbox & PC
FALSE. Platform support varies per title. Please check the list at https://www.avsforum.com/threads/dolby-atmos-for-gaming-thread.2941270/ 


### THD Atmos is always bigger than 7.1
FALSE. Dolby authoring apps typically use bit-reduction to save space. In many cases it can be smaller than 7.1 48/24.


### Dolby Atmos releases are deliberately lower volume and lacking bass compared to 5.1 releases
- Low volume: with 51, you can adjust the volume at the master and apply DRC to smash the levels up. With Dolby Atmos, you can't do this since the master is object. Loudness needs to be at the source, or you need to insert a FX on every object to bring the volume up ( cumbersome) 
- Low bass. With 51 & historical practice, i suspect studios didn't apply bass management properly, LFE is sent directly to the sub (wrong), AVR applies a 10dB gain, and consumers turn down the sub to compensate. With DA, DAR apparently applies BMS +10 LFE, so the LFE monitoring levels should be correct. Consumers who had set the sub lower for 51, would notice in DA the bass is too low. 

So conclusion, what had been done with 51 in the past was (probably) incorrect with too high bass levels, with DA it should now be correct. See <https://en.wikipedia.org/wiki/Bass_management> for more details about 10dB.

### DDPA artefacts at height

## Dolby Atmos for Home Theater supports unlimited speakers anywhere
FALSE. DA HT supports a maximum of 35 speakers in a 24.1.10 layout, arranged in 2 layers. Here are the positions (not in order):


- Front: L R C, Lscr Rscr, Lc Rc, Sub
- Side: Lw Rw, Ls Ls1 Ls2, Rs Rs1 Rs2, Lrs2 Rrs2
- Back: Lrs Lrs1, Rrs1 Rrs, Lcs Rcs Cs
- Top : Lfh Ltf Ltm Ltr Lrh, Rfh Rtf Rtm Rtr Rrh

## DTSX supports unlimited speakers anywhere.
FALSE. DTSX HT supports a maximum of 32 speakers in a 30.2 layout, arranged in 5 layers like a dome. Here are the positions:

- Front: L R C, Lc Rc, Sub1 Sub2
- Side: Lw Rw, Lss Rss, Ls Rs
- Back: Lsr Rsr, Cs
- Height: Lh Rh Ch Lhs Rhs Lhr Rhr Chr
- Top: Ltf Rtf Ltr Rtr, Oh
- Bottom: Lb Rb Cb


References: [Trinnov Speaker Layout Guide](https://www.trinnov.com/en/blog/posts/trinnov-speaker-layout-guide/) , [DA HT Installation guide](https://www.dolby.com/siteassets/technologies/dolby-atmos/atmos-installation-guidelines-121318_r3.1.pdf) ,  [DA HT studio guide](https://dolby.my.salesforce.com/sfc/p/#700000009YuG/a/4u000000lFHc/UYA0IZeD632SUXVmEPmUcr.wIuhpHp6Q7bVSl4LrbUQ) 

Music Specs
https://dolby.my.salesforce.com/sfc/p/#700000009YuG/a/4u000000lFJ9/IVkxI54tPvDbGymtjQ6tyIjEvkaA7xPa_Byq6.vH_dA

### All consumer Dolby Atmos content will fill up my 9.1.6 system
False. There are a range of factors which contribute to poor speaker occupancy.
1. The average movie in DA does not have much height activity, and about half of mixers don't know to use (enough) objects
2. THDA authoring has a default of 12 elements, so when there's too many objects, spatial coding will downmix to about 7.1.4 
3. Many Studios are monitoring on only 7.1.4, so speaker occupancy beyond that isn't something they typically test


### Dolby Atmos mastering is the same as traditional mastering in that you need to push up loudness levels to remain competitive
FALSE. Although there are software like Hornet SAMP which can emulate master bus processing, Dolby Atmos music specifications mandate a -18LUFS target, so there isn't a need to heavily compress your master to meet traditional loudness wars targets like -9 LUFS. You could achieve this just by adjusting track gains.

### 5.1.2 and 7.1.2 are good monitoring layout for mixing Dolby Atmos
FALSE. Height in 5.1.2/7.1.2 is just a straight line of speakers, and the way DA height is downmixed to 2 speakers is a summation-type downmix. So you can't monitor the whole height geometry. It may leade you to make bad mixes since depth panning at the top has no effect, but there are very real consequences for people with lesser and more speaker layouts, as it results in increased correlation and precedence effects. In a sense, it's a downgrade from 5.1. Which is why Dolby recommends a minimuim of 5.1.4 for mixing in DA, and subjective feedback from Home Theater owners is that 5.1.4 is 2x as good as 7.1.2.


### It's not possible to  achieve a good speakers and headphones mix
FALSE.

img: https://ent.box.com/representation/file_version_798342603666/thumb_1024.jpg?shared_name=oxnoownji36b37aa9u0q1a4vx64tlken
via learning material: http://web.archive.org/web/20210729211208/https://learning.dolby.com/hc/en-us/articles/360055055311-Appendix-A-Dolby-Atmos-Delivery-Codecs 

### The defaults for DDP encoding are fine
DEPENDS. They're more movie-oriented and would work okay for music up mixes but if you wanted to preserve the levels or have more control than you'd want to set them yourself. 

### The defaults for THDA encoding are fine
DEPENDS. The default spatial elements is 12 (lower than DDPA) so if you don't exceed that it's fine. Otherwise, you'd want to set it higher.

### The Legacy trims don't matter
FALSE. Playing back on a legacy device, both Atmos and legacy may trims apply, since the DA to 5.1 trim is used to generate the legacy 5.1 core. Thereafter, the legacy trims apply. So on a legacy device, you may get double attenuation as both DA to 5.1, and legacy 5.1 to 2.0 trims may apply. Some software may ignore legacy trims and apply a -3dB surround trim for the legacy 5.1, so it's important to account for all situations and set both sets of trims appropriately.

### The Dolby Atmos Renderer is better than a DAW internal renderer
Depends. Its a matter of workflow preferences. Internal offers a more seamless workflow. The DAR supports higher speaker layouts and array mode for theatrical applications. And DDPA MP4 encoding. You can use the DAR if you like, but some users have experienced LTC sync dropouts.

### The Dolby Atmos Renderer sounds more accurate than a DAW internal renderer since it's by Dolby
FALSE. DA DAWs typically licence renderer SDK code from Dolby for their Dolby Atmos implementation so they sound the same. It's just that the UI looks different.

The Dolby Atmos renderer is a licensed technology which includes the Binaural renderer, with its signature sound. If DAWs made their own implementation of DA, their binaural renderer would sound different due to different using different IRs. For example, Noisemakers Binauralizer uses measurements from the Neumann KU100, which sounds very different to DA BRM. But instead, regardless of which DA DAW you use, most of them sound the same, including in bunaural, because they use the same DA SDK from Dolby.

The UIs look different due to technical reasons. If the Dolby renderer SDK provided full UI code, it's unlikely to be useful for technical reasons. Every DAW uses their own frameworks and libraries to draw the UI, so if Dolby provided full UI code, it would be incompatible. For example, Dolby may use JUCE, but the DAW may use WDL. Also, even if these technical issues were overcome, having a Dolby-provided UI would look inconsistent with the rest of the DAW.

In conclusion, most Dolby Atmos DAWs use Dolby renderer SDK code for the renderer, so sound the same. It just looks different for technical & internal consistency reasons.

### CBA mixes are better since spatial coding isn't used
FALSE

https://professionalsupport.dolby.com/s/question/0D54u00009YkmRBCAZ/bypass-spatial-coding?language=en_US

### The bed positioning will not change depending on down mix mode.
FALSE. Although the surrounds and 71 will always be summed together for 5.1 regardless of downmix mode, the positioning of the top side channels in 7.1.2 may change. So you get either precedence effects, or overloading the surrounds. This is why one should avoid a 7.1.2 bed and use either 7.1 or 7.1.4.

### It's possible to upmix 5.1 to 7.1.2 and have a downmix that adds unity
TRUE. However, this is only in theory and I don't know any software that exists that implements this. Upmixers typically mix front & rear content into the top side channels, (AKA summing to mono depth) and this can't be reversed. Which is why again, one should use either 7.1 or 7.1.4 beds if you care about quality.

### 5.1 downmix mode only affects 5.1
FALSE. 5.1 downmix mode also affects 5.1.2 and 5.1.4


https://rantingsofamadaudiophile.wordpress.com/2017/05/20/dtsx-vs-dolby-atmos-part-ii-dolby-surround-vs-dts-neuralx/ 