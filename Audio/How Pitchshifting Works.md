# How Pitchshifting Works

Introduction
---
Good, modern pitchshifters are complex beasts that use a combination of time & frequency domain manipulations to achieve a convincing quality.

Varispeed
---
The simplest way to change pitch. But also changes time. Seemingly not useful if you want to fix one, but keep this in mind.

Implementations: Adobe Audition 4, REAPER (don't preserve pitch when changing rate)

Windowed
---
Windowed is the simplest way to change pitch or time, fixing the other. You chop up the audio into small blocks. Repeat blocks if you want to increase the length, and vice versa for shortening. For pitch shifting, you can varispeed the blocks. You typically do short fades on block edges to smooth the transitions (aka Windowing). This is very low CPU, but it sounds bad cuz combing artefacts appear due to cancellation of frequencies from playing same, but off-phase similar material. You may also get double drums. And you will almost certainly need to change the settings depending on your content, like a short window for drums & a long window for vocals & pads.

Implementations: REAPER (Simple windowed), pitch_ola.reajs

FFT
---
FFT pitchshifting is quite simple. When you get to the point where you have individual frequency bins, you can just shift the bins. Unfortunately, FFT works on a linear scale, but pitches & notes are a logarithmic scale, so a simple shift up sounds very bad & very unnatural. Even if you scale the bins such that you get a logarithmic shift, interpolating the amplitudes & phases into new bins gets messy, and also probably sounds bad. So you prolly don't want to use this for pitchshifting as a core method, but we'll see its purpose later.

Implementations: fft-ps

Drum loops
---
If you use any of the methods above to stretch drum loops, it will sound bad. You will get double drums, unnatural drums, or both. There's a simple & good method to stretch drums. Drum loops typically have silence between hits. So by lengthening or shortening the silence between hits, we have a simple, but good-sounding method to stretching drums. Obviously this will sound terrible for most other things, but drum loops is an important case in modern music production.

Implementations: Adobe Audition 3

PSOLA
---
PSOLA stands for phase-synced overlap & add. What this means is that the audio is chopped up into small blocks, then duplicated & shifted like Windowed as above. If pitch needs to be changed, you can use varispeed. But, we use [Autocorrelation](https://en.wikipedia.org/wiki/Autocorrelation) to find the shift that sounds the best for a block. Now if you're performing this on stereo, stereo has difference between L & R, so the optimal shift will prolly be different. This manifests as a widening of the image, and is undesired. So what should happen, is that the shift is the same between channels, so you don't get (unstable) widening artefacts. Same applies to multichannel, so if you're stretching multichannel audio, you need a multichannel pitchshifter. The highest pin count for a VST I know of is 8 for 7.1 surround. But it might go higher for integrated solutions.

Implementations: Traktor Pro 3, Elastique 2?

Phase vocoder
---
Just like a classic frequency-amplitude vocoder, the phase vocoder takes its phase from something else, like previous frames. The process goes like this (from my understanding of the [surina article](https://www.surina.net/article/time-and-pitch-scaling.html) & the [cycling 74 tutorial](https://cycling74.com/tutorials/the-phase-vocoder-%E2%80%93-part-i), we take the FFT of the audio & scale it as per usual. But, the phase difference of the unscaled audio between previous & current frames, and applies a scaled difference to the scaled audio. Then iFFT as usual. 
The phase of the current scaled frame is often stored in an array and is referred to as "running phase" by some articles. Some articles also refer to "phase wrapping", which loops phases into a standard 0-360* range, but this might be already performed by your maths functions. Due to phase errors accumulating over time, artefacts can crop up. Sounds may get less percussive. And since phase vocoding is done on individual channels, the stereo width can increase. There are some approaches to fix this, including using a [weighed average](https://www.researchgate.net/publication/2608783_Phase-locked_Vocoder) of the phase across channels, locking the phase [of peaks](http://www.ee.columbia.edu/~dpwe/papers/LaroD97-phasiness.pdf), and doing mid-side (or LCR) processing instead of L&R.

Implementations: Soundtouch, Rubber Band Audio

Combination
---
PSOLA sounds good for the general case, like smooth sounds. But for transients like drums, it will sound bad cuz you may hear double drums. So we take a hint from drum loop stretching, try not to duplicate transients, but loop smooth sections instead.

Implementations: Elastique 3?

Formants
---
If we use varispeed to change pitch, it sounds unnatural, especially on vocals. So we can perform some formant correction, maybe using FFT. But the formant frequency differs between content, so good shifters should have frequency & shift controls. I'm not sure of the exact changes, whether EQ or shifting. If you use a vocal shifter, you can get potentially higher quality &/ lower CPU than a general shifter. Non-vocals don't have a formant per-se, but can still benefit from formant correction as they have a general FFT envelope that's distorted when shifting.

Maybe: geraintluff's [Warble](https://geraintluff.github.io/jsfx/#Warble) , [tb_voicepitcher](https://www.toneboosters.com/tb_bustools_v3.html)