# How to capture VHS with VirtualDub

## Introduction
This guide is intended to be a AIO guide which covers a reasonable amount of issues & knowledge. This guide is written in 2021 & collects my knowledge & online resources for a few years experience capping VHS. It's not meant to be a highest-quality lossless workflow, but a reasonable medium-high quality for archiving/playback. This guide assumes windows.

## Hardware

### USB Capture stick

It's popular to have HDMI capture devices for your PS6 or XBS1X so you might get a composite to HDMI converter. But also not ideal since I'm not confident about its handling of interlacing & you'll make bigger files since it's upcaled to HD.

I recommend [Hauppauge USB Live 2](https://www.hauppauge.com/pages/products/data_usblive2.html) . It does interlaced output which is correct for analog sources. There are [other products](https://www.linuxtv.org/wiki/index.php/Conexant_CX2310x) with the same Conexant 2310 chip. Be careful when buying USB capsticks. I had a counterfeit version of EasyCAP, it doesn't handle interlacing correctly, and has no built-in audio output.

### VCR Machine

I recommend Japanese VHS decks. I have a few Panasonics. I mainly cap 80s & 90s home videos which are mono. I get a few which are stereo which are newer or professional recordings. You can't tell which tapes are stereo, until you put it in a stereo VCR. So it's suggested to buy 1 Hi-Fi stereo VCR (it will have L & R audio ports). Some tapes have mono audio which sound better on certain VCRs. So it's suggested to get a 2nd VCR which is mono of a different brand.

If you plan on capping PAL & NTSC tapes, you need to get a multi-system VCR. NTSC tapes have [better audio quality](https://en.wikipedia.org/wiki/VHS#Original_linear_audio_system) than PAL tapes since NTSC tapes run faster. NTSC has 10khz co, and PAL 8khz co.

If you want to go a step up, get a SVHS deck. But those are expensive & rare. For stabilizing the picture, stabilizers and TBCs are available , but again, more cost. https://anarchivism.org/w/How_to_Rip_VHS#Digital_Video_Stabilizers

### Computer

You will need at least a 2.4ghz dual-core CPU for smooth x264 encoding. It is recommend to have a minimal of other programs running while you capture as they can use CPU & interfere with timing.

### Software

Ulead VideoStudio SE DVD came with my EasyCAP (bundled commercial software). It can do directshow recording to MPEG-2. Make sure to set a high bitrate of 6000-8000kps VBR. Use PCM audio. Audio levels are fine.

VirtualDub is free software. It somehow doesn't do Directshow on my capstick, so you need to use WDM instead. With WDM, Audio levels are so loud so you need to set it very low & might clip. But it can do HQ H264 with x264 VFW.

### Cleaning
A fast way to clean a VHS is to FFWD & rewind the tape to loosen the mould (could do this on a spare/no-picture VCR). You can open the top swing cover and empty out the dried mould into a bin if you wish. DO NOT open a VHS case to clean heavy mould. Mould is usually benign, but can sometimes be life-threatening.

You can open a VCR to clean the mould, wear a mask if you wish. There is the big slanted video head and the audio head to the right. 70% ethanol is available at pharmacies. Grab a Q-tip or small cloth, apply some ethanol, and hold it while spinning the head (move a Q-tip up & down for greater coverage). It's suggested not to clean the head(s) if you're not having any problems. This method works, but might not be the best method/chemicals. Don't clean the sticky gooey grease on other mechanisms, they are part of proper operation.

### Setup
Connect the VCR to the capstick using 3 RCA cables. Hi-Fi stereo tapes have higher levels, which will clip, so it's recommended to use PC line-in for those tapes, which have lower levels. You will need a RCA > 3.5mm cable for that.

## Method
1. Download & install drivers for your capstick
2. Download & install [Virtualdub 32b](http://virtualdub.sourceforge.net/) . VirtualDub2 has a native x264 plugin, so potentially no need for 0 latency (see later), but I haven't tried this.
3. Download & install [x264 VFW](https://sourceforge.net/projects/x264vfw/)
4. In the Windows Sound control panel, click on the capstick, or line in audio. Then press [set Default] . This will be the chosen audio for WDM capture.
5. In VirtualDub, File > Capture AVI, and Device > WDM (if vdub freezes replug the USB capstick & restart vdub)
6. Video > Compression > x264 VFW > configure
- [v] Zero Latency (VirtualDub expects this, otherwise we'll get sync issues)
- ABR 6000-8000kps or CRF 21
- Preset: Faster (we'll change this later)
- Extra CLI: --tff --threads 4 (tff = top field 1st interlaced. Set threads equal to 2-4 depending on how many logical cores you have. Don't set higher than 4 as it reduces quality for SD. You must set at least tff for correct interlaced handling in x264.)
7. Video > Custom format > 720 x 576 (or x480 for NTSC)
8. Audio > Compression > PCM
9. Capture > Settings > 25 (or 29.97 for NTSC)
10. Capture > Timing
- [v] Drop frames when...
- [v] Insert null frames...
- Null frame burst limit: 100 (you will need >10 in the general case since tape borks take up more than 10 frames, so it will desync unless you set >10)
- (o) Sync audio to video (I have tried sync video to audio before but that didn't work)
- [] Correct video timing, [] Automatically disable resync
- Audio latency (o) fixed 0ms (since 0 latency was enabled in x264)
11. File > Set capture file (you will need to do this every Vdub launch). Capture > v Autoincrement filename after capture.
12. Capture > Capture video. Wait until Resample is stable <+-0.1st, otherwise you may hear pitching in the file. May take 1-2mins. Then play your tape. Ideally we can see people speaking (we're doing a test capture). In the Windows Sound control panel > $DEVICE > Properties > Listen > [v] Listen, and > Levels. Adjust levels until the peaks average -10 in vdub. For me this was 2-20%. You can adjust the listening level in Volume Mixer.
13. Monitor CPU usage in task manager > performance (ctrl-shift-esc). It should not exceed 50% total too much for a SMT CPU or 80% for a non-SMT CPU.
14. Capture > stop capture after 30s or software. If your CPU goes lower than the previous thresholds, use a slower preset, but no slower than Medium (slower preset is prolly not useful for VHS) and Return to step 12.
15. Play the captured AVI back. Mouthes should be in sync. If not, experiment timing settings in step 10.
16. For next capture session (after you close FFMPEG), the settings are saved, and you can just enter capture mode, set filename, & capture.
17. Unplug the capstick since it tends to get warm.
18. This completes our steps for WDM capture in vdub.

## Filtering
The next phase is to make a smaller, filtered file. This tpoic will not be covered too much here. Crop a bit, but not too much. Many guides on the internet recommend yadif for deinterlacing, but it often produces weird artefacts. You could use w3fdif in FFMPEG, or QTGMC("fast",edithreads=2,Sharpness=0.0,fpsdivisor=2) in avisynth/vaporsynth. Optionally, sourcematch=2,lossless=2.

## Troubleshooting

### Muffled audio
Try FFW & RWD tape. Or try it in a different VCR.

### Snapped tape
If you have a snapped tape, basically just tape it back together with sellotape. [This tutorial](https://www.youtube.com/watch?v=clQSFl_qzao) suggests to tape the underside of the tape, but in my case, this was impossibru cuz the tape was snapped off the spool at the end. Could tape the top & bottom side of the tape but apparently this is bad for the head. The tricky part for me was to re-thread the tape back, before closing the case again. Consult internet pictures for how a VHS should look in its proper state.

### Case swap
In case you have a VHS case that is in a bad condition, you need to do a case swap. See [this tutorial](https://www.youtube.com/watch?v=4k7tOVwhqgE)

### Sync
I have found the settings above to produce in-sync audio. Clock drift is an [inherent part](https://www.gearslutz.com/board/newbie-audio-engineering-production-question-zone/1131487-drifting-clocks-i-think-how-sync-them.html) of using 2 different clocks (in our case, video & audio clock). If you have made captures with bad settings, you need to fix sync.

1. Open the avi in VLC and press jk to adjust audio delay, or mpv and ctrl & +- . You can then remux with a constant delay in FFMPEG. Example command with -200ms audio delay (also reduces audio to mono): ffmpeg -i "video.avi" -c:v copy -c:a pcm_s16le -af "pan=mono|c0=c0,atrim=start=0.2,asetpts=PTS-STARTPTS" video_out.avi" . Play the video.
2. If the audio is still not in sync, then there is a rate difference. In vdub > frame rate: (o) Change so video and audio durations match. In my case, the FPS was set to 24.998 . Play the video.
3. If the audio is still not in sync, you will need to recap.

## Thanks
To ST, reddit, and anyone on the internet that has written anything on VHS.
