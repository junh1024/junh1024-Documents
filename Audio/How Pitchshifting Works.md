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

PSOLA
---

Combination
---