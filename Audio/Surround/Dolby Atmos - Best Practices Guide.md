# Dolby Atmos - 

## Intro

This document is under construction.


## Cubase/Nuendo
- Dynamics: See below
- EQ: Most stock EQs work in surround
- Utilities: With Mixerdelay, You can use this plugin to trim and re-route individual surround channels. Mixconvert (automatically instantiated when converting channel formats) can also adjust trims when downmixing.

Plugins: surround VST2 is supported, but the channel order may be different.

Overall: The Dolby Atmos implementation in Cubendo is comprehensive, based on many years of surround support. You can do a 7.1.4 track, and it can be converted to a object bed easily. Multiple beds and labeling of entities into groups is possible.


## Studio One

The Dolby Atmos renderer requires your sound card to support 512sa latency. If you don't have that, then you can Download voicemeeter as a virtual sound card.

Spatial audio project types were added to S1 6.5 Pro in September 2023. It's now possible to mix in Surround and Dolby Atmos. If you're targeting speaker surround but only have headphones, you'll need to mix in DA to have binaural/stereo monitoring (unless you use external VST3).

## DA Basics

Like Logic, multiple beds & group labelling are not possible, so if you need to do DME delivery for movie, you'll be better off using something else. If you have too many objects (>118), then Studio One will stop you from exporting a master, which makes sense. If your routing is too weird and your signal path includes some objects, then it may make glitches.

The DA panner is pretty basic. Surrounds spread (no decorrelation) isn't the same as object size (some decorrelation).  Even on a 9.1.6 monitoring layout, object size decorrelation only occupies 7.1.4, which is good (below the 16e limit for spatial coding). Zone masking isn't available, but at least you get Trim & Downmix unlike Logic. Although dome would be useful for music, Pan modes aren't there in the S1 DA panner. But you can mute channels with Mixtool and track width.

In S1 you can put analysis effects like Level, Phase, and Spectrum meters on the master. For DA, Master inserts influence the bed, but post effects are monitoring-only effects.

It's possible to change the volume of overall master just by using the Renderer volume knob, which avoids the use of external virtual master plugins. In the renderer, you can easily change the BRM of multiple entities at once, by shift clicking or selecting all of them.



#### Effects

- Dynamics: See below
- EQ: Most stock EQs work in surround, but I prefer channel strip since it's simple. If you want to split the high frequencies upwards, you'll need to use buses & ProEQ3 since that offers a symmetrical LC/HC with 6dB slope.
- Reverb: Roomverb works in surround, don't forget to mute the LFE in the panner or Mixtool. Although Mixverb does surround processing, I think it's more like a multi-stereo reverb rather than a true surround reverb. Since you need to diffuse the signal beforehand (eg, through a 4.0 quad bus) before you get surround reverb activity.
- Stereo Imaging: Technically not a surround effect, but you can use their chorus in doubler mode if you want more stereo spread.  Despite being called "Binaural Panner", this is a tool to adjust stereo width.
- Utilities: Mixtool on a surround track allows you to adjust the trim of each channel


### Mixing

Unlike REAPER, there is no parameter modulation, so you need to input automation points manually. If you want to make a continuous circular pan, you can copy and paste automation points.

- Plugins: Some VST2 surround plugins work, but a notable exception for me is ReaJS - ReaJS is only a stereo plugin in S1.

#### JSFX on Windows

[Kushview Element](https://github.com/kushview/element/releases/tag/0.46.6) is a plugin loader in VST3, so you can load ReaJS VST2 there. Note scanning of VST is only supported in the standalone app, not the VST. So a double-loader process. Note that the combination of Element and ReaJS doesn't offer PDC, so you'll need to use zero latency effects or maybe Voxengo Latency Delay to compensate. See [here](https://github.com/junh1024/Reaper-Surround/blob/master/README.md#vst-compatibility)  for ReaJS instructions.

Note that As a workaround to support ReaJS in surround in S1, one currently has to use Kushview Elements VST3, to load ReaJS VST2 in a awkward "double-loader" setup, which then supports surround output in S1. But Kushview Elements doesn't support PDC. To fix the PDC problem, you then need to use Voxengo Latency Delay, so effectively using 3 plugins to load 1 effect. There are other JSFX loaders like YSFX, but API support is buggy, which rules out many JSFX. The below picture shows the required Elements-ReaJS-Latency Delay setup to load JSFX properly in S1 with PDC.

#### JSFX on Mac or VST3
YSFX can load JSFX into VST3, but its buggy API implementation rules out many of my JSFX.

## Routing
Routing in S1 is pretty basic. For files in the inspector, you can change the channel order. For FX, you can bypass and re-order channels.

### Performance

If you want S1 to start up faster, you can disable some services in the preferences. Also, in S1 > S1 installation > Installed content, disable all addons.

Going further, moving extensions and plugins can noticeably speed up startup time and reduce memory usage, but this is done it on risk.

as this  
You can also De-Esser, Fat Channel, Tuner



While S1 is generally responsive, some plugins are CPU-hungry. Like room reverb in surround. The performance monitor has a handy feature to sort FX by CPU use, and then disable plugins. If you want a low-CPU surround reverb, try FDNreverb with FDN size 16-32.

Conclusion: Dolby Atmos support in S1 is basic, buggy, and responsive. It's still usable though if you know what you're doing.

