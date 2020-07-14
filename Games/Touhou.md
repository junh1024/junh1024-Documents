# My un-conventional un-experience with Touhou

Introduction
===
Hi. Today I'd like to discuss how I know touhou

Popularity
===
Touhou is a popular game franchise, particularly in Japan, but also worldwide. The main game series is a [Danmaku](https://en.touhouwiki.net/wiki/Danmaku) genre game, or "Bullet Hell" where the aim is to dodge bullets & other projectiles. At the time,  mikos (shrine maidens) fighting against each other was a somewhat original concept. But mecha musume e.g, Kantai Collection (which I'm more familiar with) was not. Since c.2015, the number of KC circles at comicket exceeds the touhou ones (but touhou has its own Reitaisai event), but still remains relatively popular & well-known. 

History
===
The 1st 5 games were for PC-98, starting from *Highly Responsive to Prayers* (finished in 1995), owing to its graphics & sound capabilities & wide adoption in the Japanese home in the 90s. With the rise in Windows & IBM PC clones, usage & manufacture of PC-98 machines declined, and the next 12 games (as of 2020) starting from *Embodiment of Scarlet Devil* in 2002 would be for Windows. This is In contrast with western franchises such as Test Drive & Need for Speed, which started with DOS, then Windows. Reimu & Marisa are the only 2 characters that feature in the main series [says KYM](https://knowyourmeme.com/memes/subcultures/touhou-project-%E6%9D%B1%E6%96%B9project), so TH6+ can be considered a (soft) reboot.

Influences
===
Computer Science students tend to be into ACG (Anime Comics Games)

Impressions
===
In the chats that I participated at the time, playing touhou was sometimes mentioned, I'm more familiar with Kantai Collection tho. As of Despite being younger, KC has >200 characters, while touhou has >100. But KC is much more commercial & has more staff. I haven't played either game.

If I think of fighting characters, I might think of something like Tekken so I might assume touhou looks something like this https://wiki.gbl.gg/w/Immaterial_and_Missing_Power/HUD . But the main series is actually like this https://en.touhouwiki.net/wiki/File:Th06screenLayout.jpg

With videos such as "Bad Apple!" and ["Down Beat Touhou"](https://www.youtube.com/watch?v=_iuwajdRwX4) (the Tom & Jerry parody with Reimu being unhappy about her newspaper-reading being disturbed by music & a bear)

images like https://safebooru.org/index.php?page=post&s=view&id=794351


tekken

Abbreviations
===
Apart from

- Undefined Fantastic Object = UFO = Undefined Flying Object (no doubt a deliberate reference)

there are 2 more abbreviations that can be understood as something else to me.

- Embodiment of Scarlet Devil = ESD = Electrostatic Discharge
- Perfect Cherry Blossom = PCB = Printed Circuit Board

ESD is something you want to *avoid* when handling electronics as you can harm equipment. You may've seen [special bags](https://en.wikipedia.org/wiki/Antistatic_bag) covering electronics. Conversely in touhou, you want to *avoid* bullets. PCBs are a major component of mass-manufactured electronics.

There don't seem to be many other abbreviations that have other obvious meanings so they may be just coincidence.



Video
===

x264 tune touhou
---
It seems that it was added in [July 2009](https://code.videolan.org/videolan/x264/-/commit/71b9d885aacd1cc86851248af6824ed0cd965d98) with a new preset/tune system.
I do video encoding so I stay up to date by viewing chat channels. x264 has an undocumented touhou tune, which was mentioned in one of the chats, a while after it was added. I recall someone said it's good for tracking small moving details better, but I could be wrong. Looking at the [code](https://code.videolan.org/videolan/x264/-/raw/master/common/base.c) now, (search for *touhou*) I think it does this to improve quality & compression efficiency, in order of estimated importance:
- Enable 8x8 transform(s): better efficiency in general
- Double the references: games have compressible & predictable motion
- AQ strength is 1.3: more bits spent on areas that would otherwise get less bits (e.g, very low or high detail areas)
- psy-trellis 0.2: more bits spent on small details
- reduced deblocking: less blurring (but potentially more blocks)

With the exception of deblocking, most of these are prolly good for most content in general. But it's probably meant for use at low bitrates &/ fast encoding to give a bump in the most important settings. The slowest pair I would suggest is "--preset slow --tune touhou" & if you're using "--preset slow" as a general thing (which is the slowest preset I suggest) then all you need to add is --deblock -1:-1 (which is basically what makes  --tune touhou slightly unique)

NB: I have not encoded any touhou.




1st mbtree test

mb-tree
Touhou was used for the 1st (public) mb-tree demo to show off x264's new capabilities. What does mb-tree do? It lowers quality on complex/moving parts of scenes where a reduction in quality is not as noticeable (as static parts), hence a reduction in bitrate. [Discussion](https://forum.doom9.org/showthread.php?t=148686) , [Clip](https://cdn.discordapp.com/attachments/505520008357740564/732910448956932137/UltraLowBitrateAnime.mp4) touted as 67kps anime

This isn't the clip I remembered, it was maybe 240p 12fps of at least a few seconds with no audio,  there was a girl trying to find something in a pile of junk by throwing stuff out 

Audio
===
Touhou is also known for its large amount of doujin albums. There's a large collection of it online, I initially assumed it was music from the games, but if you do some quick maths on the size, and it's all fanmade remixes. So around 2010-2012 I was looking for Key & Pokemon music and it just so happens that a few of those songs are on mainly touhou albums. Now, if it's touhou doujin music, it's relatively available thanks to TLMC. If it's not, well, YMMV. But you can't get individual songs. So you have to get the entire album. So I got an anthology, I liked some of the songs, and I got the source albums, "Multiple Far East" & "Faith of Shrinemaiden" from "XL Project". Another album I got was "BubbleRecords - Reel". I've been listening to them a few times over the years. I made 2 Anime House mixes, which I was happy with, and I wondered if I could make a Touhou house mix. And the answer is, [yes], with a few extra pieces. So, now I'm looking into making 2 more, in different electronic styles.

Key music in TLMC