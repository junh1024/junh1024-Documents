# Anime Mashups Mixing Notes

## LS-KE

During July 2020, I was listening to the LS Remix albums. The Glucosa mix stands out as being different since it barely resembles the original MTSF, no-one sings the melody. Rather, there's some voice clips over some mellow lo-fi beats. I was also listening to some Katamari albums, collecting songs for my electro, house, and dance/909 mixes. I wake up one morning with a song in my head. It's Katamari, and maybe it's cosmic lounge, maybe something from Novita. I search up cosmic & lounge, nope, wrong song, but it is on Novita. It's KE. Maybe the next day I realise it would go well under LS voice clips.

I was wanting to avoid using ML for this, I had in mind Kagami's discussing about the grocery store in ep17, but that's not a lot of talk, and not very interesting/expressive as the acting on Glucosa mix so ML it is. The vox is still from the MTSF OP, but the voices are played sequentially instead of simultaneously.

 Also, Glucosa is chill at x bpm, but KE is fast at 14 bpm, so I had to do a compromise bpm to try to keep the chill feeling while not too many artefacts. Also, I did some variable stretching at the start to have sections start on 8-bar edges for easier cutting.

I originally used the older lalala.ai algorithms Rocknet or Cassiopeia back in 2020/1, it sounded a bit bad. UVR 2 was a bit better. Revisiting this mashup in 2023, I had got DEMUCS3 vox in 2022, which sound much better since it gets more of the vox w/ less artefacts. lalal.ai now has a Phoenix algorithm, and also does drums, bass, e.gtr, a.gtr, piano, strings, winds, synth now.

Konata & Miyuki's lines have bleed into each other in the song. I want to remove that but I probably can't find them up exactly so I need to use FFT. Initially, I thought of using FFT subtract, but that would also remove some useful speech since they bleed into each other. I could use my 5.0 upmix & mute the centre, but that would require them to be exactly aligned, since the centre is mono. It could also the 51>71 upmix in ITU circle+ mode, but that might be overkill. So I just used a FFT subtract in dual mono. I wasn't able to completely remove the bleed, but it's noticeably reduced. Coming back to this a few years later, the gaps between the voice is a bit long, so I shorten the gaps to about 2 bars. 

Originally, I put some effort into making the voices roughly start & end at a musical place, but I'm caring less about musical alignment now due to power loss as said above. And to end the song quickly, I cut it the end of a section and add some reverb to make it sound smooth.


## Irony-BDD
Original finished Aug '17-ish. There was feedback in the past about how it was out of key at times. I revised it shortly after, but pitchshifting sounded awkward. My Nexus-Mutsuki mashup didn't do so well on r/Oreimo, but there was a positive comment which encouraged me to revisit this for a post. I finished replicating the pitch shifts for the rest of the song & infrastructure upgrades. I was about to call it finished, but then I realized it missing a bit of contrast due to the missing bridge. I cautiously extended the song.

The vox needs some shifting to appear in key for the instro bridge. But it might be a 5th out. Copying a technique from my SOMH-Haruna mashup, I make another track for a few small sections that need zplane retune. The instro is shortened at the final chorus & ending to avoid boring repetition. The ending chords are off-key, so I shift them, but only some of them, again, to create variety & avoid much repetition. There is a pre-final-chorus bit that I could fill in w/vox since I filled that part earlier in the song, but I feel it could use a break in energy.

## Prism Sympathy - Perfect Area Complete
I revisit this in 2021 to fix some things. The project is too slow so the instro has shifting artefacts. I make it a bit faster, but still audible. I also replace the infrastructure with my own tools & make the instro wider for more surround activity. Some bit loop obviously to keep the timing so I make some changes to make it less obvious. There is a break near the end so Musically, it would make sense to raise the key. But production-wise, would be bad due to pitching & quality reasons.

## Perfect Area Complete-Hanayamata
I had to check whether I had duplicated the aca/instro on another mashup since I want to avoid doing so, and I recall using one of these songs in a previous mashup (*see above), which I wanted to revise. I haven't., so this mashup can go ahead. PAC centers around tonic/dominant chords in the verse, but HOI centers around mediants. So I need to chop the HOI instro and make a loop which starts with a tonic so that it sounds OK. HOI ends a bit abruptly so I add a reverb to the end to keep the energy going for a bit. There is a MV for this, so I tried to keep the aca as uncut as possible. The ending was long, so I cut it short. During the instrumental breaks, there is a drop in energy so I constructed a "...HAI...HAI....NEVER EVER GIVE UP,...HAI...HAI....NEVER GIVE UP" loop which didn't really exist in the original. I had to loop a piano clip for the bridge. There was some bass around the edges of the loop so I was inspired by the loop, which had a hipass, to hipass it further to reduce the bass. Overall, about 60 cuts needed to assemble this mashup.


## Aru-Money

### Initial editing
I got this mashup idea when listening to the Aru character song. But I know there will need to be some editing done to Abba money because money is completely in minor, but Aru switches between major and minor. There are multiple cover MTs of money from jamkazam and Deezer. But both of them have a non-constant BPM so I can't really use them. I have to resort to MIDI. The verses have note-level editing to make the instruments in money to fit better with the major verses of Aru. Some instruments were muted globally. The chorus of money was shortened to match Aru. Money has a pre-chorus but not really a bridge. Aru has a bridge but money doesn't. So the pre-chorus of money was used for the bridge in Aru.

I was spending and procrastinating time on tweaking the MIDI verse of money and it was close to the submission date so I decided to hurry up an copy the MIDI data to fill in the verses and the choruses. I need to edit the MIDI in the chorus since my bass guitar VSTi doesn't support pitch bend. I noticed that the introduction is a bit low-energy and there are some lines at the end so I moved them to the intro. I mute some clips to add variety and match the power of Aru. I adjust the tune parameter of MDA piano to make it sound like a honkey-tonk piano but it's not quite the same. I delete the 3rd verse since overall it's a bit repetitive & 3rd verse has some instro leakage. This was the version that was submitted to the contest.

### After the contest

Revising this mashup a few months later, I extended this mashup to its full length by reverting to an earlier version, so I need to port over the changes from the newer shorter version. The artefacts in the third verse were fixed by automating FFTMT. I thought a reason that the production wasn't holding well together with the lack of reverb so I listen to the original ABBA Money song to confirm this. A dedicated reverb bus was added, so I need to turn off the reverb in the XG MIDI synthesiser. 

I spend quite some time fixing and reviewing the chord match error in the chorus. Since I'm used to hearing the uncorrected version in its contest state, the fixed version sounds strange to me. But I'm convinced it's "correct". I added some notes in the higher octaves of the piano to increase energy and tension in the last chorus, but also sounded strange, so I muted that for the final version.

I hadn't watched episode 12 when I made this mashup but there is a small link between Aru and money in that episode.

> Aru starts a quiz, what is the thing that she most wants? Sotoka announces a gold bar. After initially rejecting the answer, she accepts it since she can't think of anything better.

### Audio and plugins.

I replaced the audio with the CD version as I mentioned in my Gift mashup. The vocals no longer have a glitch in the 3rd verse, so the automation can be removed.

The Yamaha XG VST was replaced with a portable version, but it has a different DLL name and the save state seems to be different. Without looking at this mashup retrospective, I remembered I may've disabled the internal reverb and used a reverb bus instead. Inspecting the base64 save state, that seems to be the case.

### Reddit feedback

This mashup won 1st place in the r/Mashups "People's Names" contest in September 2022, out of 6 entries. During the voting phase, it got 2 votes, which means it could place, if it passes the Judge's minimum quality requirements. I suspect it was due to use of an English song (as an instrumental) as opposed to my usual Japanese mashups, but post-contest, the voters claimed other factors. Somehow, my mashup "stood out" from the others, and it was an "unlikely combination" that went well (but ofc with lots of editing & MIDI).

The revised version was submitted to /r/HitoriBocchiOfficial , and got a reasonable amount of upvotes.

### Additional mixing

There was also some feedback elsewhere on my mashup, that it was good, even though the vocals were a bit strong. I turn down the vocals by 1dB & boost the XG track by 1dB. Listening to my mashup on speakers & earbuds, I don't know how I missed this, but the shaker in the chorus is annoying as it's panned hard right. I want to move this to the centre but with only 1 XG VST, it's hard to also avoid narrowing the strings. It's also probably impossible to individually control the panning of individual drum elements. So I need to have a separate instance of XG for the drums. Then I can use a similar strategy of what I did Platina-peppertones and use stereo enhancer JSFX to narrow the high frequencies. This project was apparently done without any loudness meter on the master & it's slightly quieter than my other mashups, so I turn the master gain trim up a bit.

### Reaper 6 upgrade

Starting with Superlove-chasse at the beginning of 2023, I started using reaper 6.5 instead of reaper 4.52. This is mainly so I can automatically tag my mashups with metadata, to help the judge compile & organise the mashups for public distribution after each contest is over. I had mainly been avoiding using newer versions since MIDI notes in the track arranger keep on getting smaller. If you add metadata in RPR6, but then re-save your project with RPR4 you will obv lose that information. So I need to set RPR6 as the default app for reaper documents. I need to rename RPR app to reaper_6.exe so Windows can tell it's apart from 4. However, Having a big upgrade in a short time is not without its downfalls as I was about to discover later. Also, Free item positioning management (FIPM) was moved to a more visible place, the track menu instead of the track manager. 
 
### Pitch

Playing back the project in RPR 6 I immediately noticed something is wrong with the pitch of the strings. It turns out RPR is somehow finding a pitch up before the current MIDI clip resets the pitch with an event, maybe from a previous clip which might even be muted. So, I remove a few pictch bends and turn another into regular notes. Then I just sort of gave up. Looking at the what's new changelog, there were a few mentions MIDI so I upgrade to RPR 6.7 and that seemed to solve the MIDI pitch issue. I need to be careful when updating RPR since I have a symbolic link to my JSFX folder in RPR 4. So I need to rename it before installation to something else, then restore its name after installation. That somehow didn't work this time, and I need to recreate the symbolic link.

### MIDI stuck notes

Upon rendering the project to MP3 with RPR6, I can hear stuck notes, more noticeably towards the end of the song. Doing a web search, it seems to be a well-known issue, at least amongst people affected, and a worsening problem on newer versions. 2 quick fixes were proposed - inserting ReacontrolMIDI, and MIDI_sanitizer. None of them seemed to completely eliminate stuck notes even with adjusted settings.

Basically, the only other suggestion was to clean up & and eliminate overlapping notes. I don't think I have any of those, so I try to tidy up notes around clip edges.

Stuck notes are commonly caused by excessive events in a short time, so I remove some setup & control messages. Those didn't seem to help, so I began a project clean-up. My mashup changes the verses to major, so some muted & off-key tracks can be deleted. Some MIDI clips were joined & and looped to make it neater & reduce project size. Stuck notes mainly occur on the string track so I gave that its own XG VST instance. I also tried reducing the note polyphony settings. None of them seemed to work. About halfway in the chorus, the strings often seems to trigger a stuck note but there are no particular CCs or excessive of notes. It's pretty bad that a normal situation is triggering stuck notes. Surely the XG VST can't be this buggy with was released in the 2000s. Maybe it's my version? Maybe it's internally extending the notes?

I remember someone saying turning off anticipative FX for Fiedler Dolby Atmos composer, and it reduced some glitches so I tried that. And it mostly eliminated stuck notes for my project on playback, but that wouldn't work for a full-speed offline render. Also, on the audio buffering page are some settings for audio threads & priority. I then remembered that in RPR4, I had set custom CPU & thread settings, So I opened RPR4 to check them. It turns out I had set RPR4 to use 3/4 cores (I have a 2core +HT) and to not relocate threads. So, I set RPR6 to use 2 threads for the app & audio, and not to relocate threads, and those seemed to resolve stuck notes on a full-speed offline render, most of the time. I also tried a 1x offline render, to similar results.

I did  multiple renders to FLAC & compared them. There were some slight differences when you do a null test.  Since the XG VST and my other MIDI instruments are 32-bit VSTs, but I'm using the 64-bit version of Reaper, they are hosted in a separate process since. There could be inter-process communication (IPC) issues. So I tried using 32-bit version of Reaper. It took about 10 minutes to rescan all my VSTs. But this still didn't completely eliminate deviations between renders, so I just need to live with it, since it otherwise sounds the same with regular listening.

Initially, I clamp the value of the piano MIDI notes to control the dynamics, but later on I realised it was missing some dynamics in the verse, so I used velocity scaling instead to bring back the dynamics. I need to tune the value carefully to match the overall loudness when I used clamping.

I noticed there were some odd volume changes in the e.guitar, but there's not much volume events & MIDI velocity seems to be about the same. In the MIDI editor, sometimes,  expression is shown as levels, not points. Expression is used in this song to fade in notes, which is a bit useless IMO. So, I can delete them. But I need to do that in the text event view. After that, the volume is +- even.

Now onto the strings. I had previously limited the strings to a certain velocity and I want to add back some Dynamics. Initially, the strings notes & Dynamics in the chorus started off a bit inconsistent so I fixed that. I'm using MIDI tool II to control Dynamics. The Order of Operations is approximately and the Order of the controls. Velocity scaling comes before velocity limiting, so if you want to slightly compress the dynamics while targeting a certain loudness, you need to be very careful and precise in the values you choose.


### Reaper settings
- don't inform plugins offline state. Needed for some plugins including Reapitch.
- 1 midi editor per-project. Otherwise that Docker will get really annoying to use if you're editing multiple MIDI clips.
- Project backup location.
- Store multiple redo paths. This is helpful if you're trying to compare changes, but you accidentally save something else. This way, future undo history is not lost. You just need to right-click the undo pallete with the address of a star, and load alternate redo history.



## I love you Kara hajimaru

There were some vocal artefacts so I applied some reverb. The vox were a bit narrow as shown on the phase vectorscope, so I applied some widening with pseudostereo. The vocals & artefacts were a bit exposed during the quiet Bridge section in the instro so I replaced that with a busier section to hide them. Even though this is labelled instrumental, there is still BVs, mostly at the end of choruses. They seemed to interact with the LVs sometimes, which is nice. But during the last chorus, there's a lot of BVs which is inconsistent with the previous choruses & and also slightly conflicting with the LV so I replaced it with an earlier section w/ no BVs for these reasons.

Both these songs pitch up at the last chorus, but by different amounts & at slightly different positions. Due to the raspy & broadband character of the vocals, it's hard to find out which formant setting is the best. As a result, regardless of which formant setting I chose, the LVs noticeably have a lower formant during the last chorus. I submitted this mashup to a contest. But after my submission, when listening on different earbuds, I noticed some problems. The vocals seemed imaged at the front of my head but the instruments were imaged between my ears. This is because the vocals were mixed slightly too high volume and the vocals had some reverb added but the instruments didn't. So I added some reverb to the instruments. The instrumental needs spleeter to move the piano and drums to the front during a surround upscale. I also need spleeter to narrow the drums only. Using Hacken Lee vox also reduced some issues as his voice is less raspy = formant easier to handle when pitchshifting. But his cover is somehow at a different speed than the original.

- A few months after the contest I have time to continue this project. I add the spleeter stems and surround infrastructure.
- After a few months I had forgotten about the width issues on the drums & piano. Reading this retrospective reminded me so I add effects to do that. Due to the very wide crossover in stereo enhancer narrowing the base also narrows the treble so while watching the phase vectorscope I narrow the piano & bass on the drums very slightly. The spleeter rhythm and piano stems were compressed into a single track L&R using FIPM to save space Since extra tracks were required for surround and dual delivery.
- I wanted to have the BVs vocals imaged slightly front instead of at the sides like the strings but spleeter didn't pick up bar enough BVs to reliably do this.
- On my desktop speakers the Japanese vocals sounds slightly too loud, but the balance sounds ok on my earbuds, so I slightly reduce the Japanese vocals.
- The high amount of reverb on the Cantonese vocals don't really fit in with the song so I removed the extra of reverb I added and tweak the levels of the 3 front channels to create the Illusion of reducing reverb. 
- I ran the finished 5.1 mix through an RMS meter and found out the RMS of the front 3 channels were similar, so this confirms the music-vocal balance is close to correct.
- There were also some monitoring issues on PC. At first I thought the vocals were too soft and that was because C was being downmixed into l&r by my driver with an incorrect coefficient of 0.5. I need to implement the correct coefficient of 0.7 in foobar for correct monitoring of c without a physical C speaker.

## Prelude in Black

I know I need the piano part in MIDI since I need to control the tempo. The vocals are almost constant BPM which is good. I need to make multiple small cuts to the vocals so that it fits with the piano. There's not much vox to match in the middle section of the prelude so I just leave it as a piano solo. Microsoft wavetable MIDI GS synthesiser plays audio with a delay so I need to use a VST to make a piano sound. MDA piano is ok but it sounds noticeably cheap. Remarkably, after adding a good amount of reverb, it substantially improves the sound and doesn't sound as cheap. I was also going to have the last section be a repeat of the first section, but that's boring. 

My aim was to have a dubstep remix section at the end to make it exciting. I inserted some synth bass and a drum kit. The drums, unfortunately, sounded like lo-fi hip-hop remix so I muted them for the final mix. There are remixes of the prelude online but none of them I thought came close to my vision. 

I extracted the bass line from the piano parts and copied it to the synth bass. But the piano kept on overpowering the bass so I split the notes between the piano & synth bass. There is no JSFX MIDI 2-band note split but there is a midi note filter, so I set up a few buses to accomplish the roles. I also find that the piano is overpowering the vocals so I turn it down a bit. 

To avoid it sounding bad in different situations like my previous mashup, I tested it on 2 earbuds. My usual bass-lacking earbuds from my phone, and some bass-heavy earbuds which were purchased. The level of the piano & bass needed adjusting to sound acceptable on both earbuds. Since there were vocal artefacts from using DEMUCS3, I tried using MDX B. Unfortunately, that missed some vowels so I stuck with DEMUCS3. I gradually increased the tempo during the middle section to make the piano performance less robotic. Some small sections and the beginning and the end had their Tempo increased to make my mashup shorter and thus more palatable for casual listeners.

This was for a Halloween mashup album. There was a bit of back-and-forth as the album organizer wanted me to make improvements, mainly smoothing over artefacts with small xfades. The general consensus on my mashup is that it's surprising coming from me, but it's still good. Honestly, it shouldn't be surprising since it's not possible to pull this off without an appreciation of classical music. And like Rachmaninoff himself, it's far from my favorite.

## Never say dis

The theme for this week's mashup contest is 90s genre clash. Which means >=1 song has to be from the 90s, and the other song must be a different genre. Going through my mashups idea pool there aren't many 90s songs. I checked an idea with the contest judge, but he thought the two songs sounded too similar. He suggested 90's dance songs like Eiffel 65 - blue going with something else. Going carefully through my ideas pool again, there is the Danganronpa OP and infinite ryvius OP - dis. I thought that the key of dis was two dissimilar so I used blue as the instrumental. Miraculously, Danganronpa OP and Blue are the same key and BPM. Since the chord progressions in blue don't match Danganronpa, I need to chop up blue every half bar to create the chord progression I want. This is complicated by the fact that there are stems for blue, and I need to use them so the infrastructure for my project is quite complex. Basically I need to divide the stem section into two parts. The first part has chopped up melodic small clips which make the chord progression I want with the base piano and pads activated. The second part is playthrough stems which have larger clips eclipse to preserve the variation in the drum tracks and the drums activated. In this initial draft of my mashup project there were over 180 clips and over 10 tracks. It was getting complex to develop.

I then realised that infinite ryvius - dis only needs to be shifted a few keys to match Danganronpa so I switched to that instrumental to that and my project got a whole lot simpler. The keys and BPM now don't match so I need to pitch down Danganronpa OP, and speed up & up pitch Infinite ryvius. It also helps that the chord progressions in the chorus already match. I was going to make a custom chord progression in the verses to match Danganronpa, but that's not necessary since rap verses match any chord progression. I was a bit surprised that for the Danganronpa OP, not all vocals, for example the vocal fills and voice synthesiser were not removed from the instrumental, so I can't isolate them. There were also backup vocals in the dis instrumental during the pre-chorus so I looped the verse. There are several rappers during the verse so I need to EQ them differently. Unfortunately reaEQ band gain isn't automatable. So I need to use rea x-comp for that.


Now that the basic matching is done, mashup is "complete but a bit boring. I tried to insert 50 cent "pay attention boy" from disco inferno to spice up the intro, but didn't fit well. 

The vox in Danganronpa are gated during the last chorus on the lyrics "never" so I replicated that to the instro. The instro has different elements for the drum loop. Kick, hihat, and other. I turn to "boom boom tap" from DJ hero for inspiration. The rhythm basically goes boom boom tap, b-boom b-boom tap... . That section now has a lot of intensity and tension,. To duplicate that to the rest of the song would be tricky, since I need to balance consistency, variety and not annoying.


I tried a DJ solo (beat sampling and gating), during the bridge French verses, but sounded too intense and weird. The French vox in Danganronpa had imaging issues & was a drop in energy so I eventually replaced them with some previous verses.

I duplicated the vocal chops from the end of the song, and also made new vocal chops to match the vox in the 1st chorus, but sounded weird and too intense. straight 1/16th gating for 1-2 bars sounded boring and weird. There is also the problem of how to handle the 1st "never" at the end. For those, I settled on a "gentle" boom boom tap x2 rhythm which gives a bit of energy but doesn't drop out too much silence. For the intro and ending, I settled on a bit of 1/16ths gating to give a bit of surprise and tension. 


## Hitotsudake-Arifureta

I got the idea for this mashup by listening to the ending of Oreimo ep 11. Obviously, the song structures don't match and it took some time to figure out the best way to extend Arifureta to cover the instro. After this first full pass of editing, I extended Most clips to crossfade with the previous to cover discontinuity artefacts. I considered leaving it as finished, but some mismatched chords in the verses were bothering me, so I did some further editing on the verses(but with no cross fades) to better match the chords of the aca.

My master sync for the mashup is the acapella song since there are some AMVs on YouTube I could pair it up with later. There is no instrumental for Hitotsudake. so I need to use ML for the acapella. There's an instrumental break after the bridge which would be boring if I didn't put in the electric guitar or something. Most vocal stems produced by ML don't grab the guitar. So I need to use g audiolab to get the electric guitar out. This is my first time using g audiolab. I considered doing surround delivery for this project since there are some strings that can be spread to the back speakers, but surround activity is still low. During the bridge, there are some Echoes on the vocals so I put those in the back speakers for some discrete surround activity. Now it is somewhat more worthy to be delivered in surround. The acoustic guitar is panned hard left and sounds a bit unpleasant on earbuds. If I reduce the stereo width, then the volume of the stereo strings would also be reduced, which is undesired. So I just left the stereo width as is.

After testing on my surround speakers, the vox at the back sounds bad since my rear speakers have a very different timbre to my front (very mid-heavy), and the strings are barely noticeable from the back, so I changed upmix settings to put more strings @ back & remove the vox automation. Now, it's barely worth surround, so I just deliver as stereo. I then spend the next while adjusting V/I balance and EQ. It's not a busy House song, it's a semi-acoustic pop song so the vocals should always be on top in virtually all situations. I also fix a small chord match problem in the bridge. Tange Sakura vox is slightly restrained due to the compressor, so I dial back the compressor settings, so now the vox is barely being compressed. The midrange sounds strong on my desktop speakers so I boost the high frequencies slightly.

