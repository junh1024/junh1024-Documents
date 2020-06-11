# How to make (good) mixes

Introduction
---
A mix is when you join multiple songs seamlessly, with a focus on the transitions and keys.


Concept
---
I usually make thematic mixes (& hence cohesive), with the theme being genre. Why genre? Cuz genre implies some closeness in instruments & BPM. Pop is a meta-genre ie, songs aren't really close. I always have problems with pop.

I avoid reusing the same versions of songs in mixes, different versions are OK. Example: I used Tomare! in my rock mix. But I also used that in my house mix, but a house remix. I also used Kaze no message in my initial rock mix, but I might use it in a future mix, so in the process of improving my rock mix, I removed that song & a few others, and re-released it.

I make constant BPM mixes. This is easiest to comprehend & manage. There are techniques to join songs of very different BPMs, they won't be covered here. Sometimes there are songs with "missing beats", ie, incomplete bars so that the usual 4/4 phase is thrown off after some time. Again, for management reasons, I extend it, or chop it off. For times when those don't sound good, IMO it's most important to have sync at the end of a song, so that the phase is correct when you join the next song.

Surround
---
Using surround in mixes is completely optional, but offers more flexibility. You can make surround mixes, but it will most likely be upscale. You can upscale after making a mix, but that's lazy & bad quality cuz phase information that upscalers use is mangled by pitch-time stretching. So, upscaling *before* is preferred. Deciding whether to make a surround mix or not depends on a few factos, how well I like the songs, and how well they upscale to surround. Non-vocal mixes I usually don't consider for surround.

Order for 51/71 is L R C LFE BL BR SL SR (SMPTE-MS)

If you make a 3ch mix of a song, you can have more control over vox, providing the instro is only in LR & vox is mostly in C. How to make such a clip is not covered in this guide. If you wanted this level of control previously, you would have 2x stereo clips. Having them as a single surround clip ensures they never get misaligned & bypasses the grouping hassle. Unless you have a DAW that imports stereo as separate mono clips *ahem Pro Tools*.

If you're upscaling to 5.0 padded to 5.1, you also upscale the instro to the corner 4. If the vox has a significant side component, and you sometimes need a pure instrumental (ie, no vox) sometimes, and you're aiming for 5.0 surround delivery, you can upscale the vox to 3ch, but move L&R to SL SR. Then you can mute the side & get a surround instrumental. It's suggested to downmix the vox in side to the front for 5.0 surround.

As I said earlier, upscaling to surround (at least in DSP order) before making your mix is preferred, but you don't want to waste time upscaling songs, only to throw them out, cuz tuning upscaling settings for a song takes 2 hours. I also have another quirk where the timing for the surround clip is changed, cuz if I make a new project, I usually start the songs to beat 1. This makes cutting easier (cuz the beat phase is matched with your DAW phase, at the expense of cutting a bit of audio at the start), and also offers dependable sync, ie, if I replace the file with another source (different sources can start at different times), I just re-sync to beat 1 and I don't need to re-align the project that depends on it (ie, a mix). What you can do, is make a mp3 proxy. And then if you are definitely using that song in your mix (maybe halfway to completion), you can spend your time to tune the upscale, and it will be well-spent.

Planning
---

Note for REAPER: REAPER doesn't have the concept of a clip BPM (maybe other DAWs too), so use my "Set item BPM.py" in https://github.com/junh1024/Reaper-Surround , and see my [Reascript Python](https://github.com/junh1024/Reaper-Surround#reascript-python-setup-for-windows) guide.

Keys
---
Unlike mashups, knowing theory is almost mandatory for makng good mixes.

If you're like me, you would've heard the circle of 5ths being mentioned many times, but not knowing how it's useful, until now. Here it is below in strip form with C major at the center, and relative minor below.

C#	G#	D#	A#	F	[C]	G	D	A	E	b	F#
a#	f	c	g	d	[a]	e	b	f#	c#	g#	d#

If you join 2 songs in neighboring keys or modes (move horizontally or vertically), it might sound good. But if you move both (move horizontally and vertically), it might not.

Instruments
---
It's not uncommon to have a section of 8 bars where ingoing & outgoing songs are both played, maybe with a hipass on the incoming piece. Sometimes you might need more separation than EQ to help glue them together. you can use Yellow DrumExtract to isolate the drums, or you can use VSTi to recreate some motifs.

Fades
---
You can do fades to join 2 clips. The simplest fade is a crossfade, where 1 clip (slowly) fades out while the other fades in. Your DAW may do automatic crossfades if you overlap 2 clips, or you can manually fade 2 clips on separate tracks for more control. You could also do a L-fade where 1 clip fades out but the other cuts in.

As for length of fade, what's appropriate can vary by genre. So for house, there's the standard 32 beat or 8 bad crossfade. But for rock, a fast fade or a cut may be appropriate. For pop, it's ticky & depends on song.