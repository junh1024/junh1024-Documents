# Home Theater 3D Audio format Myths

# Introduction

There are many misconceptions about 3D Audio formats on the internet. Here should be some common basic ones, some strange ones I've encountered, and some personal esoteric ones. You may see vague or flamboyant language to describe or misrepresent systems, which I will not do. I also do not have any commercial interest in the below systems, so there is no loss to attempt to tell the truth. I do have some interest in my own 15.1 system, but that is open-source & available for free.

MAYBE. 
FALSE. 
TRUE. 

- UBD =4K UltraHD Blu-ray
- ps = bits per second
- EC3 Atmos = Dolby Digital Plus with Joint Object Coding aka Dolby Digital Plus with Atmos
- ELL = ear-level layer. I won't call this the bottom layer since NHK 22.2 has 3 layers, including a bottom layer.

## General

### Atmos & DTSX is only supported on UBD
FALSE. Atmos is an extension to TrueHD. TrueHD, while supported by many AVRs, is an optional codec on BD so may create compatibility problems in rare cases. Also, some labels like sony may reserve the 3D audio presentations for UBD. Combined, may support this myth.

- Hobbit is 7.1 on BD, Atmos on UBD.

### Auro3D is not supported on UBD
FALSE. As Auro3D is carried in PCM, it can be supported on UBD through TrueHD & DTS-HD MA, too.

### Atmos has 128 objects
MAYBE. The cinema version of Atmos, hereon called Atmos Pro, supports up to 128 objects. Since the bed is usually 7.1.2, this leaves 118 (dynamic) objects in practice.

### Atmos Pro is the same as Atmos Home
FALSE. The consumer version of Atmos hereon called Atmos Home, has reduced objects for bitrate purposes. If all 128 objects were active, and simply ported to a consumer UBD, that might mean 50mps of audio, which would lead to reduced video bitrate & quality to fit within UBD limits. Hence, objects are reduced for Atmos Home. Bitrates for THD Atmos are typically 3-7mps.

### THD cannot do height
FALSE, PROBABLY. Some (newer?) version of Dolby Media Producer/Encoder allow 5.1.2 TrueHD via channel input. I haven't tested this.

### DTS-HD cannot do height
FALSE. DTS Master Audio Suite allows several height layouts. But may not be correctly supported by older AVRs. It may appear as DTS-X on newer AVRs, but support is still flaky. You may need to choose the exact speaker layout & enable Neural-X DSP.

### THD Atmos on BD has up to 24 objects

FALSE. Since Atmos is an extension to THD, you might look up "extension" in the dictionary and conclude addition, and consequently add 7.1 & 16 = 24. Let's review what we know:
- The legacy 7.1 THD presentation is a complete presentation, downmix of height & ELL, with no missing audio
- Legacy AVRs cannot decode objects
- Objects (can) have additional audio

If you add the object audio to the 7.1 audio, that would result in an over-complete presentation and would violate #1. Subsequently, the only way to not violate this is if the object count includes 7.1 ELL as well as height. So an max object count of 16 is correct. See also the myth about games. Also, the objects are encoded as a differential to the 7.1 mix to save bitrate.

### DTS-X Pro is superior to Atmos Pro
TRUE. DTS-X Pro supports 256 objects rather than 128, and may have a more flexible base layout.

### Channels and objects are equivalent
FALSE. Objects can move, and channels can't. This is what makes an OBA system superior. Objects can also be rendered at different volumes to have the correct pan law regardless of speakers. Same can't be said of channels.

### Channels & static objects are equivalent
FALSE. Except for C & LFE, channels must have a 1-1 mapping to a speaker. Objects can be partially image between multiple speakers.

### Channels are always at ear-level and objects can only be at the top
FALSE. Atmos Pro Base is 7.1.2, 2 side height. Objects can also be at ELL.

### You can hear the difference between channels and objects
FALSE, MOSTLY. Height of objects are not predictable as above. Also, spatial remapping for Atmos Home converts everything to objects. But the objects don't move much.

### DTS-X Home is superior to Atmos Home
DEPENDS. While you would think 16 objects in Atmos Home vs 7.1.4 + 5 objects in DTS-X Home are equivalent, there is the difference between channels & static objects so imaging may be different. Also, DTS software isn't as smart as Atmos software which automatically does spatial remapping to reduce objects. Instead, you must manually choose which objects to channelize and others to keep as objects. What happens in practice is studios just skip this process and channelize everything. Except for a few small studios like Well Go on say, "Ip man 3". [Ref2](https://www.avsforum.com/threads/trinnov-altitude.1516103/page-147#post-51314001). For 7.1.4, mixes in either system should sound similar. But for more speakers, since DTS-X is channel-based, it might be better since it can upmix missing speakers. But Atmos will probably leave them blank most of the time. Which is why many AVR owners with many speakers install additional AVRs to upmix more speakers rather than native Atmos rendering.

### THD Atmos is superior to EC3 Atmos
DEPENDS. Although THD is obviously lossless unlike EC3, some titles may have more objects on a EC3 release.

### Auro3D is superior to Atmos
FALSE, MOSTLY. I'll split this up into 3 myths.

### Auro3D codec is superior to Atmos
FALSE. Auro3D must be stored at a full 24b since that's where the data is. Atmos and DTS-X can operate at lower bitdepths so they can have potentially lower bitrates. It is sensitive to mishandling if it's in PCM/FLAC rather than THD/DTS-HD MA, so bitstream may not work if the PCM is tampered with (aka some scenarios with KODI).

### Auro3D speaker layout is superior to Atmos
FALSE, MOSTLY. Many A3D titles use the 11.1/5.1.6 layout. Hence Many people with legacy 7.1 speakers will get no benefit from A3D, unlike Atmos and DTS-X which are typically 7.1, since A3D 5.1.6 downmixes to 5.1. Also, In A3D 5.1.6, there is reduced rear & rear height resolution due to only 2 back speakers for each level. The layout is also uneven. A few newer A3D titles use 13.1/7.1.6, which rectifies problems with legacy systems & ELL back, but not height back.

### Auro3D in practice is superior to Atmos
DEPENDS. This boils down to your preference for speaker layout & acoustics. Dolby recommends if your ceiling is low, that upfiring speakers be used instead of in-ceiling ones to create a better impression of space. The overhead/VOG speaker is the marketing point for A3D so Auro recommends one anyway. Some people prefer it. Some people dislike it.

## Technical

### THD Atmos can be worth 24 bits
FALSE, PROBABLY. THD is 24b, but the number of active bits is usually lower, and there's no option to turn off bit-reduction. Likely to save bitrate. Decode a THD Atmos through eac3to, and it may show something like this:

	Original audio track, L+R+LFE+BL+BR+SL: constant bit depth of 20 bits.
	Original audio track, C+SR: constant bit depth of 21 bits.

### DTS-X can be worth 24 bits
TRUE, PROBABLY. DTS-X Encoder Suite has a preconditioning option, which is off by default. Which gets you call 24b. High preconditioning probably reduces the bits, probably down to 18b.

### The Atmos used in games is the same as the Atmos used in BDs
FALSE. Atmos for games uses Atmos MAT. Through HDMI probing (what's the proper name?), the device can find out the AVR supports Atmos. It can then skip the AC3 core & legacy 7.1 downmix, and trasmit Atmos MAT. Since no legacy material is needed, this leaves space for more objects.

### TrueHD always has a AC3 core
FALSE. Although on BD THD must have a AC3 core since THD is an optional code on BD, it is possible to have THD without a AC3 core. In fact they are separate streams with the same ID on BD.

### DTS-HD always has a DTS core
TRUE. The core is required to decode the HD part.

### The AC3 presentation of TrueHD is always an automatic downmix of the TrueHD
FALSE. It can be your custom downmix or even completely different content. 2016 Atmos Demo where the AC3 track is just simply an announcer saying to switch your player to bitstream mode.

### The DTS presentation of DTS-HD is always an automatic downmix of the DTS-HD
TRUE. You can customize the downmix coefficients but sometimes there are weird constraints.

### EC3 Atmos is always 7.1
FALSE. Sometimes you can get 7.1 but For streaming unfortunately, it tends to be 5.1. It should still have a 7.1 ELL if you have a newer AVR.

### You can convert THD Atmos to EC3 Atmos without the master file
FALSE, MOSTLY. Only in the most desperate situations may Dolby allow this, like HDMI eARC in TVs. The reason prolly being that THD Atmos may have a low object count, and if you wanted to raise the objects for a EC3 Atmos track, you can't do this unless you have the master.

### THD Atmos uses a different master to EC3 Atmos
FALSE (I think). You can create both types from the same masters. There are 2 master file types, Atmos master file set, and BWF. They should be equivalent. But for streaming, EC3 may have a different dialnorm which tells the decoder to change the volume, which contributes to this perception.

### You can separate THD core using FFMPEG
TRUE, PROBABLY. FFMPEG has a bitstream filter to remove the Atmos data from THD.

### You can separate EC3 core using FFMPEG
FALSE. FFMPEG does not have a bitstream filter to remove the Atmos data from has a bitstream filter as of 2020. The EC3 bitstream filter is for removing the 7.1 part.

### EC3 in mp4 is a hack
MAYBE. Depending on how it was muxed, it might not be compliant, and may fall back to AC3 decoding or may not work. You could use mkv or n2ts containers.

### 7.1 adds rear speakers to 5.1
DEPENDS on who you ask. Dolby & SMPTE will say yes. Microsoft will say no (in WAVEFORMATEXTENSIBLE back comes before side, so 5.1 has back speakers, not side speakers). DTS (in a YT video) claimed "7.1 splits the surround speakers of 5.1 into 2 pairs for an enlarged sweet spot). This must be universally correct since it's vague. The side/back difference in ordering can cause problems in data exchange.

## For Consumers

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

### THD Atmos uses a fixed 7.1.4 print, and studios don't care about 9.1.6 users
MAYBE. Some studios use 12 objects. Also, mixing software such as PT & Nuendo use a square panner which has L & R in the top corner. If you wanted to have consistent content in the width speakers, you would need to increase the diffusion of objects from L&R, or move them a bit back.

### Atmos remixers are lazy and don't care about height
MAYBE. There's a problem with tools and effort. Most Atmos panners are cube-based. So if you want to use height, it's a separate control on top of ELL movement. There is a dome panner in DTS-X (and other suites like mine, and OBA suites) which makes 3D panning as easy as 2D panning by using the center of the circle for height. The other part is effort. Some people just don't put in the effort. Like "The Lion King" (1994), there were opportunities to use height, like dialog from above for certain scenes (others have claimed), but it just wasn't used.

### X system is better than Y system
DEPENDS. They all have their flaws, some are more flawed than others. No system is more natural, realistic, or emotional than others. That's just marketing collateral. But there are technical differences, and personal tastes.

### You will get the same experience at the cinema regardless of system
FALSE. As most movies are mixed in Atmos, others may be conversions. As the renderer in Dolby Atmos Mastering & Production suite renders up to 7.1.2 only, other presentations such as DTS-X, Auro3D, and IMAX will be inferior conversions. It would be nice if the DAMP renderer offered 7.1.4 renders or even 9.1.6. Also differences in speaker layout & inherent system.

## Legacy formats

### DTS is superior to AC3
DEPENDS. DTS is a more inefficient codec but is typically used at higher bitrates. As long as the bitrate of DTS is 2x of AC3, it is better.

### DTS-HD MA is superior to THD
TRUE, MOSTLY. DTS-HD MA typically takes up less bitrate than THD. It offers single-stream compatibility. But legacy streams must be a downmix. Dolby has somehow turned their disadvantage (of more bitrate) into an advantage by claiming THD 5.1 presentations need not to be a automated downmix of the 7.1 (at the expense of using more bitrate).

### DTS-HD MA is equivalent to THD
TRUE, MOSTLY. They're both lossless codecs. But THD is dolby, and THD has dialnorm. So playing both codecs, THD may have a different volume due to dialnorm so may be perceived to be different/quieter. And louder is generally perceived to be better, so some may favor DTS-HD MA.

### Cinema AC3 is the same as Home AC3
MAYBE. Cinema AC3 uses 320kps compared to home with is typically 384/448kps for 5.1.

### Cinema DTS is the same as Home DTS
FALSE. Cinema [uses APT-X](https://en.wikipedia.org/wiki/DTS_(sound_system)#Theatrical_use) which again, runs at lower bitrate so that an entire movie could fit on 1 CD.

### DTS EX is completely discrete system
FALSE. "Despite its name, it is in actuality a combination of discrete and matrix technologies". [Spannerworks](http://www.spannerworks.net/reference/10_9a.asp). But it's very good. In summary, The base track is matrix 5.1 for compatibility with older matrix decoders. The extra BC is fed to the BC speaker, and subtracted from the surround speakers.

### DD & DTS EX means that the source was 6.1
FALSE. EX is just a flag. It doesn't change what the contents inside are, it is only a label. Analogy: if you have a jam jar, and stick a peanut butter label on it, some might think there's peanut butter inside, but the actual contents inside are not changed from jam. If it was mixed in 6.1, it should've gotten a discrete 6.1 release later. It's hard to tell at a glance, whether something is true EX or fake EX, unless you do detailed analysis/listening.

Doubtful cases:
- Harry Potter M1-3. It was supposedly EX, but all that was released on early BDs was 5.1. Later BDs got a DTS-X remix. So the source may not be 6.1.
- Arashi no Yoru Ni got a DVD with 5.1 AC3 EX. It was a TV movie. I doubt it's true EX due to budget, and it's historically popular to use the EX flag even if it's not EX to use extra speakers (if you have them)

Proven cases:
- Spirited away eventually got a 6.1, for the Japanese BD. Not that much separation tho. Most dubs are 5.1, may be EX. 
- Finding Nemo had DTS EX for some releases. Eventually it got a 7.1 BD, with almost duplicate back channels. This is acceptable.

### There was no 7.1 before BDs
FALSE. Sony SDDS 7.1f added front speakers in the 90s. And there were apparently some cinema formats in the 70s that added front or back speakers. Unfortunately, any unique 7.1 mixes will most likely get downmixed to 5.1 for BD, or lost, even though DTS-HD supports several alternate 7.1 layouts . The 7.1 wide layout adds wide speakers, but not center speakers so would not be spatially correct, but would be a possible 1-1 mapping. Some current-gen 3D formats can have speakers in the right locations, or you can encode the extra speakers as objects.

## For Creators

### You need expensive hardware to encode Atmos
FALSE. The RMU is expensive, but "Dolby Atmos Production Suite" is an addon for PT that is $300, a software renderer. You can also access Atmos encoding through Amazon Mediaconvert.

### You need expensive hardware to encode DTS-X
FALSE. DTS has said that DTS-X is a purely software solution (but may need routing hax in PT). The DTS-X creator suite is a few $K, but the encoder suite is cheaper.

### You need expensive hardware to encode Auro3D
FALSE. Again, Auro3D is a software solution, but the software is still expensive.

### You must have object input to encode Atmos
FALSE. You can feed 7.1.2 to most Atmos DAWS for the base. And some encoders allow 9.1.6 input. But that's about it. If you want other layouts, you must make static objects, or pad to 9.1.6.

### You must have object input to encode DTS-X
DTSXES is more flexible, and allows 5.1.2 up to 7.1.4 input for DTS-X, including weirdo layouts like 7.1.3. For more channels, you need to use objects.

### You must use Dolby, DTS, or Auro3D tools to mix for those formats.
FALSE. You can mix in other channel-based 3D surround formats using any tools. Such as my suite, spatial PCM, or even ambisonics (but this is dispreferred). But you must use their encoder to ensure bitstream compliance.

### Dolby charges license fees per title

FALSE. "We have never charged content fees for our licensed technologies..." [ref](https://dolbyac4.com/uk/cost.php)

### DTS charges license fees per title
???

### Auro3D charges license fees per title

Auro3D charges an annual codec license. [ref.](https://www.auro-3d.com/buy/)

Special thanks to the individuals that have contributed to my understanding.

Date: Dec 2020