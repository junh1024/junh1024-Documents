# How to choose PC Parts & Performance tips

Aim
---
This guide is meant to accompany your process of choosing PC parts for a PC tower or similar,  pre-chosen builds https://pcpartpicker.com/guide/ or https://www.logicalincrements.com/ , or your own. My aim is to build a low-mid range, quiet, power-saving, money-saving PC that lasts, for light Audio/Video work. If you need to do very intense work all the time, or don't care about the above properties, this guide is not for you.

## Case
Get a sensible case with enough room & slots for your needs. High end models may have plastic clips & rails for HDDs which make installation quite painless. Most cases will have holes to install case fans. If you need a fan (like, for cooling HDDs) get a large, low rpm fan for quietness & longevity. Models vary, check your local PC shop.

I am not a fan of RGB LED PC hardware, as LEDs consume power, and may disturb your sleep if you sleep in the same room.

## CPU
Get a CPU with 4 physical cores. You can get more, but software might run slower due to lower clock, jumping between more cores, or mismanaging cores. www.REAPER.fm is particularly effective at utilizing multi-core CPUs, while other DAWs are playing catch-up. TDP is not a measure of how much power it will use in practice. Many low/mid-end CPUs have integrated graphics, so pick those. Just don't expect to do gaming at high settings, or at all. Many iGPUs support >1 monitor. Many low-mid range CPUs will also come with a cooler & thermal paste so you could skip those.

If you have lags or glitches when doing audio, try turning off SMT/HT in your BIOS. You can also set CPU throttling in your control panel to get more consistent performance, or more consistent quietness.

## GPU
If you must get a dedicated GPU, there are a small selection of fanless ones available for quiet operation.

If you're doing video editing, many functions are dependant on CPU (so you need a good CPU first), and the functions that are accelerated might not be using the main capability of the GPU (video decode uses ASICs & some VFX uses compute cores). The trick to doing HD editing on a slow CPU is to use LQ proxies. Like, edit using LQ footage, and substitute for HQ just before you export your final video. Also, please check GPU acceleration compatibility with your software & functions.

## Capture
If you want to record TV, check out the range from [Hauppauge](https://hauppauge.com/pages/products/prods.htm) . I have a [dual-tuner](https://www.hauppauge.co.uk/site/products/data_novatd500.html) set to diversity mode with 2 antennas for error correction on 1 programme. The 2 ports are connected to a cheap rabbit ear+UHF loop antenna, and a mini indoor UHF fishbone antenna with small UHF loop. 1 of them is connected to a 4G TV filter. I have found that PCI GPUs disrupt TV recording so I don't have one installed.

USB capture hardware is also possible. See my [guide](https://github.com/junh1024/junh1024-Documents/blob/master/Video/How%20to%20capture%20VHS%20with%20VirtualDub.md#introduction) for VHS capture using a USB Live 2.

## RAM
An increase in RAM frequency isn't going to give a big performance increase, so you can keep it low. It'll use less power & heat. ~~DDR4 is a bit expensive atm so you could choose DDR3.~~ Pick a modest amount of RAM, like 8GB. The problem with more RAM is there will be a slight increase in heat, but also lags due to large pagefile size, as by default windows scales your pagefile depending on RAM, and most users won't bother to tweak it. I'll suggest a fixed size of 4-8GB.

## Motherboard
AMD tries to keep CPU pin layout compatible with older mobos, while Intel doesn't. If you have any legacy hardware, like FDD/IDE devices, or PS2/RS232 devices, keep in mind when choosing a mobo. You also want a digital out like DVI/HDMI/DP to get a HQ picture from your iGPU. Also, keep in mind the connections on your monitor/TV, and the difference between DP & DP++.

### Audio
Try to choose a mobo with at least 6 audio ports. This usually means 7.1 surround, 2.0 line in, and 1.0 mic in. Gaming mobos nowdays may also have " 7.1+ 2 multi-streaming " which is an independent audio out on the front panel, so you can do 7.1.2/5.1.4 surround out. But you prolly need to aggregate them with ASIO4All, since windows doesn't have built-in audio device aggregation. You can also aggregate 7.1 analog with 7.1 HDMI audio out, but you may need to do latency correction in your DAW for the HDMI part.

There are cheap 7.1 USB soundcards like the [Vantec NBA-200U](https://www.amazon.com/Vantec-NBA-200U-External-Channel-Adapter/dp/B004HXGJ3S) but they take some fiddling to get it working in W10, and the SNR of a good onboard chip nowdays can beat the SNR of a cheap USB box. Some mobos even have headphone amps.

If you want to play arbitrary surround audio codecs through SPDIF, you need a AC3 transcoding system like MPC + AC3filter. For systemwide SPDIF surround, you need a Dolby Digital Live sound driver or similar.

## HDD
If you want decent storage for cheap, get a conventional HD. Choose a NAS HD with a 5400rpm speed. I know you wouldn't usually pick a NAS HD for general use, but it's a valid choice. NAS HDs are built to handle a bit of heat & vibration, and usually have a decent warranty. A 5400rpm speed means it will probably run cooler, quieter, last longer. Yes it is a bit slower, but it's tolerable at sizes of >1TB.

You can have a SSD. You'll get less, but faster storage for your money. Just keep in mind you might run out of space unless you also have a HD.

Run chkdsk or fsck yearly. Also, check your SMART regularly with crystaldiskinfo or smartctl.

## ODD
DVD writers go for dirt cheap, you may already have one, so there's little excuse not to have one. Also consider a BD writer so you can backup data or make BDs. USB ODDs are also possible.

## PSU
Many guides will suggest a 80+ bronze PSU. I'll suggest a semi-modular PSU (for better cable management), and a 80+ gold to save more power. You might save $20-50/year depending on how much you use your PC. Some lower watt PSU are only available in the SFX size. You can buy brackets/adaptors to fit a standard PC case. I suggest Corsair although Cooler Master or Seasonic might do. Do NOT cheap out on a PSU. You can damage your PC if you do.
