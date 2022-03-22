# UHD BD Audio and Video survey

## Introduction

Note that there are duplicates in my sample, so the number of unique titles is about 500. And my sample represents a western movie collection so the true value may differ.

## Statistics

### Color Format
- Dolby Vision: 142
- HDR10: 910
- Other: 51
- BT709: 21
```
DV   : ||||||. (12.9%)
HDR10: ||||||||||||||||||||||||||||||||||||||||| (82.6%)
Other: ||. (4.6%)
```

The majority is in HDR10, with a minority in DV, or other. It's probably very easy to convert BT709 to BT2020, encode in H265 10bit, and then slap a HDR10 label on it. Which is probably done for most back catalogue titles. So not really an improvement over a regular BD, apart from maybe banding. DV has multiple profiles, and some allow for dynamic metadata. DV represents an increase in workflow complexity, so you should hope for more impressive HDR.  Although there are exceptions. Like DV titles that are unimpressive, or HDR10 titles that look good.

### Sound Format

- Dolby Atmos: 649
- DTS-X: 146
- Other: 306

Most UBDs use DA as their (3D) sound format. Many don't use either, but use 5.1 (due to being back catalogue), or 7.1.

### Average Length

### Average Dolby Atmos elements

- 12: 362
- 14: 163
- 16: 124
- avg: 13.25

Elements is defined as dynamic objects + 1 for the static LFE bed. 12 is the default for spatial coding elements in Dolby Atmos Mastering Suite so not surprising to see 12 as the most popular. Due to duplicates, the true average elements may be slightly higher, but the true active elements is certainly lower, since some titles are "Dolby Atmos", but upmixed to a static 7.1.2 bed from 5.1 or so for a variety of reasons, including lack of source, or studios being lazy.

us:
jp:

Japan OTOH, cares about quality so their average is a lot higher at almost 16.

## Foreign dub format:
THD Atmos (2nd):9
DTS (2nd): 645
DDP (1.5nd): 119
AC3 (2.5nd): 1675.5

Method: foreign dub is defined as:
- 2nd THD Atmos track, since 1st THD Atmos track is likely the primary English dub
- 2nd DTS track, since 1st DTS track is likely a DTS-HD primary English dub
- 1.5th DDP track, since there are a few BDs with DDP English track
- 2.5th AC3 track, since 1st AC3 track would be the legacy stream in  THD Atmos, and some have a duplicate legacy track, or English commentary/EAD.

Some BDs use DTS 5.1 for foreign languages, followed by DDP 7.1 in 3rd, but by far the most common is AC3 5.1

## Questions

### Do longer movies have more elements?

### Do higher max br movies have more elements?

### Do DV movies have more elements?

### Do good DA movies have more elements?

Let's have a look at some good DA movies according to critics, and their elements:

- Fury: 12
- Overlord: 12
- The Meg: 12
- Blade Runner 2049: 12
- Kong Skull Island: 12
- Midway: 12
- Mission Impossible Fallout: 12
- John Wick 3: 16

The average is: 12.5, which is lower than the average for all movies, but due to the small sample size, I would say good DA movies probably don't have more elements.

## Conclusion and recommendations
To Dolby: perhaps increase the default spatial elements to 14. For DDP, the AC3 core & surround extension can be reduced in bitrate since they're not used for Atmos decoding, so that the overall stream size can be reduced.
