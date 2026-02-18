# Ambisonics - Reusing Effects

## Introduction
There's a lot of literature or marketing copy on the internet that says you can only use Ambisonics-specific effects on Ambisonics signals so as not to wreck the "delicate" imaging. They say this because they want you to buy their Ambisonics plugins. This is only partially true - you can use some conventional effects on Ambisonics given some conditions. In this document, I'll show you how to use surround effects in Ambisonics, and also the reverse, highlighting issues. 

Ideally, you will have some experience with Ambisonics.


It may get a little technical. If you want to avoid this and go the easy route of just buying ambisonics or surround plugins, you're welcome to - stop reading now. If you want to learn, read on.

The document has a lot of reaperisms. If you're working in Ambisonics you're likely working in Reaper anyway.

Whether you work in surround or Ambisonics, I recommend you download the [IEM Suite](https://plugins.iem.at/), and maybe [MCFX Suite](http://www.matthiaskronlachner.com/?p=1910) since they have many useful plugins. There's also my [Reaper-Surround suite](https://github.com/junh1024/Reaper-Surround/blob/master/README.md#introduction) with plugins ending in .txt


## Background
there are many free or paid surround and Ambisonics Suites. Those won't be covered here. There's also ways to use stereo plugins in multichannel by duplicating them. Some DAWs do this (like pro tools & wavelab) and will be briefly covered in each section. Some Daws have inbuilt surround plugins. There won't be covered here but I'll just say that Cubase/Nuendo has inbuilt surround plugins, and they will effect the audio in Ambisonics if applicable. The document will cover adapting surround effects for Ambisonics and vice versa and higher order surround (12 channels and above.) Since certain effects are hard to find for free in those formats. 

## Basics

It depends per effect, but in general, as long as the transformation or scaling of each channel is exactly the same, then you can use it in surround Or Ambisonics. When using surround plugins in Ambisonics, you need to make sure there's no special treatment for the 4th channel AKA LFE in surround. This information won't be repeated so you need to keep this in mind for every effect type.

## Equalizer
Almost any surround equaliser can be used in Ambisonics and vice versa. Free ones include mcfx_filter, and IEM MultiEQ. Thus, it is multi-mono safe.

### Dynamics

Any surround compressor or gate can be used in Ambisonics provided that there is 100% channel link. 100% channel link means that regardless of which channel triggered the threshold, all channels are affected. 0% channel link means that only channels which triggered the threshold are affected. Please do some testing yourself. The following reviews are written sarcastically.

Reacomp INBUILT
Since reaper 6 was released in 1886, a limited amount of inbuilt plugins have been enabled for multi-channel operation via the FX IO panel. Reacomp is one of those. You can run it in multi-mono, multi-stereo, or multi-channel, equivalent to a channel link of 0% to 100%. And the usual ample controls. 
Verdict: 0/10 too perfect, would not use ??????

Compressor_multi.txt JSFX
It sort of works, but gain changes occur in steps of 46 FPS so only suitable for long-term compression, and the controls are extremely limited. Either the developer is on crack, or they don't know how to code compressors. Probably both.
Verdict: 10/10 there's no way a compressor can be this Janky.???? ?? 

IEM Omnicompressor VST
This is actually a Ambisonic compressor with the trigger as the W channel, which means L in surround. It's actually not that much of a step down from a certain surround compressor I used in the past where L&R are the trigger channels only. (if you so wanted, you can make a mono downmix and send that to the 1st channel of the compressor). Also it only works on a square number of channels such as 16. Also it's limited to short-term compression. 10/10 would misuse again. 


In my experience, although channel linking theoretically preserves the image, the opposite is true in practice. This is because rhythm,usually mono, triggers the compressor, so as the signal is turned down, the rhythm is still more prominent, leading to a reduction in perceieved width. Therefore In surround, multi-mono safe. In ambisonics  multi-mono unsafe.

### Pitch shifting
Pitch shifting is a hugely complex effect and you can find more on how it works [here](). As with surround, the decisions must be synchronized across all channels. Even though you might think that the plugin is doing the same thing across all channels, the reality is that it's making slightly different decisions because each channel is different, leading to small misalignments = distorted imaging when played back. Therefore, you need to use a dedicated multichannel pitch shifter like [zplane Elastique](https://products.zplane.de/products/elastiquepitch) , which supports 16ch. There is a free one, but it's misaligned so not relevant. multi-mono unsafe.

# Denoising

If you're trying to denoise Ambisonics, the usual and safe approach to work on a decoded format like A-format, or convert to T-format. Although if you're trying to denoise Ambisonics, maybe the Sparta array2SH preprocessor can somewhat do that when converting A-format to B-format.

Multichannel denoising can be done in Audition with "Noise Reduction", ReaFIR in REAPER, or most other stereo denoisers. ReaFIR can operate in multichannel in the FX IO panel with manual settings. Using the subtract mode in ReaFIR, a noise profile can be built, or you can draw a manual shape.

Angelo Farina covers [denoising in T-format](http://pcfarina.eng.unipr.it/Aurora/Ambisonics-Denoising.htm) in Audition with SPARTA ambidec and ambienc. The T-format equivalent for B-format usually has more channels. The main thing to note for SPARTA ambidec is to select the SAD decoder approach, and deselect max_RE for both bands. Converting to and from T-format isn't fully lossless, but it's close.

But Let's say you wanted to do denoising in B-format Ambisonics for reasons of efficiency or limitations. Denoising is a operation which subtracts the same amount from each channel (in the frequency domain). So, denoising in SN3D would denoise higher orders too much since the amplitudes go down as the orders go up. The reverse is true for N3D. You can choose Fuma/1N normalization, where the harmonics stay about the same amplitude from orders 0-3, but normalization of individual harmonics very. You can convert to/from Fuma with ambix_converter, then denoise with ReaFIR. This approach hasn't been validated in theory or practice by anyone else. YMMV.

multi-mono risky.

### Reverb


Reverb is probably multi-mono  safe, but is likely not what you want. A stereo reverb has only 2 channels to interact with each other, but in multichannel, a stereo reverb cannot make all channels interact with each other. Therefore, a dedicated multichannel reverb should be used. We shall discuss 2 multichannel reverbs.







- Ambifreeverb 1 , [simply spreads the W signal](https://www.researchgate.net/publication/289958469_AmbiFreeverb_2_WigWare_-_Sounds_in_Space_2015) to the 4 channels. So it can theoretically be repurposed for 4.0 or 5.1 surround with the right routing, but this is not elegant.
- Ambifreeverb 2 processes in A-format.
- IEM FDNreverb I would recommend as a general multichannel reverb and works for Ambisonics & Surround. Make sure to mute the 4th channel in surround or else your LFE will be muddy.


### Distortion
Distortion is a special case of compression. You can build distortion with any compressor if you set the attack & release to 0ms and a high ratio.

As with compression, adapting Ambisonics compressor to surround or vice versa, an important point is the trigger channel(s) and channel link, so before you do this, please do testing to make sure the behaviour and sound is what you want.


### Gain

IEM Toolbox can be used to change the gain of surround or Ambisonics signals. As it's targeted towards Ambisonics, the inputs must be a square number of channels.

Bitutils V2 in my suite can be used to change the volume of a signal with the volume and shift sliders. It works on arbitrary channels, and you can type in channels if 16 isn't enough.

multi-mono safe.

### Delay

mcfx_delay  is a free multi channel delay, but you need to diffuse the signal first.

If you use cubase/nuendo , there's a built-in mixerdelay. But again you need to diffuse your signal first. 

O3A delay  is a dedicated ambisonics delay. Included in the [O3A core suite](https://www.blueripplesound.com/o3a_core) suite




### Appendix

I've been wanting to type something up about common plugin limits, and I finally have an appropriate document to type for the now, so here it is:

- 2 channels: this is the format for over 90% of plugins since they Target to stereo. 
- 4 channels: this means first order ambisonics or for some very old plugins, quad surround. 
- 6 channels: this likely means 5.1 surround. Many plugins developed in the 2000s would have been made for 5.1 surround and not updated for newer formats. 
- 8 channels: this usually means 7.1 surround. There would've been some plugins developed for 7.1, but not a lot compared to 5.1 surround. Occasionally you get the odd plugin developed for octophonic
- 10 channels: this can mean 7.1.2 Dolby Atmos bed. Again, a few older plugins for DA bed only would've been made in the 2010s for this, and weren't updated when higher beds were available.
- 12 channels: this means 7.1.4 bed and a few Plugins developed after 2020. 
- 16 channels: this could mean 9.1.6 surround or third order andisonics. Some plugins from the 2000s onwards were developed with a third order ambisonics (could be Fuma or Ambix), but from 2020, a small rise in plugins developed for 9.1.6 surround like reverbs
- 24 channels: this would usually mean to 22.2 NHK surround. But not a lot of plugins. 
- 32 channel: around this number are speaker output limits for some software, but again not a lot of plugins
- 64 channels: this was the multichannel limit for reaper for many years. Many ambisonic suites have been built around to this limit to accomodate 7th order ambisonics.
- 128 channels: reaper 7 recently raised it's channel limit to 128, and some ambisonic Suites have been updated to reflect this.

