# Surround Music Mixing Notes

### Goldeneye

I wanted to do GoldenEye in surround since it's a great song by Tina Turner. The version is the movie has sound effects and it's shortened so it's not a great source to start with. Apart from the movie, there are two other versions of GoldenEye. The single version, and the full version. I chose the single version since you can sync it with the music video even though the music video isn't that great due to frequent cuts between inconsistent sources. I wanted to place the bells up high. Even though the Bells sounds very much like a piano, none of spleeter or G audiolab managed to get them out in the piano track, so I need to extract using different methods. In the movie, the brass was placed halfway between front and back so for my version, I can place it mostly back for increased stability.

I think the original version had some balancing issues where the bells & brass were too loud and obscures Tina's voice, so I put them down by 1-2 DB. I also brought down the other instruments too. the bass is really powerful so I need to EQ it down with ReaFIR (linear EQ) & make some space for Tina's vocals. I also added some reverb to the brass since they sounded too fake & Direct. After listening to it on my surround speakers, the brass didn't have enough impact, so I let more of the dry signal through in the reverb. The feedback I received was mostly positive but there could be some improvements made with imaging and vocal EQ and reverb.

I encoded it to DDP Atmos. They were compatibility issues with certain software. After a few frustrating hours, I figured out it was due to 384kps using additional coding tools. 448kps doesn't, so it has no compatibility problems. And despite the height being "simple", there was artefacts & raspiness in the encoded height channels. Increasing the bitrate didn't fix this.

After increasing diffusion of percussion to back, I noticed there was still triangle from the back, and this wasn't completely controlled by the drum stem so I added some ReaFIR to remove it.

Some months later, I revisit this project, mainly to set the sound to end on more silence. I also check the vocal balance with my vocal loudness meter trick, and it seems the vocals are too loud, so I reduce them a bit. I a;sp redp the gain settings to make it more simple. Also, the surround image of the strings is slightly biased back, so I inch it forward by tweaking the upmixer settings.


## Crazy by Gnarls Barkley

The song seemingly presents a narrative of someone getting more and more delusional. So I'm mirror this with instrument panning getting more outwards and higher as the song goes on. The Illusion of slow dynamic panning is accomplished using static routing, but automating the wet/dry knob. I'll take the opportunity to do things I wouldn't usually do, like setting the cymbals up really high, or having the BVs in front ELL but also at back height, or the snare drum at the back. There was some noise that sounded like walking on gravel, so I put that in the bottom speakers. I only got a single drum stem, but this wasn't enough separation to have different parts of the drum kit in different places, so I need to recreate this using MIDI.

## Castoff Jazz

Why castoff? The stems were available on an audio forum that I frequent. They weren't really happy with how the project went, so they were releasing it to the public, hence the name castoff. The music itself received some praise for its "high level", assumedly music theory. The stems were recorded separately, and There was some amount of alcohol involved, so the musical quality of individual stems vary. The author told me in PM that the guitars weren't so good so I muted them in my mix. This makes mixing easier so I don't have to balance so many elements. In my first draft, the cymbals were "too loud" even though they were quiet. I also applied some compression to the piano. But that was also still too much. So in my second draft, I turned both of them down.


I want the piano to introduce itself & be heard, but also blend in. The start of the piano section also sounds too loud, so I add a fade in, but the clip starts about halfway in the project with several seconds of silence, so the fade in sounds more like automation.

I was about to release this a few weeks prior, but issues keep on popping up a few times.
This bit of bass resonance in the lower notes so I turn it down by 1 DB and add a multiband compressor to compress the low frequencies by another DB. I notice the bass ending early while doing a scale, so I copy over some bass also doing a scale or something from earlier. I also notice the e.piano is mono & originally panned right, but it's panned back in my mix, so I use pseudostereo to widen it.

 One night I decided the hihats were too annoying. They are boosted by 10 DB but it's the reverb that's making the hi-hats bigger than they seem, even though the reverb is lowpassed. So I turned down the hihats. There was a lot of checking, anguish, and uncertainty over the hihats level. I wanted them to be present, pleasant, but not buried. I checked some of my old trance/house mixes. The hihats were definitely present, but more pleasant at a lower frequency/tone. I finally settled on a gain of 2.5.
 
 
### Oxydlate 
The song is seemingly in 12/8 time, initially set to 6/8 in my DAW, But was later changed to 3/8 time so that the song begins within 1s & on a whole measure. It's mostly in Am.

I decided to start this project since it's a rare opportunity to have stems for a song that are in Japanese, not counting the Vocaloid stems (part of a NND online festival?) with synthesised vocals. Originally this was going to be mixed by someone else, but they never got back to the vocalist. My mix wasn't finished so they "whatevered" it in about Oct 2021.


### Oxydlate stems
It turns out the project is only vocal stems + instrumental, So I need to use spleeter to get the drums and piano out. 
 
Spleeter didn't really pick up on the piano in the chorus. So I need to use g audiolab, which is now available in 2023. That picked up more piano in the Bridge but still not perfect. Since g audiolab doesn't export MP3, subtracting from the FLAC instrumental won't produce a lossless "other" track & it won't add to unity. So I need to use the MP3 "others", and bass, piano, stems directly. This will save some tracks since there will be only 1 track for each stem, not 2 (1 for input to subtract, 1 for output & FX). Also, it gives me more flexibility to deal with stems.

I don't want the marimba/xylophone to be at the back, so I extract it with the XG Yamaha VSTi & FFTMT. Same with horn/trumpet. It's not doing a great job since there's still bleed to the front.

In September 2023 I decided to have a go at lalal.ai separation since I thought of the song, and it has strings and wind with a trumpet icon separation. The preview is 1 minute at the start of the song, so I need to cut a 1-minute section around the bridge to preview anything useful. And the results were quite disappointing. Only a fraction of the strings and brass were extracted with the strings & winds stems respectively. The synthesizer option is just everything except the rhythm, which is useless. There is another option which is moises.ai but you need to pay to use the string separation. The next step up would be to use melodyne, but that takes a lot of time.

### Oxydlate Vocals Pitch

In the 1st version of the provided stems, the vox already had pitch correction, but it sounded robotic due to the fast correction speed & unnatural due to pitch manipulation. Initially, I thought it might be something like elastique efficient in Reaper, but it turns out they did manual correction in melodyne. Luckily, the raw uncorrected vocal stems were still available from the artist. With automatic correction in Reaper, it now sounds in pitch without being unnatural. There was some positive feedback from the vocalist about this.

The lead vocals use a 200ms attack, since the lead vocals are prominent, but need to sound natural. The backup vocals use 100ms attack, since there were more faults & they really need to be In tune, otherwise they don't sound cohesive when they make a chord. These times & strengths are specific to Reaper and might not map directly to other pitch correction software such as Antares autotune which has stronger correction per time constant. I did some manual correction by cutting the voice clips since some notes seem to be wrong in the original. 

Selecting the right pitch shift algorithm is sort of important for vocal pitch correction in REAPER if you care about low CPU & high quality. If you don't, you can just choose Elastique pro (high CPU & quality) & be done with it. I would usually use soundtouch on vocals because it's low CPU but it produces discontinuity artefacts when pitch shift amount changes rapidly. elastique efficient works, but it makes the vocals sound dull and unnatural. And so we are left with elastique soloist in speech mode, which is low CPU & sounds natural.

I added some exciting to the lead vocals to give it some air and also to make it stand out. 

The lyrics have a theme of breathing. Nakuru Aitsuki has some breaths in the verse, and the breaths are quite loud in the chorus. It gets quite breathy at the start of the pre-chorus too. Nou has some breaths in the verse but you can barely hear them in the chorus due to the music.

### Oxydlate Mix General

Vocal balancing is a tough job for this cover, since the vocal character is completely different to the original. It felt like the song was specifically made for the singer. They have a beautiful, strong voice sort of like Nana Mizuki but the pronunciation of Japanese vowels is slightly off in places. After carefully listening to the original, it seems that the way the lead and backup vocals are able to coexist is that the lead vocals are at the lower registers while the backup vocals onto the sides & more airy or in the higher registers. So I applied some high pass EQ & exciting to the backup vocals. After exciting, it needs de-essing to reduce the HFs to make them less annoying.

I still had some trouble with the lead vocals cutting through the mix. It seems that shifting the formant up by 50 cents generates some distortion, so the lead vocals can cut through better now. I thought The piano was too loud in the original so I turned it down. The bass is barely there so I add distortion to make it more heard.

There were only about 3 backup vocal stems. I placed the high & mid lines wide left and wide right and the low line at the back. This uses the extended positions of 15.1 surround, but the mix doesn't really have much activity beyond 5.1. But 7.1 users would get more resolution if I increased the mix to that, so I did.

This project has two reverbs. There's a global surround reverb which shapes much of the character. There is a stereo vocal reverb which is activated on-demand to accent The Voice at the end of choruses. It's a bit cliched, but it's appropriate. I initially had the fdnreverb set to -25 and sends at +10 or so, but then I set it to -10 which is more usual with my other projects.

Left-right panning was added to the lead vocals at the ending to complement the Rising tension, similar to the ending of the last bullet.

The project was taking a little long to render, so I wanted to reduce the CPU usage. My own FFT tools have silence CPU gating but manually gating them further reduces CPU use. I thought upgrading from elastique 2 to 3 would reduce CPU, (NB this would be incompatible with reaper 4), but it actually increased CPU. Good that they kept v2. Retune and elastique soloist have their own CPU gating, which is quite effective, so it's not worth it to make manual automation for those. Changing the project sample rate from 48k to 44k reduced to render time about 25% since all of the media is 44k.

### Oxydlate Drums

I thought the drum pattern was too complex so I muted it and created a new drum track. The loop with the most intensity was created first, and the earlier loops with lower intensity had notes taken out. I did most of the Loops about 1 1/2 years ago (Mar 2021) but I didn't sequence the bridge which had a different idea. Coming back to this project in March 2023, I thought I had forgotten my idea and therefore the project can't continue. After listening to the bridge a few times I think I have +- the idea Back. It follows the rhythm of the strings and has a different snare accent than the verse & chorus.


### Where do you go mixing notes

The first step is to ingest the stems. So this means to pair up stems that might go well as a stereo pair. Like backup vocals and similar sounding guitars. Remove duplicates. So the stems were reduced from about 44 to about 33 .

There is a difference between Overdrive and distortion guitar. [This video](https://www.youtube.com/watch?v=nEe1eNv7o40) by Kevin Balke shows examples. I initially researched this topic due to criteria for a mashup contest where no distorted electric guitars were allowed. So Overdrive guitar is want that sounds like a square wave where you can still hear the fundamental clearly. A distorted guitar is one with lots of harmonics & noise.

The next step is to make basic mix. This means adjusting the balance of instruments. Regardless of how you set the lead vocal level it's wrong, so you need to apply some compression. Individual clip gain was also applied. With a high compressor ratio example >5, regardless of how you boost that input volume, the output volume will stay basically the same, so if you want to have some pre-compressor volume control, you'll need to lower the ratio. The vocals also needed some reverb to sound not raw. But of course as with most mixing practice stems you get, they are not fully raw. They will have pitch correction applied, and most of the time it's obvious and overdone. 

The drums also needed processing to sound better. It seems the snare drum was recorded from the top. It's almost as if the snare wire were disengaged. So I apply some distortion to give it more impact but it sounds a bit bad. I think David may have opted for drum replacement but I wanted to keep it simple. The hi-hats and symbols are also lacking volume, but if you just boost or pan them this also affects the snare due to mic bleed in the overheads. So you need to apply a high pass EQ to remove the kick & snare from the overheads. Carefully listen to the overheads as you adjust the filter frequency so that you don't remove too much. Then you can Pan and adjust the overheads with more control.


## Kanon ED
**The place where the wind arrives**

I was hesitant to start this surround project since there didn't seem to be many elements that could be put in surround. But on a careful listen, there are some pads, so I thought I'd give it a try and also fix up in the issues to be discussed below.

I noticed that the bass was too wide. I chose to select the left channel only to avoid issues when both channels are mixed together, since they seem to be stereoised by applying a time delay. Stereo width has some side signal which has some volume. So I compensated for the loss in volume due to reduction of stereo width by applying a small volume boost afterwards. I later reverted the 1db boost since the bass was ample strength on the FFT. Some stereo width was added later. 

The harsh bell at the start of the song was turned down using ReaFIR. ReaFIR Tip: By default if you're only doing cuts, neighbouring frequencies could be boosted since it's trying to interpolate a smooth curve. If you're doing targeted cuts, it would be better to use the sharp mode so that cuts don't boost.

The drums high frequency was also slightly cut and the width was reduced.

Vocals being too quiet is the main issue of this song. I thought a 1 DB boost would fix it, but it needs something like + 2.5 DB. Gentle compression was used in the chorus To prevent the vocals being too loud. When the vocals are boosted, more issues are apparent like the vocals need de-essing and maybe exciting as well.

For the elements that I'd try to pan to the front I'd usually get them separated out. Like the piano. But no ML could get all the piano out. Luckily, MO had sequenced the MIDI file, so I have some more options. initially, I tried to remove the piano from the back, but not all of the piano was removed. So I tried the reverse approach of adding the pad to the back. That was more successful. One needs to be careful about how much sound to move to the back since front/back balance would be impacted. As with my Aespa - Better Things, surround activity was lacking. The vocals were upmixed to 5.0 surround & some bleed from the front was added. I was going to get the strings out and widen them, but I'm not bothered with enough bleed from the upmix.

Vocal extraction left some artifacts when listening to the full mix since the vocals were originally too quiet. It turns out that MDX23 is the current rage. I looked into the code, and it seems to be doing Kim vocal first and then DEMUCS, which is the reason for its High Quality. But I couldn't see that --clip-mode clamp was set for DEMUCS, and hence the balance of stems might be off. 

After a few days of hesitating, I finally set up MDX23. I need to use the --single_onnx option otherwise it would crash. It took about half an hour for a successful run. MDX23 has better isolation and less artifacts on the vocals. But it doesn't add to Unity - there is a difference in bass after comparing with the original.



## Unforgettable

I know the song since it was being played at a funeral and I was invited to control the audio for it. I know Sia sung it for Finding Dory since I read the Wikipedia article for it. Earlier this year, the song popped into my head, and I thought that Finding Dory might have a surround version of it. It does, but there are some sound effects over it.

So I need to use FFT to remove SFX with the CD version (no SFX) as a side chain. After a while of trying, it should work, but it's not working very well. I eventually realized that the CD is at the original cinematic 24 FPS, speed but the BD is at 23.976 FPS speed. Similar to my Garden of Words project. So after slowing down the CD, the SFX can be removed much better. There are some distortion artifacts left. From some analysis of the 7.1, mixing the front and back channels forms the side channels, so the side is therefore upmixed & not unique. It can be removed. This is similar to the initial 2011 BD release of the Lion King with 7.1. But after revisiting this project some months later and applying the vocal loudness metres trick, I find out that the vocals are too loud due to the balance being changed with side chans removed. So I reduce the center channel by 2dBs. The center channel is still louder than 2dBs under the 4.0 subset, but this might be the right balance for this mix since the center channel also contains content apart from vocals.

I was going to call it finished since there were some noises I can't remove. But I asked myself, can I do better? And the answer is yes.

By starting from the CD version and using the BD version to assist. Perhaps I should've done this 1st.

So I redid the project. Upscale CD to 3ch, using FFT to "correct" the center ch with BD, and using FFT to pull content into the back speakers, also with BD. To reduce the bass going into those channels, I use Hipass EQ on those channels from the BD version, before FFT. I need to check carefully the amount of strings moved to the rear to balance image & F/B domiance, since FFTMT is >100%. One issue was balancing adequate surround activity without having the image be too backwards. So I used Use automation to change the surround levels during the string swell before the intro and during the cello-heavy Bridge.

While I was reading the ReaFIR manual I saw that the subtract mode can be used to denoise and you can also build a noise profile. It's not a right minus left kind of subtract. I was thinking maybe it can be used to remove dithering noise. FFT subtract isn't the same as EQ. EQ is a multiplication, so in most cases you will need not be able to completely remove the noise for a particular frequency. Also if you're using EQ to remove to the noise, you will also likely affect musical content. Since FFT subtraction is actually a subtraction, you can more effectively target noise and as long as the subtraction amount is low, musical content will be minimally affected. Tuning the thresholds is an important part, so I set the thresholds to remove some of the noise while making the fade-ins not look like they have FFT holes.

- Start: 17/07/2023
- Finish: xx/03/2024



## Kaijutsu Renka

I know the song from rewrite arrange album. The drums in the original version sounded weak, so I wanted to replace it with something stronger from the Ridge Racers 2004 soundtrack. In the end, I chose Night Stream over Vanishing Point. The BPM of this project was set to exactly halfway between the two songs. 

### Drums

The drums varies in intensity in the original, so I found 3 sections in Night Stream which were varying intensities that I can put in the appropriate places, cut to 16 bars long. The most intense section was dropped by about 1 DB for balance reasons. When mixing the drums into the original, I want the drums to be heard alongside the vocals and not behind it. It's a very subtle difference of 1 DB.

My original approach to making this remix and surround mix was to have the stems stretched since DEMUCS has better isolation than spleeter, so hopefully there's less phasing. But after listening to the stretched stems, it felt like something was missing, so I need to use the upscale-then- separate with FFT approach like I've used in the past for spleeter.

Depending on the pitch algorithm & settings, drums from Night Stream can sound different. Obviously Elastique 3 sounds better, but uses more CPU & isn't Legacy compatible. So I used Elastique 2 with a slight pitch down towards varispeed.

DEMUCS didn't put all the percussion in the drum stem, so I need to use looping & FFT to get more of the drums out from the original.

One of the problems that I wanted to fix and the original regardless of everything else, the vocals were a tad quiet , so I boosted it by 1db.

The surround activity is going to be a bit low for the song, so I want to have some rhythm bleed to the back. So the piano is on the half removed before surround upmixing. Some reverb was added to the back speakers.

Listening on speakers, the voice was a bit boomy and obscured by the drums, and the image potentially too backwards for a string quartet. So I did a tiny mid-boost with linear EQ to the vocals, and slightly lowered the drums and increased the mid-cut. the image was moved slightly forward in the surround upmixer and the reverb bus was turned down. A 3/16 delay fadeout was added to the drums to gradually bring down the energy for the outro.


SoundCloud directly accepted the 5.1 and automatically downmixed to stereo, the balance sounds roughly correct. no stereo master was generated on my end, unlike the xmas album on BC.

### About the artist

The singer is credited is mao in the song. The same mao that sung the OP for Doraemon 2005. However, people online have speculated she's the same person as Duka who sang *Ai no Niwa* from [Garden](https://vndb.org/v335) . Pay attention to her expression/articulation when she jumps between two notes far apart. It's understandable to have different aliases for general works and another one for adult works. Regardless, mao/Duca his many fans worldwide. 

