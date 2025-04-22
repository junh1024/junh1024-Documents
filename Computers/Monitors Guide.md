# Monitors Guide

## Introduction

Monitors are an unassuming but very integral but  part of your computing experience. This document will cover general aspects of monitors for home and business use, including a few reviews. There's a focus on real-world usage issues, not image quality.

## General Notes

When choosing a monitor, make sure it has the display connections you want, or at least figure out the cables & adaptors you need. Monitors may have USB ports, so access & placement is a consideration if you're regularly plugging things in and out. Also, ensure that the design isn't too distracting and fits into your environment, including from the back.

Monitors that are thin or aesthetically pleasing probably have an external power supply. This is annoying if you're moving the monitor and forget to take the power supply, so the monitor is rendered useless. So, try to get a monitor with an internal power supply that takes a standard IEC power cable.

Most monitors will have options for adjusting the tilt, and many will have options for adjusting the height through the stand. If you can't adjust the height, the workaround is very simple - just add some books under the stand.

## Monitor technologies

The first computer monitors were CRT-based. From the 2000s onwards, LCD technology became cheap enough to be integrated into monitors for the everyman. LCD technology was basically better in every way - they use less space & power, better ergonomics and sharpness. Probably the only downside is retaining sharpness with lower resolutions. CRTs have mostly become obsolete, except for some people wanting an authentic legacy experience.

From the 2000s, the lighting technology was CFL. It was okay, but the thing about CFL is that because it's fluorescent, the brightness goes down as the years pass by, and it becomes a bit dim after five years, so you'll need to replace it by then. LED monitors became popular around 2015. They last twice as long as CFL monitors, use less power, and less dimming over time. Although most LED monitors still use LCD for color rendition.

There are three main display technologies for monitors, arranged in order of cost and viewing angle: TN, VA, and IPS. They have various benefits and drawbacks, which won't be covered here. I've been using a TN monitor for many years, and I found it fine, but most of the time you'll find VA as the main technology for budget displays. 

## Dell P2213T

I purchased this in 2018 second-hand to replace an aging AOC 2216SW using TN and CFL. It would be very difficult to buy one of these nowdays. It's a 20-inch 1680 by 1050 display with a 16:10 aspect ratio. The reason I wanted to get it at this resolution and size is because the pixels would be the largest.

There are occasionally apps that just don't work well with DPI scaling and stay the same size regardless of your monitor size and DPI, so the larger your monitor, the smaller it will display on your screen. With improvements in Windows 8 and 10, incompatible apps will now scale at the cost of being more blurry, but this is no replacement for physically bigger pixels which would stay sharp all the time.

The Dell monitor is a bit heavy. The USB ports are stacked and recessed, so it is difficult to access. Apart from that, it's been a mostly fine monitor. You can change the brightness of the display using the Dell Display Manager app which is nice. This uses DDC/CI. Unsure of which version, but here is a link https://archive.org/download/dell_display_manager/ddmsetup.1.56.2110.exe 

For other monitors you can try https://github.com/nubix/ClickmonitorDDC

## Acer V246HL

The 24-inch monitor was bought second-hand. Although a consumer monitor, it has a handy VESA mount if you want to put it on a swivel for office use. There's no HDMI port. From the computer, a USB-C to DP adaptor was used, then a DP cable connected to the monitor. The DP adaptor is sometimes subject to electrical interference. Sometimes the monitor won't display an image   until the monitor is restarted. I'm not sure where along the line the fault lies. There have also been instances where the monitor will not display an image at all unless the power cable is removed and inserted again.

The monitor does have audio in and speakers, but the sound is so poor that phone speakers are probably better. If you're using this over DP connected to a computer, the default sound output device is the monitor, which is undesirable. To prevent the monitor from being used as a sound output device, you need to disable the monitor speakers via Device Manager in Windows.

## HP E24 G5

I had to choose between two monitors: this one or the AOC 24 G4. I picked the HP monitor because I didn't want gaming design, features & philosophy to permeate a monitor. Hopefully, I made the right decision.

I haven't really been looking at monitors since about 2018, and back then I was looking at second-hand monitors, so you could say I was out of the market since about 2015 or 10 years. It seems like monitors with very thin bezels are the fashion nowadays. We'll talk about that later.

The HP E24 G5 monitor is a business monitor. This is fine for my use as I do a mix of tasks that don't require fast response times, such as typing documents, research, and audio and video editing. It could probably work for gaming as well. My main interest is racing games, not FPS games.

The menu system has a lot of options and is easy to navigate with the four-way button. It has a bunch of inputs at the back, including HDMI, so you can just plug in an HDMI cable and you're off. It has two USB-A ports at the back, so it can function as a USB 3 dock or a charging station.

One gripe that I have is that even in power save mode, power is still supplied to the USB ports even in standby mode. I guess this is by design since the monitor cannot know whether the computer has monitor off to save power, or if the computer is actually off. You need to fully turn off the monitor to turn off the USB ports.

I note that the back of the monitor, even after a while of operation, is still quite cool. This may be in contrast to some business monitors in the past like the Dell Ultrasharp u2410, where the back of the monitor could get warm after short use. The stand can be a bit wobbly if you're trying to adjust it, as the stand is thinner than previous designs.

About the thin bezel design, I don't like it since it seems like the image is disappearing into the surroundings and I'm just used to old-school thick bezel designs. One workaround is to use the [CRU utility](https://customresolutionutility.net/)  to add a custom resolution of 1712 x 1080, then select that resolution in Monitor Properties > All Modes. This has a slight advantage when typing documents, as the text is closer to the center of the screen, but it would be slightly detrimental when playing media, or having to arrange windows side by side.

Overall, the HP monitor is a decent option for everyday and office work, but if you don't like its design and specific features, shop around.
