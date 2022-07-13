# Kantai Collection Mashups Mixing Notes

## Aya Suzaki, 烏屋茶房 - Neguse-Tameshite Mite mo

### Concept

So I decided to get a bunch of KC songs so I can make mashups. Basically the character albums. In total, I got about 70 files, or 30 distinct songs (excluding instrumentals). So I have about 40mins to do my initial listening run, listening to both versions & skipping some tracks. That's 1-2m per song. I do 3 things:

- Sortove get familiar with the song
- Try to detect it as another song
- Try to play the melody of the *other* song in my head, while I listen to this song over speakers

I recently did this with the SHNY & LS character singles. Going by the number of mashup ideas I've noted as the production effort, SHNY 2006 is OK since there are a few ones, SHNY 2009 is eh/bad. And even though LS has 12, it's still eh. KC otoh, is good/OK, but it's a bit weird, as if to represent the quirks of each ship. Lemme explain.

* People liek "Teitoku to no Kizuna" (I think it was used for the Hiei YT video) but the intensity varies a lot so it's difficult to put any other vox apart from itself, and have vox & instro balanced. Like, the lyrics & structure are made exactly for that arrangement. Unless you do some substantial editing/spleeter-ing.
* I've already done Miiro & Fubuki mashups, those are mostly homogeneous rock-orchestral songs and "Let's not say goodbye" in a mix. Those 3 were used in the anime, and anime songs are usually sensible & homogeneous. [My previous KC musics](https://hearthis.at/jzgmyrcb/set/kantai-collectionkc-related/)
* A Shigure single was recently released & I like her, but I find the song a bit hard to use & the production sounds a bit cheap/un-cohesive.
* Nagato's image song is good, but there's a lot of double-speed drums in the chorus. Usually that's used to build tension for short sections, but when there's a lot of it in the chorus makes it weird. Also, I think there's a Koto in there?
* There's a few songs which use traditional Asian instruments/have a pentatonic sound like Hana no Nisuisen/Misaki as if to portray a sense of age & time
* There's a few rock-ish songs which might go well with some from MSLN/nanohurr, but they didn't sound that close
* I'm also trying to find an "Endless Story" in there but again, didn't sound that close
* That leaves Yuubari

### Process

"Tameshite Mite mo" is in a familiar modern house style. It sounds similar to "Vanilla salt". I already used that vox with Neguse, so I'll avoid doing that again. So I can try Neguse vox over Yuubari. I used to like Yuubari, but not so much now. But she did get a K2 recently. I guess that "I'm not a weapons freak, I just wanted to collect the best data" finally paid off. Neguse is sung by Aya Suzaki as Tamako from TM. She's voiced [a few ships](https://en.kancollewiki.net/Category:Suzaki_Aya) in KC, but I'm not detecting it as any particular ship since I don't play the game, I don't hear their voice lines, so I don't know their voices/associate it with any particular ship (apart from Kongou dess due to Kongou pak). There's about 250 ships in KC now, so I guess it's surprising to find a VA that doesn't voice multiple ships.

I'm more familiar w/Neguse so the key of Yuubari is changed instead. To match key, Yuubari needs a +3. But that's a big change so you get artefacts. So I have to speed it up to 145 to lessen the artefacts and insert a Disperser to boost the bass phase. Yuubari is 131.997. Usually I round fractional BPMs & it works out OK. But this is one of the times where it's not and there's a slight misalignment as the song goes on, so I have to redo some edits, luckily, it's not too much. There's a bit of noise sweeps & buildups which is a bit inappropriate for this song so I tried to cut it out.

After polarity reverse to get Neguse vox, there's a lot of bleed. I'm trying to use my own tools so I need both FFTMT & upmixV3. For the quiet sections, I manually use exponential fades. Tamako blurting out random words in the bridge is a bit weird. Neguse structure is a bit weird, like, the bridge is *before* verse2. The instro has an annoying piano so I compressed the mids with ReaFIR. A small change in ratio makes a big difference.

I usually do a EQ boost in the mids for vox & EQ cut on the instro to make the vox stand out. But after doing that out of habit, the vox stands out too much, I was thinking of looking at my old notes since I had a similar problem in another mash, but icba & tried the reverse & it worked. There was a lot of small EQ/volume tweaks to balance A/I over the next few days. Elastique soloist speech is an alternative to Pro, but I still used speech since artefacts & formant/sibilance awareness makes the vox stand out, efficient while smooth, is too smooth and dull.  

There's a nice motif in the intro before verse1 which I originally cut out, and also some buildup  pre-chorus. So I used MIDI piano to put some Neguse pre-chorus, and pre-verse motif in the bridge. sfz HS piano would since nice, except there's prolly a bug in my octaver JS so only mdaPiano guarantees the right note. Some delay & reverb were added to blend in. The 2nd part of the bridge I shift the loop up an 8ve to increase intensity in line with the Yuubari. I ul it to HTA, there's some artefacts as usual, I try stereo reduction on the highs, and gating the vox, which have some HF bleed. Overall, it (mostly) fits, but the average vowel length is probably shorter.

## Starlog-Nagato

I said in my previous KC mashup that this song is weird. You can't build a mashup based on only a fitting chorus. And a few months later, it still doesn't (completely) fit. starlog is a good song, but due to the tricky key changes in pre-chorus, I think it's unlikely to find a matching instrumental. I did some detailed chord analysis (but it wasn't that useful in the end) & made 2 changes each pre-chorus so I don't sound like a total noob, but it still sounds bad. The vox also elevates keys during chorus, so I think it's reasonable to shift it down to match the constant-key instro. Vox needs formant control to sound natural. I use TB_voicepitcher since it has CPU gating on silence & non-wet, unlike ReaPitch.

Some light EQ on the instro to help the vox stand out. I initially had upmix then a mch pitching VST on the instro bus for the best theoretical quality since stretching may change phase & upmix doesn't. But after some thinking & working on my pitchshifting doc, zplane is prolly using time-domain stretch instead of FFT. So I can do stereo pitch then upmix. After leaving it for at least a couple of months since july, since I wasn't sure of how to pitch & chord the special post-V2 chorus bit. I later decided to drop that bit since it sounds out of place & there's not really a matching bit in the instro. I quickly finished most of it in Jan 2021. I tweaked the EQ & adjusted the instro level up a bit since due to energy level dropping a bit when the vox drops out in March.

Since this song has some strings, I wanted to upscale it to surround. But there's lots of sectional pitch shifting & piano, which makes it a challenge. If you pitch shift the piano to subtract from the instro (using either TD or FD approaches) it will prolly not work since the phases differ. I tried FFTMT to subtract the piano pre-upscale & add it back to the front post-upscale, and to my surprise, it worked reasonably well.

S: June/July 2020
F: Mar 2021

## Nexus-Mutsuki

So on the day that Osanpo [trailer](https://www.youtube.com/watch?v=LSOFp-KwPzQ) was posted on the sub, I thought of doing a mashup with Nexus. Since the album was already released on the day, I decided to get the album. The web version doesn't have instrumentals, so I used a LQ web ML separator to get one. Should've used a HQ one. Some regerts. Making a DIY aca of Nexus was easy, and so was syncing the mashup for the first part of the song. The chord progressions are simple, and the songs are mostly in neat 8-bar blocks. Actually there's some slight structure mis-alignment throughout, but it sounds OK. I did some re-looping for structure matching & to remove the annoying percussion sound. There is some shamisen, which I tried to turn down with ReaFIR.

During the bridge, there's some tricky key changes in Osanpo so following a past [suggestion](https://old.reddit.com/r/kancolle/comments/h969xe/negusetameshite_mite_mo/fv1xfic/) from u/Ak-300_TonicNato , I inserted some voice lines during the bridge as an energy & space-filler. There's also a voice line at the start, due to timing & structural problem with inserting claris there instead. The VLs are all in order, no K2 lines, library & secretary 1-3. For the trailer, the bass was lacking. The album ver is a bit better, but I boosted the bass anyway.

In March 2021, I decided to do some final checks & export. But after listening to it a few times, I feel there's some timing problems at the end (vox aren't that on time with the instro, but it's fine when I'm mixing. So I try a few things in rough order:

- MP3 (VBR) decoding latency vs FLAC
- FFTMT/surroundlibf CPU reduction on silence vs disabled
- EQ & compressor are 0L but I turned them off anyway
- 48k vs 44k
- Reapitch vs TB_voicepitcher 

It turns out that Reapitch is the culprit (might be related to "ReaPitch/ReaVoice: lower CPU on silence"). Changing algorithms didn't help. I remember a similar problem with DTSnu years ago when an export in Audition didn't sound the same as mixing and but I fixed this in REAPER 4.15 in the past with "Inform plugins of offline rendering state" unchecked. I guess I forgot to do that for 4.52.

After unchecking that, the vox are in time (I can change to Soundtouch instead of Elastique to save CPU), all is well, except for the other projects I need to re-export due to finding out this bug.


### Quality

I saw Mutsuki's VLs have a cutoff of 12k, & I thought it was LQ. The bitrate is around 75kps. The ogg vorbis has a date of 2015 on wikia, but phase 2 was 2018 so I wondered if there's better versions for the web game. I also remembered there's a PS Vita version which might have better audio & there's a few references of on the wiki, but it'll prolly be a massive hassle to extract anything, esp if it uses a ATRAC codec. Then I remembered I was linked Kumano's battle call on DC, & that goes up to 16k, so I guess the vorbis clips are OK quality. So I applied some of my FFTMT noise control/gap filler & some EQ to boost quality.

There are some later clips like Mutsuki's 5th anniversary & Shigure's spring 2020 event, those are suprisingly lower quality at 56kps mp3, and you can hear the chirping artefacts. So I guess the vorbis ones really were better.

## Secret of my Heart-Haruna

So on the day that [HNJ trailer](https://www.youtube.com/watch?v=mu2oWcoXn0w) was posted on the sub also, I thought of doing a mashup with "Secret of my heart" due to the chords in the chorus. I also searched 榛名の時間 on YT, and apart from the songs, it gives results for bike riding on what I presume is Haruna mountain. I guess it gives new/old meaning to riding on Haruna since Haruna (ship) was built &/ its implementation in KC. 

As for the mashup, Unfortunately, the verses don't match so there's a lot of cutting there. There is also a mode difference, clip pitchshifting on vox. There is a dedicated zplane retune track for a crucial note which occurs a few times.

There's several key changes in HnJ so I use clip pitchshifting to undo that/fit to SomH. The instrumental bridge in HNJ fits the vox bridge in SOMH quite well, except for the end where retune was used on a crucial part. I shortened the outro of the instro. And used the BVs from the start of SOMH + reverb to fill the space (section
, no loop, extend).

At the end of The refrain, there is a part that is a 5th out of key, since if it was in key it would sound worse due to lots of shifting.

I originally used RX7 vox for SOMH. But that's not enough vox isolation to be convincing on the quiet parts. I now have vox by vocal-remover 4, MGM 44k model, but sometimes too much isolation (missing vox). So I need to fill in missing parts with FFTMT in gap-filler mode & some reverb. The vox & instro have high DR, and there's balance problems, so I use compressor on both. Still some balance problems, but hopefully better.

Due to Mutsuki mashup experiments above, Soundtouch is the exclusive pitch shifter for this project. But it doesn't handle cuts well, so I need to audition each cut in the vox & instro and make micro-fades to smooth them.

In 2022, I can now use some more ML implementations. I initially tried Demucs3. Since I can run it myself, it's reproducable.  But the quality isn't good enough as there's still some drum bleed in the chorus. MDX B is better overall, but imparts some drum bleed in arbitrary places. I also redid some fades at the end to sound better. SN said that the song was lacking bass, so I did a 1dB bass boost.

