# How to choose PC Parts & Performance tips

Aim
---
This guide is meant to accompany your process of choosing PC parts for a PC tower or similar,  pre-chosen builds https://pcpartpicker.com/guide/ or https://www.logicalincrements.com/ , or your own. My aim is to build a low-mid range, quiet, power-saving, money-saving PC that lasts, for light Audio/Video work. If you need to do very intense work all the time, or don't care about the above properties, this guide is not for you.

## Case
Get a sensible case with enough room & slots for your needs. High end models may have plastic clips & rails for HDDs which make installation quite painless. Most cases will have holes to install case fans. If you need a fan (like, for cooling HDDs) get a large, low rpm fan for quietness & longevity. Models vary, check your local PC shop.

I am not a fan of RGB LED PC hardware, as LEDs consume power, and may disturb your sleep if you sleep in the same room.

## CPU
Get a CPU with >=4 physical cores. You can get more, but software might run slower due to lower clock, jumping between more cores, or mismanaging cores. www.REAPER.fm is particularly effective at utilizing multi-core CPUs, while other DAWs are playing catch-up. TDP is not a measure of how much power it will use in practice. Many low/mid-end CPUs have integrated graphics, so pick those. Just don't expect to do gaming at high settings, or at all. Many iGPUs support >1 monitor.

Many low-mid range CPUs will also come with a cooler & thermal paste so you could skip those. You need box CPU since you need fan.

If you have lags or glitches when doing audio, try turning off SMT/HT in your BIOS. tweaking the min/max processor state in "power options"   to reduce dropouts  in DAWs.


i9 & i7 are generally overpriced & you pay for the name, more than the performance. Example, comparing the [i7-11700 vs i5-11400](https://www.cpubenchmark.net/compare/Intel-i7-11700-vs-Intel-i5-11400/3947vs4233) , the i7 performance is 23% better, but the price is 55% higher. So not worth it IMO. The i5s & especially i3 is where the value is at for intel.

don't buy intel 12th-gen (Alder lake) core processor due to the [big.LITTLE](https://www.anandtech.com/show/17047/the-intel-12th-gen-core-i912900k-review-hybrid-performance-brings-hybrid-complexity/4) architecture. Software isnt optimized yet, so some apps will run unexpectedly slower since they will be moved to the E-core when you least want it.

AMD CPUs generally offer [better value-for-money](https://www.cpubenchmark.net/cpu_value_available.html) WRT performance, and may have extra features like ECC RAM support for consumer CPUs (unlike intel). AMD also changes socket more infrequently (4y vs 2y), and may have better APU/iGPU performance.

If you want to use Linux, it might be best to choose a older CPU such that it's supported by your kernel.

### Thermal Paste
AAA

## GPU
If you must get a dedicated GPU, there are a small selection of fanless ones available for quiet operation.

If you're doing video editing, many functions are dependant on CPU (so you need a good CPU first), and the functions that are accelerated might not be using the main capability of the GPU (video decode uses ASICs & some VFX uses compute cores). The trick to doing HD editing on a slow CPU is to use LQ proxies. Like, edit using LQ footage, and substitute for HQ just before you export your final video. Some NLEs nowdays have a dedicated proxy function. Also, please check GPU acceleration compatibility with your software & functions.

## Capture
If you want to record TV, check out the range from [Hauppauge](https://hauppauge.com/pages/products/prods.htm) . I have a [dual-tuner](https://www.hauppauge.co.uk/site/products/data_novatd500.html) set to diversity mode with 2 antennas for error correction on 1 programme. The 2 ports are connected to a cheap rabbit ear+UHF loop antenna, and a mini indoor UHF fishbone antenna with small UHF loop [similar to this](https://www.walmart.com/ip/Hdtv-Antenna-Indoor-Terrestrial-Digital-Sr8-Broadcast-Home-Tv-Antenna-Indoor/756037112). 1 of them is connected to a 4G TV filter. I have found that PCI GPUs disrupt TV recording so I don't have one installed.

USB capture hardware is also possible. See my [guide](https://github.com/junh1024/junh1024-Documents/blob/master/Video/How%20to%20capture%20VHS%20with%20VirtualDub.md#introduction) for VHS capture using a USB Live 2.

## RAM
An increase in RAM frequency isn't going to give a big performance increase, so you can keep it low. It'll use less power & heat. ~~DDR4 is a bit expensive atm so you could choose DDR3.~~ Pick a modest amount of RAM, like 8GB. The problem with more RAM is there will be a slight increase in heat, but also lags due to large pagefile size, as by default windows scales your pagefile depending on RAM, and most users won't bother to tweak it. I'll suggest a fixed size of 4-8GB. Check the RAM mhz etc is compatible with your mobo.

## Motherboard
AMD tries to keep CPU pin layout compatible with older mobos, while Intel doesn't. If you have any legacy hardware, like FDD/IDE devices, or PS2/RS232 devices, keep in mind when choosing a mobo. You also want a digital out like DVI/HDMI/DP to get a HQ picture from your iGPU. Also, keep in mind the connections on your monitor/TV, and the difference between DP & DP++.

Try to choose a mobo with dual BIOS or some sort of contingency/failsafe BIOS flashing/loading since you may need to update BIOS regularly to work around CPU bugs.

### Audio
Try to choose a mobo with at least 6 audio ports, which should be most mid-end mobos. This usually means 7.1 surround, 2.0 line in, and 1.0 mic in. Gaming mobos nowdays may also have "7.1+ 2 multi-streaming" which is an independent audio out on the front panel, so you can do 7.1.2/5.1.4 surround out. But you prolly need to aggregate them with ASIO4All, since windows doesn't have built-in audio device aggregation. You can also aggregate 7.1 analog with 7.1 HDMI audio out, but you may need to do latency correction in your DAW for the HDMI part.

There are cheap 7.1 USB soundcards like the [Vantec NBA-200U](https://www.amazon.com/Vantec-NBA-200U-External-Channel-Adapter/dp/B004HXGJ3S) but they take some fiddling to get it working in W10, and the SNR of a good onboard chip nowdays can beat the SNR of a cheap USB box. Some mobos even have headphone amps.

If you want to play arbitrary surround audio codecs through SPDIF, you need a AC3 transcoding system like MPC + AC3filter. For systemwide SPDIF surround, you need a Dolby Digital Live sound driver or similar.

## Speakers

Usually, you'd connect your PC to desktop speakers, HiFi, AVR, or headphones. AIO surround sattelite+sub packages like Logitech X-530 Z5500 (legacy products) , Z-506 Z-506 Z-906 (current products), are not recommended since they have a sub, and you can have inconsistent bass levels due to inconsistent bass/lfe management in mixes & your sub levels. But an alternative worth considering is USB speakers, especially for surround. There are some benefits:

- Low power = save money
- USB power = automatically turn off with your PC, if connected via PC (save time)
- Flexible cable management since you can buy USB & audio extension cords, and they're thinner than mains power cords
- Flexible power management, since 1 USB multi-charger can power multiple speakers.

So you will mainly be looking at the [Genius](https://us.geniusnet.com/speakers/) range of speakers. I have the SP-U115 (a discontinued model) which has a FR of 200-18khz. Newer models average 150-20khz, and the [SP-HF280](https://us.geniusnet.com/product/sp-hf280/) does 100-20khz if the manufacturer is to be believed. Speakers may not be on display to test, so you will need to have some faith, or a good returns policy. For my speakers, there is a bit of bass, but not much, so I don't use them as main LR speakers. The newer models should have more bass. It is important for LR speakers to have good bass, so have traditional powered PC speakers if you must.

USB extension cables you can pretty much get any one, I haven't had many break so far. But for 3.5mm audio cables, do NOT get cheap $2-5 ones that are 3.5mm thick. Those break easily. Instead, get "professional" ones which are about 5mm thick. They cost a bit more, but don't break easily.

As for USB power supply (if not using your PC mobo), you may be tempted to get a [USB multi charger](https://www.orico.cc/us/product/detail/3690.html), but unless you have a power board/power strip with individually switched ports, I suggest you get [this with 2 power sockets & 5 USB ports](https://www.orico.shop/en/orico-socket-with-2-sockets-and-5usb-charging-port.html) . All ports are controlled by 1 master switch so you can switch on/off traditional & USB powered speakers at once, and there's a handy notch for holding a phone/tablet while you charge it. Keep in mind USB chargers may have idle power draw (you can check with a digital power meter), but Samsung single chargers tend not to.

### Music & Movies

### Headset
You might choose a surround headset for gaming, but you can do software HRTF surround free via HESUVI.

In this age of pandemic, you might want a noise-cancelling headset for online meetings. You want a wired headset since bluetooth ones are annoying to charge. You can choose USB-A if you use them for computer, or USB-C for PC or phone (check both devices have such a port). Some devices also allow you to disconnect further into a 3.5mm jack for further compatibility. Examples:

- Logitech H390 USB-A
- Jabra Evolve 40 (USB-A/USB-C & 3.5mm)
- Poly Blackwire 3325 UC (USB-A & 3.5mm)

### Gaming

Other neck speakers are available, but they may not have a mic, and almost certainly don't have discrete surround.

https://www.panasonic.com/uk/consumer/home-entertainment/gaming/sc-gn01e.html


## Storage

### HDD
If you want decent storage for cheap, get a conventional HD. Choose a NAS HD with a 5400rpm speed. I know you wouldn't usually pick a NAS HD for general use, but it's a valid choice. NAS HDs are built to handle a bit of heat & vibration, and usually have a decent warranty. A 5xxx rpm speed means it will probably run cooler, quieter, last longer. Yes it is a bit slower, but it's tolerable at sizes of >1TB. Suggestions:

https://old.reddit.com/r/DataHoarder/comments/hsbmnr/wd_red_nas_helium_vs_air/

- WD Red Plus
- ST Ironwolf

Specific models change all the time, favor 5xxx rpm, **avoid SMR** (slow writing), rpm-class (WD) is [NOT rpm](https://arstechnica.com/gadgets/2020/09/western-digital-is-trying-to-redefine-the-word-rpm/). Favor mod2 sizes or multiple of 4TB HDs, since those sizes may be available for longer.

You can have a SSD. You'll get less, but faster storage for your money. Just keep in mind you might run out of space unless you also have a HD.

Run chkdsk or fsck yearly. Also, check your SMART regularly with crystaldiskinfo or smartctl.

Helium is available for high-capacity models, and may [have some benefits](https://old.reddit.com/r/DataHoarder/comments/hsbmnr/wd_red_nas_helium_vs_air/) but I slightly prefer air HDs since may be better for data recovery,

### SSD
SSDs were the hot new thing in early 2010s. In 2020, it is almost a taken. Things have come a long way since the early days, and manufacturers have learned a few lessons.

Tiers:
- Top: Samsung 860, Intel
- Good: WD Blue, Crucial MX500
- Mediocre: WD Green, Crucial BX500, Sandisk SSD plus

The difference btw good & mediocre is the inclusion of DRAM in the good tier for more speed & longevity. Good SSDs usually have a longer warranty (5y vs 3). Don't skimp out. Also, SLC > MLC > TLC in terms of speed & reliability, but at lower cost tiers, there is little choice. BTW, I haven't installed any SSDs yet in my PCs, so do your research, but my advice should be roughly in the right direction. YMMV.

SSDs are available in several formats, traditional SATA, M2 NVMe, M2 SATA, and PCI. But not all mobos can boot from PCI, and M2 SSD may have heat issues.

If you want  

#### Brackets
AAA

2.5" cases are common, if you need to externalize a M2 SSD, [cases](https://www.orico.cc/us/product/detail/7122.html) are available. Some might look like giant USB sticks.



### External HDD
Branded external HDD may have a proprietary partitioning scheme when you take the drive out, forcing you to use 1st-pty recovery services, so it's recommend to use a generic USB HD case + HD instead. Since SSDs are cheap & reliable in 2021, pick one from the suggested SSDs above.

### USB stick
AKA USB flash drive. Recommended: Sandisk ultra/extreme with metal USB plugs, NOT the standard series with plastic USB plugs which break easily. Try to buy a USB3 one. Not that they will reach those speeds, but they tend to have a write speed >=15mps. See benchmarks on https://usb.userbenchmark.com/ . And format them to NTFS for reliability.

## ODD
DVD writers go for dirt cheap, you may already have one, so there's little excuse not to have one. Also consider a BD writer so you can backup data or make BDs. USB ODDs are also possible.

## PSU
Many guides will suggest a 80+ bronze PSU. I'll suggest a semi-modular PSU (for better cable management), and a 80+ gold to save more power. You might save $20-50/year depending on how much you use your PC. Some lower watt PSU are only available in the SFX size. You can buy brackets/adaptors to fit a standard PC case. I suggest Corsair although Cooler Master or Seasonic might do. Do NOT cheap out on a PSU. You can damage your PC if you do.

- [Corsair SF450](https://www.corsair.com/us/en/Categories/Products/Power-Supply-Units/SF-Series%E2%84%A2-80-PLUS-Gold-Power-Supplies/p/CP-9020104-NA) Modular, gold. It is SFX, so you'll need to buy an adaptor
- [Seasonic Focus SGX](https://seasonic.com/focus-sgx) Modular, Gold. 
- Other modular gold PSUs are available, but I have only listed those with lower wattage

https://outervision.com/power-supply-calculator

## Monitor/Display

Most important when you're buying a monitor is that you're comfortable with the size & PPI. It's not a question, but you should be buying LED monitors since they're bright & last long. And you should have some sort of digital input for a clear picture (DVI, HDMI, DP). I have some legacy apps that might not behave well on custom DPI settings, and I want a small-ish screen so I have the Dell P2213 , which is 22", but 1050p & has USB ports. It's a discontinued product, which I got 2ndhand. If you want a new monitor with low PPI, luckily, there are now 27" 1080p screens for sale. But a bit big.

Avoid monitors with inbuilt speakers as they sound terrible and you might accidentally route audio to them (if they're connected via HDMI or DP), but not biggies if they do. You can get around this by using a DVI-DVI cable, or HDMI-DVI cable.

## Laptop peripherals

Most laptops these days don't have an ethernet port, and if you want guaranteed stable network speeds, you'll need a wired ethernet adaptor. Choices:

- [Ethernet adaptor](https://www.orico.cc/us/product/detail/3335.html)
- [Ethernet adaptor with USB hub](https://www.orico.cc/us/product/detail/4058.html)
- [Ethernet adaptor with USB hub, HDMI, and card reader](https://www.orico.cc/us/product/detail/7119.html)

NB: If you get a USB2 Ethernet adaptor then you can only enjoy 100mps network speeds. Some Ethernet adaptors with USB hub may corrupt data, so if you want to be cautious, avoid using USB storage with them.

## bootloader

GRUB supports windows, but install windows first, to avoid windows overwriting GRUB.

## HIDs

## Keyboard
Basic USB or PS2 keyboards are easy to find & cheap. For a slight enhancement, you want a keyboard with a USB hub to plugin your USB mouse & a USB stick. And optionally a palmrest for ergonomics. The Dell [KB522](https://www.amazon.com/Dell-Multimedia-Keyboard-Removable-Palmrest/dp/B003BFQF4Q) combines all these features & is cheap. If you want a palm rest for any existing keyboard, you can buy gel wrist rests, or use a curled towel, or even a draught stopper.

Mac users might be familiar with the [wired aluminum keyboard A1243](https://en.wikipedia.org/wiki/File:Apple_iMac_Keyboard_A1243.png) .  It is no longer being sold by apple, so you need to get one 2ndhand, or use replicas like the [Matias FK318S](https://matias.store/products/fk318s)

I would not recommend wireless HIDs in general since batteries have a finite life, need charging, and are an additional thing to manage.

### Mouse
You can pick any mouse, but I use the [A4tech OP-620-D](https://www.a4tech.com/product.aspx?id=229) since it has a double-click button. 

### Other

Trackballs, trackpads, and tablets exist if you want alternative, RSI-friendly input devices. Keyboards with trackpads exist. Wired Keyboards with trackpads [also exist](https://www.logitech.com/en-nz/products/keyboards/k400-plus-touchpad-keyboard.920-007165.html), but rarer/more expensive like the [HP FK218AA](https://www.hp.com/gb-en/shop/product.aspx?id=FK218AA&opt=&sel=DEF).

IF you're looking for a graphics tablet, the [Huion Kamvas](https://www.amazon.com/HUION-13-Graphics-Full-Laminated-Battery-Free/dp/B083TTQFKJ) is worth a look as many reviews say it's nice & cut-price.
