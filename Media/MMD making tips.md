# MMD making tips

### Introduction

This is not a complete beginner's guide, rather a bunch of info & tips. And my views/preferences. Use [MikuMikuMoving](https://sites.google.com/site/mikumikumovingeng/home) instead of MikuMikuDance cuz it has a better workflow & tools. KFS & lipsync depend on MMM.

## How the system works

### Camera
You can set the FPS of the clip in MMD (menu) & MMM (File tab).

The camera XYZD is in MMD & MMM. The camera pivots about a point some distance D from the model, so a simple about X axis rotate (or YZ plane), needs a D and Y adjustment, too. In MMD, there are two sets of camera angle controls. One is for about a point, the other is for absolute, absolute is really a shortcut for about angle and absolute position, which is nice.

### Curve Interpolation
Interpolation curve is saved with VMD files. Curve interpolation works/makes sense if you select TWO keyframes and adjust the curve

### Files

Models are saved via reference in MPJ (MMM proj) files so that if you make a change to a model or accessory (X) file, these changes are reflected upon reopen. If you move a mpj (or model file), you will be prompted to reassociate them on reopen. This is nice so you can reorganize your files anytime.

## General tips

### Model

You can have wardrobe or prop changes to keep viewer interest. For >1 models, they should be from the same franchise & unit for visual cohesion & realism. Many free models have use/modification restrictions so try to follow those. There are some sandbox-type "girl simulators" like Koikatsu that allow you to make & modify girls with hundreds of sliders & export them. This allow for quick creation of HQ models with less restrictions. You can also buy models from sites like melonbooks.

If you're using edited models, make sure everything works as expected (morphs, bones, etc). Check body proportions & parts are realistic. You don't want to end up with "can't unsee" type of glitches after you've completed your video.

### Song

VBR MP3 does not sync well with MMM. Use CBR instead.

### Scenery

The scenery should complement, or at least not detract from the model.

### Motion

The motion should be smooth & realistic. Spline keyframes makes it better, but MMM makes it much easier to batch spline keyframes (aka curve interpolation). For videos with >1 models, it's very obvious when they're making exactly the same movements & timings (even if mirrored), it's so robotic. I recommend adding variation (even a simple delay) to the keyframes, or use [ApplyNoisePlugin](https://sorairo.pictures/3dcg/tools/). There is also a [RandomBlinkPlugin](http://t.co/jyNYVHUSzC).

### Camera

Camera should not be too close, or far. Same note about splining applies to camera. Camera cuts should be sharp and last 0 frames, not a few - it looks glitchy. Shots should last at least a few seconds, and there shouldn't be so many cuts that you can't appreciate each shot properly.

### Effects

There's nothing wrong with the default shader. Serious shader is okay. The Truecamera & Motionblur plugs make my iGPU lag really badly. If you add an effect and the result is unexpected, try reordering them. I have issue if you apply too many effects (bloom, HDR, etc) such that the midtones are gone, and too many post-production effects such that it's overproduced.

### KFS
Keyframes per second. MMD is hardlocked to 30 keyframes per sec. And it seems VMDs are 30fps as well. You can mostly disregard this issue you're mot adding/modifying keyframes.

MMM allows custom KFS. KFS is saved with mpj. Mpj uses last KFS by default for empty project. Screen cap FPS & output screen size is not saved with MPJ. KFS is saved with mvd. A mismatch between project & mvd/vmd KFS results in a conversion. For Low KFS (lower than display FPS), MMM can figure out if you want to do a camera cut, and cuts accordingly.

Why is a custom KFS important? Many videos are music-based, and music has a BPM which is usually unrelated to KFS. If you're doing copypasta for (short) loops repeatedly, you might need to do some fiddling with keyframes so that successive pastes don't drift out of time. Or you may be making tweaks to keyframes in general so that it looks on time. With custom KFS, you can have keyframes that snap to the beat, making good timing easier.

You will need to find the BPM of your song. We assume a constant BPM, songs >2010 usually are. I use Traktor Pro (actually a DJ app), but there are other solutions & sites like https://tunebat.com/ . Most importantly, the figure should be accurate as your whole project depends on this magic number. Divide BPM by 60 to get BPS, and times by 4 or 8 to get KFS such that it falls within 5-15 KFS. Set that as the project KFS.

### Lipsync
Lipsync is an option for a video, and usually tedious to do, but looks impressive. I present a less labor-intensive method, based on the [lipsyncloid](https://bowlroll.net/file/29218) plugin. It's fairly quick to do, even if you're making a low-effort "assemble elements & upload video" thing.

You can run lipsyncloid on the full song, but you'll have lips moving all the time, which is prolly not what you want. You need a vox stem for your song. If you don't have a ML separation thing installed, you can use a web version of spleeter like www.melody.ml , www.moises.ai , www.splitter.ai , www.ezstems.com , www.musicara.ml , or www.lalal.ai (their own ML). Should be faster if you pick the least stems (vox+I). The quality is quite mediocre but all we need is vaguely-accurate vox amplitudes.

I suggest you make a new project for vox & keyframe treatment, and it must be 30 KFS (since lipsyncloid assumes 30, timing will be off otherwise). Import your vox into this new project along with a model, and run lipsyncloid. It seems that correct vowel detection is rubbish (unless maybe it's vocaloid with no modulation). You can now convert KFS to match your main project KFS, you can save multiple versions of this vox project.

If you have multiple singers, you can have multiple dummy models, and copy/delete keyframes as appropriate. It's maybe helpful to move faces impossibly close together such that their lips are close, like the cover of Queen's [The Miracle](https://upload.wikimedia.org/wikipedia/en/e/e3/Queen_The_Miracle.png)

The raw output of lipsyncloid is likely jittery, so you can reduce the KFS. For my project using a custom KFS, 9 KFS was the best compromise between responsiveness & smoothness. 6 KFS looks smooth, but lip openings/closes are too slow. If you're using the default 30 KFS (or another KFS), reduce the KFS to a factor. You can change/convert KFS multiple times to smooth lip movements, but to finally match your main project KFS. Export as mvd to keep KFS info.

### Video
Video fps should be 30 (rounded NTSC) or 50 (double PAL). <30 is too jerky, and 60 won't look much smoother but it'll take longer to encode. Arbitrary fps may cause compatibility or visual issues.

The aim is to produce quality encodes, with a decent filesize, in a reasonable time. I suggest using the "slower" & no tune , or "slow" & animation tune in x264 for encoding, no other options. CRF 18-16 (CRF = unpredictable filesize, but constant visual quality).

There are guides which recommend many custom options, but they won't explain why it's useful. The problem with increasing settings is slower encodes & diminishing returns, and some of those options aren't actually helpful. You can't go wrong with options close to defaults.
