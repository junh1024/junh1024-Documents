# Anime Upmixes Mixing Notes

## Beautiful Sentance

## Kibouu no Tsubomi
I was introduced to this song by someone who said it was an epic song. It's a fast and high-energy song similar to beautiful sentence from Trinity Seven. There were few things that I wanted to do with this song. 1. Slow it down because it's too fast and 2. add more vocal Harmony in the chorus since I think it's a composition error. There is also no instrumental available. All of these things are simple in isolation but combined, pose issues. Adding vocal harmony in the chorus is simple. All that was needed is to add a pitch shifter to the rear channels after surround up-mixing and add automation.  There is no instrumental to help make a surround version but there are multiple vocal versions.

For these type of projects where I want to slow it Down I usually use varispeed to slow it down first then use digital pitch shifting afterwards. A side chain was created by subtracting both vocal versions leaving behind vocals of both. Initially I tried subtracting the side chain from the main using FFT to to separate the song into instrumental and vocals then pitch-shifting later. This works but I later found out that it makes lots of artefacts due to different decision making in the pitch shifter in the instrumental vs the vocals. I then moved the pitch-shifting to before separation and that resulted in much less artefacts and a more punchier instrumental. I also applied some linear EQ to the instrumental to carve out a bit of space for the vocals and restore some high frequencies due to pitch shifting.

There was some drum and piano leaking into the vocals and rear speakers so I used spleeter to make those stems. spleeter also made a vocal stem but that turned out worse than my own FFT efforts. 