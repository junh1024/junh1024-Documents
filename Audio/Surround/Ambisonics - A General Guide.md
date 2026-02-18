# Ambisonics - A General Guide

This document aims to be a comprehensive introduction to Ambisonics

## What is Ambisonics?

Ambisonics is way of authoring 3D audio which uses spherical harmonics, or "spatial audio soup channels" instead of objects and beds like in Dolby Atmos. Like Dolby Atmos, it can be rendered to speakers or binaural.

Steinberg [says](https://steinberg.help/nuendo/v13/en/cubase_nuendo/topics/surround_sound/surround_sound_surround_configurations_available_r.html)  Ambisonics uses "an encoded bundle of audio signals to position sound sources at any place in the sound sphere. ... Higher-order Ambisonics provide more signals and allow for a higher precision of positioning"

Comparing to other approaches:
- CBA (Channel based audio or conventional surround), the soundfield is only defined at the points of expressed channels. More channels fill in the soundfield between existing points. A bottom-up approach.
- OBA (Object based audio). Implementations such as Dolby Atmos or EAR Production Suite. Beds are supposed to occupy multiple speakers but objcts can occupy points and single speakers, but this varies in practice.
- HOA (Higher order ambisonics). The soundfield is defined everywhere, and further channels add detail. A top-down approach.

In convention surround, you downmix to provide a lesser representation. In ambisonics, because higher channels just extend the precisionof the lower channels, you simply discard higher channels to  provide a lesser representation. Simple and elegant.

## Why REAPER?

Many people use REAPER for ambisonics since (along with the effectively infinite trial period = free DAW).  . and you build your own journey, but it's really flexible and the powerful

## DAW considerations

### REAPER

REAPER would be my 1st choice when working with Ambisonics, or a DAW in general. It's true that RPR has slightly more learning curve, but it's really flexible when you get to learn it.

A major attraction with RPR is that the trial period is effectively infinite. There is a 30 day trial, but you can still keep on using it afterwards with a reminder (nagware). A boon for the cash-strapped.

It still supports VST2 by default so you can go up to 7oA or 64ch effortlessly.

The powerful partial-sends ability surpasses cubendo & PT. ie, you don't have to send the whole signal - pick & choose the channels you send - a boon for surround & multiple channels work. Also, every effect has an integrated matrix router.

Due to its generic multichannel approach, there are no dedicated buses for ambisonics or surround - you have to keep track of what track is what. But sometimes this can be freeing & simple - the DAW isn't blocking you from accomplishing things a certain way.

The one thing you should do in RPR is to disable "Solo via dedicated solo bus" in preferences, otherwise soloing may sound wierd.


### Other DAWs

Other DAWs like Cubase/Nuendo and Pro Tools offer a more sheltered or guided approach to Ambisonics. They have dedicated buses for ambisonics, but can sometimes be a drag.

Cubendo is the only DAW to block VST2 by default, you can still [enable VST2](https://support.slatedigital.com/hc/en-us/articles/43558339270803-Missing-Plugins-When-Loading-Cubase-Sessions-VST2-vs-VST3) (for now) .   Also, VST3 support is limited to 24ch, and there are no ambisonics buses >4th order. Thus, Cubendo isn't good for 5oA work.

Cubendo tries hard to prevent incorrect signal flow & may do automatic conversions for you. Example: EQ is qualified for ambisonics work, but MixerDelay is not. MixerDelay allows you to adjust gain and delay in surround. While there are possible use-cases for this in ambisonics, there is a 99% chance you don't know what you're doing. Therefore, it's disabled in ambisonics.

Pro Tools also has dedicated ambisonics buses and goes up to 7oA, but supporting AAX only means basically no free ambisonics plugins.

## Plugins



### Required plugins
- [IEM Suite](https://plugins.iem.at/)
- [Sparta suite](https://leomccormack.github.io/sparta-site/)

### Suggested Free

- [Ambix Suite](http://www.matthiaskronlachner.com/?p=2015) 
- [MCFX Suite](http://www.matthiaskronlachner.com/?p=1910) . (generic multichannel tools)
- [Blue ripple O3A core suite](https://www.blueripplesound.com/o3a_core) Usefule Meters/visualizers, and spatial delay. They also have paid suites.

### Older Free
- https://www.soundfield.com/#/products/surroundzone2 was the first free active decoder
- [Wigware](https://www.brucewiggins.co.uk/?page_id=78)

### Suggested Paid
- [Audiobrewers Software](https://www.audiobrewers.com/plugins) Their software has been often promoted by influencers. They offer many "cheap" plugins with good capabilities, but the cost quickly adds up.
- [Noisemakers Ambi Bundle HD](https://www.noisemakers.fr/product/ambi-bundle-hd/) This is the only paid suite i'll recommend. Simple, but powerful. They also offer [edu/indie discounts](https://www.noisemakers.fr/indie-edu-discount/)
- [SSA bundle](https://www.ssa-plugins.com/plugins/axbundle/) a paid bundle with some traditional production FX

## Ambix & Fuma conventions

Conventions means order and scaling of the channels. There are 2 main conventions - Ambix and Fuma. You'll mainly be working in the Ambix (newer) convention but some older plugins use the Fuma convention. Most software mentioned in this guide will use the Ambix convention.

Ambisonics was created [in the 1970s](https://en.wikipedia.org/wiki/Ambisonics) by Michael Gerzon, among others. In the 2000s, ambisonics was extended to 3oA 16ch with the Fuma convention. In the 2010s, people wanted higher orders, but Fuma had its limitations - the order and scaling of the channels was mathematically inelegant. So the Ambix convention was created by Kronlachner along with the ambix suite, and the community decided in 2016 to switch to the Ambix convention going forward.  The new Ambix convention is  mathematically  elegant and the orders can be extended indefinitely but in practice people should mostly use 3-5oA. One [benefit of Ambix]() is that you can just use a Mid-Side decoder on the 1st 2 channels to get a basic stereo version. Many new suites were created with the ambix conventions, but a few older softwares is yet to be updated. Although some software like [Wigware](https://www.brucewiggins.co.uk/?page_id=78) is still available in both

To summarize, if the plugin is >2016 or >16ch, than it likely uses Ambix, and of the plugin is <2015 or <= 16ch it likely uses Fuma. But please check the documentation.

[Further reading](https://en.wikipedia.org/wiki/Ambisonic_data_exchange_formats) on ambisonics technical issues

## Signal Flow

The source for a ambisonics signal can be a traditional mono or stereo signal (even a synth), a ambisonics microphone, or a multichannel signal.


Source --> Mono/Stereo Effects --> Ambisonics Encoder/Panner --> Ambisonics/Multichannel Effects 

If you buy a ambisonics microphone, the should come with a A to B converter. Either way, Sparta array2sh  is always an option, and can sound better than included software.

## Ambisonics microphones

Unless you have a very good reson for sticking to 1oA mic, like budget or low noise, I would highly recommend using a 2oA+ mic. The reason im pushing for HOA is that there's tons of FOA recordings online, you can probably buy or get a clip of what you want on Freesound https://freesound.org/ or https://www.asoundeffect.com/

Also, if you want to capture musical instruments as opposed to ambience with zylia, I recommend placing the zylia at instrument height or 1 meter since due to the small radius -  it is sensitive to height. This way you get better separation as the instruments are around the equator of the microphone. 

## Decoder


Decoding is the most complex part of ambisonics

ALLRAD & pinv

in phase & maxRe weightings

What does passive & active mean?

Passive means using only matrices so it has a fixed (lower) resolution

Active is better since the signal is analyzed and audio steered for increased separation which can surpass the limitations of the ambisonics order


In general, DAW routing & conversions is passive. A decoder with a latency of >=2048sa is probably active


## Ambisonics order

The Ambisonics order is a number and relates to the number of channels. Higher orders offer more spatial resolution, at the cost of more channels, more processing power, and storage space.

Formulae:

- channels = (order +1) ^ 2
- resolution of ambisonics in degrees = 360 / ((order +1) x 2 )

Explanation of different ambisonics orders:

- First order ambisonics : this has 4 channels, and a resolution of 90 degrees. And 6db bleed when decoding to speakers. Since the quality is so low, you shouldn't be mixing in this, and you should only be delivering in this if the output mandates this for. For example, YouTube. Commonly used for VR & headphones, I wouldn't use this if delivering for speakers.
- Second order : this is 9 channels and a resolution of 60 degrees. This is a step-up from first order, but still not great quality.
- Third order : this is medium quality with 16 channels and resolution of 45 degrees. This is the limit for some early ambisonics implementations in professional software like Cubase and Pro Tools. However, **if you're converting to ITU 5.1, there is significant bleed to the Center channel** since the front 3 channels are 30 degrees and the resolution of 3oA is 45 degrees, unless you change where you Pan the sound and extract the channels. This should be the minimum quality you mix in for most purposes.
- 4th order: this is 25 channels and has a resolution of 36 degrees.
- 5th order: this is 36 channels and has a resolution of 30 degrees. **This would give you high quality 5.1 up to 9.1.6.** This is a general use high quality format and is good for Many purposes. This is a good compromise between space & high quality and many people shouldn't need to go beyond this.
- 6th order: this is 49 channels and has a resolution of 26 degrees.
- 7th order: this is 64 channels and has a resolution of 23 degrees. You should only author in this if you have lots of speakers.
- 10th order: this is 128 channels and has a resolution of 16 degrees. this is mostly only for research purposes or if you have very many speakers. The tools for this are also quite Limited.

If you're decoding to a hemispherical speaker array, channels * 3/5 would give you the approx amount of speakers it is good for. Example: 5th order is 36ch, x 3/5 = 21.6, so good for about 22 speakers in a hemisphere.

In general if you want medium high-quality output on an evenly-spaced speaker array, then you should author in ambisonics format which is which has at least twice the number of channels is your target speaker layout, since your speaker layout is likely to be hemispherical for rather than spherical. If your target speaker layout is uneven, like surround, then you also need to take into account the minimum angle between speakers.

In general, you would be authoring in 3oA which is minimum for quality. 1oA if you really need VR which only supports 1oA. 5oA ideally for high quality. Not really useful to go any higher unless you have >25 speakers.

Has anybody tried using Ambisonics like Dolby Atmos /oba with that bed / object approach? For example, ambience and textures in a low order such as third order. And moving elements in a higher order such as fifth order?

Flo: Yes, I’ve definitely done this on a number of occasions. It’s more of a creative thing than anything else, and I’m not sure it really compares to beds vs objects in Atmos, in the sense that all the things which might be considered best practices in theatrical Atmos directly translate to this approach. But it’s definitely something worth exploring, also in a frequency-dependent manner.


Also, some people can  tell the difference between 3o and 5o on head phones

https://www.brucewiggins.co.uk/Pics/AmbBinGifs_slow/ICSA_Wiggins_Gifs.html


## Converting to UHJ or matrixed
Fuma 1oA: ATK
Ambix 1oA: Wigware UHJ
HOA: Decode to quad, then use

## WFS
WFS is a sound rendering method that uses delays as well as amplitude. WFS requires not only the exact layout, but the exact dimensions as input to the system since the rendering is based on sound propagation. As such, it's mostly suitable for live performance where the renderer can cater to the exact speaker layout and positioning.

It can go beyond traditional panning methods, but there are likely consequences like phasing if you downmix it since WFS is based on delays.  Traditional panning methods like LBAP/VBAP (surround), HOA (ambisonics), are more robust in that aspect since they don't use delays.

PS: Just because it's rare, it doesn't mean it's better :^)


## Converting Zylia to DA 

would be as follows. We need reaper since logic not support 19ch zylia files.

1. Install reaper <http://reaper.fm/> and Sparta suite <https://github.com/leomccormack/SPARTA/releases/tag/v1.7.1> , and  Atmos composer essentials <https://fiedler-audio.com/dolby-atmos-composer-essential/> .  Atmos composer has some flaws, but it's prolly acceptable for ambisonics use & its free. By making ADM, we can guarantee channel order.
2. Making a new track, and set to **20 channels** wide in the routing options.
3. Insert Sparta Array2SH , select ** 3rd order**, and select **Zylia **preset. 
4. Add Sparta compass decoder  and select  **3rd order,**   **11.x 7+4** output preset. The linear to parametric slider should be set to 1/3  up to reduce artefacts. 
5. Insert Dolby Atmos **beam **, and reset the layout to **704 **
6. In the  Beam plugin, select object 4 which should be called LSS . Then bring down the volume to** -6dB** .
7. Repeat step 6 for  object ID 5 to 11 EXCEPT for LTF & RTF.  This is to work around that 51 downmix trim isn't available in logic,  and to reduce perception of backwards image when playing on speakers IRL   by trimming down surround channels. 
8. Insert Dolby Atmos **composer ** plugin on the master, and change the composite to **714**.
9. Seek to the end of your recording in reaper and click** set out point** in Dolby Atmos composer.
10 . Click export from Dolby Atmos composer. 
11. In reaper, go file > render and click **dry run**. 
12.  import the rendered ADM into logic.
13. You could  Move the top 4 objects to the edges for a  more  spacious image

### Converting DA to ambisonics

Render to 714
Use IEM MultiEncoder

Check side/back order which your DAW export maybe do a circular pan test first.


## Ambi video 
For video work with 360 video, [Noisemakers Ambi Pan](https://www.noisemakers.fr/product/ambi-pan-hd/) is my recommended software. It has a transparent window so you can overlays the pan icons on top of another window which has the video. discount pricing is available. 

Audioease 360 has something for this too, but it uses more CPU since "it is transporting frames from the Pro Tools ... video window to the 360monitor", and is more expensive.


For a free option, you can try [this](https://www.audioease.com/360/#goodies)

## Games VR

I suggest using Wwise middleware. Unity can only understand 1oA and it’s not really good.
 Pyry: Wwise is also quite good with file compression and optimization that is necessary for VR.

