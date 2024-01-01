# Atmos Music Mixing Notes

## Introduction
These are my mixing notes for my [Atmos Music Collection](https://github.com/junh1024/junh1024-Documents/blob/master/Music/Atmos%20Music%20Collection.md#introduction) . Downloads in the previous link.

## General volume
So near the end of Nov 2020, I was told about a reasonably-priced Atmos encoder. I spent a few days setting up my acc & then the following few weeks to rework my old 3D projects to be less hax & sound better. I also felt the need to get more stems to remix into songs, to form a substantial collection rather than just a few songs.

- Optinuum had little changes.
- Katamari Stars had major infrastructure changes. It is now back to surround, but now with std 15.1 routing. The levels were re-balanced. Replacing the 3oA panners with 151 panner via RPP editing was compatible, but the ranges were slightly different so needed a bit of adjustment. Slightly more sophisticated string upscaling. Strings slightly lowered.
- AC4 Blockade. Also had major changes. Since people will now listen with >5 speakers, I replaced the cheap 4ch reverb upscaled to 8ch, with a real 10ch reverb (FdnReverb). I discovered more notation errors with strings & horns so I fixed them, but prolly still not totally accurate. A few panning changes. Slightly more sophisticated string upscaling.
- Amapola. A few panning & notation changes.


## Cello Concerto
Overall, I liked it. I found it on the CMT page, and was expecting it to be something boring like a Mozart or Beethoven symphony, but it got my interest. Maybe since it's in minor. The introduction was a bit weak but due to stockholm syndrome I'm now a bit ambivalent about it. It concerto also sounds a bit like Greig's Piano concerto, mainly since they're both in Am. There is a subforum on the CMT site for the concerto. Unfortunately, there aren't many mixing retrospectives, apart from "eggshell"

Like me, eggshell applied reverb, compression, but doesn't want to spend too much time on automation. One of the first things you do to a classical MT is apply reverb. It makes the orchestra seem larger. But you can only apply so much reverb to enlarge a lack of players, before it sounds bad. The brass is panned to the back, but this also includes a tuba, but the Tuba does bass duty (bass should at the front). Ethan then gave me a Tuba MIDI, which I then changed to a Bass Guitar. Which now makes more sense. I then realized that due to the length of the Concerto, that it would totally dominate the length of a pop compilation.

So I started marking possible cuts & testing them out. The cadenza is easy to cut since there's only 1 instrument, but most other sections are hard. I started cutting from the end. Cutting is hard since there's some key changes. I need to use my knowledge of cadences, but Bending rules like 5 > 1m. The cutting is based on cutting out sections of theme 1. The intro was also shortened so that the cello solo comes in within 1 min, (like Greig's Piano Concerto), rather than within 2.

Despite spending some effort finding & explaining cuts, Ethan preferred to leave his concerto uncut. A few weeks later, I found some musopen sessions on the Internet Archive, so that it won't be out of place with a 16m length, as part of a classical compilation rather than a pop compilation.

I thought that Adding in section dynamics by comparing to Ethan's 2020 mix would be enough, but comparing sections the instruments balance is still off. So I need to do bus automation. With section bus automation, I did a reduced range of automation compared to Ethan. For me, The main thing is the strings-wind balance. It doesn't matter if the brass is a bit soft. It should sit in the mix, and not be too distracting. Since the brass is @back, this adds additional emphasis, so you can deliberately mix it slightly lower. Due to reduced range, my string bed is a bit higher than Ethan's during the cello solo sections. I prefer this, but mainly since I'm used to hearing the whole mix w/o automation. Since Ethan knows the most about his work, I sorta expected no need for automation of his Cello solo track (ED: he also didn't play it, Steven Thomas did). This isn't the case and it needs some dynamics work.

After a few weeks of leaving it, I realized the front may have too much reverb when downmixed to 51/71. So I need to change the reverb from 91 to 71.

I have made changes to percussion to be more playable with heavy handheld crash cymbals. The tambourine in the ballerina section was moved slightly to be more in time with the orchestra. The accenting is cool, but might be hard to play IRL.

I sent Ethan a copy and he said it needs section dynamics. I had accidentally turned off global dynamics. Also, Revisiting the concerto in March, I decide to take a closer look at global dynamics automation. The motif should be about +1.5LU relative to -18LU, and section loudness should be compared to neighboring sections & globally.

The French Horns are obviously synthesized, he said so himself on his page. So there's a problem of making them sound more realistic by softening the attacks. My initial approached use FFTMT & Mashtactic for transient designing. It's effective on slow sections like rehearsal mark G, but might eat attacks during fast sections. Also uses latency and CPU. I also added a louder FH send to the reverb while lowering the main send. This resulted in too much surround bleed. I finally settled on my own FFTMT (modified to be more effective) to reduce transients, but only on select selections using bypass.

There were also some timing issues. Ethan said he edited some timings, but I did further editing. The tambourines on the ballerina section which I fixed early in the mixing process, and the strings on J-K. Since it would be unconvincing that strings would be out of time with a cello solo IRL.

Ethan had some more feedback after the 1st surround version sent. The winds have some important countermelody that needs to be balanced within & outside the wind section (scales around the motif). He also heard some noise so I turned off auto mode in Bitutils V2. Turns out that good-sounding psycho bit reduction needs more work for quiet sections. He also wanted brass louder, but it would bias the surround field too much to the rear so I made only minimal changes to the brass.

## Pure Luxury
Again, found on the Cambridge MT site. I was expecting another mediocre pop piece, but I liked it. At >100 tracks, I thought it must be the production of an accomplished artist. I started getting ideas for surround as I listened to the song. But when I got the stems, I was slightly disappointed by some of the vox SQ, Since "Vox-stacked-ahhs-all" was all in downmixed stereo. The artist didn't have further separation due to being overdubbed on hardware, but I really wanted the idea to work. I thought about Melodyne.

Initially I was using Melodyne wrong by doing too much note manipulation & using stereo input. Then I did 2x mono input & that was better. I wrote a Melodyne quickstart guide shortly after. Ingesting the stems took several weeks. There were several issues with the vox. There are stems labelled L & R, which are 2x stereo. So space could be saved by combining them. Some are panned at different widths, so combining them may change volume. Some are clipped. So I had to recreate them by gaining the opposite channel. sox somehow doesn't do fp32 properly (it works in int32 & clips at 0dB), so I have to reduce all vox by 6dB to avoid re-clipping. I then decided to reduce the volume of all other stems for consistency. I then recreated some reverbs & synths for MIDI note keytrack panning.

I had another idea for The blip percussion, have blips alternating L&R , and travelling through to back & height, I thought would be too complex to implement & almost gave up, but again, loop_slicer_6 to the rescue.

Having the 'stop' clips come from different speakers in 716 was also another early idea I had. But it's fraught with implementation issues. The 51 legacy presentation downmixes side & height side into rear channels so a F S B surround delay won't sound symmetrical in 51. The samples are also done on a cycle length of 8. mcfx gain_delay also has a very low max delay limit. In the end, I settled on a cubular stop arrangement, which works well with 51 downmix &can work well with readelay + loop_slicer_6

Implementing this was a bit tricky. The stop track begins on a half-beat. So I need to listen to other tracks to hear the context. So the main vox begins on beat one, then the stop repeats on 1/8ths. For the simplest implementation, this means that the delayed stop should start on the right then progress backwards. So I reversed the clips of stop so that it starts R L. Readelay is set to feedback at 0dB, so I need to bypass the FX when I want it to stop. Luckily, the buffers are also cleared when it gets un- bypassed so I can have it delay a new section.

After a few months, I finished vocal ingest. I condensed & disabled some vox tracks. The instro project (I now had 2 projects for instro & vox) was sounding a bit different to the reference mix, but I was convinced that adding the vox would make it sound a lot more similar. I was wrong, there's still a lot of difference. Adjusting bass, tamb, vox levels, adding reverbm vox EQ helped a bit. I figured the delay is 1.5 1/8ths, so I can't use mcfx gain_delay as that doesn't have enough buffer. Also, HS & side use isn't possible.

## Wahrheit
I was glad when I got this MT in Nov 2017 that there were lots of BVs, so that I can pan them into surround. Including a studio choir and a gospel choir. But I was a bit overwhelmed about which to use, and the arrangement. I left the project for a few years. In 2021, there is a need for Atmos material so I open this project, and start working on it again. After working on "Earth Song" a few weeks ago, I'm a bit clearer on what to do. BVs at the back. Vocal fills at the top. I find that the gospel choir has too much reverb, so I can skip that. Like ES, the idea is to build up the song towards the end. This means muting clips for a faux-crescendo, and rearranging clips to make melodic sense & consistency. Applies to BVs & choir.

I revisited this after a few months to finish it, and was expecting a short job, but I was wrong. After I added reverb, routing & levels needed attention. I had learned from mixing Maryam from HOFA, that even tho the levels for reverb might look OK, it might still sound a bit too back-biased. I also reduced the compression on the LVs, and EQ'd the BVs to make them clearer. I had a listen to the reference mix, and it sounds very different. That's expected, but they did sidechaining on the bass to make it stand out more. I tried PMOD LFO for fake sidechaining, but it sound unsatisfactory. So I did true sidechaining with Reacomp, which sounds better. There were also a few arrangement tweaks to make things less annoying/more consistent.

In 2023 I want to deploy this to share this is an example good Dolby Atmos mix. I redid the balance of the vox by turning them down. The hi hats were slightly annoying due to the left right panning,  so I reduced the Stereo width and volume. I wanted to have only free plugins effecting the sounds, but this has kilohertz disperser, which is a pain plugin, so I replace it with the ReaEQ + allpass filter with a narrow bandwidth to try and replicate it, but the effect is weak compared to disperser.

A mastering engineer said overall it was ok, but maybe there could be more bass and less mids & Highs from about 1k. 

## Transit of Venus across the sun
When I first heard this song I thought it was something special & might have enough instruments to make a 3D mix. When I listened to the tracks of the MT, it sounded really raw & I was worried it was gonna take a lot of work to make it sound like the video, but after a while, the mix started to come together quickly. Initially, I had the BVs @ side & xylophone @ top, but if it were muxed w/video it might look strange, so I put them @ front & slight height respectively. The overheads of the drums were quiet, and I was almost not gonna use them, but then I remembered wiz's drum panning style so I put them @ top. There are 2 big groups which send to the reverb bus. The rhythm group which needs only a bit of reverb, and a orchestra group which needs more. Vox is in the 2nd group. The brass arrangement is the same as the video, only more shifted right to avoid a quadrant gap in soundfield. The brass ends the song, so w/my usual panning style it will be back-heavy during brass section solos. This can't be herped. There are string synths which I would upscale to surround, but didn't due to avoiding back-heavy too. During the bridge w/ latin lyrics, I was unsure whether to boost the lyrics since they're a bit shrouded in these stems. A check of the album version reveals that the bridge vox is clear, and also has thicker strings, so I boosted the LVs there. And also applied a compressor. For other pieces the organ's at the back. I can apply a bandsplit to that to vertically extend the organ. Then the piano's usually at the front. For the final chorus, I considered elevating the piano like Tokio Myer's BGT performance, but that would be unrealistic. Also, organ vertically extending @back compared to ELL piano would shift focus to the rear, so I implemented them vv. AKA organ @ front, piano @ back.

## Peer Gynt suite
So since getting stems from a game/app might be hard, I did a search on "Solveig's Song", which led to the Peer Gynt page on Wikipedia. I noticed that the audio samples were by Musopen. Well, turns out they recorded a bunch of classical works, which includes "Peer Gynt" suite 1 & a lot of other works. With session files on Internet Archive. Since they're public domain, there's no need to ask for permission. So I downloaded them to make a surround remix. 

The files aren't named in a sensible order. Like "1st violin B_02F" isn't necessarily from the same take as "bassoon_02". Since some instruments may be omitted from certain songs since they're inactive, N means the N-th occurrence of that instrument in this pack. Which is not helpful for assembling a project in another DAW from scratch. The takes are also not in movement order.

I had to guess how it should be edited. The converted PTFs seem to be just imports, and little editing. They also seem to have misalignment in some tracks. I decided to have a program of 4 songs for editing convenience. The audio comes in 7 takes, or about 2 takes per song. The 1st take is usually a complete run. The 2nd take is partial so I need to figure out what mistakes were made. Because the 2nd take starts partway in, the mistake is that length inwards of the 1st take. The mistake is usually mistimed winds. Contra bassoon & harp clips were also included, but are actually not used (the mics are active due to bleed). I checked wiki & the score to confirm this. I did the breaks such that there's silence 5s long from end of last note's tail, to 1st note of next song.

The bassoon mic is almost redundant since it bleeds into the other wind mics at a high level. There are 7 room mics, but I only used Decca C. I did a small boost to most of the strings, and some cuts to winds & brass. Compared to Ethan's concerto, there is almost no need to spend days on manual automation since the conductor is controlling the dynamics and the orchestra reacting to itself. However, a big downside is the high bleed since the orchestra is recorded as a whole, not segregated.

When I finished editing, the next step is surround panning. As usual, I put the brass to the back. But during brass solo sections, there is significant bleed to the front, as most other mics pick them up, to the point that solo brass is almost front-heavy. I thought my FFTMT would do the job of fixing the bleed, but it doesn't really fix the bleed, until it also removes strings. So I set it to a moderate amount. There is enough bleed even w/o a surround reverb. Initially I had a separated F/B reverb ReaVerbate for front & ambiverb for back, but I tot a difference in character would be inconsistent so I removed ReaVerbate from the front.

My test section is the solo horn call in mvt1. You can remove some bleed with EQ, but that only works for the minority of the instruments since most of the occupy the midrange which the horn is also occupying. So then I had the idea of using the stereo info in the instrument pairs to remove the horn. This sorta relies on knowing the instrument/mic placement via the orchestra setup map (which seems to be slightly wrong at times). So I upscale to 5.0, keep the channel which focuses on the instrument, turn C down, and reject the other channels. There is chamnix2 use for post-gain (to keep the loudness of the original instrument) and mapping to LRC. FFT surround upscaling is CPU intensive so I made a lite/small version of my 2>5 upmix (unfortunately, the saving is only about 10%). I also tried ReaFIR for EQ, since the curves are sharper, but the difference with IIR EQ is small (and it uses more CPU), so regular EQ it is. This technique was applied to all strings & some winds. Overall, the horn rejection is 3-6dB for each instrument & master mix. Which is enough to move the horn from mostly front to mostly back (hopefully). 

The next step is to remove what should be front from the back. Since not all of the brass is stereo, I can't use my upscaler for all of them. I want to remove the timpani from the back, and the timpani is relatively isolated. I apply a lowpass to it, and send it to the brass bus. I need 2 instances of FFTMT to reduce the timpani from the brass. Care needs to be taken for IO routing to pass through audio, so that they both work simultaneously.

I thought I was ready to export it, but then I notice the cymbals are missing, so I unmute the Adue track. I also find that the bass drum is too powerful at the end, so I need to EQ lowcut the wind tracks and some low shelf EQ on Adue.

## Tchaikovsky Symphony 6

With this suite, I had a logic project to guide my editing, but getting an actual logic conversion working in RPR was a "long" and unsuccessful journey. Converted PTF to RPPs aren't very useful as usual (no editing done). The logic files have a preview in windows, but still not ttly useful. I boot up my OSX 10.6 VM. Logic 8 express eventually opens up the logic documents after a few errors. But it took several tries to get the audio clips looking right, since I tried to load LQ stubs instead of 96/24 in logic initially. It seems that logic stores fseek offsets in documents as for WAV files, so only files of exactly the same sample format will do.

AAF & OMF converts were unreliable to RPR. In the end, I settled for screenshots of the edits in logic (with filenames/takes clearly visible) & recreated them in RPR. Although the length didn't always match for some reason.

## Golden Hour

Why this song. Stems were available for this song and the artists looked a bit Japanese like Joji so I decided to check out the song on YT. It turns out the song is in English, but it sounds ok so I go ahead with the project.

This is a pop-orchestral ballad with drums, piano, strings, and strings. There's potentially a combination of real & fake violins. The piano part sounds like Chilly Gonzales - White Keys from his Solo Piano II album.

There are some people that don't like the song other artists due to what was done on tiktok about it but I don't know about that. From what I gather Charlie puth also went on tiktok and basically made light switch in front of tiktok and released it as a song. But it's more a run-of-the-mill pop-EDM song rather than an emotional song so it's less polarising.

The stems also seemingly have DC offset and dither so reducing bitdepth doesn't really remove them.

There are limited stems and most stems are reduced from multiple sources, which might not make sense in terms of organisation. The FX & risers stem has vox reverb, and the bass has some non-base synths. I don't like the rap in the verses so I mute it for my arrangements. I then listened to the instrumental on YT & that sounded good, so I can just take out most of the vocals.


The bass in the bass stem isn't very prominent since its more like a sub. To add distortion to the bass to make it more prominent, while leaving the other synth in the bass stem, I use ReaXcomp to compress the low frequencies at a high ratio and fast time constants.

There is some high-pitched synth in The synth stem along with a pad, so I can witti's 2band splitter to effectively Pan the high-pitched synth up. There is an arp synth which is heard in isolation earlier, so I can use FFTMT to get it out when it is mixed in. 

The string bass heard in isolation earlier so I can get it out when it's mixed ,but it's not enough to isolate the violin ostinato. I make some MIDI notes and the Yamaha XG VST makes the sound. Surprisingly, this gets most of it out so I can pan it separately. The panning idea come from [this Eru Matsumoto](https://www.youtube.com/watch?v=wUYByf8mcaw) video. There, the string section and drums pan counterclockwise around the listener, about every 8 bars or 32 beats. In this project it's a 6/8 song and I chose every 6 bars or 24 beats.

The arrangement changed. The vocals were removed. And I found that I needed to change the arrangements and balance to make the song work so that the chorus has enough impact when it comes in, rather than a power loss. To do this I slightly boosted the piano since it carries the melody and also looped the strings from the second part of the chorus. 

Tunebat says 94bpm for this song but it's actually 94.5. There's still misalignment after you set the correct BPM since there's a tiny ritardando before the first chorus (why is it there if it hardly builds tension?). I need to fix this & conform the whole song to constant BPM, otherwise PMOD LFO panning will be a bit tricky.

Previously, the violin sidechain occupies a few channels due to duplicating MIDI notes - working around bugs in my MIDI octaver. There might be a way to reduce the tracks if there was plugin that duplicates & shifts notes. MIDI tool II & MIDI router certainly don't. MIDI chorderizer does do the job, and you can also control the velocity of the extra notes which is good, but it always makes 4 notes, so it potentially increases the volume via duplicate notes. You can shift high the unwanted notes & remove using MIDI note filter, but that leaves extra note off events which might overload the Yamaha XG VST. Recall Excessive MIDI events may cause glitches as I documented in my Aru-money mashup. So I made a variant of MIDI chorderizer that is able to turn off unwanted notes. An additional feature that would be nice as to see the extra notes to a new channel for more flexibility but this will have to do for now.

I found a bug - only voices 1 & 4 make sound. voices 2 & 3 make MIDI events, but you can't hear the sound. This bug is also in the original. I found out this is due to the velocity is too low due to a equation error. This is fixed in my version.

In sept 2023, I do some balance tweaks, finally turn down the discontinuity glitches in the piano stem, and add some reverb so that the piano fades out nicely. The song starts on bar 1 instead of bar2. For that, I needed to change the phase of the PMOD of 2 tracks. I was about to finish revision J, but upon magnifying the peaks with Peaks Display settings, there's some residual activity in the heights in chorus 1. So I need to bypass a panner to remove it, and tweak my clip timings.

3D reverb is not used in this mix since there was a small problem getting it working, and also CPU issues.


## Aespa - Better Things

How I know the song. Someone shared a compilation comparing the stereo & DA versions of songs. I liked that song, but I wanted to see if the dynamic panning of the auxuliary percussion could be converted into static panning. I did a quick test of effects in the song w/o ML separation, and it seems that the cowbells and the clap are separated in time, so that with dynamic panning I have the illusions of separate stems and static panning.

It took a few months for the DA version to arrive on tidal so I can listen on speakers. But it doesn't sound that great on speakers. It's an object mix, but most of the objects are clustered around two-thirds front. I wanted to do ML stem separation to get stems, but I deferred it due to low space.

A few months later, an instrumental is available and I thought it would be a good time to start The Project properly. the ML stem separation actually turned out pretty good. I was a bit hesitant about using DEMUCS since DEMUCS is bad with piano, but the piano turned out fine. It also put some electric piano in the guitar stem and there are somehow some vocals in the instrumental. I don't how like that electric piano is doubling the vocal Melody, so I turn it down with linear EQ since there is some pads I want to keep in the same stem. Originally, I had a more complex setup where the saw pad in the other stem was panned slightly to the side for 7.1 via phase shift to emulate object size, but seeing how the pad is also in the guitar aka electric piano, I was happy with the pad in the guitar stem being the front, and the other stem being the side of the pad, but the phase shift on.

Since I need the cowbells and claps isolated, I tried drum separation. But they weren't isolated for the whole song so it's not a huge improvement in usability over the original drum steam. So the cowbells and claps were isolated by looping the start of the song which has those plus the hi-hat, and removing the hi-hat using linear EQ and using that as a side chain for FFT to cover the whole song. +- 50% sounded too wide for those elements, but 25% sounded too narrow, So I used plus minus 33%.

DEMUCS didn't reliably extract the choir so again, FFT was used along with sidechain. Similar to my golden hour mix, this song has multiple layers of height.  The rhythm at ELL. Some stereo elements like pads at 1/3 height, then finally choirs at 2/3 height.  The choir was slightly boosted, but I undid that since they were now too loud on the stereo downmix. Initially when making this project I had planned for this to be in 5.1.4, even though there May be precedence effects and pan law errors since I don't know what to make difference between the sides and the back. The DDPA encoder would then upmix to 7.1.4 . But I decided to have vocals upmixed to 5.1s and somehow figure out to redo the vox automation, then have the pads upmixed to 5.1b . 

I rendered a 5.1 version to check surround activity, But it was a bit low. *So actually, this is a fun song, but you might be struggling to find stuff to put in the back speakers, because during the chorus there are few textural elements like pads* . To get more surround activity overall I did some things I may not usually do like spreading a small amount of rhythm to the back speakers and putting some secondary vocals (not VFs or BVs) in the back speakers as well.

The vocals were isolated by subtracting that instrumental from the vocal version in the time & frequency Domain. Since there is some high frequency bleed on the vox, I use linear EQ on the drums to turn down those high frequencies to compensate. Linear EQ is used a lot in this project to avoid phasing artifacts.

I also listened to the demo version of better things mostly out of boredom, but I was inspired to change the arrangement to get slightly more surround activity. In this second part of the last chorus, I put in some pads to fill the surround speakers, but you can barely hear it.

## Vantablack - IES V1

I chose this project to do since the author's mix was underdone, and there was another mix that was overdone. This EP is three songs.

I thought it would be a good idea to do a full album workflow while mixing this album, as a learning experience for myself. So this would mean adhering to the Dolby Atmos music spec as close as possible, and mixing the all the songs in one project to enforce consistency. The main points for albums are (rephrased from the DA music spec):

1. Each bed/object ID should have the same BRM across songs (N/A for my workflow, but each track should have similar content across songs)
2. Each song must have the same length, and be within 1,000sa @48k of sync as the stereo master
3. Each song must be an individual file, and should be exported from the same project

To match the timings, I downloaded LQ previews off Bandcamp. Luckily, it seems that all the songs are 120 BPM, every song ends on whole seconds, and the inserted silences are also whole seconds, so that makes it a lot easier to align or realign if mistakes happen.

To adhere to point 1, this means a lot of organization which I'll describe below.

Ingesting and organisation took at least a few days.

I initially imported all 3 songs at separate times and separate tracks in my DAW. Each song has about 30 stems, so there were over 90 tracks in my Daw initially. I spent a few days reducing the number of tracks by putting similar instruments on the same track. Where there are separate tracks of similar sounds and similar intended panning, but the audio content doesn't overlap in time, then those can be combined into a single track. Of note there were about 11 string stems in the 2nd song (of various instruments & articulations). This was compressed to about six tracks. They were compressed to about 26 tracks for each song, and 36 tracks before mixing & additional buses.

