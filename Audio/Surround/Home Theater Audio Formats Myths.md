# Home Theater Audio Formats Myths

## Introduction

There are many misconceptions about Home Theater 3D Audio formats on the internet. Here should be some common basic ones, some strange ones I've encountered, and some personal esoteric ones. You may see vague or flamboyant language to describe or misrepresent systems, which I will not do. I also do not have any commercial interest in the below systems, so there is no loss to attempt to tell the truth. I do have some interest in my own 15.1 system, but that is open-source & available for free.

- UBD = 4K UltraHD Blu-ray
- ps = bits per second
- EC3 = Dolby Digital Plus
- EC3 Atmos = Dolby Digital Plus JOC (Atmos)
- THD = TrueHD
- DTS-HD = DTS High Definition
- DTS-X = DTS:X
- ELL = ear-level layer. I won't call this the bottom layer since NHK 22.2 has 3 layers, including a bottom layer.

## Formats
- THD Atmos extendeds THD (consumer version introduced 2014)
- DTS-X extendeds DTS-HD and is fully compatible. (consumer version introduced 2015)
- Auro-3D embeds height channels within PCM, in a compatible manner. (introduced 2010)

These are the 3 contenders for 3D sound in the Home Theater arena. They are compatible with previous BD formats. The main purpose of the new formats is to store height. A secondary purpose of some is to be scalable to high speaker counts in a bitrate-efficient way, wether through the codec, or decoder.

## General

### Atmos & DTS-X is only supported on UBD
FALSE. Atmos is an extension to TrueHD. TrueHD, while supported by many AVRs, is an optional codec on BD so may create compatibility problems in rare cases. Also, some labels like sony may reserve the 3D audio presentations for UBD. Combined, may support this myth.

- Hobbit is 7.1 on BD, Atmos on UBD.

### Auro-3D is not supported on UBD
FALSE. As Auro-3D is carried in PCM, it can be supported on UBD through TrueHD & DTS-HD MA, too.

### THD cannot do height
FALSE. Dolby Media Producer allows several height layouts for THD and DDP/EC3, some of which DTS-HD also allows. I haven't tested this.

### DTS-HD cannot do height
FALSE. DTS Master Audio Suite allows several height layouts.  [See here](https://frequenz.blogspot.com/2010/04/dts-surround-speaker-layout.html) for all supported layouts. But some layouts may not be correctly supported by older AVRs. It may appear as DTS-X on newer AVRs, but support is still flaky. You may need to choose the exact speaker layout & enable Neural-X DSP.

![DTSMAS](https://live.staticflickr.com/2690/4495882941_f4df7fcde9.jpg)

### DVD and SACD cannot do height
TRUE, MOSTLY. While the formats and codecs themselves have no height mapping, you can repurpose C &/ LFE for height content in a compatible way. Some DVDA and SACD releases do this. MDG uses the 2+2+2 system for some of their SACDs.

### THD Atmos is superior to EC3 Atmos
DEPENDS. Although THD is obviously lossless unlike EC3, some titles may have more spatial resolution/objects on a EC3 release.

### DTS-X is always lossless
FALSE. DTS-X is available in DTS-X MA (lossless) and DTS-X lossy.

### Auro-3D is superior to Atmos
FALSE, MOSTLY. I'll split this up into 3 myths.

### Auro-3D codec is superior to Atmos
FALSE. Auro-3D must be stored at a full 24b since that's where the data is (the lower bits). Atmos and DTS-X can operate at lower bitdepths so they can have potentially lower bitrates. It is sensitive to mishandling if it's in PCM/FLAC rather than THD/DTS-HD MA, so bitstream may not work if the PCM is tampered with (aka some scenarios with KODI).

### Auro-3D speaker layout is superior to Atmos
FALSE, MOSTLY. Many A3D titles use the 11.1/5.1.6 layout. Hence Many people with legacy 7.1 speakers will get no benefit from A3D, unlike Atmos and DTS-X which are typically 7.1, since A3D 5.1.6 downmixes to 5.1. Also, In A3D 5.1.6, there is reduced rear & rear height resolution due to only 2 back speakers for each level. The layout is also uneven. This leads to noticeably un-smooth pans at the top/back, especially with larger spaces. A few newer A3D titles use 13.1/7.1.6, which rectifies problems with legacy systems & ELL back, but not height back.

[See here for diagrams](https://imgur.com/a/FYhUz)

### Auro-3D in practice is superior to Atmos
DEPENDS. This boils down to your preference for speaker layout & acoustics. Dolby recommends if your ceiling is low, that upfiring speakers be used instead of in-ceiling ones to create a better impression of space. The overhead/VOG speaker is the marketing point for A3D so Auro recommends one anyway. Some people prefer it. Some people dislike it.

### X system is better than Y system
DEPENDS. They all have their flaws, some are more flawed than others. No system is more natural, realistic, or emotional than others. That's just marketing collateral. But there are technical differences, and personal tastes.

## Objects

### Atmos has 128 objects
MAYBE. Atmos for Cinema, hereon called Atmos FC, supports up to 128 objects. Since the bed is usually 7.1.2, this leaves 118 (dynamic) objects in practice. Film mixers need to carefully plan their object allocation. [Frozen 2 sound interview](https://www.asoundeffect.com/frozen-2-sound/) . Atmos Home has less objects.

### Atmos FC is the same as Atmos Home
FALSE. The consumer version of Atmos hereon called Atmos Home, has reduced objects for bitrate purposes. If all 128 objects were active, and simply ported to a consumer UBD, that might mean 50mps of audio, which would lead to reduced video bitrate & quality to fit within UBD limits. Hence, objects are reduced for Atmos Home. Bitrates for THD Atmos are typically 3-7mps.

### DTS-X FC is superior to Atmos FC
MAYBE. DTS-X FC still supports 128 objects, but may have a more flexible base layout.

### DTS-X Home is superior to Atmos Home
DEPENDS. While you would think 16 objects in Atmos Home vs 7.1.4 + 5 objects in DTS-X Home are equivalent, there is the difference between channels & static objects so imaging may be different. Also, DTS software isn't as smart as Atmos software which automatically does spatial coding to reduce objects. Instead, you must manually choose which objects to channelize and others to keep as objects. What happens in practice is studios just skip this process and channelize everything. Except for a few small studios like Well Go on say, "Ip man 3". [Ref2](https://www.avsforum.com/threads/trinnov-altitude.1516103/page-147#post-51314001). For 7.1.4, mixes in either system should sound similar. But for more speakers, since DTS-X is channel-based, it might be better since it can upmix missing speakers. But Atmos will probably leave them blank most of the time. Which is why many AVR owners with many speakers install additional AVRs to upmix more speakers rather than native Atmos rendering.

### THD Atmos on BD has up to 24 objects

FALSE. Since Atmos is an extension to THD, you might look up "extension" in the dictionary and conclude addition, and consequently add 7.1 & 16 = 24. Let's review what we know:
- The legacy 7.1 THD presentation is a complete presentation, downmix of height & ELL, with no missing audio
- Legacy AVRs cannot decode objects
- Objects (can) have additional audio

If you add the object audio to the 7.1 audio, that would result in an over-complete presentation and would violate #1. Subsequently, the only way to not violate this is if the object count includes 7.1 ELL as well as height. So an max object count of 16 is correct. See also the myth about games. Also, the objects are encoded as a differential to the 7.1 mix to save bitrate.

### Channels and objects are equivalent
FALSE. Objects can move, and channels can't. This is what makes an OBA system superior. Objects can also be rendered at different volumes to have the correct pan law regardless of speakers. Same can't be said of channels.

### Channels & static objects are equivalent
FALSE. Objects can be partially imaged between multiple speakers. But channels must have a 1-1 mapping to a speaker (except for C & LFE). This might be a problem with DTS-X 7.1.4 & non-7.1.4 speaker layouts

### If you have a 5.1.2 system, but have an object at height front, it will phantom image between front & height side speakers
FALSE. It may play back using height speakers only.

### Channels are always at ear-level and objects can only be at the top
FALSE. Atmos FC Base is 7.1.2, 2 side height. Objects can also be at ELL.

### You can hear the difference between channels and objects
FALSE, MOSTLY. Height of objects are not predictable as above. Also, spatial coding for Atmos Home converts everything to objects. But the objects don't move much.

### Objects will be very dynamic on movies
FALSE. Unlike this [object visualizer](https://www.youtube.com/watch?v=lfpncHDYM6I) demo, movies usually have static music & ambience beds. Combined with an object limit, typically, the movement at ELL will be very restricted, and you may get a bit of movement at height.

### There is no point to objects
FALSE. It's closer to what mixers have, it saves bitrate, it scales to whatever setup you have (within limits), and less volume artefacts. If you had a 24.1.10 channel mix but downmix, it would use an absurd amount of bitrate, and you would get modulation artefacts & wrong volumes due to [pan law](https://en.wikipedia.org/wiki/Panning_\(audio\)) being applied to speakers you don't have, more frequently. This is still an issue with 7.1 > 5.1 downmix, but it's less frequent.

## Technical

### THD Atmos can be worth 24 bits
FALSE, PROBABLY. THD is 24b, but the number of active bits is usually lower, and there's no option to turn off bit-reduction. Likely to save bitrate. Decode a THD Atmos through eac3to, and it may show something like this:

	Original audio track, L+R+LFE+BL+BR+SL: constant bit depth of 20 bits.
	Original audio track, C+SR: constant bit depth of 21 bits.

### DTS-X can be worth 24 bits
TRUE, PROBABLY. DTS-X Encoder Suite has a preconditioning option, which is off by default. Which gets you call 24b. High preconditioning probably reduces the bits, probably down to 18b.

### The Atmos used in games is the same as the Atmos used on BDs
FALSE. Atmos for games uses Atmos MAT. This is different to TrueHD. Through HDMI probing (what's the proper name?), the device can find out the AVR supports Atmos. It can then skip the AC3 core & legacy 7.1 downmix, and trasmit Atmos MAT. Since no legacy material is needed, this leaves space for more objects.

### EC3 Atmos always has a legacy 7.1 presentation
FALSE. Sometimes you can get 7.1, but for streaming unfortunately, the legacy presentation is 5.1, 7.1 & above is locked to Atmos AVRs.

### You can convert THD Atmos to EC3 Atmos without the master file
FALSE, MOSTLY. Only in the most desperate situations may Dolby allow this, like HDMI eARC in TVs. The reason prolly being that THD Atmos may have a low object count, and if you wanted to raise the objects for a EC3 Atmos track, you can't do this unless you have the master.

### THD Atmos uses a different master to EC3 Atmos
FALSE (I think). You can create both types from the same masters. There are 2 master file types, Atmos master file set, and BWF. They should be equivalent. But for streaming, EC3 may have a different dialnorm which tells the decoder to change the volume, which contributes to this perception.

### You can separate THD core using FFMPEG
TRUE, PROBABLY. FFMPEG has a bitstream filter to remove the Atmos data from THD.

### You can separate EC3 core using FFMPEG
FALSE. FFMPEG does not have a bitstream filter to remove the Atmos data from has a bitstream filter as of 2020. The EC3 bitstream filter is for removing the 7.1 part.

### EC3 in mp4 is a hack
MAYBE. Depending on how it was muxed, it might not be compliant, and may fall back to AC3 decoding or may not work. You could use mkv or m2ts containers.

### 7.1 adds rear speakers to 5.1
DEPENDS on who you ask. Dolby & SMPTE will say yes. Microsoft will say no (in WAVEFORMATEXTENSIBLE back comes before side, so 5.1 has back speakers, not side speakers). DTS (in a YT video) claimed "7.1 splits the surround speakers of 5.1 into 2 pairs for an enlarged sweet spot". This must be universally correct since it's vague. The side/back difference in ordering can cause problems in data exchange.

### You can store Atmos in FLAC
FALSE. Atmos for consumers is generally 12-16 channels or objects, but the FLAC codec only supports 8 fixed channels, so there's a problem. If you're able to "successfully" store Atmos in FLAC, you're prolly storing the legacy 7.1 presentation of THD Atmos.

## For Consumers

### There is only 1 version of the Atmos Home and DTS-X Home decoders
FALSE. Most AVRs implement only basic decoders, but not one for complex speaker layouts. The DTS-X one is called DTS-X Pro.

### More speakers = more need for precise placement
FALSE, MOSTLY. As long as you are putting in some effort into positioning, multiple speakers in other spots can conpensate for 1 speaker in a disallowed spot. Obviously we are far from a situation where you can "place your speakers anywhere" and the system will compensate. You can do this with Ambisonics but it's tricky & has other flaws.

### Upfiring Atmos speakers do not work.
FALSE, MOSTLY. I tested this in person, and if you're at a distance, sound will appear to come from above. Some people even have fake-mos speakers, like, regular speakers angled upwards to achieve this effect. I haven't tested this.

### TV and Device Atmos speakers do not work.
MAYBE. From my limited testing, TV Atmos speakers have a much reduced perception of direction, side is lumped in with back, and seems to employ the out-of-phase trick for rear sounds. Needs more testing.

### Atmos soundbars do not work.
I haven't tested this. At least some soundbars have detachable rears, and can have upfiring drivers.

### There is no benefit to an Atmos soundtrack if you don't have height speakers.
DEPENDS. If you have a 5.1 system, prolly no. If you have 7.1 speakers, maybe. Many older 5.1 titles have been reissued with a THD Atmos track which has a 7.1 mix. Most of them AFAIK aren't upmixes. So you get slightly increased resolution.

Another benefit is [height virtualization](https://hometheaterreview.com/marantz-sr6014-92-channel-av-receiver-reviewed/) . Dolby and DTS have DSPs you can apply to 3D mixes to give a small height effect on a 2D system. It can be useful to peeps that can't install height speakers, or find physical height speakers distracting. But restrictions apply, such as not being able to apply DTS Virtual X to an Atmos soundtrack due to Dolby's AVR Mandate of 2018 which prohibits some cross-vendor DSP applications.

### THD Atmos may use a fixed 7.1.4 print
TRUE. Some studios choose 12 objects for Atmos THD or use a fixed 7.1.4 render. Supposedly this is easier/faster for authoring software such as Scenarist Ateme Titan or Sony Blu-print since it doesn't need a 2nd pass for spatial coding. Another benefit is reduced bitrate.

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
5. Effort. It needs to be a team effort from the start of the movie to use Atmos effectively, not an afterthought on one dude. Also, some people think consumers won't listen in Atmos. The result is some bad mixes, at least in part. Like "The Lion King" (1994) " Scar's Be Prepared in chapter eight is a scene that seems like an ideal time for some spacial adds to the top that never really materialize with any overhead prominence" in a review from [blu-ray](https://www.blu-ray.com/movies/The-Lion-King-4K-Blu-ray/217393/#Review), or Back to the Future [others have claimed](https://www.avsforum.com/threads/back-to-the-future-ultra-hd-blu-ray-review.3170351/#post-60174382) . But [John Wick 2](https://www.youtube.com/watch?v=Nx4vve3UGUg) and  [Mission Impossible, I assume fallout](https://www.youtube.com/watch?v=pOI0T15d4R) are apparently examples of good mixes.

### You will get the same experience at the cinema regardless of system
FALSE. As most movies are now mixed in Atmos, others may be conversions. The Dolby Atmos Renderer was limited to 7.1.2 in the past so other presentations such as DTS-X, Auro-3D, and IMAX will be inferior conversions. As of V3.5, it can now output 7.1.4 (and a few others) so a bit better, but still not perfect.

### If it was Atmos at the cinema it will be Atmos at home
FALSE. See start of this document. Also, there could be a case where a film was Atmos at a German cinema, but on the home release, the English track gets Atmos, but the German track only gets 5.1 due to the label wanting less versions of discs & space issues fitting in many languages. Said film may have German Atmos on streaming (but in lossy).

## Legacy Formats

### TrueHD always has a AC3 core
FALSE. Although on BD THD must have a AC3 core since THD is an optional codec on BD, it is possible to have THD without a AC3 core. In fact they are separate streams with the same ID on BD.

### DTS-HD always has a DTS core
TRUE. The core is required to decode the HD part.

### The AC3 presentation of TrueHD is always an automatic downmix of the TrueHD
FALSE. It can be your custom downmix or even completely different content. 2016 Atmos Demo where the AC3 track is just simply an announcer saying to switch your player to bitstream mode.

### The DTS presentation of DTS-HD is always an automatic downmix of the DTS-HD
TRUE. You can customize the downmix coefficients but sometimes there are weird constraints.

### DTS is superior to AC3
DEPENDS. DTS is a more inefficient codec but is typically used at higher bitrates. As long as the bitrate of DTS is 2x of AC3, it is better.

### DTS-HD MA is superior to THD
TRUE. DTS-HD MA:
- Uses to 20% less bitrate than THD
- Single-stream compatibility for legacy systems rather than 2 streams for THD
But:
- Slower to decode due to decoding multiple layers
- Legacy streams must be an automatic downmix (but you can customize the coefficients)
Dolby claims about THD:
- Downmix/legacy presentations need not be an automatic downmix at the cost of more bitrate. In practice, hardly anyone bothers with dedicated downmixes from 7.1 to 5.1
- Compromises between the lossy & lossless parts. In practice, there's actually no compromise with DTS-HD MA when DTS core at 1510kps is above transparency levels, AND it's smaller than THD
Overall & in practice, DTS-HD MA is (almost) completely superior to THD.

### DTS-HD MA is equivalent to THD
TRUE, MOSTLY. They're both lossless codecs. But THD is dolby, and THD has dialnorm. So playing both codecs, THD may have a different volume due to dialnorm so may be perceived to be different/quieter. And louder is generally perceived to be better, so some may favor DTS-HD MA.

### TrueHD 7.1 always has dedicated 5.1 & 2.0 streams
FALSE. While the above is possible, it is not done in practice due to increased bitrate (see "DTS-HD MA is superior to THD"). Downmix presentations are encoded as metadata.

### Listening to 7.1 on a 5.1 system will lose audio
FALSE. AVRs will try to downmix so that you don't lose audio, assuming it is configured correctly.

### AC3 is always quiet
FALSE. You can encode AC3 as loud as you like. But Dolby will do loudness management on it, and Film/TV material, which is quieter than music is usually encoded in AC3, which contributes to this myth that AC3 modifies the audio signal to be quieter. See "Referencing Volume to a Known Level - Dialogue Normalization" in [this post](https://forum.doom9.org/showthread.php?s=&threadid=56020)

### Cinema AC3 is the same as Home AC3
MAYBE. Cinema AC3 uses 320kps compared to home with is typically 384/448kps for 5.1.
(Myth needs checking)

### Cinema DTS is the same as Home DTS
FALSE. Cinema [uses APT-X](https://en.wikipedia.org/wiki/DTS_(sound_system)#Theatrical_use) which again, runs at lower bitrate so that an entire movie could fit on 1 CD.

### DTS EX is completely discrete system
FALSE. "Despite its name, it is in actuality a combination of discrete and matrix technologies". [Spannerworks](http://www.spannerworks.net/reference/10_9a.asp). But it's very good. In summary, The base track is matrix 5.1 for compatibility with older matrix decoders. The extra BC is fed to the BC speaker, and subtracted from the surround speakers.

### DD & DTS EX means that the source was 6.1
FALSE. EX is just a flag. It doesn't change what the contents inside are, it is only a label. Analogy: if you have a jam jar, and stick a peanut butter label on it, some might think there's peanut butter inside, but the actual contents inside are not changed from jam. If it was mixed in 6.1, it should've gotten a discrete 6.1 release later. It's hard to tell at a glance, whether something is true EX or fake EX, unless you do detailed analysis/listening.

Doubtful cases:
- Harry Potter M1-3. It was supposedly EX, but all that was released on early BDs was 5.1. Later BDs got a DTS-X remix. So the source may not be 6.1.
- Arashi no Yoru Ni got a DVD with 5.1 AC3 EX. It was a TV movie. I doubt it's true EX due to budget, and it's historically popular to use the EX flag even if it's not EX cuz older AVRs wouldn't use the BC speaker, unless there was a EX flag.

Proven cases:
- Spirited away eventually got a 6.1, for the Japanese BD. Not that much separation tho. Most dubs are 5.1, may be EX. 
- Finding Nemo had DTS EX for some releases. Eventually it got a 7.1 BD, with almost duplicate back channels. This is acceptable.

### There was no 7.1 before BDs
FALSE. Sony SDDS 7.1f added front speakers in the 90s. And there were some cinema formats in the 70s that added more front or back speakers. Unfortunately, any unique 7.1 mixes will most likely get downmixed to 5.1 for BD, or lost, even though EC3, THD, and DTS-HD support several alternate 7.1 layouts . EC3 & THD are particularly relevant as they support 7.1 w/ CL & CR. Or you can encode L & R as WL & WR in DTS-HD or Atmos.

### You can't have lossless surround on DVD Video, unlike DVD Audio
MAYBE. 6ch 48/16 won't exceed the DVD max bitrate, but if you're scared it won't work, Auro may have something for this, their Auro Stereomagic thing can cram 5.1 into 2ch so you could theoretically use it.

## For Creators

### You need expensive hardware to encode Atmos
FALSE. The RMU is expensive, but "Dolby Atmos Production Suite" is an addon for PT that is $300, a software renderer. You can also access EC3 Atmos encoding through Amazon Mediaconvert.

### You need expensive hardware to encode DTS-X
FALSE. DTS has said that DTS-X is a purely software solution (but may need routing hax in PT). The DTS-X creator suite is a few $K, but the encoder suite is cheaper.

### You need expensive hardware to encode Auro-3D
FALSE. Again, Auro-3D is a software solution, but the software is still expensive.

### You must have object input to encode Atmos
FALSE. You can feed 7.1.2 to most Atmos DAWs for the base. And some encoders allow 9.1.6 input. But that's about it. If you want other layouts, you must make static objects, or pad to 9.1.6.

### You must have object input to encode DTS-X
FALSE. DTS-X Encoder Suite is more flexible, and allows 5.1.2 up to 7.1.4 input for DTS-X, including weirdo layouts like 7.1.3. For more channels, you need to use objects or the DAW panner.

### You must use Dolby, DTS, or Auro-3D tools to mix for those formats.
FALSE. You can mix in other channel-based 3D surround formats using any tools. Such as [my Reaper-Surround suite](https://github.com/junh1024/Reaper-Surround#introduction), spatial PCM, or even ambisonics (but this is dispreferred). But you must use their encoder to ensure bitstream compliance.

### You can't convert between Atmos, DTS-X, and Auro-3D
FALSE.
- If you start with Atmos, you can export 7.1.4, setup a new project, and pan objects/channels in the appropriate positions. If you only have an encoded bitstream, you need to play it through Dolby Media Decoder and somehow capture the output.
- If you start with DTS-X, you can export 7.1.4 and do similar. If you only have an encoded bitstream, you can use DTS-X Bitstream tools to decode DTS-X to WAVs.
- If you start with Auro-3D, you can use channel exports. If you're using Nuendo, maybe you can convert Auro-3D panners to Atmos panners. If you only have an encoded bitstream, you can use the Auro-3D decoder in their suite.
- I haven't tested any of these.

### I can QC my Atmos mix on a PC
FALSE. As of 2020, there are no THD/EC3 Atmos decoders for PC. You must use a AVR. The situation may change in the future. If you have DTS-X or Auro-3D suites, those may include a decoder.

### I can use ADM from 3D OBA suite(s) with Dolby encoders
FALSE. Although this is the ideal situation, and the Dolby Atmos Conversion Tool can convert between DAMP and ADM formats, Dolby tools currently only accept ADM WAV files made by Dolby tools. This is due to cubular vs spherical coordinates, among other possible differences. So if you use other OBA suites such as [VISR](http://www.s3a-spatialaudio.org/plugins) or [EBU EAR](https://ear-production-suite.ebu.io/) suites and want to deliver for Dolby codecs, you're in for a bad time(tm). Unless you mix in CBA (which is what many people are doing anyway, including myself).

### It's hard to convert a legacy 5.1 project to an Atmos project
FALSE, MAYBE. In PT & Nuendo, maybe you can convert legacy projects to Atmos projects using scripts. Or you can export 5.1 stems and start a new project. I haven't tested any of these.

### It's hard to have consistent height content
FALSE. [Boom library](https://www.boomlibrary.com/shop/?swoof=1&pa_producttype=3d-surround) have released a few 3D surround libraries with room tones & weather FX recorded with a 8.0 mic array.

### Dolby charges license fees per title

FALSE. "We have never charged content fees for our licensed technologies..." [ref](https://dolbyac4.com/uk/cost.php)

### DTS charges license fees per title
???

### Auro-3D charges license fees per title

Auro-3D charges an annual codec license. [ref.](https://www.auro-3d.com/buy/)

Special thanks to the individuals that have contributed to my understanding.

Date: Dec 2020