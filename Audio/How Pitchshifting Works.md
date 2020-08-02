# How Pitchshifting Works

Good, modern pitchshifters are complex beasts that use a combination of time & frequency domain manipulations to achieve a convincing quality, like the standard Elastique by zplane.

Varispeed
---
The simplest way to change pitch. But also changes time. Seemingly not useful if you want to fix one, but keep this in mind.

Windowed
---
Windowed is the simplest way to change pitch or time, fixing the other. You chop up the audio into small blocks. Repeat blocks if you want to increase the length, and vice versa for shortening. For pitch shifting, you can varispeed the blocks. You typically do short fades on block edges to smooth the transitions (aka Windowing). This is very low CPU, but it sounds bad cuz combing artefacts appear due to cancellation of frequencies from playing similar, but off-phase similar material. You may also get double drums. And you will almost certainly need to change the settings depending on your content, like a short window for drums & a long window for vocals & pads.

FFT
---
FFT pitchshifting is quite simple. When you get to the point where you have individual frequency bins, you can just shift the bins. Unfortunately, FFT works on a linear scale, but pitches & notes are a logarithmic scale, so a simple shift up sounds very bad & very unnatural. Even if you scale the bins such that you get a logarithmic shift, interpolating the amplitudes & phases into new bins gets messy, and also probably sounds bad. So you prolly don't want to use this for pitchshifting as a core method, unless you want it to sound very alien (there are VSTs which use this to pitch mangle tho), but we'll see its purpose later.

Drum loops
---
If you use any of the methods above to stretch drum loops, it will sound bad. You will get double drums, unnatural drums, or both. There's a simple & good method to stretch drums. Drum loops typically have silence between hits. So by lengthening or shortening the silence between hits, we have a simple, but good-sounding method to stretching drums. Obviously this will sound terrible for most other things, but drum loops is an important case in modern music production. 

PSOLA
---
PSOLA stands for phase-synced overlap & add. What this means is that the audio is chopped up into small blocks, then duplicated & shifted like Windowed as above. If pitch needs to be changed, you can prolly use varispeed. But, we use [Autocorrelation](https://en.wikipedia.org/wiki/Autocorrelation) to find the shift that sounds the best for a block. Now if you're performing this on stereo, stereo has difference between L & R, so the optimal shift will prolly be different. This manifests as a widening of the image, and is undesired. So what should happen, is that the shift is the same between channels, so you don't get (unstable) widening artefacts. Same applies to multichannel, so if you're stretching multichannel audio, you need a multichannel pitchshifter. The highest pin count for a VST I know of is 8 for 7.1 surround. But it might go higher for integrated solutions.

Combination
---
PSOLA sounds good for the general case, like smooth sounds. But for transients like drums, it will sound bad cuz you may hear double drums. So we take a hint from drum loop stretching, try not to duplicate transients, but loop smooth sections instead. If we use varispeed to change pitch, it sounds unnatural, especially on vocals. So we can perform some additional manipulation using FFT to correct for that. I'm not sure of the exact changes, whether EQ or shifting. If you use a vocal VST, you can get potentially higher quality &/ lower CPU than a general FX.