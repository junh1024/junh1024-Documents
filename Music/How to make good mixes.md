# How to Make Good Mixes

Introduction
---
A mix is when you join multiple songs seamlessly, with a focus on the transitions and keys. This guide is mainly for making mixes offline in a DAW with a bias on my style, but some of it will be applicable to live mixes in a DJ program, especially the music theory parts. It's easier to perfect your mix and apply more complex techniques to make your mix better, offline. This guide will not cover too much about management, performance, and audience issues. Please refer to another source, such as [this](https://youtu.be/lBxZp0vgapk) or the [MiK book](https://mixedinkey.com/book/). This guide was written in mid-2020 and draws on my experiences making a bunch of mixes for about a year, and a few segues since 2015.

Software
---

## Information software
### Paid solutions
[As of mid-2022](https://old.reddit.com/r/DJs/comments/rn2wu5/key_detection_comparison_2021/) , Mixed in Key is still king for finding key, but Traktor Pro and beaTunes isn't far behind. Some songs are off key by a fraction of a semitone. if you can't fix it by ear, you can use Platinum Notes which will display the exact amount of cents that it's detuned by.

DJ Programs like Traktor Pro, rekordbox, djay, and VirtualDJ can also find BPM. If your app can show fractional BPM, that's a big plus as you can accurately match more songs. 

If you want a VST for your DAW, Mixed in Key has a studio edition as a plugin. There is also Hornet Songkey Mk3. Songkey displays 3 candidates in case the top candidate is wrong. But the BPM detection is rubbish. There is a Mk4 but I can't test it properly. The advantage as a plugin, is that you can manually play a loop of the root/tonic chord to hopefully improve accuracy.

### Free solutions:
[Mixxx](https://www.mixxx.org/) is the best of the free software which can detect BPM and Key (using libkeyfinder). If you want a standalone software, there is [Keyfinder](http://www.ibrahimshaath.co.uk/keyfinder/) .

[Theorytab](https://www.hooktheory.com/theorytab) by hooktheory has a small database of songs & keys, but is very good, and you can see songs categorized by chord progression, important for mashups. https://www.beatsource.com/ and https://www.karaoke-version.co.uk show BPM & key, but are less accurate & insightful. https://tunebat.com/ and several other sites are based on spotify data, which is fine for BPM (if it's not fractional or variable), but is rubbish for key. See [this reddit post](https://old.reddit.com/r/mashups/comments/uu5fn1/resource_best_databasessoftware_for_finding_keys/) for more information on each.

Keep in mind with key, no software is 100% accurate (MiK is only 85%), so please check results before using them.

## Production software
You will need music production software to make mashups or mixes. I use [REAPER](http://www.reaper.fm) since you can mix & match files with different codecs, sample rates, channels, and there are [many ways to change pitch](https://i.imgur.com/FtJAE26.png) & tempo freely with the HQ Elastique algorithm. My [REAPER Quickstart guide](https://i.imgur.com/HA1Oo7D.png) .

Beginners can give the [Mixmeister](https://www.mixmeister.com/) series a try, it does one job, but it has helpful BPM features. For live performance, many DJ apps are available. Destructive audio editors (like Audacity) are NOT recommended since they won't have features to expedite music editing (like, cutting on beats & bars). Most Video editors are NOT recommended since, in addition to not being able to cut on beats, you'll be distracted making the video, instead of making good audio.

## Setting properties
### Setting BPM
It's likely you will need to set a custom BPM/rate for your source(s). Some DAWs can set BPM directly. For those that can't, new rate = new BPM/old PBM.

REAPER since v6 can set BPM directly, in media item properties > take properties > playback rate > set. For older versions, I have made some python scripts. Setup [Reascript Python](https://github.com/junh1024/Reaper-Surround#reascript-python-setup-for-windows) guide. Get the scripts from [here](https://github.com/junh1024/Reaper-Surround/archive/master.zip) . Then, call "Set item BPM.py" which sets the BPM of 1 clip, or "Set item BPM_sequential.py" which sets the BPM of multiple clips.

### Setting Key
The key detection software above usually sets the key in the tile tags, or at least show you the detected key. I use the standard system of single letter, or appended by m for minor keys. Like C and Am for C major & A minor. For sharps & flats, I use sharps only. Like A# instead of Bb. Whatever you do, keep it consistent & clear, to make it easier to see relationships between your keys. For pop/electronic, major seems to slighly dominate, but for Rock & Touhou, minor seems to slighly dominate (2hu is a game tho).

In REAPER, you can make an empty item, type in your key, stretch to fill item, and group it to your song to make a nice big key display. https://i.imgur.com/RSGMsH2.png . In other DAWs you may resort to small text & renaming your clips. If you've come from my Mashups guide, you can go back now.

Planning
---
This guide covers constant BPM mixes. This is easiest to comprehend & manage. There are techniques to join songs of very different BPMs, they won't be covered here. If you choose songs of similar genre, that will also be easier, since genre implies some closeness in instruments & BPM. I usually make thematic mixes with the theme being genre. Pop is a meta-genre ie, songs aren't really close. I always have problems with pop.

You should have at least 2 albums worth of material to join, since you will be throwing some away. After you've analysed the BPM of your songs, take the average, throw away songs that are >=15% from the average. Then set the average as your project BPM in your DAW. After you finish your mix, you can take an average & set the BPM again (or use my "Get item BPM.py" weighted average Reascript) to get a more appropriate average BPM, since presumably you've thrown out some songs again.

Meter
---
Most songs you have will be 4/4. If you encounter a song that is a different time signature like 6/8, you could throw them away, or make a dedicated 6/8 mix.

Anyway, you can join 4/4 with 6/8 by treating 6/8 like 2/4, but to make sure they join good, the beats should be weak so they don't clash around the transition. Joining 4/4 with a song that's the same meter but 2x as fast or slow, is theoretically compatible, but may not work in practice due to a difference in intensity. 

Starting
---
Insert media into your DAW if you haven't already. Place them to the right, leave a large gap, and have your opening song to the left. You can join songs into groups of 2-3, then join those groups into a mix. Or you can join them sequentially. If you're having trouble deciding on an order, at least join songs with the same keys.

What should be your opening song? Start off your mix with a bright, mid-intensity song. Take a hint from track order on albums (but maybe not anthologies or compilations), it can help you to make a journey as the mix progresses. For a short mix, your peak song(s) should be around halfway or near the end of your mix. They should be prominent in at least intensity, and it may have a noticable melody/motif/vox, etc. You can end your mix with a bang, or a wimper, but it should sound like an end, or edit it as such.

Vary your intensity as you go through the songs, but that might happen anyway due to differences in song content & key compatibility. This is important as if it's all high all the time, it will be very boring. Aim to have a noticeable dip in energy about halfway in the mix, maybe at least an entire song. If there's a long breakdown in a song, I try to place that song at or after the middle of the mix, since my mixes seem to be around 25m.

For shorter mixes <30mins, you can have 1 beginning & end tracks. For longer mixes >30mins, you can have 2 beginning & end tracks. This is a rough guide & comes from recalling my mixes. Some of my best mixes are (partially) made in reverse, with the best songs at the end, so that's a valid approach as well. Maybe the ending is more important & it's OK to have bum transitions & filler tracks at the start.

Circle of 5ths
---
Unlike [mashups](https://github.com/junh1024/junh1024-Documents/blob/master/Music/How%20to%20make%20good%20mashups%20V2.md#introduction), knowing key theory is almost mandatory for making good mixes.

If you're like me, you would've heard the circle of 5ths being mentioned many times, but not knowing how it's useful, until now. Here it is below in strip form with C major at the center, and relative minor below. Because it's a strip, keep in mind that the ends join (like, C# joins with F#).

	C#	G#	D#	A#	F	[C]	G	D	A	E	B	F#
	A#m	Fm	Cm	Gm	Dm	Am	Em	Bm	F#m	C#m	G#m	D#m

If you join 2 songs in adjacent segments on the strip (move horizontally or vertically), it should sound good. But if you move diagonally, it might not. In the [Romantic era](https://tobyrush.com/theorypages/pdf/en-us/romantic-era-techniques.pdf) people started using 3rds more. Note that moving up & down is a 3rd, and moving diagonally down right is also a 3rd. Although horizontally neighboring keys are both a 5th apart, I often find that moving down a 5th sounds better, maybe since it sounds like a perfect cadence. Depending on how your keys come out, you might be able to move around the circle for at least a few songs. You might need to do a 2nd round of importing songs to fill in gaps in your progression. It should go without saying that joining the same key & mode (like C > C) should sound good, and joining with the same key, but different mode (like C > Cm) could sound good.

Many songs are in 1 key only. But there are some that are in 2 or more keys. These are more valuable as you can now have more possibilities to join keys, but you can only join certain keys at certain points, and it's now polarized (assuming each end is a different key). So you can't reverse your mix and it'll still sound good.

Other strategies
---
You could try to match chords between songs. Or match notes instead (chords & melodies).

Changing Keys
---
I try not to pitchshift songs most of the time, since if the key is shifted, it sounds wrong/not original, and sortove defeats key theory. But there might be a few cases when you want to.

- If there's a song you really want to include between 2 other ones, but it's off by 1st, OK, you can try changing the pitch to fit
- If there's a song that ascends key at the end and you don't want it to so it fits better, you can force it down using pitchshifting. But you might find a section with your desired key earlier in the song.
- If there's a song that doesn't ascend key at the end and you want it to so it fits better, you can force it up using pitchshifting. This might make the song better & also increase energy.
- pitchshifting may create artefacts, see my [Pitchshifting Tips in my Mashup Guide](https://github.com/junh1024/junh1024-Documents/blob/master/Music/How%20to%20make%20good%20mashups%20V2.md#pitchshifting-tips)

Fades
---
You can do fades to join 2 clips. The simplest fade is a crossfade, where 1 clip (slowly) fades out while the other fades in. Your DAW may do automatic crossfades if you overlap 2 clips, or you can manually fade 2 clips on separate tracks for more control. You could also do a L-fade where 1 clip fades out but the other cuts in. As for length of fade, what's appropriate can vary by genre. For house, there's the standard 32 beat or 8 bar crossfade. But for rock, a fast fade or a cut may be appropriate. For pop, it's tricky & depends on song. You could also do a more sophisticated split-combine frequency fade (maybe available under a different name), where you start from the top/right of the frequency and move to the bottom/left, and progressively lowpass the outgoing song & un-hipass the incoming song so that the frequency ranges form a whole, but of different songs.

8olei
---
I dub thee 8olei transition, short for 8-bar OverLap and EqualIzer. You overlay 2 clips cut to 8 bars long with aligned phases (phrase matching), with a hi &/ lopass on 1 or both. It's suggested to have only 1 clip with drums, to avoid double drums clashing. If you need more separation than EQ to, try Yellow DrumExtract to isolate drums, Cockos ReaFIR in compress mode to turn down harmonics, or VSTi & MIDI to recreate some motifs. It's also suggested the incoming song to have a small breakdown, or a transition to a new part of the song at the end, to distract the listener. When done right, the 8olei transition sounds really good, since songs usually introduce new elements in blocks, not by fades. Hence, it's very song-like. It depenz on how much variation your song has, to get the flexibility you need to choose a good transitioning section.

My Philosophy
---
Try to make mixes with vocal songs (full lyrics). They'll be more memorable to you & your audience. I started off making vocal mixes, then made some instrumental mixes later. I'm guessing that it will be half n half when I finish my current bunch. You can probably find vocal songs in most genres. Vocal house songs might be under dance. The only genres that tend to have less vocals from the genres I've tried, are trance & hard house.

I avoid reusing the same versions of songs in mixes, different versions are OK. Example: I used Tomare! in my rock mix. But I also used that in my house mix, but a house remix. I also used Kaze no message in my initial rock mix, but I might use it in a future mix, so in the process of improving my rock mix, I removed that song & a few others, and re-released it. But supposedly many DJs have a (few) songs they want to play at every gig.

I know many mixes are 1 hour long, but, I target a length of 30mins for mixes since:
* it fits on 1 side of a C60 tape (if you want to archive them on a cheap, non-digital format)
* It's not too short, or long. It's a satisfying length
* Making longer mixes is harder since you need to make lots of joins work

Generally, unless I'm making a minimix, I try to have a decent length for each song, so at least 3', and I may reject songs < 3'30". I might restructure songs so that transitions sound better, eg, moving the bridge to the start, or starting after the intro to match intensity or keys. 

When I do transitions, I try to join on a melodic part, since:
* It keeps the energy
* It's harder, but more interesting
* Some songs may not have a long drum-only lead-ins & lead-outs, like songs with full lyrics
* I also try to choose fade or 8olei & stick to that for the whole mix

Sometimes there are songs with "missing beats", ie, incomplete bars so that the usual 4/4 phase is thrown off after some time. Again, for management reasons, I extend it, or chop it off. For times when those don't sound good, IMO it's most important to have sync at the end of a song, so that the phase is correct when you join the next song.

I generally don't use mashups in mixes since double stretching = LQ. So If I were to do that, I might recreate the mashup in my mix so that the audio is stretched only 1ce.

Surround
---
Using surround in mixes is completely optional, but offers more flexibility. Though the need is declining due to realtime separation technology, general interest in surround might be increasing. You can make surround mixes, but it will most likely be upscale. You can upscale after making a mix, but that's lazy & bad quality since phase information that upscalers use is perhaps mangled by pitch-time stretching. So, upscaling *before* is preferred. Deciding whether to make a surround mix or not depends on a few factors, how well I like the songs, and how well they upscale to surround. Non-vocal mixes I usually don't bother for surround since you can't put vox for an easy discrete center.

Order for 51/71 is L R C LFE BL BR SL SR (SMPTE-MS)

If you make a 3ch mix of a song, you can have more control over vox, providing the instro is only in LR & vox is mostly in C. How to make such a clip is not covered in this guide. If you wanted this level of control previously, you would have 2x stereo clips. Having them as a single surround clip ensures they never get misaligned & bypasses the grouping hassle. Unless you have a DAW that imports stereo as separate mono clips *ahem Pro Tools*.

If you're upscaling to 5.0 padded to 5.1, you also upscale the instro to the corner 4. If the vox has a significant side component, and you sometimes need a pure instrumental (ie, no vox) sometimes, and you're aiming for 5.0 surround delivery, you can upscale the vox to 3ch, but move vox L&R to SL SR for a total of 7.1. Then you can mute C & side & get a surround instrumental. It's suggested to downmix the vox in side to the front for 5.0 surround.

As I said earlier, upscaling to surround (at least in DSP order) before making your mix is preferred, but you don't want to waste time upscaling songs, only to throw them out, since tuning upscaling settings for a song takes 2 hours. I also have another quirk where the timing for the surround clip is changed, since if I make a new project, I usually start the songs to beat 1. This makes cutting easier (since the beat phase is matched with your DAW phase, at the expense of cutting a bit of audio at the start), and also offers dependable sync, ie, if I replace the file with another source (different sources can start at different times), I just re-sync to beat 1 and I don't need to re-align the project that depends on it (ie, a mix). What you can do, is make a mp3 proxy. And then if you are definitely using that song in your mix (maybe halfway to completion), you can spend your time to tune the upscale, and it will be well-spent.

regex for titles: (\w+\r\n)---