# Opus is not that great

## Introduction

Opus was touted as a general-purpose audio codec which can scale to all bitrates. And it has made graphs to show it is superior.  But if you're promoting a codec, you wouldn't show information there is against your point. So anyone who's done any actual listening tests, may find that existing codecs are definitely competitive or might be better.

Opus his small edge around 40-80 KPS and Opus has promoted this test. 
Unfortunately, this isn't really the case. 


 as it doesn't scale to higher bitrates. It also has a few other disadvantages. Opus was designed for HQ playback, at low bitrates, on cheap hardware. Opus was also designed for teleconferencing, so it's low-latency. This also impedes Opus' quality at higher bitrates.


## Possible Mkv sync issues with opus

"Opus doesn't play well with mkv and can throw sub timing off. It also only has benefits at low bitrates when nobody should be encoding at under 128k in this day and age... it's not a good idea for anyone to start encoding anime in Opus." -kuchi on AB

## Forced resampling to 48k

Opus has forced resampling to 48k apparently to compensate for cheap hardware that works better at 48k. One could logically assume that increased sampling rate means there are more samples to compress per unit time. Frames are fixed size, so each frame gets less resources.

I have done tests at 32 KPS for Opus vs HE-AAC, and reducing the sampling rate to 32khz (for very low bitrates) does indeed reduce artifacts and increase quality. The same claim is said when exhale XHE-AAC is [compared against](https://hydrogenaud.io/index.php/topic,120936.0.html) Opus. However, reducing the sampling rate in Opus isn't possible. unless you build it yourself - something out of reach for most user. So due to forced resampling, Opus is slightly worse than it could have been at low bitrates.

## Cutoff at 20k

Most good encoders raise the cutoff to 21 or even 22k if they think it's appropriate. Most people can't hear above 20k, but some might, and it's better for editing. But you shouldn't be editing a lossy format! Tell that to me when a lossy format is the only version that's available and you need to edit it. This is likely to lessen artefacts due to LQ (hardware) SRC filters.

Due to the fixed cutoff of Opus such that there's a upper limit of frequencies regardless if the bitrate is increased, makes it unsuitable for archival and suboptimal for editing tasks.



## Artefacts

Some people disprefer the artefacts Opus makes on LBR content, due to the default prime-ish framesizes, optimized for hardware devices.

## Design & Usage issues

https://codecs.multimedia.cx/2015/01/

## Opus takes much loger to encode & decode
Decode times takes about 5x longer. [link](https://forum.doom9.org/showpost.php?p=1849225&postcount=19)


## Forced Low latency operation

The development group for the working group developing Opus had interests in low latency voice communication, and so Opus was developed with that as a priority. This is a design constraint which will impact quality in several ways is will be discussed below.


http://web.archive.org/web/20240519150254/http://www.h-online.com/open/news/item/IETF-working-towards-royalty-free-audio-codec-859394.html



## Opus is not as compatible as older codecs

## Opus doesn't use SBR

This is a technique for improving efficiency at low bitrates. Rather than storing the high frequencies directly, a description of how to approximate them from the lower frequencies is stored as side data. HE-AAC is the earliest form of SBR with a fixed SBR Point. Later implementations found in XHE-AAC, DDP, and AC4 have a more flexible SBR Point.

However, Opus [does not](https://en.wikipedia.org/wiki/Spectral_band_replication use SBR) "Opus's CELT part performs spectral folding on the MDCT bin level, making it a far less advanced but lower-delay technique compared to SBR" . So again, Opus isn't as good as it could've been, and this impacts quality at very low bitrates. At very low bitrates, Opus produces distortion which [may sound worse](https://hydrogenaud.io/index.php/topic,115745.0.html) than HE-AAC, and I have confirmed with my own personal testing at 32kps. So at very low bitrates, HE-AAC with its full SBR implementation is competitive.

### No parametric stereo
Parametric stereo is another technique for improving efficiency at low bitrates. Rather than storing 2 stereo channels directly, PS works by storing a mono sum, then side data to steer and decorrelate different bands to produce a pseudo stereo image. It has been claimed the sweet spot for PS in AAC is 12-24 KPS.

However, Opus has no such feature and at 12 KPS, stereo music is [quite mono](https://www.youtube.com/watch?v=f-_6XEmiGNc), completely destroying the spatial quality and sounding very much like telephone quality hold music, quite in line with the design aims of the codec.

## Opus low-bitrate quality does not scale to high-bitrate quality
This graph has been shown a lot of times : https://opus-codec.org/static/comparison/quality.png 
But Several tests by users have shown that vorbis & AAC beat Opus at high bitrates:

AAC 128kps (qaac) might beat opus 128kps AAC
https://www.zupimages.net/up/20/45/01gw.png
https://hydrogenaud.io/index.php?topic=120166.0 +more tests

You'll find listening tests on HA that Opus isn't definitively better than (HE) AAC, like:
- HE-AAC 43kps (FDK-AAC) comes close to Opus 43kps 
- https://hydrogenaud.io/index.php?topic=121155.0
- AAC  269kps (qaac) matches Opus 300kps 
- https://hydrogenaud.io/index.php?topic=119424.0

For quality, you really only need to care about qAAC & FDK/FHG.

Opus is quality-restrained at high bitrates since due to its low-delay design, for telephony purposes.

## Opus and FOSS

[LC-AAC patents expired](https://hydrogenaud.io/index.php?topic=118084.msg976728#msg976728) and HE will follow soon. FDK-AAC (available under a custom license) while not as good as qAAC, is close in quality. AAC in general is faster to encode & more compatible if you care about these properties.


Opus now has a [patent pool](https://en.wikipedia.org/wiki/Opus_(audio_format)#Patent_Claims) anything, but all open source software is still exempt from royalties.

But end-users don't care about open source, they just care about quality.

## Conclusion

Opus is really only suitable for low bitrates (AKA <100kps for stereo) due to its design contraints for LQ hardware devices. At higher bitrates, other codecs likely match or exceed the quality of Opus, without the many drawbacks of Opus.

You need to test at the bitrate you are using. You cannot extrapolate results past a range, since the behaviour of codecs change and one could overtake another. Opus' features (or lack of) at a certain range is going to impact the quality.

IMD
https://hydrogenaud.io/index.php?topic=116677.0

XHE 32kps https://hydrogenaud.io/index.php/topic,120997.0.html

XHE 96kps https://hydrogenaud.io/index.php/topic,121099.0.html





Opus was designed as a voice codec. Forced SRC and load latency, and to lack of SBR and PS means it's always at least 10 to 20% worse than it could have been. Means it's not optimized for music and it's another 10% penalty especially for lower tracks.



Compared to opus, the aac family may have improved compatibility &/ quality. So unless you have a specific bitrate or application, and you have tested in that specific situation, then Opus likely not be the best solution for you. AAC & vorbis for medium to high bet rates for music and program material.

Many people would automatically choose Opus since it's newer and more "open", but neither are particularly meaningful to quality, especially when Opus is tested.


