# AMV Making Notes

## Introduction

## MJ AMV
Original was a nod to thriller https://www.youtube.com/watch?v=tQ7wzh1gRiI , this https://www.youtube.com/watch?v=1UlIRmWnhCc wasn't made that well IMO so I redid it.
At the time I was making my MJ AMV, I watched several thriller dance videos on YT. To my disappointment, the dance wasn't as in time with the music as I imagined, so I edited sonico's dance to be more in time than the original. I think it shows.


## Oreimo 2e14

I got the idea for this project since I felt this scene was a bit lacking in impact & I had some candidates for music replacement. The main idea was Pokémon - tears after the cloudy weather. I need to use the movie 20th remix since it's the longest. I tried a simple sync, and a slow 5%, and speed up video to 25fps but the scene was about 20s too long. So it needs editing. I considered a few workflows from avisynth/VAPpoursynth un-resizing, hardsubbing to lossless so I can edit with Sony VEGAs, etc. But then I tried mkvmerge MMG and the edits were about what I wanted. I needed to convert the audio to wavpack before (since FLAC is bad with mkv & cuts), and re-encoding to FLAC afterwards (to fix the audio timestamps). I cut a few lines after the flashback, resuming with "so, this is what you wanted", and some crying at the end. Now, the almost all the song covers the scene. I also had an idea with the last track from the end of evangelion OST, but it's too short at 1'11", too repetitive, and the 4/5ths intervals + slight dissonance gives off an awkward/hostile feeling which is undesired. But I did find the "Flow of emptiness" a worthy candidate at 6'15". It can be edited down but it's tricky since it's long and has long sections. I did manage an edit of that in the end. I need to separate the dialog from the music. So I originally thought of using DNR utils. But if I use spleeter 5 stems I can still get 3 stems of piano, dialog, and ripping SFX. But Ruri 's crying leaks into other stems. Then I realize 2 stems is enough since during the ripping shot there's no music. Spleeter 2 stems is better.

```
timecodes to cut for MMG
00:05:41,00:07:14,00:07:29,00:07:58,00:08:08,00:08:18
```

It's a sad day when I need to use a commercial encoder to encode HQ HE-AAC 3.0, since fdk & qaac can't.


Since there were several cuts in mkvmerge. Some lines were missing in the subtitles. I had to manually re-insert them in aegissub. I also had to manually un-karaoke some moving signs because I was targeting srt for delivery. I'm choosing SRT since it's more compatible and simple.
I realise that the video audio & subtitle projects are all running at different fps so I need to decide on a fixed length that's the video will end, and then everything else will follow. I need to end on a full second because 25 is not divisible by 2.
I denoise & deband the video but it wasn't particularly effective and it killed details so I left it unfiltered from my doki source. Maybe I need a 10 bit display to see the difference. 
It's also worth noting that for all 3 soundtracks, they are all coincidentally in A minor at the end. For the passage of emptiness in evangelion, perhaps this was necessary since A is the lowest key in the piano, so you can create a dark and sombre sound. There is some piano leakage to the rear speakers so I add some manual automation to turn it down during the mainly piano sections.

If you try to put This in the full episode it won't work since the video and audio were specially edited for each other.

The Pokemon bgm might reflect the overall scene better. The evangelion might reflect her inner turmoil   better and the timing of the music is more impressive. I can do this since the original is 6min and offers many variations and intensities I can experiment with.
