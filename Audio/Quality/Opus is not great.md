# Opus is not that great

## Introduction

Opus has been touted as a general-purpose audio codec which can scale to all bitrates. There's a famous graph floating around. However, Opus was primarily designed as a low-latency voice codec for low-quality hardware, with music as an afterthought. There might be [commercial stakeholders](http://web.archive.org/web/20240519150254/http://www.h-online.com/open/news/item/IETF-working-towards-royalty-free-audio-codec-859394.html) . As a result, we shall see below that several deliberate design features (or lack of) reduces the quality of Opus, particularly for music. And Anyone who's done any actual listening tests, may find that existing codecs might be better (depending on the bitrate).

## Opus and FOSS

Just because Opus is open-source it doesn't mean it's "completely free".

Opus now has a [patent pool](https://en.wikipedia.org/wiki/Opus_(audio_format)#Patent_Claims) anything, but all open source software is still exempt from royalties.

[LC-AAC patents expired](https://hydrogenaud.io/index.php?topic=118084.msg976728#msg976728) and HE will follow soon. FDK-AAC (available under a custom license) while not as good as qAAC, is close in quality. AAC in general is faster to encode & more compatible if you care about these properties.

Also, being free doesn't necessarily mean anything about quality. And this is meaningless to end-users.

## Forced resampling to 48k

Opus has forced resampling to 48k apparently to compensate for cheap hardware that works better at 48k. One could logically assume that increased sampling rate means there are more samples to compress per unit time. Frames are a fixed size, so each frame gets less bitrate.

I have done tests at 32kps for Opus vs HE-AAC, and reducing the sampling rate from 44khz to 32khz does indeed reduce artifacts and increase quality. The same claim is said when exhale XHE-AAC is [compared against](https://hydrogenaud.io/index.php/topic,120936.0.html) Opus at bitrates around 60-80kps.

However, reducing the sampling rate in Opus isn't possible, unless you build it yourself - something out of reach for most users. So due to forced resampling, Opus is slightly worse than it could have been at low bitrates.

## Cutoff at 20k

Due to the maximum cutoff of Opus at 20k, regardless if the bitrate is increased, it's not great for archival and editing tasks. Again, this is since Opus is optimized for LQ hardware. Unfortunately, many people are using Opus at mid-high bitrates for archival. AAC (assuming a decent encoder) at >=200 kps would be better.

## Opus takes longer to encode & decode
Encoding Opus is typically longer than AAC.

Decode times takes [about 5x longer](https://forum.doom9.org/showpost.php?p=1849225&postcount=19) . This isn't an issue on desktop, but on mobile where battery life matters, Opus might take more battery to decode since phones might not have hardware Opus decoding AND Opus takes longer to decode in software.

If encoding and decoding takes longer for little (if any) benefit, depending on bitrate, one must wonder why they're using Opus at all.

## Compatibility issues

Since Opus was launched in 2013, but AAC was launched in 1996 (the HE profile from 2003), you will find that less devices & software support Opus, particularly standalone devices like TVs, and editing software.

Opus may have issues with mkv: "Opus doesn't play well with mkv and can throw sub timing off. It also only has benefits at low bitrates when nobody should be encoding at under 128k in this day and age... it's not a good idea for anyone to start encoding anime in Opus." -kuchi on AB

Opus may have problems seeking: "lack of keyframes in Opus and the 'solution' in form of preroll (i.e. 'decode certain number of audio frames before the needed one and discard them'). And not all containers support that feature." [Kostya](https://codecs.multimedia.cx/2015/01/) 

## Opus doesn't have SBR for music

Spectral Band Replication is a technique for improving efficiency at low bitrates. Rather than storing the high frequencies directly, a description of how to approximate them from the lower frequencies is stored as side data. HE-AAC is the earliest form of SBR with a fixed SBR point. Later implementations found in XHE-AAC, DDP, and AC4 have a more flexible SBR point.

However, Opus [does not](https://en.wikipedia.org/wiki/Spectral_band_replication) use SBR. "Opus's CELT part performs spectral folding on the MDCT bin level, making it a far less advanced but lower-delay technique compared to SBR" . So again, Opus is optimized for voice, and this impacts music quality at very low bitrates. At very low bitrates, Opus produces distortion which [may sound worse](https://hydrogenaud.io/index.php/topic,115745.0.html) than HE-AAC, and I have confirmed with my own testing at 32kps. So at very low bitrates, HE-AAC with its full SBR implementation is competitive.

## Opus doesn't have PS for music

Parametric stereo is another technique for improving efficiency at low bitrates. Rather than storing 2 stereo channels directly, PS works by storing a mono sum, then side data to steer and decorrelate different bands to produce a pseudo stereo image. It has been claimed the sweet spot for PS in AAC is 12-24 KPS.

However, Opus has no such feature and at 12 KPS, stereo music is [quite mono](https://www.youtube.com/watch?v=f-_6XEmiGNc), completely destroying the spatial quality and sounding very much like telephone quality hold music, quite in line with the design aims of the codec.

## XHE-AAC may be better for very low bitrates

If you're looking at quality for very low bitrates (12-32kps), it would be worth looking into XHE-AAC. [Tests](XHE 32kps https://hydrogenaud.io/index.php/topic,120997.0.html , that XHE-AAC strongly outperform Opus at very low bitrates. The quality is higher, but the compatibility is lower. XHE-AAC is [supported](https://en.wikipedia.org/wiki/Unified_Speech_and_Audio_Coding#Compatibility) in Android 9, iOS 13, Windows 11 2022, MacOS 11 Big Sur, and foobar [with plugin](https://www.foobar2000.org/components/view/foo_pd_aac) .

Encoding XHE-AAC can be done with ittiam's libxaac https://github.com/ittiam-systems/libxaac , exhale, and poikosoft [EZ CD Audio Converter](https://www.poikosoft.com/music-converter) . exhale is the most-tested of the free software.

Also, At (very) low bitrates, some people may disprefer the artefacts Opus makes in contrast to vorbis due to the default prime-ish framesizes, optimized for hardware devices.

## Opus low-bitrate quality does not scale to high-bitrate quality
This graph has been shown a lot of times : https://opus-codec.org/static/comparison/quality.png 
But Several tests by users have shown that vorbis & AAC beat Opus at high bitrates:

AAC 128kps (qaac) might beat opus 128kps AAC
https://www.zupimages.net/up/20/45/01gw.png
https://hydrogenaud.io/index.php?topic=120166.0 +more tests

You'll find listening tests on HA that Opus isn't definitively better than (HE) AAC, like:
- HE-AAC 43kps (FDK-AAC) comes close to Opus 43kps 
- https://hydrogenaud.io/index.php?topic=121155.0
- AAC 269kps (qaac) matches Opus 300kps 
- https://hydrogenaud.io/index.php?topic=119424.0

For quality, you really only need to care about qAAC & FDK/FHG.

Opus is quality-restrained at high bitrates due to its low-delay design, for telephony purposes.

## Conclusion

Opus is a "newer" and more "open" codec, but neither are particularly meaningful to quality, especially when Opus is tested. You need to test at the bitrate you are using. You cannot extrapolate results past a range, since the features and behaviour of codecs change according to bitrate.

Due to a design priority as a low-latency voice codec for LQ hardware, several features impact music quality. Forced SRC & cutoff, and lack of SBR & PS (technologies about 10 years earlier) are evidence that music was not a priority. As a result, this reduces the practical benefit of Opus.

At 50-150 kps for stereo or 25-75kps/channel, Opus probably has a small 10-20% advantage, but those advantages quickly go away if you have compatibility or other concerns. At the lower end, you can replace with HE-AAC for increased compatibility (and slightly lower quality) and at the upper end, replaced with LC-AAC or vorbis for negligible perceptual difference. Outside that range, the AAC family is definitely better quality. 

## Appendix - Encoding AAC

The best free AAC encoder is [qaac](https://github.com/nu774/qaac/releases) . But it may be tricky to get working since you also need a [coreaudiotoolbox dll](https://hydrogenaud.io/index.php/topic,85135.msg1056382.html#msg1056382) .

If you can't get that working, there's Fraunhofer/fdk_aac which is the next best thing, but is only found in specific FFMPEG builds, like [here](https://github.com/marierose147/ffmpeg_windows_exe_with_fdk_aac/releases) or [here](https://github.com/FT129/Handbrake-and-FFmpeg-with-fdk-aac/releases/tag/ffmpeg4.4) . You need to specifically choose fdk_aac as codec. [More info](https://wiki.hydrogenaud.io/index.php?title=Fraunhofer_FDK_AAC)

If you put the following in a text file, then save with a bat extension, then you can use it as a droplet (drag and drop onto) to encode HQ AAC.
```
ffmpeg -i "%~1" -c:a libfdk_aac -vbr 5 "%~n1.m4a"
pause
```

For HE-AAC, you can try the below:

```
ffmpeg -i "%~1" -c:a libfdk_aac -profile:a aac_he -vbr 4 "%~n1.m4a"
pause
```

IMD
https://hydrogenaud.io/index.php?topic=116677.0
