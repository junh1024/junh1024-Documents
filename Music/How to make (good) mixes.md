# How to make (good) mixes

Introduction
---
A mix is when you join multiple songs seamlessly, with a focus on the transitions and keys. This guide is for making mixes offline in a DAW. So only half of it will be applicable to online mixes in a DJ program. But it's easier to perfect your mix and apply more complex techniques to make your mix better, offline. This guide was written in mid-2020 and draws on my experiences making a bunch of mixes for about a year, and a few segues since 2015.

Planning
---
This guide covers constant BPM mixes. This is easiest to comprehend & manage. There are techniques to join songs of very different BPMs, they won't be covered here. If you choose songs of the same genre, that will also be easier, since genre implies some closeness in instruments & BPM. I usually make thematic mixes with the theme being genre. Pop is a meta-genre ie, songs aren't really close. I always have problems with pop.

You should have at least 2 albums worth of material to join, cuz you will be throwing some away. After you've analysed the BPM of your songs, take the average, throw away songs that are >=15% from the average. Then set the average as your project BPM in your DAW. After you finish your mix, you can take an average & set the BPM again (or use my "Get item BPM.py" weighted average script) to get a more appropriate average BPM, since presumably you've thrown out some songs.

REAPER & BPM
---
Note for REAPER: REAPER doesn't have the concept of a clip BPM (maybe other DAWs too), so use my "Set item BPM.py" in https://github.com/junh1024/Reaper-Surround , and see my [Reascript Python](https://github.com/junh1024/Reaper-Surround#reascript-python-setup-for-windows) guide. Alternatively, new rate = new BPM/old PBM

Key tagging
---
I usually go by ear to tag keys. There should be no problems with conventions for Major keys. For minor keys, you can show the minor and its relative major e.g, Am/C. For sharps & flats, I use sharps only. Whatever you do, keep it consistent & clear, to make it easier to see relationships between your keys. You can new group/join songs of the same keys. For the pop/electronic, major seems to slighly dominate, but for Rock & Touhou, minor seems to slighly dominate (2hu is a game tho).

In REAPER, you can make an empty item, type in your key,  stretch to fill item, and group it to your song to make a nice big key display. https://i.imgur.com/RSGMsH2.png . In other DAWs you may resort to small text & renaming your clips.

Circle of 5ths
---
Unlike [mashups](https://github.com/junh1024/junh1024-Documents/blob/master/Music/How%20to%20make%20(good)%20mashups%20V2.md#introduction), knowing key theory is almost mandatory for making good mixes.

If you're like me, you would've heard the circle of 5ths being mentioned many times, but not knowing how it's useful, until now. Here it is below in strip form with C major at the center, and relative minor below.

	C#	G#	D#	A#	F	[C]	G	D	A	E	b	F#
	a#	f	c	g	d	[a]	e	b	f#	c#	g#	d#

If you join 2 songs in neighboring keys or modes (move horizontally or vertically), it should sound good. But if you move both (move horizontally and vertically), it might not. Although horizontally neighboring keys are both a 5th apart, I often find that moving down a 5th sounds better, maybe cuz it sounds like a more usual descending perfect cadence. Depending on how your keys come out, you might be able to move around the circle for at least a few songs.

Many songs are in 1 key only. But there are some that are in 2 or more keys. These are more valuable as you can now have more possibilities to join keys, but you can only join certain keys at certain points, and it's now polarized (assuming each end is a different key). So you can't reverse your mix and it'll still sound good.

Other strategies
---
5ths are discussed above, but in the [Romantic era](https://tobyrush.com/theorypages/pdf/en-us/romantic-era-techniques.pdf) , people started using 3rds. So if you join songs using 3rds, it might sound OK. Or you could try to match chords between songs. Or match notes instead (chords & melodies). Really, it all comes down to sounding good, harmonically.

Instruments
---
It's not uncommon to have a section of 8 bars where ingoing & outgoing songs are both played, maybe with a hipass on the incoming piece. Sometimes you might need more separation than EQ to help glue them together. you can use Yellow DrumExtract to isolate the drums, or you can use VSTi to recreate some motifs.

Fades
---
You can do fades to join 2 clips. The simplest fade is a crossfade, where 1 clip (slowly) fades out while the other fades in. Your DAW may do automatic crossfades if you overlap 2 clips, or you can manually fade 2 clips on separate tracks for more control. You could also do a L-fade where 1 clip fades out but the other cuts in. As for length of fade, what's appropriate can vary by genre. For house, there's the standard 32 beat or 8 bar crossfade. But for rock, a fast fade or a cut may be appropriate. For pop, it's tricky & depends on song. You could also do a more sophisticated split-combine frequency fade (maybe available under a different name), where you start from the top/right of the frequency and move to the bottom/left,  and progressively lowpass the outgoing song & un-hipass the incoming song so that the frequency ranges form a whole, but of different songs.

My Philosophy
---
The following is my philosophy, and you don't have to follow it, but they might be good ideas.

Try to make mixes with vocal songs (full lyrics). They'll be more memorable to you & your audience. I started off making vocal mixes, then made some instrumental mixes later. I'm guessing that it will be half n half when I finish my current bunch. You can probably find vocal songs in most genres. Vocal house songs might be under dance. The only genres that tend to have less vocals from the genres I've tried, are trance & hard house.

I avoid reusing the same versions of songs in mixes, different versions are OK. Example: I used Tomare! in my rock mix. But I also used that in my house mix, but a house remix. I also used Kaze no message in my initial rock mix, but I might use it in a future mix, so in the process of improving my rock mix, I removed that song & a few others, and re-released it.

I know many mixes are 1 hour long, but, I target a length of 28mins for mixes cuz:
* it fits on 1 side of a C60 tape (if you want to archive them on a cheap, non-digital format)
* It's not too short, or long. It's a satisfying length
* Making longer mixes is harder cuz you need to make lots of joins work

Generally, unless I'm making a minimix, I try to have a decent length for each song, so at least 3', and I may reject songs < 3'30". I might restructure songs so that transitions sound better, eg, moving the bridge to the start, or starting after the intro to match intensity or keys. 

When I do transitions, I try to join on a harmonic, busy part, cuz:
* It keeps the energy
* It's harder, but more interesting
* Some songs may not have a long drum-only lead-ins & lead-outs, like songs with full lyrics

Start off your mix with a song that's not too intense. Take a hint from Track order on albums, it can help you to make a journey as the mix progresses. Vary your intensity as you go through the songs, but that might happen anyway due to differences in song content & key compatibility.

If there's a long breakdown in a song, I try to place that song at or after the middle of the mix. Sometimes there are songs with "missing beats", ie, incomplete bars so that the usual 4/4 phase is thrown off after some time. Again, for management reasons, I extend it, or chop it off. For times when those don't sound good, IMO it's most important to have sync at the end of a song, so that the phase is correct when you join the next song.

I try not to pitchshift songs most of the time, since if the pitch is shifted, it sounds wrong/not original, and sortove defeats key theory.



Surround
---
Using surround in mixes is completely optional, but offers more flexibility. You can make surround mixes, but it will most likely be upscale. You can upscale after making a mix, but that's lazy & bad quality cuz phase information that upscalers use is mangled by pitch-time stretching. So, upscaling *before* is preferred. Deciding whether to make a surround mix or not depends on a few factos, how well I like the songs, and how well they upscale to surround. Non-vocal mixes I usually don't consider for surround.

Order for 51/71 is L R C LFE BL BR SL SR (SMPTE-MS)

If you make a 3ch mix of a song, you can have more control over vox, providing the instro is only in LR & vox is mostly in C. How to make such a clip is not covered in this guide. If you wanted this level of control previously, you would have 2x stereo clips. Having them as a single surround clip ensures they never get misaligned & bypasses the grouping hassle. Unless you have a DAW that imports stereo as separate mono clips *ahem Pro Tools*.

If you're upscaling to 5.0 padded to 5.1, you also upscale the instro to the corner 4. If the vox has a significant side component, and you sometimes need a pure instrumental (ie, no vox) sometimes, and you're aiming for 5.0 surround delivery, you can upscale the vox to 3ch, but move L&R to SL SR. Then you can mute the side & get a surround instrumental. It's suggested to downmix the vox in side to the front for 5.0 surround.

As I said earlier, upscaling to surround (at least in DSP order) before making your mix is preferred, but you don't want to waste time upscaling songs, only to throw them out, cuz tuning upscaling settings for a song takes 2 hours. I also have another quirk where the timing for the surround clip is changed, cuz if I make a new project, I usually start the songs to beat 1. This makes cutting easier (cuz the beat phase is matched with your DAW phase, at the expense of cutting a bit of audio at the start), and also offers dependable sync, ie, if I replace the file with another source (different sources can start at different times), I just re-sync to beat 1 and I don't need to re-align the project that depends on it (ie, a mix). What you can do, is make a mp3 proxy. And then if you are definitely using that song in your mix (maybe halfway to completion), you can spend your time to tune the upscale, and it will be well-spent.
