## Studio One

## S1 Improvements

## Introduction

THIS DOCUMENT IS SUBJECT TO UPDATES AT ANY TIME

These issues affect almost ALL users that use Dolby Atmos in S1. If you don't make these changes, people, especially rookies, will make subotimal mixes.

Dolby Atmos was originally conceived in 2012 as a Theatrical-only, and professional-only system, and the defaults & concepts are geared towards that. However, 10 years later, we have a whole new generation of music mixers exposed to a complex system that's not geared towards their expectations and needs. Hence these improvements & new defaults are much needed to quickly help rookies to seamlessly make better DA mixes *by default without further action on their part*.


### Avoiding the 7.1.2 Bed trap with a proper 7.1.4 bed

A 7.1.2 bed is the default bed in S1. The way that 7.1.2 is implemented in S1 gives the illusion to rookies, that all height area is available and there are no consequences, since you can smoothly raise and pan around with a 7.1.2 bed, when the reality is far from the case. A 7.1.2 bed is bad because it has precedence & correlation effects when downmixed. It also cuts the available 3D area in half !

![pic](https://i.imgur.com/eQcHrnD.png) . 

Over-use of the 7.1.2 bed, is evident, even in the Dolby Atmos tutorial project (where most tracks are assigned to a 7.1.2 bed with all its faults), which goes to show it's a trap, even for professionals!

But Although it's possible to have 7.1.4 track in S1, unfortunately, it's collapsed to a 7.1.2 bed when routed to master, defeating the purpose. Advertising 7.1.4 OpenAir HDIRs, but no way of using them properly in 7.1.4, in a Dolby Atmos project, is a sore point.

A 7.1.4 bed can be implemented as a 7.1 bed + 4 objects internally to conform to DA primitives.

So, if you implement a 7.1.4 bed properly, and set that as a default, then rookies (& professionals) can make better mixes by default since it's a reasonable fallback if they forget to use objects. If it's not possible, please default to a 7.1 bed instead.

See also my issue  https://answers.presonus.com/79876/improved-dolby-atmos-defaults-rookies-avoiding-default-object 

### Panner new Defaults

1. Spatial object could also be the default for rookies in DA mode to avoid the 7.1.2 bed trap.
2. LFE send should be off by default, and the LFE send level should be -10 by default. This is because the LFE "is designed to be amplified by 10 dB on playback" due to [Bass management](https://en.wikipedia.org/wiki/Bass_management)

### S1 Downmix and Trim UI

1. Although manual trimming is activated separately for different layouts, every layout is available on the same page in Nuendo.

![Trim and Downmix Editor in Cubase](https://steinberg.help/cubase_pro/v12/en/cubase_nuendo/trans_picts/surround_sound/surround_sound_adm_authoring_trim_and_downmix_editor.png)

However, in S1, since different layouts are on different tabs in S1, it would make sense to, when Manual Trimming is activated for 1 layout, to activate it for ALL layouts in S1, to reduce clicks.

2. Also, unless "Manual Trimming" is deactivated, the trims show 0dB, which is potentially deceptive, since 0dB is not the default, and is not necessarily what's being applied. When "Manual Trimming" is deactivated, it should show the actual trims being applied (likely the defaults of -3 to -1.5 or so).

### S1 Downmix and Trim new defaults

1. All downmix trims should default to 0dB by default for rookies. Dolby recommends this: "For music use cases, we recommend setting trim controls to zero so that your mix is preserved when played back as a 5.1 or 7.1 re-render." 

https://professionalsupport.dolby.com/s/article/What-renderer-settings-are-recommended-for-Atmos-music?language=en_US

2. Direct render should be the default 5.1 downmix. The Dolby Atmos music delivery specification says that "All deliverables SHOULD use a 5.1 and 5.1.x downmix setting of “Direct Render”

https://dolby.my.salesforce.com/sfc/p/#700000009YuG/a/4u000000lFJ9/IVkxI54tPvDbGymtjQ6tyIjEvkaA7xPa_Byq6.vH_dA

### ReaJS VST2 Surround support

Currently, [ReaJS](https://www.reaper.fm/reaplugs/) , (as part of the Reaplugs suite ) , is capable of up to 64ch surround/multichannel support if configured as such, but is limited to only 2ch output in S1. ReaJS surround output already works in Resolve and Nuendo.

**Steps to reproduce:**

1. Download & install [Reaplugs](https://www.reaper.fm/reaplugs/reaplugs236_x64-install.exe) , which includes ReaJS
2. Download this [ini file](https://github.com/junh1024/Reaper-Surround/releases/download/0.2105/reajs.ini) , open your Reaplugs folder, and put reajs.ini next to reaJS.dll . This configures reaJS for 8 channels.
3. Add reaJS VST as an effect on a 7.1 track
4. Open the FX router. The router only shows ReaJS as stereo FX, regardless of the fact that ReaJS is configured for 8ch in the ini. You can try changing the inputs/outputs channels up to 16 in the ini.
5. This is a minimum configuation that tests FX IO routing, not audio. We'll assume that surround audio works after FX IO routing is recognized as surround.

It would be nice for S1 to recognize ReaJS as a surround FX, as Resolve and Nuendo already do so.

### General imports

Despite S1 supporting FLAC files, they're also converted to 32-bit WAV due to resampling to 48k when placed in a 48k project, defeating the purpose of FLAC files. It would be nice if S1 supported on the fly resample of files, like REAPER & Nuendo.

## Bugs

### ADM import

1. Studio One Imports ADM as 32-bit WAV even when the ADM spec is limited to 24 bit, which is wasteful. Nuendo imports ADM as 24bit WAV.

2. S1 errors when importing ADM files with coordinates below ear-level, despite it being completely valid according to the Dolby ADM spec. 

"The Z coordinate position shall have a value in
[-1,1]."

https://developer.dolby.com/globalassets/documentation/technology/dolby_atmos_master_adm_profile_v1.0.pdf

Generous behaviour would be to allow such files, and allow typing in negative elevations manually (so that Z is preserved), but not allow negative elevations dragging the numbers & typing.

Or just clamp the Z value to >=0 when importing. 

Resolve can create file with -Z, and Nuendo imports files with -Z.

CAnnot import files with no bed - make a default stereo bed?

### 916 layout

9.1.6 order is wrong in S1 and doesn't conform to Dolby conventions (at least, the output of the renderer).
- It is currently: L, R, C, LFE, Lw, Rw, Ls, Rs, Lrs, Rrs, Ltf, Rtf, Ltm, Rtm, Ltr, Rtr
- It should be like: L, R, C, LFE, Ls, Rs, Lrs, Rrs, Lw, Rw, Ltf, Rtf, Ltm, Rtm, Ltr, Rtr

See [Dolby document](https://developer.dolby.com/globalassets/technology/atmos/additional-channels-for-immersive-audio.pdf) p4 
