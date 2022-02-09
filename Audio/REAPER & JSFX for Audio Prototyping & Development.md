# REAPER & JSFX for Audio Prototyping & Development

Introduction
---
I am here to discuss [REAPER](https://www.reaper.fm) & [JSFX](https://www.reaper.fm/sdk/js/js.php) for (rapid) Audio Prototyping & Development. We compare with developing a C++ VST or a app in python.

JSFX = Jeusonic audio effect. The preferred way to run/develop JSFX is in REAPER & optionally a text editor like Notepad++. REAPER is a shareware DAW, but the trial period is infinite, with nag screens. REAPER supports many popular audio codecs, such as WAV, FLAC, mp3, vorbis, & the DAW itself scriptable via the ReaScript API.

JSFX are simple source/text files, which behave somewhat like VST (in a compatible environment). They're automatically compiled when they're loaded. JSFX uses the jsfx file extension, but others can/have been used. JSFX is designed for realtime, algorithmic, audio effects that generate/modify audio/MIDI and optionally display graphics. It is not for ML where you can get quick results without knowing audio DSP.

Advantages
---

### Fast development

- Don't waste time decoding compressed audio (python). It's provided by your DAW/wrapper (in this case, REAPER). When you write JSFX, you already have PCM samples.
- Don't waste time researching libraries. JSFX provides much of what you need for audio DSP & gfx.
- Over 200 included JSFX examples with REAPER, with [more FX](https://stash.reaper.fm/tag/JS-Effects) online, and even external [JSFX libraries](http://ajaxsoundstudio.com/software/cookdsp/) . Included JSFX are in REAPER/Effects if you do a portable install.
- [Developer help forum](https://forum.cockos.com/forumdisplay.php?f=3) . Please search before posting.
- Quickly reload JSFX (takes 1s, instead of 1min to compile a C++ VST, just press edit: reset)
- View the value of variables (but not arrays) in REAPER's JSFX IDE

### Included features

- [Basic math](https://www.reaper.fm/sdk/js/basiccode.php), trig, flow control, and FFT functions available
- Inter-effect communication via gmem or regXX 
- Up to 64ch & PDC support
- Small footprint: REAPER, a bunch of JSFX & Notepad++ takes only 100mb. Python + libraries will take up 200mb+, similar for C++ + libraries + VST SDK.

### User interaction

- Quickly make slider & menu controls
- Easy to link sliders & menus to variables
- [Graphics functions](https://www.reaper.fm/sdk/js/gfx.php#js_gfx) to draw 2D primitives like dots, lines, rectangles, circles, characters, strings.
- None of this pen-swapping rubbish (ahem Qt) just to change a color. Set RGB directly & it will be used the next gfx call.


Disadvantages
---

### General

- Runtimes (REAPER/ReaJS) are not open-source, unless you transpile to C++
- Limited ways of running it (see below)
- REAPER has only 1 global transport per project (like most other DAWs), so if you want 2 play decks for a DJ app, it's going to get quite hacky
- Getting the whole FFT pipeline to work can be tricky, slightly less friendly than numpy/scipy. You need a template. See [help threads](https://forum.cockos.com/showthread.php?t=238800#6).

### Syntax

- JSFX code of others is not always easy to understand
- JSFX language is simple, no complex stuff like reflection
- One global array per instance (of 8 million slots). Aliasing & overwriting if you're not careful
- Conditional, loop, and bracket syntax is slightly different to C
- Because it's compiled, syntax errors must be fixed before it's run, not as it's encountered (python)

### Development

- JSFX is slightly slow (10-50% speed of C++, but better than 1-10% of python)
- You can't do "printf debugging" like python, but you can view variables (as above), or use file/gfx functions.
- GFX calls might be a bit verbose but you can functionalize this


Running JSFX
---

### Windows:

- Using REAPER natively
- Transpiling to VST2 using [Geep-Jeez](https://github.com/derekjohnevans/Geep-Jeez)
- Using the [ReaJS VST2](https://www.reaper.fm/reaplugs)
- Using the [YSFX VST3 host](https://github.com/jpcima/ysfx)
### Mac/Linux:

- Using REAPER natively
- Using REAPER on Wine
- Using the [YSFX VST3/AU host](https://github.com/jpcima/ysfx)

If you're using REAPER for VST development (not JSFX), that's fine too, cuz it provides features helpful for developers like CPU & PDC figures for individual FX, CPU per track, and and overall CPU & RAM usage.

Alternatives
---
- [iPlug2](https://github.com/iplug2/iplug2) or [JUCE](https://juce.com/) for C++
- [Pyinstaller](https://www.pyinstaller.org/) can turn python into executeables. Works with PyQt4
- [Cycling74 Max](https://cycling74.com/products/max) $59 academic subscription
- [Blue Cat Audio Plug'n Script/Angelscript](https://www.bluecataudio.com/Products/Product_PlugNScript/) $99
- [DSP Robotics flowstone](http://www.dsprobotics.com/flowstone.html) $99