# How to encode EC3 Atmos using Amazon

Introduction
---
I would've liked a web service where you can encode DTS-X for a reasonable price/min. And I would pay for it. But for now, EC3 Atmos is available. EC3 Atmos is lossy, unlike THD Atmos on BDs. But it seemingly uses more objects by default (16 vs 12). This guide covers audio-only encoding with a focus on music. Much of the inbuilt help is "set the value for $setting" which is VERY HELPFUL, so I've done some research & provided some suggestions, rationale, and practical advice.

Instructions
---
1. Sign up for a [Amazon web account](https://aws.amazon.com/) , this is different to a regular shopping account.
2. Setup a [default mediaconvert role](https://docs.aws.amazon.com/mediaconvert/latest/ug/iam-role.html)
3. Select your region. Regions are separate & different from each other and may have [pricing differences](https://aws.amazon.com/mediaconvert/pricing/).
4. Make a S3 bucket. Mediaconvert export can only use S3. Codecommit doesn't seem to be usable for mediaconvert input. You get some S3 storage for the 1st year, and you pay after that. An incentive to use it quickly & store minimally.
5. Mix your music in 3D however you like. Surround, OBA, SPS are preferred. Ambisonics is dispreferred due to low separation. There is a "15.1 Ambisonics decoder.txt" for fuma in my suite. If you're using [**my suite**](https://github.com/junh1024/Reaper-Surround#introduction), use:
- mono: "1.0 to 15.1 Panner GUI (L).txt"
- stereo: [parent channels](http://d2zjg0qo565n2.cloudfront.net/sites/default/files/focusrite/Screen%20Shot%202015-06-10%20at%2014.42.00.png) . [See here](https://github.com/junh1024/Reaper-Surround#introduction-to-151) for the channel specifications and [**see here**](https://github.com/junh1024/junh1024-Documents/blob/master/Audio/Surround/Instrument%20placement%20in%20surround.md#center) for where to place instruments in surround. 
5. Target -18LUFS. [More info](https://musicsupport.dolby.com/support/home) .  You can use "15.1 to 5.1 Downmix (M).txt" and then 5.1 LUFS measurement software like Izotope Insight.
7. Export your mix as 16ch WAV for [these specifications](https://docs.aws.amazon.com/mediaconvert/latest/ug/using-dolby-atmos-encoding.html#proc-atmos-single-input-file). 48k/16b is recommended, there is little in practice that is worth much more than 16b. <16ch & WV will not work. A 916 mode is now included in "15.1 to 3D Downmix (M).txt" . If you have strong side/back, It is suggested to move the side 20-33% forward (this ability is included in the previous tool), sice the Amazon encoder makes EC3 with a 51 legacy presentation which downmixes side & back directly to back of 51, and hence may overload them. It's possible to encode Atmos EC3 with a legacy 71 presentation but prolly with older Atmos software. You content WILL be heard on 51/51x systems so you need to cater for this aspect. If you want a 16 channel test, [here is a numbered callout](https://cdn.discordapp.com/attachments/380573049893814272/790491016994095114/GVR_16ch.zip) 41" long.
8. Create a new job in mediaconvert. Remove video selector. Add a Output file group. Select the output format, remove video. Select the DD+JOC codec.
9. Select settings:
- Bitrate. Suggestions for active channels (on average), such that you get about 50kps/channel:
	- 384 kps for 7.1, 18khz cutoff
	- 448 kps for 9.1, 20kco
	- 576 kps for 11.1 (this bitrate may be available in the future)
	- 640 kps for 13.1
	- VBR isn't available so if you want faux-VBR, you could separately encode different parts at different bitrates. BUT see note about dialnorm later. I haven't checked this.
- Surround EX mode: Off. You shouldn't be matrixing a BC anyway.
- Stereo downmix: Stereo. You should be checking in stereo and some material may sound worse with DPL2. Surround downmix is almost guaranteed to sound worse due to polarity cancellation. Unless you QC with DPL2 and it sounds better or if in doubt, choose stereo.
- LT&RT, Lo&Ro surround: -1.5dB. Again, you should be checking in stereo. I use full surround levels when doing mixdown. If your stuff needs -3dB or lower surrounds on downmix, your back levels are prolly too high.
10. Amazon says Dynamic range compression line & RF relates to peak & main levels for DRC. But [wiki](https://en.wikipedia.org/wiki/Dolby_Digital_Plus#Dynamic_range_compression) says it relates to the type of listening environment. I like the wiki explanations better.
- Music:
	- Dynamic range compression line & RF: Off, aka don't mess with my music. [See this](http://www.minnetonkaaudio.com/info/PDFs/DolbyDigital_Guidelines.pdf) for coefficients . It has a gentle ratio above a low threshold.
	- Dialogue intelligence: Off. The algo measures vocal speech levels in C & sets the volume of the program based on that. But the vocal-music balance btw program and music is different, and in music there isn't always vox so it's suggested to have this off for music.
- Program:
	- Dynamic range compression line & RF: Film light. It has a harsh ratio for loud sounds.
	- Dialogue intelligence: On. The algo can't distinguish btw speech & speech+SFX, so loudness may differ by 4.5dB depending on how you mix. [Further reading](https://www.pro-tools-expert.com/home-page/2018/11/10/is-dolby-dialog-intelligence-still-fit-for-purpose-for-netflix-to-use-for-speech-gating) . 
	
11. - Note about dialnorm: dialnorm is always on, you can't turn this off. The way it's intended to work, is that the Dolby encoder measures the loudness of the program and stores metadata in the bitstream about how much to adjust the volume of playback. The reference is -31 and means no adjustment. If you mix at -18 LUFS like I do, this might result in a dialnorm of -21, so the adjustment is -10dB. This is all well & good. But the problem is when you mix content with manually adjusted dialnorm or no dialnorm at all (like FLAC or DTS). So your stream with dialnorm will suddenly sound quiet, as dialnorm target of -31 seems to be for film levels. Also, if you encode something in parts, it may have different dialnorm values, leading to different loudness (bad).
- eac3to can remove dialnorm, but this will probably result in a large volume boost. [This tool](https://forum.doom9.org/showthread.php?p=1933603#post1933603) can tweak ec3 dialnorm. I've not tested on Atmos. Customers will still need to adjust volume within at least a 10dB range. AFAIK "Dialogue intelligence" influences whether dialog in C influences this measurement. For the moment, I'll suggest keeping dialnorm on as your Atmos file will be played with other Dolby content, which will also have dialnorm. But the situation may change.
12. Create the job. Jobs usually run 2-4x realtime.
12. Download your finished job from your S3 bucket.
13. Mux to mkv, m2ts, or mp4. Optionally, add a video.
14. QC your mix. There's no Atmos decoder for PC so you need to QC on an AVR or use files prior to step 8.
15. Set your billing currency. Amazon issues monthly bills.
16. Duplicate your job for the next run. Remember to set the appropriate bitrate.