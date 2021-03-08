# Kantai Collection Mashups Mixing Notes

## Starlog-Nagato

I said in my previous KC mashup that this song is weird. You can't build a mashup based on only a fitting chorus. And a few months later, it still doesn't (completely) fit. starlog is a good song, but due to the tricky key changes in pre-chorus, I think it's unlikely to find a matching instrumental. I did some detailed chord analysis (but it wasn't that useful in the end) & made 2 changes each pre-chorus so I don't sound like a total noob, but it still sounds bad. The vox also elevates keys during chorus, so I think it's reasonable to shift it down to match the constant-key instro. Vox needs formant control to sound natural. I use TB_voicepitcher cuz it has CPU gating on silence & non-wet, unlike ReaPitch.

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

There's several key changes in HnJ so I use clip pitchshifting to undo that/fit to SomH. The instrumental bridge in HNJ fits the vox bridge in SOMH quite well, except for the end where retune was used on a cruicial part. I shortened the outro of the instro. And used the BVs from the start of SOMH + reverb to fill the space (section
, no loop, extend).

At the end of The refrain, there is a part that is a 5th out of key, cuz if it was in key it would sound worse due to lots of shifting.

I originally used RX7 vox for SOMH. But that's not enough vox isolation to be convincing on the quiet parts. I now have vox by vocal-remover 4, MGM 44k model, but sometimes too much isolation (missing vox). So I need to fill in missing parts with FFTMT in gap-filler mode & some reverb. The vox & instro have high DR, and there's balance problems, so I use compressor on both. Still some balance problems, but hopefully better.

Due to Mutsuki mashup experiments above, Soundtouch is the exclusive pitch shifter for this project. But it doesn't handle cuts well, so I need to audition each cut in the vox & instro and make micro-fades to smooth them.
