# Anime Mashups Mixing Notes 2023A

## Super Duper Love Love Days-Chasse

I initially got the idea for this mashup by listening to Damatto Yasumi Jikan from a lucky star character CD & it sounded compatible with super duper love love days from Cardcaptor Sakura. After partway through editing the mashup, I realised it sounded quite boring due to the instrumental, which is mostly drums, bass, and piano. This is due to the low production values of a character song that's mostly used to fill space rather than being used in the anime. I decided to suspend this mashup and not release it.

A while later, I came across Chasse from Hayate no Gotoku. I know that song since I was listening to a bunch of anison looking for 6/8 or house songs for music mixes, but it sounded suitable for this mashup. Being a song with high production value since it's used in the ending of the anime, it immediately gives the mashup a lot of life and interest. I set about re-editing my mashup.

Chasse begins with a chorus, but super love doesn't, so I need to find a point to cut the beginning of Chasse so that my mashup of Super Love can begin. There are some chords in the chorus of Chasse that don't match Super Love, so I just need to let it play through. Chasse has a hard ending, but Super Love doesn't. Super Love ends on a vocal fadeout, so I need to upmix the vocals to isolate the lead vocals.

ML GAudioLab didn't seem to get all of the vocals in the bridge, so I need to do some clip editing to fill time and energy. From then onwards, it's mostly balancing the vocal with the instrumental. Chasse is quite broadband as an instrumental so I need to boost the vocals around 5K

Chasse has low Dynamics throughout the song, sort of like a house track. But SuperLove is semi-acoustic with noticeable Dynamics throughout the track. I apply some vocal compression to tame the dynamic range, but it would be a bit boring if all the dynamics were reduced so that's why I think it's acceptable in this case to have the vocals be slightly low in the verses.

There was the possibility of doing video sync for this mashup, but I decided not to for several reasons. I had already decided on a surround upmix for SuperLove so maintaining that BPM for the video would make most sense. There are several seconds of mismatch between the starting and ending of my mashup and the original Super Love song so you'd have either silence for Black video. Slowing down the whole mashup to match the original BPM for SuperLove was another option but since Chase is already being pitched up one semitone slowing down further would degrade the quality so I decided not to.

In terms of instrumentation, the 3rd chorus is the same as the 2nd, which is boring. So I carefully sequenced the saw synthesiser from Chasse and bought it into the 3rd chorus. It doesn't cover all of the 3rd chorus, so I need to loop and repeat it.

- Idea: /
- Start:  /2022
- Contest: 22/03/2023 - 28/03/2023
- Finish: /2023

## Last Bullet-Back Again
I got the idea for this mashup by listening to "the last bullet" and recommending "back again" to someone else. Back again is non-constant tempo and fitting the acapella over it didn't work well. So begins the tedious process of conforming it to a beat grid by cutting it every 8 bars or so and stretching it. after that, it was much easier to fit the acapella over it.

### Vox ML
I had issues with the vox not blending in the inst. It had artefacts, but switching ML to MDX from DEMUCS 3 didn't seem to help. It turns out that the inst is narrow in stereo image, but the (BV) vox is quite wide so I narrow it, then it fits in. Its' a rock song, so the vox should be heard, but also blend in at the chorus. 

On earbuds, you can listen closely for artefacts. You can hear bits of Back again vox in the mashup, so I spent some time setting up UVR5 from 5.0.2 (2021) and 5.3 (2022). 5.3 is GUI only, but it uses models are compatible with 5.0.2. Model to JSON association is done via a hash check. The JSONs are identical across the V5. I used the 1st models, which is more suited to inst, but the vox is subtracted from the inst later via FFT to make my own inst, so the result is not identical. The UVR5 aca for inst is worse than the DEMUCS3 aca, since UVR5 is frequency-domain only (even though it has 4 bands & multi FFT size), and DEMUCS3 is a hybrid of time & frequency domain, so it manages to get more harmonics & less artefacts. UVR5 vocal models were not tested.

### Arrangement

The master arrangement for the mashup is the vocal song, since it has a music video. The bridge of back again is looped to fit the timing of last bullet. Since the bridge is extended he should be some cymbals to sound musical. Initially, I tried a Yamaha XG VST, but the pitch & thickness didn't match the original symbols in back again. I also tried the original cymbals from the bridge of back again but, I couldn't isolate them since there's other drum activity going on. The cymbal hit at the end of back again was clean enough, but didn't really fit in the bridge. There's some sibilance from the back again vocals which wasn't completely removed, which do this role and sounds vaguely like hihats. I increase the strength of FFTMT subtract so that it happens only when I want to.

When I was doing some checks, I found that the video didn't line up with the mashup sometime in the middle. I need to extend the post-chorus of back again. When you do this, there needs to be another cymbal hit to sound musical. The cymbal hit is taken from the end of back again. 

### Panning

There is an opportunity to do dynamic panning on the hello hello at the end of the verses. I considered a few ideas, but I remembered that this song is about trains. Trains go in straight lines and shouldn't go in a circle. So the sequence goes from left to right and then back left to back right. These were done with sharp cuts. It sounded a bit abrupt, so crossfades were added & tested as necessary.

The bridge is extended so now it's a bit boring. The solution is obvious. Add a slow left-right pan to the electric guitar. The ending feels like it needs some dynamic panning to supplement the increasing tension in the synth.

I Initially wanted to pan the rhythm guitar every quarter note to different speakers, but this sounded bad due to discontinuity artefacts and difference timbre of my rear speakers. A slower rate of one bar was a bit better. Reducing the stereo width of the pan was even better, but I need something that works in 4ch.

So over the course of a few weeks, I made and tested a new channel correlator tool which bleeds channels into each other and effectively reduces the surround radius. There was a lot of logic involved in making exceptions for the centre and LFE channels while having the volume gains be correct. It's not possible to automatically determine the number of input and output channels you want, so those are manual controls. There is an automatic gain depending on input & output channel count. I would rather the tool turn down the volume by too much than too little. There is an additional manual gain control in case power is lost. You will need to measure the power loss manually. 

After a few weeks of making & testing my tool, I remembered there's already a surround width control in some tool(s) in my suite. But those don't bleed the front into the back, for the better or worse.

Dynamic panning wasn't done for the guitar in the pre-chorus. I tried it but it was a bit of sensory overload and confusing since there was already panning for the vocals and the pre-chorus.



### Surround

Back again has too much rear activity during the verses due to the guitar, and not enough during the chorus. So I need to automate the rear threshold for the upmixer and Link that with additional stereo widening for the chorus. This is also linked to the stereo control & upmixer for the vocals. 

When I played the mix on my surround speakers, I noticed a loss in power during the chorus. To reduce this issue, I set the rear threshold for the chorus to the default. This means I also need to rebalance the parameter modulations that depend on this - the automation changed and so dependant elements need changing if I want the latter to stay the same. I also added some master volume automation to boost the chorus by 1 DB, and cut the pre-chorus by 1dB since the pre-chorus is a bit loud & to increase the contrast. There's still a bit of power loss when the chorus comes but I will just leave it at that since I would need to redo a lot of parameter modulation if I change the rear threshold and I just want to be done with the project.

Initially, I had a compressor on the vocals which turns it down by about 1dB on the chorus. It's losing a bit of expression so I take it off. Verse-chorus automation is available using the rear threshold from the surround upmix, so I can link it to that. With the proper scaling, vocals are slightly boosted during the verses, and dimmed during the chorus. But there is effectively no adjustment since the overall level of the mashup is boosted during the chorus.

Overall, with the mashup, TLB was improved, but perhaps BA was not. Although the chords are different, the illusion is that the chords are a perfect match, since they're similar, and there's frequent changes.


### Video

The beginning of the video is trimmed such that the bullets title card doesn't appear. The end of the video is trimmed such that the credits do appear. so that we can acknowledge the hard work of the creators. But before the Koko's arrival date appears, since that has long passed and is now dated. The ending of the last bullet is much longer than back again and there is no easy way to extend back again without being very awkward, so I must cut the last bullet video.


### Video filtering

I wanted to add a Fade In from Black since the credits end on a fadeout. I measured the fade out and it was about 50 frames, so the Fade In is set to that. There's no built-in fade function, so I need to use external scripts but there were some issues:

- vsutils: didn't work since it seemed to old. 
- muvsfunc: I couldn't get working and it seems to override some built-in functions. It's a [Leviathan](https://github.com/WolframRhodium/muvsfunc/wiki/muvs-tutorial)
- stgfunc: has a deleted transitions module and a Labyrinth of dependencies, so I couldn't get it working, even when downloading dependencies from the era of Nov 2022. It also seems to be very DRY, OO, and heavy on inheritance. 
- vs_transitions: works during the script preview, but when I tried encoding The Script, the encoder just crashed.
- FrameEval: I tried the example, but I couldn't modify it to work with my video clips.

Extracted functions:
- stgfunc: I couldn't get it working.
- muvsfunc: The extracted function from muvsfunc did work.

A Level limiter is applied to the video after the Fade In so that the video & credits conform to limited range. The video is converted to 10bit & denoising applied afterwards, so that banding and blocking is reduced.

My first encode of the script was stopped since a computer turned off so that encode is incomplete. I made a second script with the fade out removed & the script trimmed about halfway so that I could just encode the remainder & join on keyframe with mkvmerge. But this approach didn't work since there was video corruption around the join due to frame reference issues. I guess x265/HEVC isn't stitchable. So I need to encode the whole video again. This obviously worked.

In the end with CRF 21 and $settings , the video track is about 140 MB, which is roughly the combination of the AV1 and h264 video sizes. Even though the video is much bigger than AV1, it's hopefully easier to decode and higher quality than both. The bit rate is about 5 MPS. Lehmer merge was used, but you can still see blocks.

### Lehmer Merge
I asked a question in WA. The situation is thus. I have a YT video which is available in H264 & AV1:
- The H264 generally has small blocks constantly, but no big fails
- The AV1 is generally better, but has some big fails where there's huge blocks

How do I combine them, to have a single "best" video?

LightArrows suggested a Lehmer Merge, "... but you should probably do some additional prefiltering or play around with blurring filters used for the merge to make sure you don't bring over too much crud" . The 2nd part is important.

The old lehmer_merge from https://github.com/Moelancholy/Encode-Scripts/blob/master/Pizza/Urusei%20Yatsura%20(2022)/UY22_01.vpy seemed to do the job, but radius needed raising to 5 to make some gradients smooth. Changing the order of the inputs didn't seem to matter, so it's probably commutative. The call is: clip=lehmer_merge([AV1,H264],5,2)

The new lehmer_diff_merge from https://github.com/Irrational-Encoding-Wizardry/vs-rgtools/blob/master/vsrgtools/freqs.py , the order does seem to matter, and it seems you need to supply your own blurring function. I don't know of a better/faster blur than box blur, so I just used the old one.

### x265 blocking artefacts
I mentioned the [x265 Yuuki-Asuna mod](https://github.com/Mr-Z-2697/x265-Yuuki-Asuna) in WA. But I was warned not to use it since it can cause [big blocks](https://media.discordapp.net/attachments/856406641872207903/990604164226756659/vlcsnap-2022-06-26-14h50m36s.png) (loss of chroma) , and to use the [x265 amod](https://github.com/DJATOM/x265-aMod/) by DJATOM, which doesn't have a "certain commit" that "causes massive random artifacting". They didn't have any links or comparisons handy, so I assumed the issue would be from 2022.

I looked through the commits of amod & I didn't find anything that stood out to me. I did a tree diff of the x265 vs amod latest sources (2023 April), and as expected, there were many changes. I don't know what I'm looking for, so I don't know what to focus on. The bug could be a 1-liner or 10.

I was referred to IEM and I asked there about the certain commit & issue, but I was told by someone it's "specific to Amusementclub at this point in time afaik" https://github.com/Mr-Z-2697/x265-Yuuki-Asuna/commit/8d78b0fa48d09f0f2b5a58372d573a4711a432fa#commitcomment-103498859

Someone else disagreed, and discussed this issue https://bitbucket.org/multicoreware/x265_git/issues/630/rd-refine-will-cause-some-glitch-in-some

With disagreement about which issue, and uncertainty over exact commit, (short of using amod, since not everyone can fit amod into their workflow), I decided to stick to stock x265 3.5 stable (from 2021), with simple options, and hope random blocks don't appear. As someone said, "x265 is a bit hard if you want good quality tbh, I mean it's not world ending and it's goodenough (c), but if you do care, looking at the video scene to scene to see if the encoder has blasted something out of existence is annoying". It highlights the importance of QC.

### YouTube premium

I recently read that YouTube premium now has higher bitrate for 1080p streams which is labelled 1080p enhanced bitrate on the web UI. So I got someone to download that stream. I was expecting a 30% increase reading a reddit thread and h264 but it was more like 20% and vp9 but it's better than nothing. Vp9 is an expressing since it's better than h264 but it has the worst psycho visual optimisations and said above. 

Sync said amusement Club fft 3D 53d was faster than the Neo F50 3D 53b. 

I considered doing lossless trim of vp9 but the works I would be really awkward and tedious trying to cut on time and they would still be blocks from BP 9 so I decided to go the usual re-encode and filter

FFMS2 to loading the BBM or MP3 remarks produce corrupted video. So I need to be max into MP4 since our smash sauce can't read MKV 
I did a few quick comparisons and the vp9 hebe seed better than both of them. So I can skip the lame emerge. After fft 3D there is some residual blocking which I hope will be blue with x265. 

The first encode was 150mp which was a bit big and bigger than vp9 EB so with the second and code I'm dropping the psycho rate-distortion so the fire will be smaller.

- Idea: /
- Start:  /2022
- Contest: 07/03/2023 - 14/03/2023
- Finish: /2023

## Platina-Peppertones
I know the "Ready, Get Set, Go!" song from a [Suzumiya Haruhi AMV](https://www.youtube.com/watch?v=La7b_lo45ys) . Sometime later, I realised it might go well with Platina, so I started this mashup.

To match Platina, RGSG needs to be shifted down & up 2st in the verses & chorus respectively. To maintain maximum quality for that instrumental, the project BPM is set to the instrumental BPM. And therefore, Platina is stretched. I used the radio version of RGSG since the full version has extra parts which weren't really useful for the mashup. 

The pre-chorus was the hardest part since the Platina vocals were changing key, but RGSG was also changing key. It took a few hours (?) over a few nights to figure out what to do with the pre-chorus. I used some music from the pre-chorus and also the verse so that it sort of fits. The mashup arrangement was finally finished with about 1 day to go. A draft-quality instrumental was made with ReaFIR to quickly remove the vocals. That's the most important part of the mashup - the arrangement. Without that, other things like surround & ML stems can't proceed.

The original ending of RGSG had a slight conflict with Platina due to the chords. So I insert some content from the middle of RGSG at the end of the mashup so that the chords no longer conflict & also add impact.

- Idea: /
- Start:  /2022
- Contest: 22/03/2023 - 28/03/2023
- Finish: /2023

### Stems

On the final day before the deadline, I use spleeter stems to get a more proper instrumental and implement the infrastructure for stems and surround. I need to get the drums & piano out. Those should stay at the front. The drums need to be treated separately the since the snare is quite wide.

Since there's a bunch of Pitchshifting going on, the first choice is to create a lossless "others" stem and then use FFT to remove content that would create stems. Listening to the results after that was completed, I noticed that the verse sounded a bit empty and some artefacts due to imperfect vocal separation. The next candidate is therefore Gaudiolab, because no other MLs do piano.

Spleeter and G audiolab pick up different parts of the piano so I need to use FFTMT in Max mode to combine them. After replacing with g audiolab stems, it sounds better, but some artefacts remain. There is a lot of FFT processing going on, especially at the 4K size, and the Rear channels have some artifacts. So I need to use 8K FFT size on the surround upmixer to reduce those artifacts. I also put on some reverb there to further hide artefacts.

### Vocals

The backup vocals from RGSG complemented Platina so I left them in the final mix. Since the BVs are shifted up it now sounds a bit harsh, so I use ReaFIR to compress the high frequencies, but only when they're active, using Parameter Modulation - Audio Control Signal on the wet knob.

The vocals in Platina were isolated using subtraction and FFTMT to cleanup at 10% strength. There were some leftovers during the bridge, so the strength was increased there. That's not sufficient, so I need two isolate the center channel with a surround upmix. That leaves the vocals a little dry, so I need to slightly widen them with pseudostereo and reverb.

I wanted to see if I could stream audio through my network using ReaStream. Most screen sharing Solutions use Lossy audio, which isn't ideal for music production or checking artifacts. ReaStream in broadcast mode works, but there's lots of Dropouts. Local broadcast doesn't work, it might be for the same machine. Putting in the IP works. The quality seems to be PCM and supports up to 8 channels which is good. This would be my first use of ReaStream for its intended purpose, rather than using it as a surround channel mapper.

### After the contest


After I added vocal automation to Oxydlate, I decided to try that for this project by turning down the vocals 1DB during the verse. This turned out to be worse. To find out why, I inserted a loudness meter on the center which has mostly vocals, vs a loudness meter on the other 4 channels. During the chorus, the vox is 2 LUs lower than the music. During the verse, the vox is 3 LUs lower than the music with a 1DB adjustment via automation. This means that the adjustment isn't helpful.

The drums were initially pitchshifted with the rest of the instrumental infrastructure to avoid phasing artifacts due to different pitchshifting decisions. But needing to compensate using the EQ for different shift values over the song and sounding mushy made me reconsider. After narrowing the drums and not pitch shifting them, the drums now sound punchier. There is no deliberate drum diffusion to the back due to separate paths & pitch for drum sidechain and output.

Since the drums low frequencies were narrowed, this makes them quieter. So I need to boost it by about 1.5dB to compensate. But this also boosts the high frequencies, so I need to EQ them down to compensate. After some more listening, I felt the cymbals were too unbalanced & right-biased, so I also reduced the high frequencies in width a bit. This runs contrary to RMS analysis which said the left was louder by about 0.5dB in RMS. 

I use a 2-band splitter to split the drums into the snare & and overheads, then I can pan the overheads slightly left by reducing the right gain. I also slightly reduce the stereo with of the overheads. But then this makes the guitar & piano at the sides stand out, so I move the high-frequency stereo reduction to the master instead.


### Reflection

This would be my first full-length mashup with a K-pop song. Someone accused RGSG of sounding like j-pop. The Wikipedia page for [Peppertones](https://en.wikipedia.org/wiki/Peppertones) lists [Shibuya-kei](https://en.wikipedia.org/wiki/Shibuya-kei) as an influence. I hear a lot of tricky Jazz chords in RGSG so, it's probably that. It was a small issue in some of my recent mashups that they might sound a bit boring. This isn't really an issue in this mashup, also due to the interesting & rapid chord changes.

The strings are obviously fake and they failed to hit every note of the scale before the chorus. But there's some vibrato/detuning at the end of the bridge, which adds some much-needed real.

Overall surround activity is low, and I was hesitant to deliver this in surround, but I decided to since vocal extraction occasionally fails during playback & this is the 1st delivered cardcaptors mashup in surround. Also, the original version of RGSG was planned to be in surround, and it will have some editing. If I make it surround then hopefully people will be less likely to just simply replace it with a stereo flac if muxed with the AMV.


## Concent-Small Worldrop
Why Concent-Small Worldrop? I heard Small Worldrop, and the chorus sounded similar to Concent, so yanaginagi-ish. I raised this with *Lavo* , and it shouldn't be surprising since both have worked together in the past as the duet Binaria.

The verse of Concent is longer than Small Worldrop. Since the chords in Small Worldrop change faster than Concent I was thinking of chopping Small Worldrop into loops of chords, then repeating them like Concent. But this would be a bit messy with lots of clips. I tried a clip from the 2nd verse of Small Worldrop to extend the 1st verse, but that clip had a sudden increase in bass, so I reverted to looping the 1st & 2nd verses of Small Worldrop in their original places.

I looked on YouTube, but there were no full-motion AMVs of Concent or Small Worldrop. I guess that song & the Red Data Girl anime are too unpopular for that. And therefore, I can cut and extend both songs 2 to my liking without worrying about arrangement for video sync.

I decided to shorten the intro since to distinguish it from the original version. Also stel [mentioned](https://old.reddit.com/r/mashups/comments/1228363/discussion_should_my_boys_a_liar_x_enter_sandman/) that his Enter Sandman mashup was losing some viewers due to its long introduction was also an influence, even though my uncut introduction is around 30s. The structure of Small Worldrop is different to Concent, since the former has three choruses and an instrumental break, but Concent has two courses and a bridge in between. But it's a good fit since I can Shorten the instrumental break of Small Worldrop & mute the bridge in Concent.

After making my mashup, I don't like it that much due to the slightly discordant verse.

- Idea: 22/08/2023
- Start:  /2023
- Contest: 09/04/2023 - 14/04/2023
- Finish: /2023


## Hitoribocchi-Gift

There's missing audio in the instrumental of Hitoribocchi no Monologue, and glitches can be heard when I extract the acapella, but the glitch is lessened if I restart playback near that Point. Obviously, I can't do this during an offline render. In retrospect, this might be caused by my FFTMT trying to save CPU on silence. I've been using the web version of the single so far, The CD version doesn't have any missing audio in the instrumental so I replace it with that. For consistency, I also replace and sync the songs in my other mashup which uses this single Aru-money mashup.

There is an AMV available for the song if you search for the Japanese title. But Gift is notably shorter than Hitoribocchi no Monologue. There is no way of seamlessly extending the song to be long enough, so there will need to be some cuts to the lyrics to make the mashup work. There were some key changes in the instrumental, so I use pitch shifting & looping to keep it in the same key for the lyrics. The acapella has some good narrow vs wide imaging so I use my upmixer w/ appropriate thresholds to arrange that in surround. For the second verse I just let the instrumental run to add variation, and cut it short and repeat the first verse of the instrumental when the second verse of the lyrics come in.

There's a synth at the start which I removed using ReaFIR on a clip, since it sticks out like a sore thumb. There's some gospel shouts in the song which I remove using FFT since I don't like it. It needs to be done at 30% strength otherwise there's holes and power loss. The Rhythm Section is separated for surround using FFTMT since there's pitch shifting going on. It's done at 50% strength otherwise there's artefacts in the rear speakers. The break after the first chorus and the bridge are the same at 4 bars each. This is good since you don't want the bridge to be longer than the break after the first chorus

There's a bug before the first chorus, multiple singers are singing, but the image isn't wide. After measuring similar sections, I widen that section with pseudostereo. I also had the idea panning the characters in Panorama across the front from ID 1-4 Bocchi, Nako, Aru, Sotoka (the order that Bocchi friended them. But that wouldn't work to form a balanced image according to when/amount they sing. I eventually settled with Nako on the left, Aru & Sotoka on the right (the genki duo) and Bocchi in the middle. To exactly set the pan positions using automation, you need to use a script to set this since reaper itself can't set a specific value for multiple points. I found one by x-raym, but that didn't work due to external dependencies & it was quite complex. I decided to make my own simple version. It took a few hours even with referencing an old version of their script since the Reaper Python API is the most awkward of them all.

This mashup uses the most recent sources, at time of completion - Hitoribocchi is from 2019A and Gift is from 2023A

- Idea: 08/03/2023?
- Start:  /2023
- Contest: 01/05/2023 - 09/05/2023
- Finish: /2023

## Aha-Sparkling
Chuunibyou Take On Me the movie got an English release in 2018. Some people were expecting it to have some relation to Aha - Take On Me, but unfortunately it doesn't. I think I had a quick listen to the OP & ED songs a few years ago and they didn't seem to go well with Aha - Take On Me so I started looking at other pairings. Tomare from Haruhi fits perfectly in the verse, but there's a 6st key change in the chorus so Tomare sounds very distorted. I finally thought of the S1 OP - Sparkling Daydream. Note that Aha - Take On Me is vari-BPM so multiple cuts & stretches are probable.

### Aha-Sparkling Editing
Due to the chord progressions in both songs, keeping the keys, but to applying scale/chord editing using zplane retune sounded the best. But it still sounds a weird since the two keys are actually a 2nd apart.

zplane retune is turned on and off using bypass automation. There are some glitches during playback. The glitches are slightly lessened to during rendering, but they're still there so I need to accept it. Sparkling Daydream is shifted up 2st in the chorus and that is fully in key, but not necessarily chord.

The intro sounds a bit empty w/o the vocals so I use the original vocal version for that. The mashup isn't turning out that great, so i'm not intending video sync or a surround version. So I can freely edit my mashup without constraints on arrangement. After the contest, I fix the timing in the later part of the song, and add a crossfade so that the ending is less glitchy. 

### Aha-Sparkling Balancing
Since it's shifted up, there is bass loss & treble boost, so I apply some EQ & bass transient boost to counter it. Elastique 3 will keep the EQ balance more consistent across pitch changes, but I was initially hesitant to use it since it makes larger discontinuities at cuts than Elastique 2.

But I noticed some bass issues upon further listening. With Elastique 3, the bass is more consistently defined, and the bass level is around the same as without FFTMT transient boost. That now stays off because I want the bass to be consistent throughout the whole song. The bass levels are also checked with the spectrum & peak hold on izotope insight.

I noticed in the bridge that vocals were a bit underpowered, so I put on loudness meters on the instrumental and vocals. Even though the vocals are about 4 LUFS quieter than the instrumental, it still manages to be heard most of the time. But 4LUFS under is still a bit low so I increase the vocals by about 1.5dB, and that seems to fix balance issues, at least on speakers and bassy earbuds. On Cheap earbuds, the vocals are still noticeably emphasised. I had previously put on a -2.5dB mid cut on the instrumental to make space for the vocals. Increasing that to -1 DB slightly undoes the vocal rebalancing, so I left it at -2.5 dB.

Overall, my mashup is isn't that great but Chuunibyou fans will love it since there's finally something that's C2k-related that uses Aha-Take On Me. This is maybe my first mashup that was created with marketing in mind AKA doing a mashup due to the song titles rather than musical features.
 
 TODO FIX & SHORTEN

- Start:  /2023
- Contest: 31/05/2023 - 06/06/2023
- Finish: /2023


## Roki-Imouto Please (Vocaloid, Oreimo) [Mashup]
This is my 5th oreimo mashup. Overall, I'm not that happy with this mashup since it's a bit boring due to song choice.

The theme for the mashup contest is censored. Which means you need to creatively edit words in your mashup. If it doesn't have dirty words, an unnecessary censorship approach can be used.
I chose Roki & Imouto Please. The lyrics aren't that dirty, but I was hoping that there could be some words I could edit out. The plan was to complete my mashup arrangement, then perform editing afterwards to edit words, replacing with a sound similar to my Let's Dance mashup. 

The mashup arrangement & tempo is exactly that of Roki, so that people could replace Roki with my mashup (for MMD videos) like my Roki-star-circulation mashup. Imouto please was paired with Roki since they sound similar. The mashup editing slightly shows itself, as I need to repeat audio sections a few times to fill time in the arrangement. Partway through making the mashup, I realise it's not that great, and I wasn't really motivated to finish it but I got it done eventually.

The lyrics had some basis on how they were edited. The word was edited if edited, it could be dirty. I tried to keep the editing somewhat constant throughout the song with about 15 edits. Since the lyrics are in Japanese, the editing workflow is inefficient. I need to look at the video with translated lyrics and romaji. Then guess the words I want to edit. Then check I got the right word with GTL. I have some stems for Roki so I can put them to good use. An intro was made to fill time, taking audio from the end of the Imouto please and layering it with some drums at the start of Roki. Drums were added similarly to the outro and the guitar from Roki as well.

- Idea: 2023
- Contest: 25/07/2023 - 02/08/2023


### Candy POP

I know this song since someone shared a shortened edit of the song around 2009. I then recognised it used in the famous Skittles Candy Pop Haruhi AMV, inspired by the original music video. I want to make a surround mix so that I could pair it with either video. There's only a MP3 available of the instrumental, so I need to wait a while to source a lossless copy. As usual, I don't want the piano at the back so I need ML to get the piano out. Generally, I only use lossless copies when there's ML processing.

You can do some fun things with the vocals in this song like put different rappers to the left or right. I can do this in some sections where rappers switch quickly like in the introduction or 2nd pre-chorus so that it still sounds balanced. But during the verses and chorus, there's often long lines of one singer, so it won't sound balanced if I put it to one side. Also, there's is different imaging to differentiate between different singers.

In Reaper 6, you can set a default envelope Point shape for the automation lane. This is useful if you want all your points to have the same square shape so that you only need 1 point for the automation to hold onto up particular value, not 2. Like creative panning. But automation itself, is generally still finicky and it's tedious to set it to a specific arbitrary value using the mouse. 

- Idea:  11/06/23 ?
- Contest: 02/07/2023 - 11/07/2023 
- Finished:

## Hello World-Cubic Futurismo

The arrangement is mostly hello world, but there's some cuts since I can't find any hello world music video.  I did The initial vocal separation with isotope RX7. it doesn't get the vocals out well & I can't use this to balance, but I can use this to do a basic arrangement of my mashup. Due to the poor isolation, the bridge didn't sound very good & I truncated the ending lyrics to sound more snappy. But after using DEMUCS, the bridge sounds a bit better. The ending lyrics were restored (after the contest) to respect the Integrity of the original lyrics even though it sounds a bit worse.

When I almost finished the mashup for the contest, I realized the pitch shift mode is set to Elastique 3, which isn't compatible with older versions. But when I set it to Elastique 2, the LUFS stat is slightly lowered, so I apply a bass boost of 1 DB. The ending vocals have reverb but no stereo width, so I widened them with pseudostereo. Afterwards, they have some depth when listened on headphones.

After the contest, The female vocals still weren't sitting right, so I tried various things. A 1dB volume boost was too much. Mid EQ boost also didn't seem right as sometimes it was too prominent, but sometimes it's still a bit hard to hear. I looked at the waveform of the male vocals, and then I realized that the female vocals need some compression. So after applying compressor, they sit much better, but still stand out a bit so I add a gentle mid-high cut. I originally implemented this as a clip take FX, but I wanted to redo this as a track FX + automation for better clarity. After applying compression, I was going to deliver it, so I render MP3 but I subtracted with a previous version to make sure I implemented it the same. Most of the song is the same, but during the ending Echo is was non-silent. So I adjust the automation Lane. 

- Idea:  
- Contest: 22/09/2023 - 27/09/2023
- Finished:

## Yasashii Bokuyaku-Yoru no Uta

I had the idea that these two songs would go well in my head a while ago. They're both in the same key and a similar tempo. Originally I tried searching up yakusoku on YouTube to quickly remind myself of the song, but it was a bit hard to find since I had memorized the song title wrong. For Yasashii Bokuyaku, the movie 5.1 version was used since its already an acapella. For Yoru no Uta , the MIDI file version was used since there is no instrumental of the song. This also offers note editing flexibility.  but Yoru no Uta needs lots of editing to match up with Yasashii Bokuyaku. Some instruments were muted because they sounded muddy or it interferes with the vocals. 

With this song, it's quite easy to have the vocals too loud, so using LUFS meters to measure the vocal balance is important. MIDI velocity limiting was used to control the dynamics of the piano & strings from overpowring the vocals. Eventually i removed the MIDI limiting for the piano and matched the loudness with the lmited version. The vox gets quieter towards the end, but the MIDI instrumental gets louder towards the end. So the vox was sectioned and made pregressive;y louder, and some MIDI clip velocity adjustment was used for the end.

I was listening carefully to FDNreverb, and I heard some undesirable resonance. So I need to set the FDN size to 32 to make it go away. Unfortunately, this raises the CPU use by a lot of and exporting takes a lot longer. I need to edit the notes of the string so that it matches that piano and vocals

There wasn't much surround separation or activity, so I decided to deliver as stereo in the end. But the surround reverb was taking a lot of CPU, and significantly increasing the export time, so I'm replaced that with a stereo reverb, carefully matching the gain and some characteristics.
