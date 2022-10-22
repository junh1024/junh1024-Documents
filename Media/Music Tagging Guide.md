# Music Tagging Guide

These are based on Gazelle rules, but some may differ and may break rules (check your site rules before using these). If you're not sure of any field, refer to album art. You may notice a pattern while reading, if it shouldn't go in 1 field, it goes in another, or Comments. This works, as long as you don't have too many things in Comments. If you have a lot of alternate info to add, consider having a "info.txt".

This is meant to be a comprehensive, general, and holistic tagging guide, which covers multiple domains, pop, classical, and surround. I started off with using iTunes & Winamp, then moved to Mp3tag. Mp3tag is good, but "iTunes" supports some operations that the former doesn't.

Principles
---
- clear
- concise
- compatible

Conventions
---
In this document, field names use proper case, like Title & Artist. Field values or strings are usually quote-surrounded like "Thriller". Unless the field has quotes, in which case it's triple-quoted like Python.

Definitions
---
Anthology=1 Artist, but a composite of songs from different albums
Compilation=different songs from different artists on 1 album
Karaoke=Song with lead vocals removed
Instrumental=Song with ALL vocals removed 

Technical
---
Files should have their proper tag formats, like id3v1/id3v2 for MP3, MP4 for AAC (if you have raw AAC you have a problem, wrap it in MP4 first), vorbis for FLAC, etc. If you have id3 for FLAC, remove it.


Organization
---
I can't really say where your music should go, that's influenced by other factors. You might keep your music with your video franchise, or in a dedicated collection. But maybe classical & surround music collections should be separate from pop music. For most fields including Filename, excluding Lyrics & Comments, I suggest keeping them under 64 characters.

Character set
---
English
---
For roman text, it is recommended to use ASCII to avoid codepage issues, etc. Fields shouldn't have OS-reserved characters like """\/:*?"<>|""". They can be replaced with other characters. Fields shouldn't have accents.  "Pokémon" can turn to "PokÃ©mon". That also means no curly quotes. Fields & filenames should have no unique info & can be perfectly recreated from each other. Like, roomaji in filenames but hiragana in Title is bad. You can use Comments for alternate titles and Album Artist for alternate Artist.

Japanese
---
For Japanese releases, there is the decision whether to use translated, roomaji, or japanese text. Each has its own pros & cons to do with compatibility, searchability, performance, etc. Keep in mind rendering asian characters is slower and can cause issues. Use the common name for strings. Like "Mezase Pokemon Master", not "Mezase Pokemon Masutaa". And "Asuca Hayashi", not "Asuka Hayashi". For artists, use western order (firstname, lastname) for roomaji like "Rika Matsumoto", and asian order (lastname, firstname) for kanji like "松本 梨香". For albums, there might be a good translation, or at least good roomaji for Titles. NB: translations can differ. For soundtracks especially, translations can differ a lot, so prefer roomaji or kanji. People searching translated strings may get less results. What you use should take into account what's most common & easiest to search. There's usually good roomaji/english for Artist & Album so use those.

Chinese
---
For chinese, I'd suggest using hanzi Titles, since chinese alphabet soup like "Ni Di Ming Zi Wo Di Xing Shi" is very meaningless & unsearchable. Use like "你的名字 我的姓氏" instead. There may also be the issue between "Chinese Traditional" & "Chinese Simplified". Use what's common. Use for Artist & Album, if there are good english strings. Like "Jacky Cheung" & "Music Horizons" instead of "張學友" or "张学友" & "音乐无疆界演唱会". Definitely not "Cheung Hok-yau".

Filename
---
(Disc number if multidisc) Zero-padded track number Track title (so that tracks sort correctly). No symbols after Track. No other information (like Artist). Derived info like codec & bitrate information like "[mp3 V0]" should not go in the filename. You can find out this info using "Mediainfo".

Examples:
- "01 What's Going On"
- "02 What's Happening Brother"

- "1-01 Workin' Day And Night (Immortal Version)"
- "2-01 You Are Not Alone - I Just Can't Stop Loving You (Immortal Version)"

Folder
---
A minimum of Album title. There's a lot of variations that people use & it can get really junky with lot of numbers. Basically, the minimum that you can use that's reasonable & distinguishable from other folders in your context. Again, you may have external factors which influence this aspect. For a general collection, Artist & Album should be in a combination of Folder & Filename. Like, you can go "/Michael Jackson/Thriller/", or "/Michael Jackson - Thriller/" , but "Michael Jackson/Michael Jackson - Thriller/" is redundant.

If you want to have some sense of chronological order, you can go Year Album like "2007 Multiple Far East". For doujin music you could use Catalog & event like "[XLPS-0012] Multiple Far East [C72]" as long as it's not too long. If you have a franchise collection, artists will obviously differ and it might be lengthy to put Artist in Folder. To enforce order, you can make an ID with the last 2 digits of Year + a sequence number like "143 Megavolt - Sunshine" for Year 2014 & 3rd album of the year. I very definitely do NOT want to see folders with eac-archive convention like "[2013.07.03] yanaginagi - euaru [Limited Edition][GNCA-1376]". I don't like Folders (or fields) with full dates, and Catalog can go in Comments, or even the Filename of Art. Keep in mind if you do a beginning of string search with folder names that don't start with Artist or Album, you're going to have a hard time finding it. 

Filesystem performance doesn't start to degrade until >100 files in a folder, so you can flatten multi-disc albums into a single folder for a more convenient & holistic view of files. Exception: for very large boxsets (like 10+ discs), you can have folders of a few discs, but still stick to the Filename conventions above. For Folder, like "Disc 1-3 - Early Years"

For franchises, you might have a franchise folder, then you can use generic normalized names like:

- Toradora/Music/OST
- Toradora/Music/OP

or

- Toradora/Music/Toradora OST
- Toradora/Music/Toradora OP

2nd might seem redundant but often the franchise is in Album or Subtitle

Combined Albums
---
Sometimes, you have a soundtrack spread over several volumes but padded with audio dramas so it's annoying if you want to listen to the soundtrack or drama only. You could separate the discs, then make a soundtrack collection, then a drama collection. Preserve the tags, especially Album so you know which Album it comes from, except for Track or Discnumber. I prefer to group them into disc-length (80min-ish) collections. Disc can be used as a volume number even though they're not released as a collection. There are 3 schemes which make sense:

- 01 Audio Drama 1
- 02 Audio Drama 2
- 03 Audio Drama 1
- 04 Audio Drama 2

(continuous numbering within 1 folder, Track not preserved)

- 1-03 Audio Drama 1
- 1-04 Audio Drama 2
- 2-03 Audio Drama 1
- 2-04 Audio Drama 2

(discontinuous numbering within 1 folder, Track & Disc preserved)

- 1-01 Audio Drama 1
- 1-02 Audio Drama 2
- 1-03 Audio Drama 1
- 1-04 Audio Drama 2

(continuous numbering within 1 folder, Track & Disc not preserved)

Make a generic Folder + sequence number.

You could also combine related/thematic albums, or multiple OPEDs into a single OPED collection. If they have scans, combine the scans into a single folder, but prefix the scan Filename with the volume number so that ordering is preserved. Combined albums mostly make sense with franchises with many CDs. If you combine, make sure you have a good reason. I haven't really seen a case for this for western releases. Also, some people may not like this.

Major tags
---

Year
---
Should be year of release. In general, this should work well since recording & production years should not be too far apart. You can have a good ordering of songs if an artist does albums, then anthologies & concerts of the few years immediately preceding that. But there are some cases where a concert is released 10 years after it happens, and so its songs aren't close to its source albums in organization. Then you can break this rule. Maybe not a problem with posthumous new albums.

It's somehow trendy nowdays to use this as date, when it was in the past used for year. If you look at [tag mappings](https://help.mp3tag.de/main_tags.html) aka [frame types](https://docs.kde.org/trunk5/en/extragear-multimedia/kid3/commands.htmlframe-list) , some say year & some say date. I prefer to use it as a year field (see Principles), it's easier, and some information sources might not give the date. Because having "2020\\2020-07-09" in a Year/Date is awkward. 


Title
---
If the capitalization of the Titles are sensible & consistent, you can leave them. If they're not (like a mix of lowercase & proper case) & it seems not-deliberate, adopt a more generic system like proper case, unimportant (depends on context) words in lower case. For a more comprehensive guide on capitalization, see the [RYM capitalization guide](https://rateyourmusic.com/wiki/RYM:Capitalization) . Title should not contain anything else, like credits. e.g, "feat. Myka" is not actually part of the title.

Case study: Pokemon
Some artists put other information, like where it's from, like """Surf Theme (From "Pokemon Diamond / Pearl / Platinum")""". It could be abbreviated to "Surf Theme (From Pokemon DPPT)", or the source game info can be put in Comments. It's not goot to put just "From Pokemon" across all fields since different games have different surf themes. But for "Azalea Town (From Pokémon Gold - Silver Crystal)", the specific game is maybe redundant, since there's only 1 "Azalea Town" in the entire series, and you don't even need to put "Pokemon", since "Azalea Town" is quite Pokemon-specific. But if you remove redundant info from fields, this may create inconsistency. So do what's sensible & appropriate, keeping in mind conciseness. And depending on how much time you're willing to spend.


Artist
---
Who the song is by. Featured artist credits also go here. e.g, "estha feat. mintea". For instrumental songs, it makes no sense to have the Artist field same as the vocal song, since the artist does not sing. Instead, have anyone else, like the composer (if Composer is blank), arranger or producer. You can still have set Album Artist to the vocal artist if appropriate. For classical songs, the Artist field should be set to at least the orchestra. since you can make music with an orchestra (but no conductor), but not vice-versa. And the orchestra is most of the artist.

Album Artist
---
Album Artist is supposed to give the whole album a single artist, if >0 songs have >1 artist. If it's a Michael Jackson/J5 compilation,  tracks may have "Michael Jackson" or "Jackson 5" in Artist, so you can set Album Artist to "Michael Jackson". If it's a multi-artist compilation with no single artist prioritized, you might use "Various Artists". If you have doujin music, you might have tracks with artists estha, koutaq, Taishi from the doujin circle "XL Project". So you can set Album Artist to "XL Project". If the whole album has only 1 artist,  Album Artist is redundant so it [can be blank](http://wiki.hydrogenaud.io/index.php?title=Foobar2000:Encouraged_Tag_Standards).

Album
---
Name of the album. Disc number is not actually part of the album. So, "Sampled Volume 3 (Disc 2)" is wrong. It should be "Sampled Volume 3" . Putting Disc number in the album means different discs are different albums, and maybe different (nested) folders. If the disc has a meaningful title, you can use that for Album instead, and put the boxset name in Comments & Path/Folder.  You can use common abbreviations like "OST" for "Original Soundtrack" to shorten long Album fields.

For classical (unless it has a specially made title), you can choose a generic title using a combination of work + other information, but try to keep it close to the original.

Disc number
---
Number of the disc for a multi-disc release. Blank otherwise. Should be a number from 1-99. "1/1" is not a disc number. Use the Total Discs field (if your software supports it).

Track
---
Should be a number, like 01 or 1. Vinyl-style tracks like 1A, 1B, etc are apparently valid. But "1/12" is not a track. Use the Total Tracks field.

Genre
---
Ah, Genre. One of the most subjective fields. Your files may come pre-tagged with some info. You can leave it, or change it. For an album which has mainly vocal songs from anime, use "Anime". If it's a soundtrack from film/TV (including anime), use "Soundtrack". If it's a game soundtrack, use "Game". If VGM cover, you could use the cover style, like "Jazz". You can use "J-Pop" for j-pop, "J-Rock" might be taking it too far. Genre is meant for a single genre so try to choose one that represents the whole album. Or two at most. But I think "Hard House/Psy-Trance/Drum & Bass/Trance" is too long. Unless you want to tag the genre for individual songs.

Art
---
For lossless files like FLAC, do NOT include art, since it's annoying to re-tag since the entire may be rewritten (which is slow), and annoying to remove the bloat since removing art may not decrease file size. Your media player should be smart enough to find a "cover.jpg" in the folder.

For small lossy files like AAC, you can include art, and I also recommend that it's small. Like 75-150kb 512-1024px wide in JPEG or PNG.

Scans
---
Scans should be stored in a subfolder. Scan filenames should be descriptive and in a sensible order. Scans should be in a reasonable resolution, without visible compression artefacts. Moire is generally a fault of scanning at insufficient resolution, you should be scanning in at least 300-600dpi.

Minor tags
---

Comments
---
Anything else related to the song. Like maybe how it was sourced, but there might be other fields for this. There is a Catalog Number tag, but you could also store this & edition info in Comments.

Compilation
---
This one is a bit of an iTunes-ism, but if you set it to 1, it means Compilation. To stop iTunes splitting up compilations into multiple folders.

Composer
---
The full, common name of the composer. Like "Maurice Ravel", not "Joseph Maurice Ravel" or "Ravel".

Sort
---
I don't bother with these fields, and leave them blank

Rating
---
This isn't really a standardized thing across UIs. What I do, is use Comments to store a string of up to 5 asterisks (if I do it at all). But other people may not agree with your ratings.

Classical
---
For classical, it's more important to be consistent & include Composer & work than Album in Folder, so I suggest a different convention for  Folder: Composer_last_name - Work/Album, Orchestra/Conductor


- Tchaikovsky - Piano Concertos Nos. 1 and 3, Yablonsky
- Tchaikovsky - Pierre Monteux Conducts
- Tchaikovsky - Sixth Symphony, Dumka

Same conventions for filename apply. But the Title should be Work - Movement, 

- Piano Concerto No. 1 - Allegro non troppo
- Piano Concerto No. 1 - Andantino semplice
- Piano Concerto No. 1 - Allegro con fuoco
- Piano Concerto No. 3 - Allegro brillante
- Piano Concerto No. 3 - Andante
- Piano Concerto No. 3 - Allegro maestoso

If the work is already in Album like "Symphony No. 5", &/ using the work in Title is too long, you could go:

- I Andante-Allegro con anima
- II Andante cantabile, con alcuna licenze-Moderato con anima
- III Valse: Allegro moderato

Surround
---
For AC3 & DTS, Gazelle says tagging is "highly recommended", but the ONLY app that can R/W tags is foobar2000. Hence, I don't suggest tagging AC3/DTS.

Discs may have different streams with different channel layouts and maybe different mixes. Like "Audience mix" & "Stage mix". Definitely sort these into their own folder and label them in at least the Comments. For lossy codecs like AC3/DTS, also label the folder.

- Yoshimi Battles the Pink Robots AC3 20
- Yoshimi Battles the Pink Robots AC3 51
- Yoshimi Battles the Pink Robots 51

Tips
---
If you want to change the tags but don't want to change the files themselves, the [m-TAGS system](http://wiki.hydrogenaud.io/index.php?title=Foobar2000:Components_1.0/m-TAGS_component_%28foo_tags%29) gives you the illusion of doing do.

If you want to give tags to someone else without the hassle of agreeing on a txt or csv format & syntax, make dummy files with tags (like, 5s mp3s). Many tagging apps like Mp3tag support batch copying tags between files.

For tagging unknown audio, try musicbrainz picard or shazam

To preview different codepages, try notepad++. Then you can convert to UTF8. It seems that Japanese encoded with a Chinese codepage isn't uncommon.

Mp3tag can convert between filenames & tags, tag search & replace, and import/export text files.

Discogs & musicbrainz for sources, vgmdb for ACG music, and sites like touhouwiki for touhou music.

_how pitchshifting works
chord theory examples?
