# EV Nova Changes

## Introduction

EV Nova (2002) has many changes from EV/EVO. Split off from my main EV Nova Guide() for length reasons. This document outlines many of them.

### General
- New ships & outfits, notably, a lot more civilian & cargo ships. Ships are quite detailed, and they don't look like toys.
- A slideshow to introduce you to the universe, instead of scrolling text & percussion. Barry has a few tutorial missions for you.
- The universe is centered on several human races, unlike EVO
- Rebels are more idealistic & righteous, but less of a material presence in the galaxy (kinda like [Star Wars](https://github.com/junh1024/junh1024-Documents/blob/master/Science/Death%20Star%20plans%20Feasibility.md) . They have only 2 systems. The pirates are reduced to 1, but there are a lot of pirate ships wandering about in other systems. Rebels aren't red, but are green this time. Red is the color of the Aurorans.
- Less pop-culture references. Many easter eggs from EV are gone, but there's a few new ones. Recall your starter ship is a shuttle with no weapons. If you have a pilot named Kenny in EVO (I recall it happening in EV too, but maybe it didn't), you also get a blaster, and if Kenny dies, he has a special death string. In EVN, you get a blaster by default (no special name needed), but this egg is still there.
- Creating a plugin with a l33t resource, some game text will appear in l33tspeak. DL: [mac](http://www.cytheraguides.com/archives/ambrosia_addons/evn/Plugins/1752_l33t_plugx0r.bin)|[windows](https://cdn.discordapp.com/attachments/542720828610052106/765670429603528744/l33t_plugx0r.rez)
- The EV series have balloon help for the app icons. Since no-one uses it, it's become an easter egg. EVN has: "What started as a small pebble, Became an avalanche." (from memory & hex-search since Sheepshaver don't wanna work anymore)

### Map
- New universe, though there are a few familiar names like Spica, and Sol is still the center
- Systems are more unevenly spaced, which makes the map more interesting. About 4x more systems, and a greater fraction uninhabited, for a total of about 400 systems.
- Map regions have their own style. Fed space is hub & nodes, Auroran space is a bit messy, Polaris space is like a spiderweb, and Alien space is more even except around the L1551 nebula
- There is a bit more activity/conflict around core regions, like Sol. Sol is no longer the quiet haven it was in EV.
- Hypergates & Wormholes are a thing, you can traverse them to get same-day, no-fuel travel. Some hypergates are offline, since the opening story says some of them were damaged in the past. But there are plugins to modify the hypergate network and re-join them

### Gameplay
- EV has named NPC ships like USS Saratoga, Intrepid, SS Nelson, Aquila. EVN has different ones, like UFS Bismarck. These ships are currently implemented in Kantai Collection as of 2020.
- NPC ships now know how to land quickly, without swinging around like crazy prior
- In EV, you have 2 major governments & any mishap will immediately make a large portion of the map red. In EVN, you have 6, but big governments can be split up into 4 or more internal parts. You can make Sol mad, but you can still land in a few other places. Depending on how you view increased complexity/partitioning of governments it can be good or bad for fixing/evading your diplomacy.
- You can't buy a fake ID to make the Federation govt like you again. You have to earn it the hard way. But most storylines will reset your record with them after completion.
- Some outfits require licenses, and there are cheap & illegal versions of weapons with ceveats.
- You don't need to travel all the way to the pirate base to buy pirate outfits. Many are sold 1 jump away from Sol.
- EVN might be the 1st game to have ambient sounds in the spaceport. Also, it feels light there's some sound design going on as the weapons sound ambient & cohesive, not cheap like EV.

### Graphics
- Ships are faux-3D, but they behave very much like 2D as before. This has a side effect of making addons harder. You need to have a 3D model and rotate it in 3D. You can't just have a 2D top-down image & spin it, otherwise it won't fit in with the built-in ships, unless you replace them all. Also since ships are 3D, they have options for compensating weapon exit points.
- Ships can have running lights and ship animations when cruising &/turning. Planets can also be animated
- You can use the cursor to select objects, and a mini map how appears when you select your jump destination while cruising. Very handy.
- More graphics options for weapons to make your beam prettier
- New layout for main spaceport, and a more detailed UI overall. Different government ships have their own HUD graphics
- Colored ships. Used for CATS & shadeofblue (hyperactive forum poster & beta tester) in the default scenario, but there are plugins which make better use of this, like painting your ship.
- More varied explosions (but I never really paid much attention to explosions since they often happen off-screen)

### Missions
- Starting a storyline is perhaps easier
- Corporations now play a larger part of the game and missions can now appear anywhere, like the shipyard (for the Sigma storyline).
- You can now have ranks, displayed on your profile. You can get ranks by playing the storyline of major governments, or corporations. Some are aesthetic, but others have concrete benefits, like daily pay or discounts.
- A new Nova Control Bit (NCB) system which can add/remove ranks, outfits, ships, and random branching. There are 10,000 bits available, up from 512, which allows much more & longer storylines. I suspect the reason for this raise is due to faster PCs since EV was released. Since you need to perform many checks & very quickly to show the correct missions, ships, and outfits to the player, depending on which of the hundreds or thousands of bits are set or unset.
- The cron resource allows delays and timing between events & missions. It's an important part of (some) storylines.
 
### Combat
- Planets can & will shoot
- Ionization is a thing, caused by weapons, and makes your ship slower
- NPC ships only turn hostile, if they incur damage from you. Non-damage weapons such as tractor beams would previously anger CPU ships. Doesn't apply to escorts/fighters.
- You won't encounter an invisible wall at the edge of a system. Instead, you will wrap to the opposite edge. So you can actually run away from pursuers now. 
- You can assign different orders to different types of escorts & upgrade them
- Unsure if new to EVN, you can control ships up to 2 levels below, like, carrier escort + its fighters. More levels behave like independent ships, not under your control, no government

### Internals
- Apple started a shift to a unix architecture with OSX server in 1999 (which looks much like OS9), and OSX public beta in 2001, to finally have a modern OS, without the quirky & buggy memory model of OS9-, completing with the recently released Windows XP. As a result, EVN is 1st EV to be both OSX/OS9 native, thanks to use of the Carbon API.
- Also the 1st EV to have mac documentation in PDF, rather than a DOCMaker app to be future-proof for OSX
- The previous change would be helpful for the 1st EV game on windows, in 2003
- The mac version migrated to [ndat "at some point"](https://www.kickstarter.com/projects/cosmicfrontier/cosmic-frontier-override/posts/2970711) . Resource fork contents, but stored in data fork.  A different format (rez) is used for the windows port. Some things are different like  the CATS leviathan losing his paintjob after capture on windows (apparently).
- You can create pilotlog.txt & debuglog.txt files in the game folder, and they'll be filled in with information while the game is running. pilotlog will contain info like player stats, and mission bits set, so you can see which storyline you might be on and troubleshoot why a mission isn't appearing. debuglog will lot a lot of internal game events.
- About double the outfit types
- For more internal details, consult the Nova bible (in your EVN folder), Nova Reference by Azratax which summarizes game data, and [these](http://asw.forums.cytheraguides.com/topic/22191/a-list-of-nova-engine-eccentricities) [threads](http://asw.forums.cytheraguides.com/topic/22076/interesting-nova-engine-tidbits) of EVN quirks.

Date: mid Sept - mid Oct 2020, split from EVN guide

thanks to andrews05 for checking easter eggs