# Key - Various Reviews

## Introduction

This document has my own reviews, analyses, and technical notes split off from the [main document](https://github.com/junh1024/junh1024-Documents/blob/master/Games/Key%20-%20Overview%20of%20Visual%20Novels.md#introduction) due to length reasons.

## Accessibility

If you're visually impaired (AKA blind), newer Key VNs which use the Siglus engine [don't support screenreaders](https://old.reddit.com/r/visualnovels/comments/190rnek/weekly_questions_and_recommendations_megathread/kgynr6d/) . So you may be limited to older games which use the AVG32 and RealLive engine. Re-releases (including official English releases) may use the newer Siglus engine, so you may be limited to older games from Kanon through to Little Busters, and fan translations.

VNDS is a VN script interpreter. Originally for DS, but now supports  Android, iOS, PSP, Windows, Mac, Linux, and Switch. A Windows interpreter is [available here](https://github.com/ajusa/VNDS-LOVE) . CLANNAD has [been ported](https://web.archive.org/web/20101205113404/http://digital-haze.net/ch/vnds/kareha.pl/1276442564/) to VNDS.

ren'py has a self-voicing (TTS) feature. No Key games have been ported to ren'py, but there is a fan game called [CLANNAD - The Past Path](https://renai.us/game/clannadthepastpath.shtml) in ren'py.

You could always watch the English Dub of anime. Dub exists for Kanon, Air, CLANNAD, and Angel Beats.


## CLANNAD HD technical analysis

CLANNAD has been remastered for a new generation of widescreen HD consoles starting from 2008 with the Xbox 360, but the may be some changes that aren't an improvement. Ever since it was announced with a 5.1 soundtrack, I've been wanting to test it, but I got stuck about 8? years ago with AT3 files from the PS3 version. But luckily now, there is a rip of the soundtrack which is easier to convert.

Due to the widescreen HD display format, most art is now sharper, but some artwork could be cropped, leading to less picture _CHECKTHIS. On the [switch version](https://old.reddit.com/r/Clannad/comments/l0iqa3/clannad_original2004_vs_switch_hd_edition/gjtvzyl/) , "you can tilt the screen up and down using the right stick" to reveal more picture. The soundtrack has been slightly remixed, but you might prefer the original version, especially if you're accustomed to it from the original or the anime. But my biggest complaint is about the 5.1 surround handling of the soundtrack.

The 5.1 soundtrack is a significantly worse experience than the stereo version, including the OP. It's badly upmixed, the width has been reduced to almost mono, it's tilted to the left, and significant center channel activity means dialogue is subtlely obscured. It's worse than using the upmix feature on your AVR.

What I would have recommended to the developers, if you want a surround experience, but don't want to spend too much time on it, is perform mixing in the game engine like the following:
- Dialogue goes to only the center speaker.
- Sound effects go to front or center
- Music goes 66% to the front (excluding center), and 33% to the back speakers.

This would give a very mediocre experience, but it would be a significant improvement over the current situation. Ideally, every single soundtrack piece would be remixed from stems, competently, for a proper 5.1 surround experience. My [surround panning guide](https://github.com/junh1024/junh1024-Documents/blob/master/Audio/Surround/Instrument%20Panning%20in%20Surround.md#introduction) is relevant here. For now, I would recommend switching to stereo sound and using the upmix feature on your AVR. 

Conclusion: CLANNAD HD might not be an improvement, especially for the 5.1 sound. Please switch to stereo sound for a better experience. If you're on PC, you may have the choice of the original or HD version to suit your tastes. But if you're on a game console, you won't have much choice if you want to experience CLANNAD.

[back to main document](https://github.com/junh1024/junh1024-Documents/blob/master/Games/Key%20-%20Overview%20of%20Visual%20Novels.md#planetarian)

## Can Key games support surround on PC?

Game consoles have better surround support due to platform support and the way that they're typically used. PC games can have surround audio and they do have some platform support, but a bit less and for typical scenarios, surround speakers are probably less common. Before we answer this question, I'd like to go through codecs.

Most of Key's earlier games use the RealLive engine, and that implies use of NWA DPCM for the audio. DPCM has a compression ratio of about 2:1, and is transparent under basically all scenarios, but slightly big by modern standards. Unless you're DTS, most (A)DPCM is mono/stereo-only so I didn't bother testing RealLive games for surround audio support. Not to mention, I can't find any (surround) encoders for it.

Key's newer games use the Siglus engine, and some of them have a ogg vorbis soundtrack. I would say the encoded bitrate is a bit low. But anyway, ogg vorbis has native surround support, so I encoded a 5.1 file and put it in a game to test. Unfortunately, the game errored while trying to load the file. So the engine/decoder wasn't made to support surround.

My attention then turned to the movies. Key games have FMV in various formats including mpg, mp4, and wmv (yuck). But playing video is delegated to Microsoft frameworks, so surround might work. With setmovie.exe, you can select which API to use. The default is Directshow AKA "Windows Media Player". My test file was renamed to the filename and extension (which is different to the original extension) to one which the game expects. On Directshow, Using a file with H264 video, AAC audio of test tones, and viewing the level meters, I can confirm that surround audio works when the movie is played in the game. However, if Windows Media Foundation AKA "MCI" is selected, then the game stalls with an error, perhaps since the contents don't match the file extension.

Conclusion: Siglus doesn't support surround audio, but Directshow does, always has (maybe). Would be nice if Visualarts added support for decoding and playing surround ogg vorbis.



## Chihaya Rolling

<img src="https://i.ytimg.com/vi/zNimjmr1ZhM/maxresdefault.jpg" height="180">

[](https://i.ytimg.com/vi/zNimjmr1ZhM/maxresdefault.jpg)

*image: Chihaya Rolling in-game*

[Video of gameplay](https://www.youtube.com/watch?v=p_Tjh4Vs38Y)

Released in 2010 before Rewrite, is Chihaya Rolling - a mini-VN to test if your PC would be able to run Rewrite. Key was to use the new Siglus game engine starting from Rewrite, to take advantage of features found in modern OSes and Graphics APIs. If your PC wouldn't run Rewrite well, you'd know. Finally, we can finally make those pesky laggards using a Windows 2000 computer finally upgrade ... to a Windows XP computer! Despite the game looking 2D, it probably uses a 3D pipeline with DirectX since [the site](http://Key.visualarts.gr.jp/rewrite/download.html) mentions something about pixel shaders. 

Running the game initially, it has Anti-Gaijin protection AKA the infamous "This game is for Japan only" error. But this inconvenience is quickly solved with the help of Google-sama. The core of the gameplay is watching a number go up while Chihaya rolls down a hill. Saya Shinomiya's top-notch voice acting and Shinji Orito's music really gets you into the mood. We know when Chihaya's hurt - because she says so.

The visual novel is novel in that it requires changing the power/performance settings of your system in order to achieve more endings. Running this on a modern computer, I achieved the "B" ending. But limiting the CPU speed to the lowest, I was able to achieve the "D" ending. Various S and even an F endings are [apparently possible](https://www.youtube.com/results?search_query=%E3%81%A1%E3%81%AF%E3%82%84%E3%83%AD%E3%83%BC%E3%83%AA%E3%83%B3%E3%82%B0). Remember that number from earlier? It's a distance counter. Depending on your PC's performance, the distance can be equivalent to travelling from Okinawa to [various locations](#Appendix) around Japan. Such as to Kagoshima, I don't know, and even Siberia.

Conclusion: There are various free and paid VNs for PC, but there is only 1 which has Chihaya rolling down a hill.

NB: This is a satirical review of Chihaya Rolling.

[back to main document](https://github.com/junh1024/junh1024-Documents/blob/master/Games/Key%20-%20Overview%20of%20Visual%20Novels.md#rewrite)

## Siglus Engine - the Controls

Rewrite being the first Key game using the Siglus Engine the UI looks a bit Janky. But at least the button text is big and readable. Successive Key games have shrunk the button text, and with Summer Pockets, it's probably the worst since icons were added, and now the button text is now very small and in a Serif font. There are a variety of ways to implement the controls and UI for Siglus, as [shown on vndb](https://vndb.org/r?f=fwSiglusEngine-&fil=&o=a&s=released). 

Angel Beats had a good design with small icons, but medium-sized text to the right. If only the controls were enlarged to fill the whole width of the screen, then that would be close to perfect. 



## Key Box - "For two decades" review

![KeyBOX characters](https://obs.line-scdn.net/r/linenews/a/zOO7XcZNsFOEMAhI19ca2766t0a33a710/n600x400)

*image: KeyBOX contents and outside*

I'm going to do a critical review of this box set. Disc list is [here](https://musicbrainz.org/release/208f1ca5-d6c4-4b21-9810-39a51faf842f/discids). My review is based on disc list, and listening to some of the individual songs.

When I found out that Key was going to release a boxset of Key songs, I thought would be great since it would have some soundtracks, but it doesn't include any. Not even important themes or leitmotifs of the heroines as a "soundtrack sampler". To be fair, if they did include the soundtracks in full, it would take up about half of 50 discs. 

The artwork for each disc is very generic, and although there seems to be a tracklisting on each disc, it's hard to remember what's on each disc otherwise. They could have colored the discs on each section differently or had something reminiscent of the original disc artwork.

The first section of the box is great. We go through the important Key vocal songs and some nice arrangements. I'm glad The Little Busters EX "ontology" arrange isn't here. It would be too Avant-Garde for most people. The next part has Angel Beats & Charlotte vocal songs. If you don't like them, you'll be Stockholm'd into liking them (maybe).

The rest of the box might be in chronological order, but perhaps this isn't the best way to present them, and is a mixed bag. There are a bunch of remix albums/compilations, live albums, and miscellanea. Some remix albums have been compressed to a single disc, and you might not agree with the compressed selection. I'm not so keen on live albums as it's technically a repeat of content. Some people might enjoy the atmosphere & banter though. The memento remix CD set could've been included in full, rather than just 1? song from it, since there are some nice remixes on there. I'm not so keen on Vocaloid stuffs.

Modification of Key sounds & 20th Anniversary Remixes was mostly quite bland modern EDM with only a few good remixes. Notably missing is [Enigmatic Lia 4 Anathemical Keyworlds](https://vgmdb.net/album/27616) . Although that is under a different label, both KSLA & QLCD are under the same parent company. So they could've included it IMO. And a few months after the release of this box, more remixes on Modification of Key Sounds Vol 2, and Key BEST SELECTION were released, which is unfortunate.

Apart from Humanity which is a milestone as being the 1st album released on Key Sounds Label, there were some discs I felt could be left out. OTOH while "Love Song" has motifs which would form the inspiration for later soundtrack themes ( https://en.wikipedia.org/wiki/Love_Song_(Riya_album) ), overall it felt somewhat lacklustre, due to a cumulation of small reasons like similarities between tracks, composition, long length, and production quality. The "Owari no Hoshi no Love Song" concept album is a milestone for collaboration between Jun Maeda and Yanagi Nagi, but it doesn't have anything directly related to Key games. "Long Long Love Song" again, it seems more Jun Maeda than Key. 

According to musicbrainz, the average CD length was just under one hour, so perhaps they could have put a little more on a few CDs. But it might be more economic to use existing CD Masters.

They could've included a DVD-ROM or download card for MP3/HE-AAC files so that you can easily load the whole box onto your phone. Or a DVD/BD with all the songs on it. They could also put, or on a separate release, off-vocal versions of songs they don't have off-vocal versions, like Koibumi and Canoe. 

Conclusion: If you want a bunch of Key vocal songs and remixes you'll get it. But if you have specific tastes and wants like me, then you'll probably be better off buying individual releases. Perhaps this box is not for Key fans, but for other people to get introduced to Key songs.

[back to main document](https://github.com/junh1024/junh1024-Documents/blob/master/Games/Key%20-%20Overview%20of%20Visual%20Novels.md#summer-pockets)

### How to make a good remix
After being unimpressed with the style &/effort of (some) of the remixes from Key Box, I decided to write this rant.

A good remix inserts new compositional elements to make it seamlessly fit into the target genre, rather than just instrument & sound changes. Ostinatos don't count. Some examples:


- Yami no Kanata He Night Funk Remix: Apart from a few added beats, there's no new compositional elements. EQ and gating aren't composition. Bad remix.
- Catch You Catch Me House Remix (from KIRAKIRA MAJOCCO CLUV): is a good remix since it adds new compositional elements. A new brass motif was added to the introduction, and chords were made more repetitive in the verse to make them more suitable for a house style.
- Tori no Uta | cosmic seekers remix: adds ostinatos which don't count, but it adds a very prominent saw Motif in the post-chorus. Good remix.
- Sunbright | Brightest Sunflowers remix: adds a few elements. if you don't count the new motif in the introduction, there's still the post-chorus motif, and a Bridge was made out of the outro & 2nd chorus lyrics. Very good remix. 

These are some examples of (good) remixes that have new compositional elements. Ayumi Hamasaki - M | Above & Beyond Remix doesn't add many new composition elements (mostly lots of ostinatos) but somehow it's still good.


## Appendix

Full list of locations for Chihaya Rolling: Okinawa, Kagoshima, Hakata, Hiroshima, Osaka, Nagoya, Tokyo, Sendai, Hachinohe, Sapporo, Wakkanai, Siberia
