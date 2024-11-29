# How to Make Good Mixes

Introduction
---
A mix is when you join multiple songs seamlessly, with a focus on the transitions and keys. This guide is mainly for making mixes offline in a DAW with a bias on my style, but much of it will be applicable to live mixes in a DJ program, especially the music theory parts. This guide will have a very detailed approach, with a focus on mixing in key & song selection. If you don't want to change your mixing style, that's fine, stop reading. Otherwise, read on.

It's easier to perfect your mix and apply more complex techniques to make your mix better, offline.

This guide will not cover too much about management, performance, and audience issues. Please refer to another source, such as [this video](https://youtu.be/lBxZp0vgapk) or the [MiK book](https://mixedinkey.com/book/). This guide was written in mid-2020 and majorly updated in 2024, and draws on my experiences making a bunch of mixes for a few years, and a few segues since 2015.

Vinyl
---
Mixing with Vinyl is possible and was prevalent in the past. I won't go into great detail about mixing in vinyl except probably the biggest difference is enforcement of varispeed. That is, a change in speed also changes the pitch.

Vinyl is also a tricky medium, and unsteady tempo is a common issue. The easiest way to deal with that is simply to buy the digital version of that song. But [sometimes there are differences](https://old.reddit.com/r/ClassicTrance/comments/1gw0hfy/i_am_reripping_all_of_my_vinyl_15_crates_of/) in audio due to lyric changes or sample replacement as it's a big thing in this day and age. The biggest factor in tempo variation of your record is undoubtedly the condition of your vinyl. [Baking records](https://old.reddit.com/r/vinyl/comments/qxq2lr/flattening_records_using_the_ovenglass_technique/) is a thing. But apparently, your power supply can affect tempo stability, and it's [suggested to use a UPS](https://old.reddit.com/r/ClassicTrance/comments/1jh2j7n/i_found_a_solution_to_the_wandering_tempo_of_some/) to get more stable tempo. Also recall the audiophile from Japan who requested [their own utility pole](https://gizmodo.com/obsessed-audiophiles-in-japan-are-installing-their-own-1785291714) to get electricity more directly from their power co.


Software
---

## Information Software
### Paid solutions
[As of mid-2022](https://old.reddit.com/r/DJs/comments/rn2wu5/key_detection_comparison_2021/) , Mixed in Key is still king for finding key, but Traktor Pro and beaTunes isn't far behind. Some songs are off key by a fraction of a semitone. If you can't fix it by ear, you can use Platinum Notes which will display the exact amount of cents that it's detuned by.

DJ Programs like Traktor Pro, rekordbox, djay, and VirtualDJ can also find BPM. If your app can show fractional BPM, that's a big plus as you can accurately match more songs.

Traktor & Serato were popular in the 2000s & 2010s, but in the 2020s, rekordbox is [suddenly very popular](https://raw.githubusercontent.com/pestrela/music/master/census_graphs/dj_software_over_time.jpg?raw=true) . This is [because](https://wearecrossfader.co.uk/blog/why-do-so-many-djs-use-rekordbox/) most DJ controllers are Pioneer, and it's Pioneer's own software. 

**VST solutions:**

If you want a VST for your DAW, Mixed in Key has a studio edition as a plugin.

There is also Hornet Songkey Mk3. Songkey displays 3 candidates in case the top candidate is wrong. But the BPM detection is rubbish. Key detection is quite mediocre. Mk4 supposedly improves on this. The advantage as a plugin, is that you can manually play a loop of the root/tonic chord to hopefully improve accuracy.

Zplane Tonic is another option. What I like about tonic, is that you can fold the keys and enable chords, so you can play along with the chords of the song so and check the key is correct. The key detection is perhaps more reliable than Hornet Songkey, but it doesn't have a chord detection feature. Again. It works better if you have if you play the tonic cord through the plugin. 


### Free solutions:
[Mixxx](https://www.mixxx.org/) is the best of the free software which can detect BPM and Key (using libkeyfinder). If you want a standalone software, there is [Keyfinder](http://www.ibrahimshaath.co.uk/keyfinder/) .

[Theorytab](https://www.hooktheory.com/theorytab) by hooktheory has a small database of songs & keys, but is very good, and you can see songs categorized by chord progression, important for mashups. https://www.beatsource.com/ and https://www.karaoke-version.co.uk show BPM & key, but are less accurate & insightful. https://tunebat.com/ and several other sites are based on spotify data, which is fine for BPM (if it's not fractional or variable), but is rubbish for key. See [this reddit post](https://old.reddit.com/r/mashups/comments/uu5fn1/resource_best_databasessoftware_for_finding_keys/) for more information on each.

Keep in mind with key, no software is 100% accurate (MiK is only 85%), so please check results before using them.

## Production software
You will need music production software to make mashups or mixes non-live. I use [REAPER](http://www.reaper.fm) since you can mix & match files with different codecs, sample rates, channels, and there are [many ways to change pitch](https://i.imgur.com/FtJAE26.png) & tempo freely with the HQ Elastique algorithm. My [REAPER Quickstart guide](https://i.imgur.com/HA1Oo7D.png) .

Beginners can give the [Mixmeister](https://www.mixmeister.com/) series a try, it does one job, but it has helpful BPM features. For live performance, many DJ apps are available. Destructive audio editors (like Audacity) are NOT recommended since they won't have features to expedite music editing (like, cutting on beats & bars). Most Video editors are NOT recommended since, in addition to not being able to cut on beats, you'll be distracted making the video, instead of making good audio.

## Setting properties
### Setting BPM
It's likely you will need to set a custom BPM/rate for your source(s). Some DAWs can set BPM directly. For those that can't, new rate = new BPM/old PBM.

REAPER since v6 can set BPM directly, in media item properties > take properties > playback rate > set. For older versions, I have made some python scripts. Setup [Reascript Python](https://github.com/junh1024/Reaper-Surround#reascript-python-setup-for-windows) guide. Get the scripts from [here](https://github.com/junh1024/Reaper-Surround/archive/master.zip) . Then, call "Set item BPM.py" which sets the BPM of 1 clip, or "Set item BPM_sequential.py" which sets the BPM of multiple clips.

### Setting Key
The key detection software above usually sets the key in the tile tags, or at least show you the detected key. I use the standard system of single letter, or appended by m for minor keys. Like C and Am for C major & A minor. For sharps & flats, I use sharps only. Like A# instead of Bb. Whatever you do, keep it consistent & clear, to make it easier to see relationships between your keys. For pop/electronic, major seems to slightly dominate, but for Rock & Touhou, minor seems to slightly dominate (2hu is a game tho).

In REAPER, you can make an empty item, type in your key, stretch to fill item, and group it to your song to make a nice big key display. https://i.imgur.com/RSGMsH2.png . In other DAWs you may resort to small text & renaming your clips. If you've come from my Mashups guide, you can go back now.

Planning
---
This guide covers constant BPM mixes. This is easiest to comprehend & manage. There are techniques to join songs of very different BPMs, they won't be covered here. If you choose songs of similar genre, that will also be easier, since genre implies some closeness in instruments & BPM. I usually make thematic mixes with the theme being genre. Pop is a meta-genre ie, songs aren't really close. I always have problems with pop.

You should have at least 2 albums worth of material to join, since you will be throwing some away. After you've analysed the BPM of your songs, take the average, throw away songs that are >=15% from the average. Then set the average as your project BPM in your DAW. After you finish your mix, you can take an average & set the BPM again (or use my "Get item BPM.py" weighted average Reascript) to get a more appropriate average BPM, since presumably you've thrown out some songs again.

Meter
---
Most songs you have will be 4/4. If you encounter a song that is a different time signature like 6/8, you could throw them away, or make a dedicated 6/8 mix.

Anyway, you can join 4/4 with 6/8 by treating 6/8 like 2/4, but to make sure they join good, the beats should be weak so they don't clash around the transition. Joining 4/4 with a song that's the same meter but 2x as fast or slow, is theoretically compatible, but may not work in practice due to a difference in intensity. 




Other strategies
---
You could try to match chords between songs. Or match notes instead (chords & melodies).

 
- pitchshifting may create artefacts, see my [Pitchshifting Tips in my Mashup Guide](https://github.com/junh1024/junh1024-Documents/blob/master/Music/How%20to%20make%20good%20mashups%20V2.md#pitchshifting-tips)



## Mix length

I've made many mixes from 5'-60' long. 
Many mixes are 1 hour long and that's a good length to stop at.

With shorter mixes, you have greater control over storytelling and every song has a purpose. With longer mixes, there's usually a lot of padding and the direction of the mix often suffers as quantity is pioritized over quality, especially for mixes >75' long.

Shorter mixes are also more suitable for archiving on analog mediums like cassette tape or vinyl.

## Flow

Flow is the passage from one song to the next. Good flow therefore implies that the two song was mixed in key will have some relationship in key, chords, or not. This would also imply that the two songs are matched in energy at the transition Point so you need to choose your transition points carefully or do some looping / editing to ensure this, or some clever phrasing to distract The Listener. on a technical level, this would also mean that the two songs are matched in volume and EQ. Mixing live, Doing trial runs of your mix is advisable to make sure all these elements are met to have good flow. Good flow can also mean that the songs are well ordered such that there is a logical and natural change in energy or mood from one song to the next.

Having a key change every transition isn't a problem. I've done mixes like that, and it leads to a decent speed of flow if that's your aesthetic. But >= 3 songs in the same key leads to a stagnant flow, so it's suggested to avoid that.

# aaa

Generally, unless I'm making a minimix, I try to have a decent length for each song, so at least 3', and I may reject songs < 3'30". I might restructure songs so that transitions sound better, eg, moving the bridge to the start, or starting after the intro to match intensity or keys. 

When I do transitions, I try to join on a melodic part, since:
* It keeps the energy
* It's harder, but more interesting
* Some songs may not have a long drum-only lead-ins & lead-outs, like songs with full lyrics
* I also try to choose fade or 8olei & stick to that for the whole mix

Sometimes there are songs with "missing beats", ie, incomplete bars so that the usual 4/4 phase is thrown off after some time. Again, for management reasons, I extend it, or chop it off. For times when those don't sound good, IMO it's most important to have sync at the end of a song, so that the phase is correct when you join the next song.


## Song choice

The songs make the mix, so if you choose good songs, that makes the mix more interesting and engaging. You can notice the effect of song choice over a mix. If not, someone may subconsciously feel it.

Songs can be interesting due to being melodic, or reasons due to music theory. Songs composed specifically for anime/games are about 80% melodic because they must support the storytelling. Vocal songs are usually melodic, but not always (see examples). Standard house or trance is mainly designed to move the dance floor, not tell a story, so they're usually about 30% melodic.

Aim to have you mix to be >= 66% melodic. Thus, you'll probably need to make major changes in song selection.


### What is melodic?

To be melodic, it should meet these 5 criteria: variation in rhythm, variation in pitch, sufficient length (4+ bars), variation in chords, and activity level. Only the chorus/breakdown is measured. I'm trying to come up with an objective definition, but if you don't know how these criteria are going to work, it's something that you will know it when you hear it, and we'll go through some examples below.

- Melodic = 1 point
- Half-melodic = 0.5 points
- Non-melodic = 0 points

### Melodic
- BT - [Flaming June](https://youtu.be/YaOc4W_OyM0?t=286) : There's ample variation in rhythm and pitch in the motif, so this is firmly melodic
- Space Manoeuvres - [Stage One | Tilt's Apollo 11 Remix](https://youtu.be/uLyUCMRigfk?t=320) : There is synth in the background playing long notes with enough variation, and the phrase length is 8 bars, so we are forced to accept this as melodic
- Ferry Corsten – [Insolation | Ferry Corsten remix](https://youtu.be/dYgX7Yjs7rM?t=370) : The chords in the chorus are melodic.

### Half melodic

- Stoneproof - [Everything's Not You | Quivvers Space Mix](https://youtu.be/ejGBNLf3iUU?t=343) : The synth motif is sort of melodic, but the chord change from 6 to 6 dim isn't significant so half-melodic.
- Paul van Dyk - [Nothing But You](https://www.youtube.com/watch?v=j9u2DtCJde8) : The vocals have a melody, but it's fairly simplistic and the activity level isn't particularly high, so half-melodic
- Thrillseekers - [Synaesthesia | En-Motion 2004](https://www.youtube.com/watch?v=KaFlk0uWp1k) : This is a well-known song with lots of layering, but the lack of clarity in lead melody and short phrase length so only half melodic

### Not melodic

- Art of Trance – [Kaleidoscope | Sunday Club Remix](https://www.youtube.com/watch?v=SPI73X01uHA) : Although the piano can be considered melodic in the buildup, only the chorus is measured. The lead in the chorus has no variation in rhythm and is very repetitive. Not melodic.
- Der Dritte Raum - [Hale Bopp | Jackdaw Mix](https://www.youtube.com/watch?v=u0znVcTsk3c) : The main motif is only a bar long so it's not melodic.
- Underworld - [Born Slippy | Paul Oakenfold Remix](https://www.youtube.com/watch?v=KZcT8_EH0pE) : Although this song is vocal, there's little variation in pitch. The lyrics sound more like a drone or rap. Not melodic.

### Interesting

If a song isn't melodic, it could also qualify as being interesting due to music theory. This would usually mean interesting chords or key changes. 

- Cygnus X – [The Orange Theme | Solar Stone Remix](https://www.youtu.be/AHM3USRxTTU) (or most versions) : It has the chord progression of 6 4 3 _K . Which means during the chorus, it changes key every four bars, so is therefore interesting.
- Fable - [Above](https://www.youtube.com/watch?v=RlK2-56G_6U) : In the buildup it has the chord progression 6 2M. It uses the alternate mode chords of 2M, so it's interesting.
- 56K ft Bejay - [Save A Prayer | LMC Mix ](https://www.youtube.com/watch?v=Os3MWHuIUHk) : There's a key change in the pre-chorus. The vocals also have enough activity & variation to be considered melodic. So the song is both melodic and interesting.

Interesting songs don't count towards the melodic target (unless they're also melodic), but I use them to fill up the rest of the songs that aren't melodic.

### Cheese

One can classify/quantify cheese.

** Classification of cheese**
- Type 1 cheese: Overly popular or emotional (lyrics)
- Type 2 cheese: Cheap-sounding composition or production 

Songs can be both types. Cheese is incredibly subjective - 1 man's cheese can be another man's classic. Cheese is a spectrum - songs can be ordered and ranked according to how cheesy they are. I try to avoid cheesy songs in my mixes, but this is completely optional and depending on the audience, they may enjoy cheese.

## Mix Structure
The intent and delivery of your mix is going to significantly change what you do with the mix. If you're doing a live mix in front of an audience, then your primary aim is to respond and cater to the audience, and get the dancefloor moving. As such, managing the energy is more important than mixing on key. If you're making a mix that will be heard over the internet at someone's leisure, it will be evaluated more critically so being on key is more important.

Definitions:

- Uplifting = song in a major key
- Downlifting = song in a minor key
- Climax = uplifting AND high in energy
- Anti-climax = downlifting, optionally low in energy

In terms of ratio of uplifting to downlifting, I have found that 70% downlifting and 30% uplifting satisfies the classic trance crowd the best because they're mostly used to downlifting songs, and the 30% uplifting provides the needed variety. If the ratio were reversed, then many of them wouldn't like it. No more than 70% uplifting to avoid too little variety.

#### Beginning

You can start with a medium energy and medium mood song. If you're making a Halloween mix and head straight into a dark Halloween mood, it offers instant gratification, but you will miss out on some aspects. By gradually dropping the mood from medium to over a few songs you offer progression and development of the mix.

I often, but not always, the second song will be lower in energy then the first song. This allows you to have a more dramatic build-up later on. You'll see this on many pop albums.


Joining strategies for DAW
If you're having trouble deciding on joining songs, you can try joining songs with the same keys.
You can join songs into groups of 2-3, then join those groups into a mix. Or you can join them sequentially.
You can join songs in reverse if you have a known ending song. Some of my mixes use this strategy.

You can have filler tracks near the start to pad time, and most seasoned listeners will probably prefer filler at the start rather than the end.

#### Middle

After the beginning, build up or down to a climax or anti-climax. You can have multiple climaxes or anti-climaxes depending on the length of your mix. You can have an anti-climax before your climax to make their climax more dramatic. You can have the anti-climax after the climax. If you have an anti-climax you don't always have to have a climax. What is important is that you're changing the energy and mood over the mix to retain the interest of your listener. Good energy and mood management is one of those things you'll know it when you hear it.

There should be a climax or anti-climax around 50-75% of your mix.

[This guy](https://old.reddit.com/r/Beatmatch/comments/inas8k/different_moods_in_the_same_mix/g4cbrht/) suggests having 1-2 low energy songs in the middle of your mix, especially when performing live, so people can take a break (eg, going to the toilet). Even if you're not having a full low-energy song in the middle, it might be good to have at least a song with a long breakdown.

### End

Choose a song that is a bit different than the previous song. You can end your mix on medium energy uplifting. Or you can end your mix on a low energy downlifting song to finally relax the listener.

In terms of music theory, major/uplifting songs that go from 5 > 1 or 4 > 1 from the final chorus to the outro may be good candidates. These would be [perfect/authentic](https://en.wikipedia.org/wiki/Cadence#Perfect_authentic_cadence) and [plagal cadences](https://en.wikipedia.org/wiki/Cadence#Plagal_cadence) respectively. For minor/downlifting songs, this would be 3 > 6 and 2 > 6 respectively.

Examples:

- youith - [First Impression](https://youtu.be/tou9HBwHrSQ?t=338) : goes 5 > 1 from the chorus to the outro. Perfect cadence.
- Ferry Corsten – [Insolation | Ferry Corsten remix](https://youtu.be/dYgX7Yjs7rM?t=452) : goes 4 > 1 from the chorus to the outro. Plagal Cadence

If a song doesn't fit into a perfect or plagal cadence, it doesn't necessarily mean it's not suitable as an ending. These are candidate suggestions only. If you don't understand cadences or music theory, don't worry. A good ending song is one of those things you'll know it when you hear it.


### Storytelling



You may hear the term storytelling in relation to mixes. [Definitions vary](https://old.reddit.com/r/ClassicTrance/comments/1etu2cs/weekend_casual_megathread/lik27jx/) , but most people would probably agree on something like deliberate changes in energy and mood throughout a mix. A solid structure as discussed in #middle would apply. This would imply highs and lows, and in turn, a combination of both uplifting and downlifting songs placed where they make sense.

Like cheese, I would also say storytelling is a spectrum - a mix can feel like it has deliberate energy & mood changes, or not at all. I would say Mixing in key is a soft requirement for good storytelling - otherwise the listener may be distracted by clashing transitions. Again, not just "rekordbox 67% on key", but let's say about 80%. 

0 - A bunch of songs joined with little regards to aesthetic, order, or key. A mix made seemed to fit a length quota.
0.1 Songs joined together with little variation in energy/mood or no specific structure in mind, but basically everything on key and flows well
0.2 Songs joined together with some variation in energy/mood, or a specific structure in mind (maybe from light to dark)
0.4 Songs joined together, with different sections separated in energy/mood & fits a story template
0.8 Songs joined together, with different sections/songs and specific plot points, supported by lyrics of the songs themselves.

A mix doesn't have to have (good) storytelling, but it's something to keep in mind

## Mixing in Key

### Why mix on key?

Mixing on key means your transitions will sound more harmonious and seamless and therefore better. I'm one of those people that are sensitive to pitch, so transitions are off key, it is distracting to me. Other people might be tone deaf and therefore won't matter as much. It's unfortunate that DJs aren't paid more if they mix in key - they are just paid to move the dancefloor. 

### Why not mix on key?

[Critics say on-key mixing](https://youtu.be/STpNhQuUk6Q) limits track selection, creates a false sense of harmony, and similar-sounding tracks.

While creating false harmony is true since no software is 100% Perfect at key detection, I'll discuss strategies below on how to increase song selection. Similar-sounding tracks I would argue is a ~~skill~~ sourcing & library issue - just get melodic or interesting tracks in the 1st place. This was discussed above with melodic track selection. The other part is the flow, which will be discussed below.

## Circle of 5ths

There are 2 notable systems for mixing on key:

or Musical Keys


If you're like me, you would've heard the circle of 5ths being mentioned many times in music theory, but not knowing how it's useful, until now. Here it is below in strip form with C major at the center, and relative minor below. Because it's a strip, keep in mind that the ends join (like, C# joins with F#).

	C#	G#	D#	A#	F	[C]	G	D	A	E	B	F#
	A#m	Fm	Cm	Gm	Dm	Am	Em	Bm	F#m	C#m	G#m	D#m

If you join 2 songs in adjacent segments on the strip (move horizontally or vertically), it should sound good. But if you move diagonally, it might not. Although horizontally neighboring keys are both a 5th apart, I often find that moving down a 5th sounds better, maybe since it sounds like a perfect cadence. Depending on how your keys come out, you might be able to move around the circle for at least a few songs. You might need to do a 2nd round of importing songs to fill in gaps in your progression. It should go without saying that joining the same key & mode (like C > C) should sound good, and joining with the same key, but different mode (like C > Cm) could sound good.

Many songs are in 1 key only. But there are some that are in 2 or more keys. These are more valuable as you can now have more possibilities to join keys, but you can only join certain keys at certain points, and it's now polarized (assuming each end is a different key). So you can't reverse your mix and it'll still sound good.

Unfortunately for DJs, this system is a bit hard to memorize, and is a bit meaningless to DJs, which is why the following was invented

### About the Camelot wheel

![Camelot Wheel](https://mixedinkey.com/wp-content/uploads/2020/02/tutorialCamelot@2x.png)

The Camelot wheel was invented by the makers of mixed in key software. Values that are exactly a fifth apart are next to each other on the Camelot wheel. It abstracts away music theory into a system that makes it easy for DJs to be on key when mixing. This would be fine if all DJ software were close to perfect at key detection (like their own mixed in key software).

Unfortunately, that's far from the case and you will need to dive deeper if you want to actually be on key anywhere close to 90% (or pay up). Also, although the Camelot wheel is based on the circle of fifths, it seems that they wanted to make it as incompatible as possible since the starting position is very illogical from a musical POV where 1B=B and 1A=Abm. These are arbitrary starting positions on the piano. The Open Key system, primarily used in Traktor has a more logical starting point where 1d=C and 1m=Am, the 2 most important notes on a piano. If a song has multiple keys, then this won't be detected by software. It's also harder to understand extended techniques like using parallel keys and thirds.

### What system to use?
DJs would basically be forced to use camelot (or open key system if Traktor) due to rekordbox, but may need to do conversions with musical keys. 

#### What does mixing in key mean?

Mixing on key means from the current position on the wheel, you only go one step around, stay on the same key, or one step inwards/outwards. Not diagonally. Again, this would sound fine if all DJ apps were (near) perfect at key detection, but that is far from the case.


### Accuracy of DJ Software at Key Detection

Key Detection Comparison 2022
Apps & sites vs Human Ear

- **Mixed In Key**: 85%
- Traktor Pro: 74%
- BeaTunes: 73%
- Engine DJ: 73%
- DJUCED: 72%
- Mixxx: 71%
- djay Pro AI on Mac: 70%
- **rekordbox**: 67%
- Beatsource: 65%
- Serato: 63%
- Traxsource: 61%
- Beatport: 56%
- PCDJ DEX: 51%
- Lexicon: 49%
- VirtualDJ: 42%
- Spotify: 31%

[original Key Detection Comparison post](https://old.reddit.com/r/DJs/comments/rn2wu5/key_detection_comparison_2021/) by BazCurtis


So rekordbox is probably the most popular DJ app now, but is only 67% accurate. It means if you're mixing in key in rekordbox according to its key values, you'll only be about 67% on key. So every 3-5 songs there'll be a clash. Compared to if you were using MiK or keying by ear, you'll only hear a clash every 5-10 songs. This is noticeable over a mix.

### How is it wrong?

According to [this paper](https://www.ibrahimshaath.co.uk/keyfinder/KeyFinder.pdf) comparing Rapid Evolution 2, MIK 4.1, and Keyfinder 1 on the primary dataset, here are how different software detects key wrong:

- Out by a 5th: 27%
- Relative: 11%
- Parallel: 23%
- Other incorrect: 38%


### What to do when the detected key is wrong?

This is a very important topic but is neglected by basically all guides covering how to mix on key. There are a few strategies to overcome this:

- Get better software for key detection. MiK sometimes has sales (black friday, etc)
- Test out your transitions. If the transition to the next song sounds crap or clashing, the key detection is probably wrong. Try a different song. Learn to hear the difference between a on-key transition and a off key transition.
- Manually by listening to the song and then checking the key on a virtual piano
- Comparing multiple songs that are detected as the same key
- Comparing against songs that are keyed correctly, like the [Keyfinder V2 DB](https://www.ibrahimshaath.co.uk/keyfinder/KeyFinderV2Dataset.pdf)
- Checking on reputable websites which explain why the song is in a particular key, like Wikipedia, hooktheory, or guitar tab sites

### Mixing In Key Extended Technique

Mixing in key has sometimes been said as too restrictive since there are limited numbers of keys you can join together. There are some tricks that you can do to increase the songs selection:
- Truck Driver Key Change: In the final chorus of the song, raise the key by 1 semitone. This effectively doubles the number of songs you can join. This is better than the "power boost" trick described in some Mixing in Key guides, because it raises energy without being off key. You can also lower the key by 1 semitone but this sounds a bit strange so I seldom use it.
- Key stay: - If there's a song that ascends key at the end but you don't want it to so it fits better, you can force it down. But you might find a section with your desired key earlier in the song.
- Entire song key change: Sometimes if a song absolutely has it has to go in on that position, I may pitch the entire song up or down by one semitone.
- Parallel key: The parallel key is the same tonic but different mode. For example, the parallel key of C Major is C minor, or 3 steps & 1 in/outwards on the wheel. To avoid audible clashing, at least one song must be playing single notes of the tonic. As such, this technique will only work some of the time.
- Minor third: This is a move done out of desperation and won't sound that great most of the time, but is included for completeness. It is for example, the relationship between C and D#.

### Pitch Lock

I make my mixes in a DAW, so preserve pitch is on by default. But in DJ apps, it might be off by default or DJs May prefer to keep it off for quality reasons. It's best to keep the stretch amount to 5% or less for maximum quality. If you're trying to mix and have pitch lock off, keep in mind that changing the Tempo of a song will also change its pitch. A 5% change is approximately 1 semitone. The exact percentage changes needed to raise for lower by one semitone varies exponentially since it's a ratio.

If you have pitch lock/digital stretching on, I think that will rough up the waveform so it may look better


### Audio levels
When making a mix, the meters should be in the green most of the time, and just touching yellow during the Peaks. But this advice will probably be thrown out the window when performing live in front of the audience for the sake of keeping the dance floor moving.


### Transitions

In general, you can try longer transitions for slower genres like House and Trance, and short transitions for faster genres like Drum And Bass & Fast Rock. Although this is only a suggestion. You can have long transitions on Drum And Bass as well. For genres that aren't meant to be joined like pop, you might need to do what sounds best and vary the transition per track.

For all transitions, make sure your transitions the beat and phrasing is matched for both songs. If you're having trouble making a smooth transition, maybe you can change the transition point. For example, head straight into a breakdown after the transition, or do some editing like repeat the section after the 1st chorus if the song ends awkwardly (like fadeout, etc).

Note that if your transitions have long overlaps, then you basically need to be on key because both songs will be heard for a relatively long time. But if you transitions are short like 1 bar or shorter, then it's less important the two songs be in key because the two songs overlap less, although a on-key transition will still sound smoother.

Fades
---
You can do fades to join 2 clips. The simplest fade is a crossfade, where 1 clip (slowly) fades out while the other fades in. Your DAW may do automatic crossfades if you overlap 2 clips, or you can manually fade 2 clips on separate tracks for more control. You could also do a L-fade where 1 clip fades out but the other cuts in. As for length of fade, what's appropriate can vary by genre. For house, there's the standard 32 beat or 8 bar crossfade. But for rock, a fast fade or a cut may be appropriate. For pop, it's tricky & depends on song. You could also do a more sophisticated split-combine frequency fade (maybe available under a different name), where you start from the top/right of the frequency and move to the bottom/left, and progressively lowpass the outgoing song & un-hipass the incoming song so that the frequency ranges form a whole, but of different songs.

8olei
---
I dub thee 8olei transition, short for 8-bar OverLap and EqualIzer. You overlay 2 clips cut to 8 bars long with aligned phases (phrase matching), with a hi &/ lopass on 1 or both. It's suggested to have only 1 clip with drums, to avoid double drums clashing. If you need more separation than EQ to, try Yellow DrumExtract to isolate drums, Cockos ReaFIR in compress mode to turn down harmonics, or VSTi & MIDI to recreate some motifs. It's also suggested the incoming song to have a small breakdown, or a transition to a new part of the song at the end, to distract the listener. When done right, the 8olei transition sounds really good, since songs usually introduce new elements in blocks, not by fades. Hence, it's very song-like. It depenz on how much variation your song has, to get the flexibility you need to choose a good transitioning section.


## Reviewing mixes

Reviewing mixes takes the same areas as producing a mix. It's not necessary to know the songs to review a mix, although it helps the listener appreciate what was done. Here is a systematic method:

1. Transitions: Are they smooth and harmonic? 
2. Songs: Are they interesting and engaging to you? 
3. Whole mix: Is the way the songs are ordered make sense in flow, energy and mood management?

Surround
---
Using surround in mixes is completely optional, but offers more flexibility. Though the need is declining due to realtime separation technology, general interest in surround might be increasing. You can make surround mixes, but it will most likely be upscale. You can upscale after making a mix, but that's lazy & bad quality since phase information that upscalers use is perhaps mangled by pitch-time stretching. So, upscaling *before* is preferred. Deciding whether to make a surround mix or not depends on a few factors, how well I like the songs, and how well they upscale to surround. Non-vocal mixes I usually don't bother for surround since you can't put vox for an easy discrete center.

Order for 51/71 is L R C LFE BL BR SL SR (SMPTE-MS)

If you make a 3ch mix of a song, you can have more control over vox, providing the instro is only in LR & vox is mostly in C. How to make such a clip is not covered in this guide. If you wanted this level of control previously, you would have 2x stereo clips. Having them as a single surround clip ensures they never get misaligned & bypasses the grouping hassle. Unless you have a DAW that imports stereo as separate mono clips *ahem Pro Tools*.

If you're upscaling to 5.0 padded to 5.1, you also upscale the instro to the corner 4. If the vox has a significant side component, and you sometimes need a pure instrumental (ie, no vox) sometimes, and you're aiming for 5.0 surround delivery, you can upscale the vox to 3ch, but move vox L&R to SL SR for a total of 7.1. Then you can mute C & side & get a surround instrumental. It's suggested to downmix the vox in side to the front for 5.0 surround.

As I said earlier, upscaling to surround (at least in DSP order) before making your mix is preferred, but you don't want to waste time upscaling songs, only to throw them out, since tuning upscaling settings for a song takes 2 hours. I also have another quirk where the timing for the surround clip is changed, since if I make a new project, I usually start the songs to beat 1. This makes cutting easier (since the beat phase is matched with your DAW phase, at the expense of cutting a bit of audio at the start), and also offers dependable sync, ie, if I replace the file with another source (different sources can start at different times), I just re-sync to beat 1 and I don't need to re-align the project that depends on it (ie, a mix). What you can do, is make a mp3 proxy. And then if you are definitely using that song in your mix (maybe halfway to completion), you can spend your time to tune the upscale, and it will be well-spent.

https://old.reddit.com/r/DJs/comments/n36b28/if_you_buy_a_track_on_beatport_does_that_mean_you/

# Conclusion

This guide has shown you how to make good mixes due to aspects throughout the entire process. Using melodic songs will keep the listener engaged, and criteria with examples is shown. Since rekordbox is only 67% accurate, you need to listen carefully to transitions to make sure they are actually on key. Adapt transition length to the genres & songs.

regex for titles: (\w+\r\n)---
