# Opus is not that great

## Introduction

Opus was touted as a general-purpose audio codec which can scale to all bitrates. Unfortunately, this isn't really the case, as it doesn't scale to higher bitrates. It also has a few other disadvantages. Opus was designed for HQ playback, at low bitrates, on cheap hardware. Opus was also designed for teleconferencing, so it  low-latency. This also impedes Opus' quality at higher bitrates.


## Possible Mkv sync issues with opus

"Opus doesn't play well with mkv and can throw sub timing off. It also only has benefits at low bitrates when nobody should be encoding at under 128k in this day and age. … it's not a good idea for anyone to start encoding anime in Opus." -kuchi on AB

## Forced resampling to 48k

Apparently it's to compensate for cheap hardware that works better at 48k? You can encode to 44.1k, but only if you use a custom build, ie, something most end-users can't/wont do. Sometimes you just want 44k output (R)

## Cutoff at 20k

Most good encoders raise the cutoff to 21 or even 22k if they think it's appropriate. Most people can't hear above 20k, but some might, and it's better for editing. But you shouldn't be editing a lossy format! Tell that to me when a lossy format is the only version that's available and you need to edit it. This is likely to lessen artefacts due to LQ (hardware) SRC filters.

## Artefacts

Some people disprefer the artefacts Opus makes on LBR content, due to the default prime-ish framesizes, optimized for hardware devices.

## Design & Usage issues

https://codecs.multimedia.cx/2015/01/

## Opus takes much loger to encode & decode
Decode times takes about 5x longer. [link](https://forum.doom9.org/showpost.php?p=1849225&postcount=19)

## Opus is not as compatible as older codecs

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

As for FOSS, [LC-AAC patents expired](https://hydrogenaud.io/index.php?topic=118084.msg976728#msg976728) and HE will follow soon. FDK-AAC (available under a custom license) while not as good as qAAC, is close in quality. AAC in general is faster to encode & more compatible if you care about these properties.

## Conclusion

Opus is really only suitable for low bitrates (AKA <100kps for stereo) due to its design contraints for LQ hardware devices. At higher bitrates, other codecs likely match or exceed the quality of Opus, without the many drawbacks of Opus.

IMD
https://hydrogenaud.io/index.php?topic=116677.0
