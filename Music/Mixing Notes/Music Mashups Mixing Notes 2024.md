# Music Mashups Mixing Notes 2024


## Believing in Lovely

The idea of doing the Cindy-Wonder came about since someone wanted to do a mashup of Cindy & Tommy Tallerico songs from earthworm jim. The original idea didn't work well, but I had Stevie Wonder - Isn't She Lovely in mind. Since the key change is moderate, I need to use a MIDI version. This also ensures that I can make the tempo constant.

Although I used Stevie Wonder for this mashup, there is actually a real link between Cindy and Stevie Wonder. [He produced her debut album](https://www.discogs.com/artist/3036474-Cindy-26) . 

### Converting 4/4 audio to 6/8

However, Isn't She Lovely is 12/8 time, and Cindy is 4/4 time. I initially thought of editing and removing drum beats from SL. But I left that for a few months. A few months later, the idea of stretch markers popped into my head. I also found out Reaper has an adjustable swing grid. I read some information on both, but it isn't quite as easy as that since neither built-in feature can add swing to a finished song. After some research online, I came up with a working method:

1. Download and install S&M tools for RPR. I currently use RPR 6.8, and I was surprised that you only need a minimum of 5.9 for the latest version, since I remember when I was trying to add it to Reaper 4.5 (dated 2013 ish), it was quite sensitive to version changes.
2. Set a Tempo grid of 1/8.
3. Add X-raym add stretch markers at Tempo grid divisions.
4. Install mpl quantize tool. I found the latest 3.5 version too complex, so I found a 1.8 version from the git commit history.
5. Set the source as swing grid 66%, and set the target as stretch markers. This will turn your audio into 12/8 by adding swing. Since the time-stretch ratios get moderately large it works best on vocals, not instrumentals.

You also need to set the stretch marker mode to tonal, to reduce artefacts.

### Structure

The two songs differ in arrangement, and the Cindy song is quite long. So I decided on verse verse chorus, instrumental break verse chorus. The harmonica Melody in the break was modified to include parts of Cindy's melody and a bit of Pitch Bend was added.

Each sections were taken in order from the original song. Since the structure of Cindy was changed, the lyrics might not be logical anymore.

I could have also added the lalala lalala from My Cherie Amour, but I'm not bothered, and there might be some trouble fitting it in.

I tested my mashup on some headphones, it sounded a bit bright. ReaFIR was used to compress the highs /tambs since there were multiple MIDI clips.

This mashup was submitted for a love mashathon contest. The contest aims are slightly different in that there's no voting phase, and difficulty of execution as a judging criteria. so that means more than a simple A vs B mashup. Converting 4/4 audio to 6/8, and use of MIDI are factors, but that might pale in comparison to people then used many different songs.

As with MIDI in reaper 6 the output is not deterministic - you sometimes have stuck notes, so you need to render a few times, then subtract the outputs to compare differences and hope for the best.

After rendering, I noticed a difference - a bass instrument paned slightly left. I made a new project with all basses centered, but after consideration that the claivnet was panned right, it would balance the bass guitar panned left, so I left it as is.

## Bustin Loose-Super Bad

I know Bustin loose due to DJ Hero 1. I got the idea for this mashup when listening to Super Bad, and it sounded similar to Bustin Loose.

A cover version of Super Bad was used since the original had vari BPM. Super bad stems was also considered, but those were also vari BPM, so a double vari BPM mashup wood be challenging. A surround mashup would also be possible with stems, but I would need to finish mixing super bad, and this would increase my workload and dependencies. So a cover version of Super Bad was chosen. A cover of Bustin Loose was also considered, but surprisingly, I can't find many. I was trying to avoid DJ Hero sources for the Bustin Loose Vox since they would likely be time-stretched to fit their version. But after a quick listen to the DJ Hero versions, there would be other issues like not having the full song. 

The BPM was finally set to 118 to avoid double drums at 115 for the instrumental. This is now equivalent to a stretch of about 7.2%. The vocals are sped up to x BPM but also pitched down 99 cents so equivalent to a stretch of 99%.

Super Bad is basically a Jam track, so the structure and proportions of different sections is a bit off. To make it easier to match the vocal, I cut super bad into different sections, then roughly allocate different sections to the vocal in my head.

The mashup was for a brass contest. But the brass sounds a bit bad in the cover version. There are MIDI files available on the internet, but are condensed in length, and instruments and are critically missing the brass. So MIDI file isn't an option.

After I finish matching the overall sections of the two songs, I find that my mashup is a bit boring. In the original Bustin Loose, there are several brass breaks in the song. So during those periods, I can match the bustin bad in more detail by inserting guitar sections from Super Bad. Since the mashup was a bit boring, I also thought of bringing in the brass from Bustin loose, but after some testing, it was a bit off-chord, so was reverted. It's still too boring, so the only option left is To use the original super bad.

Since Superbad is vari-BPM, the plan was to chop it into Loops and duplicate it across the mashups to create the different sections. since I have stems for that, I can remove the sax solo and make the sax more of a background element like the trumpets.

There was some vocal bleed on the rhythm stem on Super bad. I used FFT with the vocal stem to remove the vocal bleed, but still some bleed/artefacts depending on amount.


TOCHECK: To do that I can duplicate the vocal track and clips of bustin loose and then replace the clips with the other stem. But because each clip of the duplicated track is grouped with the corresponding clip on the vocal track selecting all the clips on only the duplicated track is tricky. Tip. To disable grouping when selecting clips you can click disable grouping on the toolbar.

The contest version had a bunch of faults, since a lot of work was done during the last day. The imaging of the guitar sounded strange on earbuds, so I need to reduce the stereo width. It was about 1-2 DB too loud since I was mainly looking at the LUFS numbers and not comparing it with other tracks. The bass at the start of the song has noticeable reverb, so I regard this as an error in the context of a studio song, so I need to add EQ lopass/hipass before ambifreeverb.

## Yes and Killer

### How I know these songs

When a new single by Ariana Grande or Dua Lipa drops, you basically need to listen to it to keep up with music news. Yes and is no different, and people including myself have compared it to Madonna's Vogue due to 909 drums, among other things.

I've known the seal song by Melody due to radio airplay, but not what it's called. I only finally know it's by Seal, since there was a Seal surround music album at a home theatre store. If you listen to Seal's greatest hits anthology, you'll probably know a few songs.

### Idea

I got the idea for the mashup since I thought the instrumental chords are similar to yes and. According to [Hooktheory](https://www.hooktheory.com/theorytab/view/ariana-grande/yes-and) & Mixmstrstel, the "verses are notated as Bb Mixolydian and choruses are notated as Eb Dorian " . But if you treat the whole song as A# major, then it could work in a mashup.

There is a surround mix for Killer, but it's not that great and it's hard to remove the vocals from it, so I use a stereo mix. There are radio-length karaoke versions of the song. But in the end, it was possible to make an instrumental from the full vocal version of the song just by using editing.

### Mixing

The lead vocals were a bit quiet in the final chorus and I only had 1 one vocal stem, so I upmixed to 3 channels to make the lead vocals louder, then downmix back to stereo.

Going from the bridge to the final chorus, I noticed there was a drop in energy. So I used a FFT stereo imager to remove the center rhythm from the instrumental. Vocal fills were used in the bridge, and also extended to the final chorus to fill the drop in energy. The bridge was also turned down slightly after noticing a loss of impact going to the final chorus during the launch stream. Also during the launch, the high frequencies seemed a bit unbalanced, it's due to the music but also perhaps slightly broken earbuds. so I reduce the width of the high frequencies.

The mashup was submitted for a Eternal Sunshine mashathon contest. But it wouldn't qualify by itself since the rules said if you do a from single or partial song, Then you need to make another mashup. 

TODO

Idea: 2x/01/2024


## Long Distance-Intro

How I know Long Distance
無期 was being played at a music store and they had a poster of AGA Luna so I figured it would be that.

This mashup is qualification collateral for the Eternal Sunshine mashathon contest. I asked the judge, and 2 singularly non-qualifying, together they could qualify. So I considered a partial song is my second mashup for the contest - they'll be shorter and hence quicker to make a mashup.

The Saturn interlude wasn't particularly inspiring, but the intro sounded nostalgic and similar to 4536 with its chords of 2516m. I thought I could pair it with a Chinese song which I forget the name of from the AGA - Luna album. I know where I can find it since I have a segue project pairing that with Brockhampton's summer. 無期 AKA "Far off", or the English version "long distance" would work better than Summer, since Summer is basically a Jam track with little tension & structure, unlike far off, which has a clear verse & chorus structure to fit intro. I chose the English version to do my mashup since English would be appealing to more people.

### Mixing and editing

I thought the verse was too wide being mostly solo guitar, but I want to keep the width for the chorus with strings, so I used automation to reduce the width of the verse.

at 2 minutes long, my mashup already extends intro. I experimented with adding some speech from the Saturn interlude, But I later muted it since there's a thematic conflict. The Saturn interlude is about personal development, but long distance can be seen as forgoing personal development for Romance. In a sense, like the main songs for Princess and the Frog, vs the ending song.

Again like Blue Topaz, I used the approximate BPM for a song (intro) which I shouldn't have done, because it can cause timing problems. but there's no big problem so far, since the instrumental is a mellow guitar song.

Although the Chords are similar, there needs to be some editing since the phasing is different. there needs to be a 2 bar offset to match intro.

The English vocals were a bit too prominent, so I used EQ to counter that, and applying the reverse curve to the Cantonese vocals to make it stand out more.

Reverb size was reduced to 80 from 91 so that the reverb doesn't linger indefinitely, after feedback from the judge.

My initial version was the English version , but I submitted the Cantonese version slightly later as a demo. I was hoping that the judge would choose the Cantonese version because it had more natural phrasing, less engrish, end rhyme. They did like the Cantonese version better, but they wanted to include both versions on the album.

## My love is mine

This mashup was done to fill the album since that judge wanted some mashups for the boy is mine since they were none at the time and listening to TBIM, I was inspired to make a mashup. The lyrics are delicate, but it has a strong RnB beat. Hence you need to be careful when doing V/I balance, and turn down the bass & treble to make it less powerful.

I was inspired to try some Jennifer Lopez vocals like If You Had My Love, but the key didn't fit. My Love Don't Cost a Thing was also the wrong key, but it worked as a fifth trap aka mixolydian mode. I did a test mashup with minimal arrangement editing. The concept worked and got positive reception from Sam & the judge, so I decided to do a proper arrangement. The mashup begins on the 1st verse. The final chorus of the vocals were edited down to avoid too much repetition. The sections where the instrumental slows down were looped & shortened so that the whole mashup stays at a constant tempo. Although the bridge strays more out of key/chord, it offers much-needed variation. The final chorus has parts in the instrumental where the instrumental drops to silence for about 1 beat. it was a bit tricky to decide where to put this, and I decided to put it on the 2nd & 4th iteration of the final chorus. The was no delay on the final word of the song and the vocals, but I added it in because it felt right.

The instrumental mode was changed to Elastique 2 efficient to reduce discontinuity artefacts. Clips that have similar values at their edges can somehow make pulse/phazor sounds, which is very nonsensical. Vocal mode was changed to Elastique 2 preserve formant. Pitch shift without formant has less pitch distortion artefacts, but her voice sounds too low and dim. The pitchshifter was eventually changed to TB voice pitcher 3 (now free). It sounds more natural but slightly less airy, esp on phone speakers, and I also applied a de esser.

The stereo image was too wide, particularly in the bass, so I used stereo enhancer to reduce the width of the low and high frequencies separately. I also thought about using stems which which would be easier, but not worth the hassle for a small project, Considering I'm also delivering 3 other files.

TODO

## Senorita-Wow Thing

### Why
Senorita was in my mind because I was trying to find a certain R&B song asking for Reddit help. Someone suggested Senorita, it was only 1% relevant but it was in my mind.
I heard Wow Thing in a strings and acoustic mashup contest submission, used as an instrumental. I liked the funky chords. The mashup wasn't done that well though. I thought it would fit well with Senorita since Senorita has similar chords in the chorus. The introduction mentions Memphis, Tennessee. Justin Timberlake was born there. 

### Song

This is a b or c-class song, because it's short, there are few instruments, and there's a mixing issue - the vocals are too loud. If it was a a-class song this wouldn't happen. Also, the unit may have been formed specifically for the song

### Editing

Wow Thing is a lot shorter than Senorita, so I need to loop Wow Thing to cover Senorita. I know Senorita has a music video so my target arrangement is that. If my mashup is the video arrangement, then I'll need to delete a Bridge, but that's ok since there's another bridge earlier. 

The bridge is slightly tricky since it changes key. My my goal for the bridge is to make it sound acceptable & maybe use a 5ths or 3rds trap to avoid shifting Wow Thing by too much, since it's already shifted -2. Luckily, +1 and -1 sounded ok & seemed to match the chords and key of Senorita.

Almost all of the Wow Thing instrumental was used to cover the mashup. Some variation was added to the calling section near the end. Wow Thing didn't end nicely, so I edited in a hard ending from elsewhere in the song. The Wow Thing instrumental had a low-energy section after the first CHORUS so I just left that run to add some variety. I also put in a low-energy section from Wow Thing in a chorus also to add variety.

Originally, I used a combination of FFT and time domain to isolate the vox, but there was some high-frequency bleed in the middle of the song, so I need to use 100% FFT instead. if you remove all the instrumental, there's some pumping of the vox prolly due to master compression. Wow Thing is RnB song, also with strong beats so that could hide some pumping artefacts.

There were some high-frequency bleed from the acapella. I initially turned the high frequencies up from Wow Thing due to loss of high frequency from shifting down, but then I turned the high frequencies down, since there's was high frequency bleed from Senorita. 

With my mashup, [the theme](https://en.wikipedia.org/wiki/Wow_Thing) of the lyrics was flipped from an "independent woman"-type of song, to serenading a woman, which is a notable change.


Overall, even though the chords are similar of 6 & 3M (3M can be replaced with 3 and still sounds fine, I checked), but the unique Groove of Senorita is lost.

### Elastique

I was editing my mashup and I noticed some discontinuity artefacts around the middle even though there didn't seem to be any large discontinuities in the cut waveforms. I tried changing the sampling rate but it didn't have an effect. The default pitch shift mode was set to Elastique 3. Changing it to Elastique 2 lessened the discontinuity artefacts, but also reduced the bass. As shown by this issue and also in Oxydlate, newer isn't always better.

Idea:
Contest: 
