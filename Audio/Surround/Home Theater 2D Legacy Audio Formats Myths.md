# Home Theater Legacy Audio Formats Myths

## Technical

### TrueHD always has a AC3 core
FALSE. Although on BD THD must have a AC3 core since THD is an optional codec on BD, it is possible to have THD without a AC3 core. In fact they are separate streams with the same ID on BD.

### DTS-HD always has a DTS core
TRUE. The core is required to decode the HD part.

### The AC3 presentation of TrueHD is always an automatic downmix of the TrueHD
FALSE. It can be your custom downmix or even completely different content. 2016 Atmos Demo where the AC3 track is just simply an announcer saying to switch your player to bitstream mode.

### The 5.1 presentation of TrueHD is always an automatic downmix of Atmos
FALSE. TrueHD can store a separate 5.1 presentation. This "multiple presentations" feature of TrueHD dates back to the 2000s.

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

### 7.1 adds rear speakers to 5.1
DEPENDS on who you ask. Dolby & SMPTE will say yes. Microsoft will say no (in WAVEFORMATEXTENSIBLE back comes before side, so 5.1 has back speakers, not side speakers). DTS (in a YT video) claimed "7.1 splits the surround speakers of 5.1 into 2 pairs for an enlarged sweet spot". This must be universally correct since it's vague. The side/back difference in ordering can cause problems in data exchange.

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

## Matrix

### It is best to listen to matrixed soundtracks with the same decoding system as the encoder
#### For example, DS soundtracks with a DS decoder, DPL2 soundtracks with a DPL2 decoder

FALSE. Although DS/DPL1 decoders might be more authentic to period limitations, DPL2 preserves the original better, even when the audio is DS encoded, since DPL2 implementations have 20-2000ish bands of steering vs DS of 0 and DPL of 1. Not to mention, DPL2 decoders are downmix-compatible, unlike DPL1 decoders. Also, all encoding methods use the same method (out-of-phase/wide phase) to indicate rear sounds in stereo, which is what all decoders pick up on.

![DS & DPL2 decoding comparison](https://i.imgur.com/0o7Rflf.png)

### DTS EX is completely discrete system
FALSE. "Despite its name, it is in actuality a combination of discrete and matrix technologies". [Spannerworks](http://www.spannerworks.net/reference/10_9a.asp). But it's very good. In summary, The base track is matrix 5.1 for compatibility with older matrix decoders. The extra BC is fed to the BC speaker, and subtracted from the surround speakers.

### DD & DTS EX means that the source was 6.1
FALSE. EX is just a flag for 5.1. It doesn't change what the contents inside are, it is only a label. Analogy: if you have a jam jar, and stick a peanut butter label on it, some might think there's peanut butter inside, but the actual contents inside are not changed from jam. If it was mixed in 6.1, it should've gotten a discrete 6.1 release later. It's hard to tell at a glance, whether something is true EX or fake EX, unless you do detailed analysis/listening. This practice was historically done since older AVRs wouldn't engage BC unless the MTX flag was on (apparently).

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
