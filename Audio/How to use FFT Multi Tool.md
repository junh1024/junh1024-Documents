# How to use FFT Multi Tool

Introduction
---
FFT Multi Tool can be used to remove sounds from a main audio. Using FFT, it still works when tracks are slightly misaligned. But it still works the best when tracks are aligned as much as possible. REAPER supports up to 64ch so FFTMT works on 4ch directly (dual stereo), so you need only 2 tracks to work it. There are VSTs to do this job, but most other DAWs are limited to only stereo/2ch, so you need 6 tracks with complex & awkward routing.

![img](https://i.imgur.com/3XkpIoe.png)

Instructions
---
0. Install REAPER DAW (  www.reaper.fm ). REAPER is available as a 2147483647 day trial, which should be plenty for our purposes.

1. Extract ALL of [this zip](https://github.com/junh1024/Reaper-Surround/archive/master.zip) into your Reaper EFFECTS folder. 

- REAPER/Installdata/Effects (for normal install)
- REAPER/Effects (for portable install)

2. Open a template in REAPER , it will prompt to choose your full mix & subtractand.
- [default template](https://cdn.discordapp.com/attachments/397574988657328132/749033717888057374/FFTMT_L_subtract_template.rpp)
- [stronger template](https://cdn.discordapp.com/attachments/439994725622087681/736031090917244958/FFTMT_Subtr_Greatest_Genie-20a.RPP_S.RPP)

3. Right-click on the top clip and item properties > uncheck "preserve pitch when changing rate". OK. Repeat for the bottom clip.

4. Zoom in at the start using mousewheel & drag to align tracks. Zoom in at the end. Check if they are still aligned at the end. If they are, skip to step 8. 

5. Zoom in at the start & trim the bottom clip to a reference transient by dragging the handle at the left edge. Zoom in at the end and trim the bottom clip to another reference transient.

6. Alt-drag the clip edge at the right end to strech-align the bottom transient with the corresponding transient at the top clip. Repeat steps 4-6 until they're aligned to satisfaction.

7. Un-trim the bottom clip.

8. Press Play & adjust FFT MT settings.

9. File > Render to export. File > Save Project.

Benefits:
---
- REAPER supports mp3, FLAC, vorbis, etc. Not just WAV
- don't pre align, align using the REAPER GUI with precise stretching
- adjust & hear the results in realtime, not 1 minute later
- fast workflow
- generic algorithm with small additions & tunings
