# How I memorize music

## Introduction

This model is constructed from how I think I memorize music, and is roughly sorted by ability to recall. The below text graphic outlines the rough sizes of each section. It's not like I wanted to memorize music this way, but it's approximately how my brain does. The theme seems to be making playback deterministic when memorization memory is limited and vague. The problem with writing these sorts of thought-related documents is that the more I think about it, the more inaccurate it could get. This model has been derived from almost a decade of deliberately memorizing music. The oldest sound clip I can recall is over 2 decades old ish (ao 2014). 

Base===== | Hdr | Struc | Meta | X | V |

Basedata
Headerdata
Structuredata
Metadata
Extradata
Video
Putting it all together
Playback over time
Examples of corruption

## Basedata

Just lots of audio data. This contains the bulk of the data for the song stored in an efficient, like notes, relative pitch of notes, relative rhythm instruments, sounds, beats, etc. It also stores the different versions of a song (like org, remix, solo, orchestral, etc). Vocals too. If I am allowed to listen to MT or surround versions, that may be stored, too. Acapellas/Backup vocals from upscales, etc. COvers also. 
This part stores the variations of stuff in basedata. Variation in music, lyrics, instruments, etc. If no variationdata is found where there should be, the song just repeats the basedata according to structuredata.

Audio data stores some harmonics to recreate the original, because when it's corrupted, harmonics can sound weird or muffled.

## Headerdata

This has information about Pitch & Tempo. Not necessary, but helps to get the right pitch for a song quickly. (ED: it's actually a complete I-frame, ie, first few seconds of audio)

## Structuredata

This small but important part says how the parts of the song are meant to be played/linked together. On the large scale, it may have cursory parts like overall song structure. 

What's the next part to play based on the current part? 

As a result, seeking could be hard.
On the small scale, it may have timing (stipulated and hard caps on how long bits are supposed to be) , general pitch contours & amplitude envelope info to keep the song on track if a wrong bit is being played.

Envelope data may store drums if song has them.

Structure (envelope) data takes shorter to load than melody (base) data. So may take a few secs or a short playthru to load the melody during which playback of envelope/structure only may sound weird

## Metadata

Not all the following may be stored. Sometimes little or none. Last played date, first played date, bookmarks/playlist position, along with some more traditonal metadata like title, artist, album, year, album cover, etc. Memorized quality might be stored, ie, 44k xxbit 112Ckps AAC. 

## Extradata
Panning, dynamic, articulation data. 

## Video
I may have seen some sort of video for the song, that's stored. Though it's usually sparse. Sometimes the video helps the structuredata, but this is extremely rare (Clannad2B)


## Putting it all together

For a typical, 1-language pop song consisting of Intro, Verse A , Chorus, Verse B, Chorus, Bridge, Chorus, Outro:

Basedata will have Intro, Verse A , Chorus, Bridge, Outro
Structuredata will have this structure
Variation data in Basedata should have differences in lyrics/instruments between verses etc.

Typically, Structuredata guides myself into make the right decision into which basedata part to load/play next based on the current basedata part. 

For some long, classical music with many unique parts like Poulenc's 1st piano concerto, there will be lots of data on Basedata, but still some bits in Structuredata.

Some songs in rondo form like Erik Satie's Jeux with a ABACABA for, will have ABC in Basedata, rondo form as Structuredata.

## Playback over time

Any two playbacks may be different.

Over time, structure/basedata may become corrupted, so songs lose or change parts. Corrupted basedata may lose instruments. Missing Extradata will lose dynamics in the song. Corrupted basedata/headerdata may slightly affect the pitch.

Some playback errors are correctable or workaroundable, some aren't

Songs may also repair themselves (but this is a long process, takes years), as no two playbacks are the same. Songs may also be repaired by listening to the original version (obviously). Some songs may seem to have magically repair themselves, but most likely, i would've had a full listen recently.  If you haven't listened to a song in a while, it fels like clearing the dust off a LP by having the needle run through it.

Behaves like tape? Poulenc Pcto1, pitch goes down by ~.8st, lowpassing on vocals, on kobato songs. High contrast spikes stick out. Aqua terraria pitch -0.1st

I frames, ie, the start of the song are very important. If you don't have start of song, you might not be able to start song, or may start at wrong pitch. (ex: hohoemi no plumage i remember the chorus better so i seek around to reveal the I frame)

## Examples of corruption

Basedata was damaged in Crystal Kay's I like it, so about 7s of the into was missing. Fixed.

Structuredata was damaged in Megumi Nakajima's Watashi ni Dekiru Koto (ED size) so a whole half of the song was missing! Fixed-ish.

Some basedata was damaged in the Pokemon S1 OP, so the lyrics in each of the verses are incorrect.

Simplified instrumentation on Jellyfish no Kokuhaku, & sped up by 5-10%?