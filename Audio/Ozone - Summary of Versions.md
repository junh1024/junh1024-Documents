# Ozone Mastering Suite - Summary of Versions

previously called **Ode to Ozone**

## Introduction
Isotope Ozone is a well-known software plugin for mastering audio. This document will overview versions and features for a informational, but not necessarily mixing context. Although I've used Ozone for mixing, izotope would rather you use Alloy 2, but that has been discontinued as of 2017 in favor of Neutron and Nectar for vocals.

## History

### Early versions

Version 1 released in 2001 and was offered in DX and winamp formats. Version 2 was offered in VST format for more DAWs and offered presets. Version 3 had more modules like stereo imaging, maximizer. Summary of versions 1-3 is provided from [splice](https://splice.com/blog/the-evolution-of-izotope-ozone/).

![Ozone 4](https://rekkerd.org/img/articles/izotope_ozone4.jpg)

Back in the day, I used a bit of Ozone 4 (2008) for mixing, since it has a nice suite of tools all in 1 plugin, like EQ, reverb, exciter, and the CPU use is low to boot. Version 4.04 (2011) is the first version to have 64-bit release and therefore the earliest version that will run on most modern DAWs. Only 2 things are missing:
1. The EQ Target curve from version 3 was removed since they claimed it's not a meaningful Target
2. And two that UI is a bit small on Modern screens

![Ozone 5](https://medias.audiofanzine.com/images/normal/izotope-ozone-5-advanced-374874.jpg)

In Ozone 5 (2012), Individual modules as available as separate VSTs in your DAW for reduced CPU use, since the combined modules version takes about 50% more CPU. The architecture was also changed so that if you reinstall your PC, some modules won't function correctly since it also relies on the registry to function. The reverb module was upgraded to a hybrid setup. More filters were added to the EQ including brickwall. Matching EQ is now a lot easier to use & access. It was in 4, but it's quite tricky to use since it also involves adjusting spectrum settings. I've used matching EQ a few times, but usually I just EQ by ear.

Ozone 5 also introduces the ability to change the phase of selected frequencies in digital EQ mode. This is useful if you want to turn a non-linear phase plugin into almost linear phase, by applying a maximum phase adjustment. Since you can't adjust phase without an EQ change, you need to add 2 EQ filters on top of each other, but with opposite amplitudes, so that they cancel each other in gain but you still have phase control. I've not seen many EQs that allow you to control phase independently of gain. Version 6 onwards restricts the phase control to linear/minimum so this trick might not work.


### Later versions

![Ozone 6](https://dt7v1i9vyp3mf.cloudfront.net/styles/news_large/s3/imagelibrary/O/O6_06_15_02-mJak_wEcuLLflhbb_MD5mk3_hpcNKMgT.jpg)

Versions 6 to 8 were a blur with nothing useful to me & I had to consult online documentation & reviews for these (mainly Sound on Sound) since I haven't used past 5 much.

Version 6 (2014) unfortunately removed the reverb and many people lamented the decision. Ozone even wrote the 2013 Edition (and earlier versions) of their [mastering guide](http://web.archive.org/web/20130409151949/http://downloads.izotope.com/guides/iZotopeMasteringGuide_MasteringWithOzone.pdf) saying "Mastering reverb can be used as a way to unify" instruments when they don't sound very cohesive together. As such, 6 was marketed as a creative mastering suite, not a complete one. Version 6 also removes module & global amount sliders. I guess that was 1 of the lesser-used features that they removed. It's also the 1st to expose & enlarge the graph flow into the main interface, and remove the fixed module pages. So now, users need to manually add modules if they wish to use them. Version 6 is also the 1st version available in standalone.

Version 7 (2015) adds some vintage modules (EQ, compressor, limiter, tape). Vintage was all the rage back then, I guess after Taylor Swift's release of 1989 in 2014. Thank god that tape doesn't add wow & flutter, as it's 1 of the things I loathe about analogue, and would also add latency. Version 7 also adds codec preview, which some people applauded, but I would argue it's not that useful since unless you can have the exact encoder & settings as the final encode, the artefacts will be different. Also, general transparency rates are known. Default in LAME MP3 is HQ/slow, but some services may use fast instead. Default AAC encoder for Apple Music would ofc not be Fraunhofer either.

Version 8 (2017) adds Dynamic EQ, not that useful/working for me TBH. Version 8 to 10 also adds spectral shaper & stabilizer which tames frequency problems like resonances, or broad adjustments like oeksound soothe & soundtheory gulfoss respectively.

![Ozone 9](https://cdn.mos.cms.futurecdn.net/ETyy4rBCJEYMon2u2uGdYR.jpg)

Version 9 (2019) has master rebalance which uses ML to change the level of vocals, drums, or bass in a stereo mix. Again, if you reinstall your PC or copy over the VST from another computer it won't work due to registry and other dependencies. This is a different algorithm/model than music rebalance 1st introduced in RX7. There is Acon Digital extract dialog, but while more efficient, it's clearly worse & not built for music. Low end focus is apparently new so you can add punch to low frequencies, would be useful for adding bass punch on DRC'd songs but IDK if it would work in practice. 9 spins off Match EQ into its own module.

Ozone Elements 8 and 9 were available for free for a limited period but they might be a bit hard to find now. They included the EQ, imager, and maximizer modules. Trash 2 was also free for a limited time.

Version 10 (2022) adds an impact module to increase or decrease Dynamics. I wonder if it will be useful on your usual DRC Masters. In the past, I've been using Voxengo Transgainer for that.

Version 11 (2023) adds a clarity module. Version 11 adds vocal balance to master assistant. It uses ML to separate and analyze the vocals to be the correct volume. this feature this also available in the elements addition.

 
## User Interface

### Controls

You might not notice this, but the lack of rotary knobs is a deliberate design decision. Instead, they have sliders and sometimes, vertical knobs. You can also type in specific values. I don't have any problems with rotary knobs (if you can adjust the value via horizontal/vertical mouse movement), unless they behave literally like a rotary knob, like, you need to move the mouse in a circle to adjust the value. From version 6 text is enlarged and controls are simplified. But I wonder if you lose some control in the process. Version 10 onwards his circular elements which behave like vertical sliders like The Orb widgets in zynaptiq plugins.

![Ozone 11 orb controls](https://claudiomeloni.it/wp-content/uploads/2023/09/iZotope-Ozone-11.jpg)

### Colours
Version 5 makes the UI a lot bigger. Version 5 opts for a muted light green instead of fluorescent green look from the first four versions. Version 6 begins a process towards interface with blue highlights instead of green, bigger text, and simplification of the UI. Version 7's vintage modules have a light yellow background, but Version 8 changes them to black and blue - the same as other modules.

## Alternatives

I use REAPER. Most of the modules in Ozone I have now replaced with free or built-in alternatives which usually use less CPU, but the control & sound will be slightly worse.

- Equalizer: ReaEQ, ReaFIR
- Reverb: Reaverbate
- Dynamics: ReaComp, ReaGate, ReaXcomp
- Exciter: LOSER/Exciter, ReaXcomp with fast constants
- Imager: LOSER/stereoEnhancer, Liteon/pseudostereo
- Maximizer: ReaComp, ReaLimit (new)

- Spectral Shaper: ReaFIR
- Vocal Balance: LUFS meters & manual gain

- Trash 2 Distortion: distort-fuzz

## Conclusion

Summary of different versions:

- Ozone 4: Low CPU use
- Ozone 5: Comprehensive legacy features
- Ozone 9+: Modern features

Although I have mostly migrated to free plugins. Ozone over its 20-year history (starting from 2001), has incorporated current trends. While real mastering engineers (R) may prefer to use something else, it's been [credited]() with making mastering more accessible, and it's there if you need it.
