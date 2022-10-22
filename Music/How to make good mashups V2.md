# How to Make Good Mashups V2 (Now with chord theory)

Introduction
---
A mashup is a popular way of simultaneously combining 2 songs. It should be made by overlaying acapella vocals of one song, over an instrumental of another song. There are other mashup structures, but they are harder to execute well. This guide has been revised a few times (V2 in 2020, V2.2 in 2022) and draws on my experience of several years & many mashups. Aim to complete no more than 1-2 per week, as this allows time for review & reflection.

Prerequisites
---
What do you need?

* Solid ideas. Ideally, the 2 songs would be within 10% of the same BPM & key. Otherwise, digital pitch-time shifting artefacts will start getting audible.
* Solid software. You will need to find the BPMs & keys of both songs so that you can later match them. You'll also need production software. See my [Mixes guide](https://github.com/junh1024/junh1024-Documents/blob/master/Music/How%20to%20make%20good%20mixes.md#software) for more information.

Sources
---
Ideally, you have a studio acapella and an instrumental. Stems or MT are the best, but rare. Surround mixes are usually better than stereo but most aren't ready-made A+I so will need some processing before it's usable. You can get cover sterms from www.karaoke-version.com and www.jamkazam.com . You can make a DIY acapella if you have a full song + instrumental. iTunes and Amazon music stores often have karaoke covers with instrumentals so you can make a DIY acapella, as well as get an instrumental. To get more out of an instrumental, you can use [ReaFIR](https://www.reaper.fm/reaplugs/#tour) or freeform FFT imagers like [Mashtactic](https://quikquak.com/Prod_MashTactic.html) . Recently, there are some ML solutions. They can vary a lot, and should be last resort.

Philosophy
---
Generally, I listen to a song & if I think it sounds similar to another piece in terms of instrumentation, arrangement, melody, or chord progression then I'm inspired to make a mashup. It's done on a musical basis, not on a marketing (similar names) or convenience basis. I don't batch-analyze a bunch of songs for BPM & key and then pick 2 that are similar to make a mashup (aka mashup factory). And I avoid making reverse mashups (ie, same songs, but switching vocals for instrumental to get a new deliverable), since 
it's low-effort. If I'm doing a switch, I also change a song. Your philosophy may differ.

I'm not fan of mashups that switch vocals frequently. It's distracting, and potentially shows lack of skill if you switch vocals on a tricky section. Mashups that use 1-2 full sources will likely fight with one another.

Maybe about half my ideas are successful, the others may not work due to large differences in key, tempo, arrangement, or tricky chord progressions. But I do enjoy listening to most of my mashups, and the songs I used.

I analyzed the stats of 25 mashups up to 06.2020, and the average years for the vox & instro were 2001 & 2006, but the average difference is somehow 6. The medians are 2001, 2008, and 4 (median difference)

Planning
---
You may find it helpful to draft your mashup in a DJ program, say, Traktor before committing in a DAW. I used to do this, but realizing your idea in a DAW isn't that much slower. 

You will need to match the BPMs of both songs. We assume both songs have a constant BPM. If they don't, you'll spend much effort conforming one to a constant BPM, or warping the other to be non-constant. REAPER V6 introduced a [new item warping](https://www.reaper.fm/v6img/itemwarp.gif) mode.

As the BPMs of both songs are probably different, you will want to reconcile them. Vocals are more conductive to changes, but sometimes I change the instrumental instead, due to constraints (e.g, an in-memory acapella), or to match my artistic vision (e.g, I'm familiar with the vox/song so any change in key sounds bad).

There are several valid methods. You can:
1. Use the BPM of the acapella (perhaps due to a in-DAW DIY acapella)
2. You can take an average of both songs, then round to the nearest integer (to balance the artefacts of instrumental & acapella)
3. A 2/3 bias towards the instrumental (since shifting the instrumental rather than the acapella results in lower quality)
4. Use the BPM of the instrumental (perhaps due to stems, since pitchshifting many tracks is CPU intensive)

Keep in mind lower pitch=slower tempo=natural, in line with varispeed results. 3 usually results the best quality. The limitations of 1 & 4 can be overcome with using varispeed on the clips, then routing to a bus then correcting with pitchshifting. I don't have any other specific advice for keys apart from it should sound good.

BPM Temp
---
The acapella is usually the most recognizable element in a mashup, so keeping its pitch is suggested. It's possible to maintain pitch of the acapella while maintaining quality for the instrumental.

1. Shift the pitch of the instrumental to match the acapella
2. Adjust the speed of the instrumental by 5.6% for every semitone you shifted it (average, over the whole instrumental). This could be 0, if there was no change in pitch, and it could still be 0 if the pitch changes cancel out (like, +2st & -2st). We are effectively doing varispeed stretching on the instrumental. Note the BPM of the instrumental.
3. The ideal BPM of your mashup is now between the current BPM of your instrumental & the BPM of your acapella.
4. Set the BPM of both instrumental and acapella partway between both these numbers. You want to bias it towards the instrumental since stretching instrumentals is more likely to produce artefacts. If the acapella sounds too awkward, set it to about halfway.
5. If the pitch shifting quality is still too low, shift the acapella 1-2st towards the pitch of the instrumental (I hope I’ve got the maths right), and go back to step 1.

Starting
---
Insert media into your DAW. Set appropriate volumes for both. Loudness statistics are a good rough guide to matching, but should not trump your ear/brain. Set your project and clip BPMs. Beat align your 2 songs. You should Have at least 2 beats of Silence before your mashup starts.

Match the keys of the songs. You're allowed to make fractional pitch changes to either track to make them more cohesive, or make manual block pitch changes to make certain words or sections, etc more on-key.

Many noobs, after basic matching above then call it a day, but it's far from it. You need to match the song structure of the 2 songs, as they differ. Turn on snapping. You will be cutting by beats & bars now. The verse of the vocal should match the verse of the instrumental, etc. Cut both as appropriate. Match the intensity of the acapella song for variety & contrast (otherwise you'll have no breakdowns, etc). If there are instrumental breaks in the instrumental, you may need to add vocal fills/samples from the acapella to keep the energy up. If there are missing parts in the instrumental (like pre-chorus, or bridge), try to grab loops from elsewhere &/ use MIDI production.

You can do your editing in multiple passes. Like, do a quick 1st pass to match the basic structure, then do a more detailed 2nd pass which matches the chords better (see later). The pre-chorus & bridge are often the hardest parts for a mashup, followed by the verse. The chorus is often the easiest part since they may use common chord progressions. If you can't match the pre-chorus, you can cut it out, but if you can't match the bridge, it'a a big deal as it can make or break a mashup. It's almost necessary to have a bridge in a pop song since it offers a welcome break in intensity &/key.

A quick & effective way to edit, especially for unfamiliar songs (I do this to realize an idea I have in my head, that 2 songs (should) go together well), is to slice up the instrumental into loops of compatible chord progressions, of varying (musical) intensities. Extend the loops to cover various song parts, increasing intensity from verse to chorus, and from start to end. This ensures some variety. Short & sweet > long & bad.

If your source(s) are non-constant BPM, cut them into clips of 8-16 bars long and then stretch until each clip aligns with the beat grid of your DAW.

There are multiple methods for the arrangement of the mashup:

1. Acapella master sync, cut the instrumental
2. Cut both to fit each other and remove gaps
3. Instrumental master sync, cut the acapella

I would reccommend 2 for beginners. 1 & 3 are beneficial if you want to pair your mashup with the video of the acapella, or instrumental (perhaps AMV) afterwards. You can just set the appropriate rate & delay, and mux your video losslessly with mkvnix. Speeding up video isn't a problem, since it will appear smoother. But slowing down 24fps videos may noticably add stutter.

Chord theory
---
Knowing chord theory is not required to do mashups, but it will help you to make better mashups. This guide uses my [Shorthand Relative Chord Notation System](https://github.com/junh1024/junh1024-Documents/blob/master/Music/Shorthand%20Relative%20Chord%20Notation%20System.md#shorthand-relative-chord-notation-system) so please read that beforehand. Chord theory is useful about 25-50% of mashups where the chords don't match and they don't sound good by structure matching only.

### Chord matching
Chord matching will make your mashup more seamless. When the chords in the instrumental are closer to the chords in the acapella, your mashup will seem more like 1 song, rather than 2.

Chop up your instro into clips/bars of chords, and match the chords of the instrumental with the chords of the acapella (full song of the original). But, restrict yourself to the current section. Like, only match chords of the verse in the acapella, with chords of the verse in the instrumental. This is to make the intensity in each section consistent. Pre-chorus can count as verse if you can't find matching chords.

### Chord shifting
Sometimes you may need to pitchshift clips to get the right chord, because the wanted chord is not available in the original.

Say you have chords 1,2,4,5,6 but you want a 3. Since 3 is minor, you know to pick 2/6 (which are minor) & shift to make a 3. But if you wanted a 3M, you'll need to pick from the major chords of 1,4,5.

### Chord substitution
For times when shifting doesn't sound good, maybe due to synths making whacky chords or polyphony, you may need to substitute. Here are 2 approaches:
- Analyze the dominant note in the melody, and choose a chord which has that note, ideally not in the bottom position. You can try 7ths. Sounding good is idempotent.
- Choose a chord which is a 3rd apart. e.g, instead of 6, choose 4 or 1. Sounding good is not idempotent since performing multiple substitutions like this will sound bad.

Chord Progressions
---
Now that you've changed one chord, you may need to change other chords & follow some conventions so that they don't sound bad. According to https://tobyrush.com/theorypages/pdf/en-us/harmonic-progression.pdf ,

* any -> 1 -> any
* any -> 5

Choose whatever sounds good. But with all this theory, you might just choose a loop and use that without any analysis in practice, since even if the chord doesn't match the original, it sounds more natural to have chords change at the same rate throughout the song.

Scale shifting
---
You can use zplane ReTune to shift notes in a chord, but I more often use it to change modes. e.g, change a major vox to fit in with a minor instro, but only for a short periods with the wet/bypass feature in my DAW. It's a small, but very important change to keep things on key/on-mode.

Pitchshifting Tips:
---
* You can change your pitchshifter/settings & balance sound quality & CPU.
* Elastique V2 is a HQ general-purpose shifter w/medium CPU use, and standard across many DAWs. DAW-specific algos such as AL's "Complex Pro" might suck. Elastique is available as VST if you need it.
* Elastique V3, may be available if you upgrade your DAW. It's better for greater shifts & uses less CPU.
* Elastique Soloist Speech for vox & Elastique Efficient on instros can work well for small shifts to save CPU. Elastique Soloist Speech may do some internal formant correction. If speech has blips due to instro bleed, try efficient instead.
* Soundtouch should sound good on vox, and might sound OK on instros. Watch out for blips.
* Pitchshifting vocals require formant awareness/control for >1st changes to sound good.
* Pitchshifting changes the frequency distribution, so you may need to EQ, kilohearts disperser (to shift the phase of the bass & hence boost the kicks), (rhythmic) distortion to compensate
* Elastique Pro Preserve Formants is good for larger changes on vox. It can also be good for larger changes on instros @ PF high frequencies as a high-CPU alternative to an EQ boost.
* You can gain more control by using varispeed on your stems then inserting a pitchshift FX on your tracks. But this requires carefully doing pitch maths on your part. speed * 1.059 (or 12th root of 2) = +1st, since 2x speed = up 12st or 1 octave.
* If you have stems, separate unpitched (percussion) & pitched (others) instruments. Then you can apply separate time-pitchshifting settings to each to make both more natural. Like, varispeed for percussion & elastique for pitched instruments.
* It may be helpful to read [how pitchshifting works](https://github.com/junh1024/junh1024-Documents/blob/master/Audio/How%20Pitchshifting%20Works.md#introduction)
* RPR (earlier versions?) may have a bug with rendering & PDC. Please disable "Inform plugins of offline rendering state".


General Tips:
---
* Lead vocals should be narrow. Widening instruments can sometimes help contrast.
* Vocals should not face an uphill battle with the instrumental, nor should it overpower the instrumental.
* To make your vocals stand out more, analyze it via FFT, and EQ boost a dip >3k. Cut the dominant vocal frequencies that you found in the instro (prolly <3k). This isn't just good advice for mashups, this is good advice in general. If it stands out too much, do the reverse. If the instro has an annoying synth, compress the mids with ReaFIR.
* You may need to apply (long-term) compression to vocals &/ a bit of reverb to hide artefacts
* You can insert elements of each to have a more elegant mashup. If stems are not available, don't be afraid to make some MIDI snippets. If the song of the acapella originally had a silence, silence the new instrumental for a few seconds. Same goes for EQ cuts, fades, etc. This adds variety & familiarity.
* After a few jobs, you'll inevitably encounter Tricky chord progressions. If all else fails, you could try having a different instrumental for the verses & the chorus.
* If you find, after matching pitch, EQ, loudness, 2 musical elements aren't cohesive (this is more applicable to mixes), maybe it's an imaging problem. You may need to make their widths more similar or dissimilar. A (multiband) width tool may be useful.
* It is possible to make surround mashups. Most of mine have been upscales (upscale A & I separately, with different settings). Surround upscales, particularly with mashups, mostly sound bad depending on how well the instrumental upscales. For it to sound good, you will prolly need at least stems for the instrumental. For best quality, you probably want to varispeed the tempo stretch, then upscale to surround, then use a surround pitchshifter (e.g, Elastique VST).
* Layer clips if you're short on ideas for ending.
* Sectional/clip filtering is good.
* If you've matched the pitches of A & I, but it still sounds bad & you don't know why, maybe it's a 5ths trap (they're a 5th apart), or it's possible A/I have shifted keys, particularly in the (pre) chorus.
* In Traktor, fractional BPM with a deviation of 0.001 to an integer can usually be rounded & ignored. But if it's 0.003, maybe it's right

Video
---
If you've kept the arrangement of the acapella with instrumental as above adding a video will be easy. This section covers this case and results in a quick process with no quality loss. We assume you have downloaded a music video which matches the arrangement of your acapella/instrumental, and from a site such as YouTube. You will need MKVtoolnix.

If you have made an arbitrary arrangement for your mashup, then you may need to make a dedicated video in a video in a NLE. If stretching video in Vegas, uncheck "resample frames" to avoid blending. 

1. Insert the video in your DAW. If you're having trouble, extract/convert the audio so that it's accepted by your DAW. Quality doesn't matter, this is only for sync purposes. 
2. Set the BPM of your video to your mashup BPM 
3. Trim & Align the audio of the video to your mashup such that the video starts at time zero in your timeline. If the video starts before your mashup audio, that is fine. 
4. Note the "start in source" time for the video, and convert it to milliseconds
5. Mute the video in your DAW
6. Export the mashup audio from your DAW to a file
7. Open MKVtoolnix GUI
8. Insert the video into mkvmerge, but uncheck the audio afterwards
9. Insert your mashup audio from the step 6
10. You will need to get the rate of the video from your DAW. If it doesn't, Rate = mashup BPM/original video BPM. Then divide 1 by this number.
11. Select the video track in MKVtoolnix GUI
12. Insert the value from step 10, into the "stretch by" field of the video track
13. Multiply the value from step 4 by the value in step 10, and insert this as a negative value in "delay"
14. Start muxing
15. Watch & test your video

You now have a video file with no quality loss of an arbitrary fps. Not sure what happens when those get uploaded to a video site.

What next?
---
After you have followed these instructions, you should have a mashup of minimum quality. Making mashups of modern/EDM (2015+ stuff) is easy because it sounds very samey. For a challenge, try some stuff from 2000s or older.

A [mix](https://github.com/junh1024/junh1024-Documents/blob/master/Music/How%20to%20make%20good%20mixes.md#introduction) is where the songs are sequentially combined. Sometimes, a it's better for songs which otherwise a mashup would be hard or unsuitable, or for combining songs of similar moods, key & BPM. Sometimes, it's easier & requires no stems, but a few cuts. Sometimes, it requires advanced techniques such as MIDI-powered vocal pitchshifting. I've done both and none is definitively better or worse. But, mashups focus on compatibility, while mixes focus on consistency.

Retrospective
---
Over the years, I've improved my mashups in these aspects. Most of these techniques are documented above.

1. Use of chord theory to make mashups more correct and seamless
2. Use of ML extraction to open up more mashup possibilities
3. Use of ML stems for better surround
4. Use of partial or full MIDI for better/more mashup possibilities
5. Use of additional samples/arrangement to fill time
6. A weighted approach to project BPM instead of binary/simple average approach for better audio quality
7. Master sync is the stretched acapella, which allows for easier video marriage
8. Increased use of open-source plugins
9. Silence at the start for better mastering compliance
