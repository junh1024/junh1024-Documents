﻿# How to make (good) mashups V2 (Now with chord theory)

Introduction
---
A mashup is a popular way of simultaneously combining 2 songs. This guide was revised in mid-2020 and draws on my experience of 5 years & 25 mashups. Aim to complete no more than 1-2 per week, as this allows time for review & reflection. What do you need?
* A solid concept. Ideally, the 2 songs shall be within 10% of the same key & BPM, because past 10% of change, digital pitch-time shifting artefacts will start getting audible.
* A solid DAW. REAPER is recommended as you can mix & match files with different codecs, sample rates, channels, and [many ways to change pitch](https://i.imgur.com/FtJAE26.png) & tempo freely with the HQ Elastique algorithm. Video editors & destructive editors (like Vegas & Audacity) are NOT recommended because they won't have subtle features helpful for music (e.g, cutting on beats)

Sources
---
Ideally, you shall have a studio acapella and an instrumental. Stems or MT are the best, but rare. Surround mixes are usually better than stereo but most aren't ready-made A+I so will need some processing before it's usable. You can get stuff from www.karaoke-version.com www.jamkazam.com , iTunes music store, etc. If you want more from an instrumental, (freeform) FFT imagers may help. Recently, there are some ML solutions. They can vary a lot, and is only a last restort.

Philosophy
---
The way I make mashups is that it's done on a musical basis, not on a marketing or convenience basis. e.g, I listen to a song & if I think it sounds similar to another piece in terms of instrumentation, arrangement, melody, or chord progression then I'm inspired to make a mashup & do it on-demand. I don't batch-analyze a bunch of songs for BPM & key and then pick 2 that are similar to to make a mashup. Your philosophy may differ. Maybe about half my ideas are successful, the others may not work due to large differences in key, tempo, arrangement, or tricky chord progressions. But I enjoy listening to most of my mashups/the songs I used. FYI, I analyzed the stats of 25 mashups up to 06.2020, and the average years for the vox & instro were 2001 & 2006, but the average difference is somehow 6. The medians are 2001, 2008, and 4 (median difference). I avoid making reverse mashups (ie, switching A for I to get a new deliverable), cuz I think it's cheap. If I'm doing a switch, I also change a song.

Information
---
You will need to find the BPMs & keys of both songs. I use a DJ app (Traktor) for finding BPM, but there are other methods. For key, I use my ears & brain. Some DJ or library apps (like beatunes) can find key.

Planning
---
You may find it helpful to draft your mashup in a DJ program, say, Traktor before committing in a DAW. I used to do this, but realizing your idea in a DAW isn't that much slower. 

You will need to match the BPMs of both songs. We assume both songs have a constant BPM. If they don't, making a mix will be harder, unless you spend much effort conforming them to a constant BPM. Ableton Live is supposedly good at warping to fit. REAPER V6 introduced a [new item warping](https://www.reaper.fm/v6img/itemwarp.gif) mode.

As the BPMs of both songs are probably different, you will want to reconcile them. Vocals are more conductive to changes, but sometimes I change the instrumental instead, due to constraints (e.g, an in-memory acapella), or to match my artistic vision (e.g, I'm familiar with the vox/song so any change in key sounds bad).

There are several valid methods. You can take an average of both songs, then round to the nearest integer. Or a more complex approach like a 2/3 bias towards the instrumental. If you have a MT or stems, you want to use the BPM of that instead, because pitchshifting many tracks is CPU intensive. Keep in mind lower pitch=slower tempo=natural, in line with varispeed results. I don't have any other specific advice for keys apart from it should sound good. 

Starting
---
Insert media into your DAW. Set appropriate volumes for both. Loudness statistics are a good rough guide to matching, but should not trump your ear/brain. Vocals should not face an uphill battle with the instrumental, not should it overpower. Set your BPM. Beat align your 2 songs, then Match the keys of the songs. You're allowed to make fractional pitch changes to either track to make them more cohesive, or make manual block pitch changes to make certain words or sections, etc more on-key.

Many noobs, after basic matching above then call it a day, but it's far from it. You need to match the song structure of the 2 songs, as they differ. Match the intensity of the acapella song for vareity & contrast (otherwise you'll have no breakdowns etc). Turn on snapping. You will be cutting by beats & bars now. The verse of the vocal should match the verse of the instrumental, etc. Cut both as appropriate. A quick & effective way to do this, especially for unfamiliar songs (I do this to realize an idea I have in my head, that 2 songs (should) go together well), is to slice up the instrumental into loops of compatible chord progressions, of varying (musical) intensities. Extend the loops to cover various song parts, increasing intensity from verse to chorus, and from start to end. This ensures some variety. Short & sweet > long & bad.


Chord theory
---
Knowing music theory is not required to do mashups, but it may help you to make mashups faster & better. This guide uses my [Shorthand Relative Chord Notation System](https://github.com/junh1024/junh1024-Documents/blob/master/Music/Shorthand%20Relative%20Chord%20Notation%20System.md#shorthand-relative-chord-notation-system) so please read that beforehand. We assume you have/can chop up your instro into clips/bars of chords. Sometimes you may need to pitchshift clips to get the right chord, because the wanted chord is not available in the original.

Say you have chords 1,2,4,5,6 but you want a 3. Since 3 is minor, you know to pick 2/6 (which are minor) & shift to make a 3. But if you wanted a 3M, you'll need to pick from the major chords of 1,4,5.

Chord substitution
---
For times when shifting doesn't sound good, maybe due to synths making whacky chords, you may need to substitute. Here are 2 approaches:
- Analyze the dominant note in the melody, and choose a chord which has that note, ideally not in the bottom position. You can try 7ths. Sounding good is idempotent.
- Choose a chord which is a 3rd apart. e.g, instead of 6, choose 4 or 1. Sounding good is not idempotent cuz performing multiple substitutions like this will sound bad.

Chord Progressions
---
Now that you've changed one chord, you may need to change other chords & follow some conventions so that they don't sound bad. According to https://tobyrush.com/theorypages/pdf/en-us/harmonic-progression.pdf ,

* any -> 1 -> any
* any -> 5

Choose whatever sounds good. But with all this theory, you might just choose a loop and use that without any analysis in practice.

Scale shifting
---
You can use zplane ReTune to shift notes in a chord, but I more often use it to change modes. e.g, change a major vox to fit in with a minor instro, but only for a short periods with the wet/bypass feature in my DAW. It's a small, but very important change to keep things on key/on-mode.

Pitchshifting Tips:
---
* In 2015 (but this article was written closer to 2018), Elastique V2 was standard across many DAWs. But if you upgrade your DAW, you may get Elastique V3, which is better for greater shifts & lower CPU.
* Pitchshifting vocals require formant awareness/control for >1st changes to sound good. 
* You can change your pitchshifter/settings & balance sound quality & CPU.
* If you're making small changes, you can try Elastique Soloist Speech on vox & Elastique Efficient on instros to save CPU. Elastique Soloist Speech may do some internal formant correction. If speech has blips due to instro bleed, try efficient instead.
* If you're making larger changes, you may need to use the default Elastique Pro mode (medium CPU) &/ change the formant shift too. Or maybe you can try the different Elastique Pro Preserve Formants variations (high CPU) to make it sound more natural. For large changes to instros, you could try  Elastique Pro Preserve Formants as a high-CPU alternative to an EQ boost.
* You can gain more control by using varispeed on your stems then inserting a pitchshift FX on your tracks. But this requires carefully doing pitch maths on your part.
* If you have stems, separate unpitched (percussion) & pitched (others) instruments. Then you can apply separate time-pitchshifting settings to each to make both more natural.
* Pitchshifting changes the frequency distribution, so you may need to EQ, kilohearts disperser (to shift the phase of the bass & hence boost the kicks), (rhythmic) distortion to compensate


General Tips:
---
* Lead vocals should be narrow. Widening instruments can sometimes help contrast.
* To make your vocals stand out more, analyze it via FFT, and EQ boost any large gaps. Cut the overall vocal frequencies that you found in the instro. Both changes are 1-3dB. Little can be huge (™ spark). This isn't just good advice for mashups, this is good advice in general. If it stands out too much, do the reverse. If the instro has an annoying synth, compress the mids with ReaFIR.
* You may need to apply (long-term) compression to vocals &/ a bit of reverb to hide artefacts
* You can insert elements of each to have a more elegant mashup. If stems are not available, don't be afraid to make some MIDI snippets. If the song of the acapella originally had a silence, silence the new instrumental for a few seconds. Same goes for EQ cuts, fades, etc. This adds variety & familiarity.
* After a few jobs, you'll inevitably encounter Tricky chord progressions. If all else fails, you could try having a different instrumental for the verses & the chorus.
* If you find, after matching pitch, EQ, loudness, 2 musical elements aren't cohesive (this is more applicable to mixes), maybe it's an imaging problem. You may need to make their widths more similar or dissimilar. A (multiband) width tool may be useful.
* It is possible to make surround mashups. Most of mine have been upscales (upscale A & I separately, with different settings). Surround upscales, particularly with mashups, mostly sound bad depending on how well the instrumental upscales. For it to sound good, you will prolly need at least stems for the instrumental. For best quality, you probably want to varispeed the tempo stretch, then upscale to surround, then use a surround pitchshifter (e.g, Elastique VST).
* Layer clips if you're short on ideas for ending.
* Sectional/clip filtering is good.
* If you've matched the pitches of A & I, but it still sounds bad & you don't know why, maybe it's a 5ths trap (they're a 5th apart), or it's possible A/I have shifted keys, particularly in the (pre) chorus.
* In Traktor, fractional BPM with a deviation of 0.001 to an integer can usually be rounded & ignored. But if it's 0.003, maybe it's right

What next?
---
After you have followed these instructions, you should have a mashup of minimum quality. Making mashups of modern/EDM (2015+ stuff) is easy because it sounds very samey. For a challenge, try some stuff from 2000s or older.

A mix is where the songs are sequentially combined. Sometimes, a it's better for songs which otherwise a mashup would be hard or unsuitable, or for combining songs of similar moods, key & BPM. Sometimes, it's easier & requires no stems, but a few cuts. Sometimes, it requires advanced techniques such as MIDI-powered vocal pitchshifting. I've done both and none is definitively better or worse. But, mashups focus on compatibility, while mixes focus on consistency.