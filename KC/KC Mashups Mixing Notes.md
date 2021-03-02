# Kantai Collection Mashups Mixing Notes

## starlog - nagato
June/July 2020
I said earlier that this song is weird. You can't build a mashup based on only a fitting chorus. And a few months later, it still doesn't (completely) fit. starlog is a good song, but due to the tricky key changes in pre-chorus, I think it's unlikely to find a matching instrumental. I did some detailed chord analysis (but it wasn't that useful in the end) & made 2 changes each pre-chorus so I don't sound like a total noob, but it still sounds bad. The vox also elevates keys during chorus, so I think it's reasonable to shift it down to match the constant-key instro. I use TB_voicepitcher cuz it has CPU gating on silence & non-wet. Vox needs formant control to sound natural. While CPU compared with elastique V2 Pro preserve formant is slightly higher, it uses less on silence.

Some light EQ on the instro to help the vox sound out. I initially had upmix then a mch pitching VST on the instro bus  for the best theoretical quality since stretching may change phase & upmix doesn't. But after some thinking & working on my pitchshifting doc, zplane is prolly using time-domain stretch instead of FFT. So I can do stereo pitch then upmix. After leaving it for at least a couple of months since july, since I wasn't sure of how to pitch & chord the special post-V2 chorus bit. I later decided to drop that bit since it sounds out of place & there's not really a matching bit in the instri. I quickly finished it in Jan 2021.

## Mutsuki mashup

So on the day that X trailer was posted on the sub, I thought of doing a mashup with Nexus. Coincidentally how I know nexus was also due to a mashup. Since the album was already released on the day, I decided to get the album. The web version doesn't have instrumentals, so I used a LQ web ML separator to get one. Shoudl've used  HQ one. Some regerts. Making a DIY aca of Nexus was easy, and so was syncing the mashup for the first part of the song. The chord progressions are simple, and the songs are mostly in neat 8-bar blocks. Actually there's some slight  structure mis-alignment throughout, but it sounds OK. I did some re-looping for structure matching & to remove the annoying percussion sound. There is some shamisen, which i tried to turn down with ReaFIR.

During the bridge, there's some tricky key changes in X so following the suggestion from [Ak-300_TonicNato](https://old.reddit.com/r/kancolle/comments/h969xe/negusetameshite_mite_mo/fv1xfic/) , I inserted some voice lines during the bridge as an energy & space-filler. There's also a voice line at the start, due to timing & structural problem with inserting claris there instead. The VLs are all in order, no K2 lines, library & secretary 1-3.

For the [trailer](https://www.youtube.com/watch?v=LSOFp-KwPzQ) , the bass was lacking. The album ver is a bit better, but I boosted the bass in anyway.

Quality

I saw Mutsuki's VLs have a cutoff of 12k, & I thought it was LQ. The bitrate is around 75kps. The ogg vorbis has a date of 2015 on wikia, but phase 2 was 2018 so I wondered if there's better versions for the web game. I also remembered there's a PS Vita version which might have better audio & there's a few references of on the wiki, but it'll prolly be a massive hassle to extract anything, esp if it uses a ATRAC codec. Then I remembered I was linked Kumano's battle call on DC, & that goes up to 16k, so I guess the vorbis clips are OK quality. So I applied some of my FFTMT noise control/gap filler  & some EQ to boost quality.

There are some later clips like Mutsuki's 5th anniversary & Shigure's spring 2020 event, those are suprisingly lower quality at 56kps mp3, and you can hear the chirping artefacts. So I guess the vorbis ones really were better.

## Haruna no Jikan

So on the day that X trailer was posted on the sub, I thought of doing a mashup with "Secret of my heart" due to the chords in the chorus.  Unfortunately, the verses don't match so there's a lot of cutting there.  There is also a mode difference, so zplane retune use, & clip pitchshifting when it doesn' work. There's several key changes in HnJ so I use clip pitchshifting to undo that/fit to SomH.

At the time the trailer was initially released, I searched ????? on YT, and apart from teh songs, it gives results for bike riding on what I presume is Haruna mountain. I guess it givies new/old meaning to riding on Haruna since Haruna (ship) was built &/ its implementation in KC.
