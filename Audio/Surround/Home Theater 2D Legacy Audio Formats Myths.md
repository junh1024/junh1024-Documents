# Home Theater Legacy Audio Formats Myths

## Introduction
This is the 2D legacy companion to my 3D doc.

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

### The 7.1 presentation of TrueHD is the main mix, and everything else is a downmix at the bitstream level
FALSE. TrueHD has the following structure:

* Substream 1: 2.0 downmix
* Substream 2: 5.1 extension
* Substream 3: 7.1 extension
* Substream 4: Atmos extension

As such, the 2.0 core is actually the standalone mix, and everything else is a reconstruction. Substream 2-4 are not usable by themselves. This is the reason that some AVRs do a 7.1 to 5.1 summation downmix, since it's easier to decode just substreams 1-2.  But it's still useful to refer to 7.1 & below as downmixes, since that's what software tools refer to them by.

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

### 7.1 DDP is as efficient as 5.1 DDP
FALSE. 7.1 DDP is structured as a DDP 5.1 core + [4ch surround extension](https://professional.dolby.com/globalassets/dolby-digital-plus/dolby-digital-plus-audio-coding-tech-paper.pdf) . The extra channels replace the surrounds in 5.1. Thus, it needs about 2x the bitrate as it's effectively storing 9.1.

### The 5.1 AC3 core of DDP Blu-ray profile is fully independent and separable from the 7.1 extension
FALSE. The 7.1 extension relies on the 5.1 AC3 core for some channels in a similar fashion to the above.

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
- Arashi no Yoru Ni got a DVD with 5.1 AC3 EX. It was a TV movie. I doubt it's true EX due to budget, and it's historically popular to use the EX flag even if it's not EX since older AVRs wouldn't use the BC speaker, unless there was a EX flag.

Proven cases:
- Spirited away eventually got a 6.1, for the Japanese BD. Not that much separation tho. Most dubs are 5.1, may be EX. 
- Finding Nemo had DTS EX for some releases. Eventually it got a 7.1 BD, with almost duplicate back channels. This is acceptable.

### There was no 7.1 before BDs
FALSE. Sony SDDS 7.1f added front speakers in the 90s. And there were some cinema formats in the 70s that added more front or back speakers. Unfortunately, any unique 7.1 mixes will most likely get downmixed to 5.1 for BD, or lost, even though EC3, THD, and DTS-HD support several alternate 7.1 layouts . EC3 & THD are particularly relevant as they support 7.1 w/ CL & CR. Or you can encode L & R as WL & WR in DTS-HD or Atmos.

### You can't have lossless surround on DVD Video, unlike DVD Audio
MAYBE. 6ch 48/16 won't exceed the DVD max bitrate, but if you're scared it won't work, Auro may have something for this, their Auro Stereomagic thing can cram 5.1 into 2ch so you could theoretically use it.

###  Dolby Digital is stored on a digital track on LDs
FALSE. Dolby Digital is stored on a analog track. It typically requires a suitable LD player, or demodulator (both expensive) to extract.

###  DTS is stored on a digital track on LDs
TRUE. DTS is stored on a digital track on LDs.

## General Encoding

### Saving a AC3 file with exactly the same specifications and bitrate as the original will result in no quality loss
FALSE. When you edit audio in an audio editor, the audio has already been decoded to PCM, and so the saving process has no knowledge of the original AC3 data. In addition, when you re-save as AC3, you are likely getting a double hit in quality since:

- A Lossy to Lossy conversion was performed
- You are likely using free encoders which have [inferior quality](### Free Dolby Digital, DDP, and DTS encoders are competitive with commercial encoders) compared to paid professional ones. The only way to avoid any quality loss is to use tools that operate directly on the bitstream and can't perform arbitrary editing like mkvmerge.

### I must encode in DD or DTS to be compatible with hardware players
FALSE. These days, many devices accept H264 & AAC in mp4/mkv for digital delivery, of which there are excellent free encoders, so no need to encoder DD or DTS. However, if you want *disc* delivery, you must encode DD/DTS, or use PCM.

### Free Dolby Digital, DDP, and DTS encoders are competitive with commercial encoders
FALSE. Free encoders don't produce acceptable quality at low bitrates and are thus not competitive. In addition,

For DDP: "New E-AC3 coding tools are not actually implemented, unless required by the bitstream. Due to some coding improvements its minimally better then AC3 at any given bitrate, but probably not even measurable" - nevcairiel on [Doom9](https://forum.doom9.org/showthread.php?p=1951632#post1951632)

For THD: The FFMPEG implementation:
- Doesn't include a DD core
- Limited hardware compatibility (might be related to above)
- Limited to 5.1
- Doesn't support Atmos

For DTS: Free encoders may have [artefacts on hardware decoders](https://forum.doom9.org/showthread.php?p=1754796#post1754796)

### Free or 3rd-party THD and DTS-HD MA encoders produce files of the same size as 1st party encoders
FALSE. Free/3rd-party encoders may produce bigger files:
- Versus [FFMPEG THD](https://forum.doom9.org/showthread.php?t=183363)
- Versus Totalcode DTS-HD MA: maybe larger files.

### DTS Core bitrate for DTS-HD MA doesn't matter since the output is lossless
FALSE. Very old devices will only get the legacy core, hence you 

### Downmix trims don't affect filesize
FALSE. Setting custom downmix trims may increase filesize.

### Default downmix trims will be full-volume
FALSE. Default downmix trims may be set lower to reduce clipping on downmix.

## Dolby Encoding

### You should always set the dialnorm to -31
FALSE.

Dialnorm is meant to represent the loudness of the program, measured around the dialogue. The idea is that you mix with the dialog at a certain level, and everything else accommodates that. With the DN set correctly, you will experience approximately the same loudness across different programs.

Assuming a device reference of -31, a value of -31 means no adjustment, and a value of -21 means an adjustment of -10dB. Using free software, it's possible to get an approximate figure by measuring RMS of a section with dialog only, and round to quieter.  Ideally, you should measure the program loudness with Dolby implementations.  [Reference](https://forum.doom9.org/showthread.php?t=56020)

If you set it to -31 (off), or remove the DN metadata (equivalent to -31) it would be a bad experience for consumers who may experience a jump in volume with material that has DN set correctly. Setting DN incorrectly could also [remove Atmos capabilities](https://forum.doom9.org/showpost.php?p=1953784&postcount=14) . This makes sense since Atmos has mastering specifications for loudness.

### You should always remove dialnorm
FALSE. Removing dialnorm is not recommended.

1. It is loss of information
2. Many free software ignores dialnorm anyway, but it may lead to inconsistent loudness between programs on hardware as said above
3. It leads to removal of Dolby Atmos capability on hardware and software


### DRC profile doesn't matter
FALSE. Setting the DRC profile inappropriately may cause artefacts. Music profiles tend to gentle compression from a low threshold while film profiles tend to hard compression at high thresholds.  See other documentation for further details.

### It's not possible to put >448kps DD on DVD
FALSE. You can author DVDs with 640kps DD. Whether they're in-spec or play is another story.



## DTS Encoding

### It's fine to put DTS as the sole track on DVD
FALSE. DTS was a late addition to the DVD spec, and DVD players aren't required to include a DTS decoder (unlike DD). Hence it's recommend to include a DD or PCM track also (they are mandatory codecs for DVD).

### You should always set the highest core bitrate of 1510kps
FALSE. For stereo encodes, setting the highest core bitrate of 1510kps may significantly increase encoded size.
