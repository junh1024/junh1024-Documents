# Anime Mashups Mixing Notes 2024A

## Yukitoki-Shonen

I had this idea a while ago. Note that Shonen is in the relative minor of Yukitoki. This is another mashup that turned out not that great after I made it, but it got one vote in the brass contest. The mashup arrangement is kept close to the vocal song, so I had to cut Shonen from about 6 minutes down to 4, resulting in some obvious cuts. The good thing about the mashup is that it could be delivered in surround since I can just upmix the Orchestra of Shonen . They were some chords in the backup vocals of Yukitoki that didn't quite fit the music, so I used my surround upmixer then muted the side channels to turn down the BVs during that section. 


## Koi wo Shita no wa-Okaeri

I think I got this idea when I resumed watching Non Non Biyori. The first verse fits pretty well, but the chorus doesn't, since song 1 is single rate 4536, and Song 2 is double rate 4536. So I need to do lots of cutting and it doesn't sound that great since clips and audio are noticeably duplicated. it takes a long time to do this, and I had slow progress for quite a while, until I come across the post-chorus of chorus 2. That has a double rate 4536. I then restructure the whole mashup so that the chorus of the acapella is replaced by the post-chorus and it sounds a lot better now. if I had used my original strategy of matching chorus to chorus etc, then my mashup would be about six minutes long. But with this new strategy, it's only about four minutes long which is still okay. Since I'm repeating the post-chorus, I need to be careful. The "darling" lyric at the end of the post-chorus is removed from earlier iterations, and reserved only for the final chorus since there is a sense of finality about it. 



Koi wo Shita no wa-Okaeri
aiko, ZAQ
A Silent Voice, Non Non Biyori

- Start: 01/11/2022


## Blue Topaz-Dance The Night

### How I know the songs


Dua Lipa - Dance The Night: It was probably through a mashup - that song was mashed with Britney Spears - slave for you. It was used as an instrumental, and from the opening few seconds of the luscious string hook, I could immediately tell it could be a good song.

Ridge Racer - Blue Topaz: I've done a few mixes/remixes with Ridge Racer songs, but I've never actually written how I know The Ridge Racer soundtrack. So in about the mid-2000s, I was going over to a graphic design classmate's house since our Moms wanted to talk. It was around the time that the Sony PSP was released here, and I was into racing games like Need for Speed Porsche Unleashed (1999) since due to my crappy Sony Vaio laptop, I couldn't play the latest titles.

One of the games that they had was Ridge Racer PSP. I entered the race, and I was drifting through a futuristic City while the song disco ball was playing. When I got home, I quickly looked up Ridge Racer's soundtrack. And from then on, the rest is history.

### Instruments

Dance The Night bass has distortion, so it sounds good and cuts through the mix even when it's stretched or pitched by a moderate amount. 

The strings in Dance The Night sound like real strings, but the strings in Blue Topaz are obviously fake. But somehow, the mashup still works well and you won't really notice a switch. The strings in Dance The Night were brought back for the ending in a crescendo to add tension, otherwise it would be too boring. 

I Used DEMUCS for Blue Topaz, but the piano separation wasn't good enough, so I need to use gaudiolab.

Since the separation was imperfect, I was thinking about recreating some stems for Blue Topaz, but it seems that quality is just enough for a mashup. In the chorus I need to keep on switching between +1 & +3 semitones shift for Dance The Night. I realize in Blue Topaz, that the chorus is actually a circle progression. 

### BPM choice

Initial BPM choice is important. To fit Blue Topaz, Dance The Night needs to be pitched -2 semitones during the verse, and up to +3 in the chorus. The average of that is +0.5 so it would do good to slightly speed up Dance The Night. Also, Blue Topaz is stretched by a moderate amount to match the tempo of Dance The Night, so any speedup of Dance The Night is welcome to maintain the quality of Blue Topaz.

Since the pitch shift of Dance The Night is quite moderate, then the cymbals change pitch. I was considering using stems for Dance The Night & then treating the drums separately, but elastique Pro preserve formants high performance does an okay job of preserving the pitch of the cymbals. It's also quicker and easier than using ML stems. Since I'm using preserve formats for the main song, I also need to use preserve format for any FFT side chain subtraction.



### Less is more
It's important to play around with level and arrangements of the different stems in this mashup since it's instrumental versus instrumental. There are strings in both the chorus of Blue Topaz and Dance The Night. For a moment I thought it could fit, but it sounded too busy so I removed the dance the night chorus strings. Dance The Night strings were also mostly removed in the choruses, but I bought it back at about a half volume in the verses. The strings are in the others stem. Since I'm removing the other stems as part of a sidechain, then if I want to add the strings back, I actually need to turn down the strings in the sidechain.

The clip volume of the piano in Blue Topaz was also changed over the mashup. The guitars & electric piano were also removed from Dance The Night to get more space. The guitars in Blue Topaz could also be removed, but they're a part of the other stem at the sides, so they would need FFT stereo imaging to remove.

Low pass at the start of the 3rd verse on Dance the Night which gradually disappears seemed like the right thing to do.

### Timing issues
When I was almost finished doing the mashup arrangement, I noticed that the kick of Dance The Night isn't aligned with the clip boundaries. I also realized this is why the piano in Blue Topaz is too early at the start of The mashup. I realise that this is due to both songs having fractional BPM, as opposed to the integer BPM I found on Tunebat. This is going to be a tricky issue to solve.

I had briefly considered this issue in the past in the context of different CD rips. if different people rip the same CD, then all that would change is the start offset. Even if you stretch the audio in editing, the solution is simple - just shift all the clips by a constant amount. If for some reason the CD is a Remaster and there is a rate change, then you're screwed.

I now think that it's possible to fix a rate change. Firstly, the start offset should be corrected with the factor old rate / correct rate. Then the correct rate should be applied to the clips taking into account the project BPM, with the formula correct rate / project BPM. The approximate vs actual BPM for Dance The Night and Blue Topaz are 110 and 130. Therefore, the formula and values are

**Start offset factors:**
- Dance The Night: 110/110.004 = 0.99996363768590233082433366059416
- Blue Topaz: 130/129.998=1.0000153848520746473022661887106

**Correct playback rate**
- Dance The Night: 116/110.004=1.0545071088324060943238427693538 
- Blue Topaz: 116/129.998=0.89232142032954353143894521454176

I made some new Python scripts based on similar scripts I did in the past. Applying these operations to the clips, the timing problems are now fixed, but there are slight discontinuities at clip boundaries due to inaccuracies and editing. It would obviously be better if I had edited at the correct BPM in the first place, but this is the best I can do without completely remaking my mashup. A lesson learned: BPM of tunebat is fine for quick evaluation of ideas, but may not be ok for heavy editing. An accurate BPM needs to be measured.

My usual loudness Target is -18.5 which means a loud song. But if you Target -18.5 for this song then compare it to other vocal pop songs at -18.5, then this mashup will be too loud due to no vocals among other things. So you would need to target 1-2 LUs below that.


I was also considering surround for this mashup, but surround activity is a bit Mediocre and the brass didn't get Upmixed to the back in Blue Topaz. The strings in both songs are too backwards when upmixed to surround, so I reduce the stereo width. The piano could also be reduced in width as well.



### Testing on speakers

I listened to my mashup on my desktop speakers, and I noticed that the bass was a bit resonant & loud so I turned down the bass in an EQ. But when I looked at the EQ there was also a mid-cut. I also checked later on my bright headphones that the high end might be a bit loud. So overall, Dance The Night can be adjusted 2.5 DB down instead of a bunch of cuts. 

Also, the piano in Blue Topaz sounds like it's coming from behind. Perhaps due to the combination of the reverb and the placement of my desktop speakers below ear level. If I put some dry IR like SADIE2 KEMAR then that makes the piano sound more forward.

To reduce unintentional imaging on headphones I wanted to recreate it using EQ. I was briefly considering Waves Brauer Motion, but Waves plugins are a hassle to install. White Noise was played through the IR, and I recreated using EQ that a sharp dip at 1750hzm and then a slight gentle wide boost at 3.5 k. The dip at 1.7 k -10 DB was quite colouring and noticeable so I reduced it to - 5 DB.
