# How to use FFT Multi Tool

Introduction
---
FFT Multi Tool can be used to remove sounds from a main audio. Using FFT, it still works when tracks are slightly misaligned. REAPER supports up to 64ch so FFTMT works on 4ch directly (dual stereo), so you need only 2 tracks to work it. There are VSTs to do this job, but most other DAWs are limited to only stereo/2ch, so you need 6 tracks with complex & awkward routing.

Instructions
---
0. Install REAPER DAW (  www.reaper.fm ). 

1. Extract ALL of [this zip](https://github.com/junh1024/Reaper-Surround/archive/master.zip) into your Reaper EFFECTS folder. 

- REAPER/Installdata/Effects (for normal install)
- REAPER/Effects (for portable install)

2. Open [this template](https://cdn.discordapp.com/attachments/397574988657328132/749033717888057374/FFTMT_L_subtract_template.rpp) in REAPER , it will prompt to choose your full mix & subtractand.


3. Zoom in using mousewheel & align tracks.

4. Play & adjust FFT MT settings

5. File > Render to export.

Benefits:

- REAPER supports mp3, FLAC, vorbis, etc. Not just WAV
- don't pre align, align using the REAPER GUI
- adjust & hear the results in realtime, not 1 minute later
- fast workflow
- generic algorithm with small additions & tunings

![img](https://i.imgur.com/3XkpIoe.png)