# Comissions

## Introduction
Comissions are a way to support me while getting something in return and increasing amount of surround music available. Mixing a short film/movie is charged at the same rate.

## Process & Contact
1. Contact me on the originating site/forum, or [twitter](https://twitter.com/junh1024/) that you want to do a surround remix, with details about your song, any panning ideas, revisions, delivery options, etc.
2. I quote the job
3. Acceptance of job requires a 50% upfront payment to https://donorbox.org/junh1024 , with your username as reference
4. After mixing, about half of the song sample will be sent.
5. Acceptance of further work is the rest of the payment, which should include the rest of the sample, revisions, and deliverables.
6. Additional costs may be incurred for complex jobs. I'll tell you about this.

## Pricing
All prices in USD.

- Stereo mix only: I will use spleeter to separate it, and it will be charged as 5 stems.
- Stems/MT of your own song(s): $1/stem/minute. Min charge $25.
- Remix stems or CMT stems: please check with the artist that a remix is allowed.
- I may check with the artist check that permission has been sought.
- https://www.karaoke-version.com/ $50/song , min order 2 songs (this restriction is due to licensing agreements/costs, and most of it will go to licensing anyway)
- [Musopen project 2012](https://ia902809.us.archive.org/view_archive.php?archive=/20/items/musopen-dvd/Musopen-DVD.zip) $10/min, min 5 mins. NB: the mp3 previews are roughly representative of the source material, but not the quality/editing/imaging.
- Stems are assumed already mixed, and only require surround panning/mastering. If mixing is required, the cost may be 2-3x more
- Every $25 paid will include 1 free revision, up to a max of 4 revisions, free or paid. Additional revisions $10.
- Quotes of <$50 may be static only
- Discount of 2% if you tell me the referring site/page
- Discount of 20% if I want to include it in my [Atmos Music Collection](https://github.com/junh1024/junh1024-Documents/blob/master/Music/Atmos%20Music%20Collection.md#introduction)

### Examples
- 5 stems, 4 minutes: $25 (min charge). 1 revision, static panning.
- 10 stems, 5 minutes: $50. 2 revisions, dynamic panning.

## Stems

### Music
Please remove imaging FX such as delay, reverb, stereoization. These may be recreated in surround. Please also include a reference stereo mix. 

These are the suggested thresholds for different surround formats:
- 5.1: >= 10 stems
- 7.1: >= 20 stems
- 3D/Atmos: >= 30 stems

I assume the stems are balanced, an even spread over the available instruments. Not 25 drum tracks & 5 everything else. These thresholds are intended to ensure a rich mix for the target format. Lower stem counts are possible but may not sound that great. I will automatically select an appropriate format based on stem count & content.

### Movie
A minimum of dialog, FX, ambience, music is recommended.


## Delivery
1 delivery option is included, additional delivery options $5 each. Surround will be exported at -18LUFS unless otherwise specified. I suggest not going louder than -12 LUFS.

Surround codecs 5.1/7.1:
- FLAC 48/16 (16bit has an excellent noise floor of -120dB, and is suitable for music)
- AAC 300-500kps (you can specify a qAAC quality value or fixed rate)

Atmos containers:
Atmos will be encoded to lossy Dolby Digital Plus, 384-640kps, depending on how active the mix is.
- ec3 (raw)
- mp4 (best for Apple devices)
- m2ts (best for BDPs)
- mkv

Other:
- 7.1.4 SMPTE-Dolby WAV for Dolby encoder
- 7.1.4 mono WAVs for DTSX encoder
- 15.1 master format WV for REAPER
- Ambisonics for YT, and other options may be possible, contact me.

Atmos will include a dummy grey video for compatibility. Album art may be possible.

Atmos file delivery (mp4/mkv) is suitable for file-based platforms such as https://bandcamp.com/ and http://surroundmusic.one/ . For streaming platforms like TIDAL & Apple Music, those need Dolby ADM. Dolby ADM delivery is being investigated.

## Limitations
I will be using my own [Reaper-Surround](https://github.com/junh1024/Reaper-Surround#introduction) suite to mix in surround. For 3D, 15.1 will be converted to Atmos. It isn't true object Atmos, but it avoids some common traps of Atmos mixing (limited 7.1.2 bed, certain positions), and some unique features (loop slicing, DSP). It will sound very good on systems up to 7.1.6. If you need it to scale to higher, again contact me.

E&OE.