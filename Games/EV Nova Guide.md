# EV Nova Guide
*by junh1024*

## Introduction

EV Nova is a space adventure game, released in 2002 for Mac OS classic & X, and 2003 for windows. There are a few small differences, prolly bugs, but otherwise almost the same. Most of the story is told through text. It was published by Ambrosia Software, founded in 1993 and defunct in 2017. It's a bit astonishing that an indie software company lasted 25 years. Although it's the third game in the Escape Velocity series, it features a different story/universe. Returning players from EV/EVO will notice the many graphical & gameplay/QoL improvements. See [Appendix I](https://github.com/junh1024/junh1024-Documents/blob/master/Games/EV%20Nova%20Appendix.md#appendix-1) for a comprehensive list.

![pic](https://vignette.wikia.nocookie.net/evn/images/c/c9/Ships.png)

There are 6 major govenments in the game you can "join", and some factions within each. The Federation has become corrupt with its power but they cover the center portion of the map (roughly anagulous to "the Empire" in Star Wars), and so a simplification could be everyone else vs the Federation. We assume you have done Barry's tutorial, or at least know how press buttons & know what they do. This guide is slightly spoilerific to cover some pitfalls & nasties that you may experience so you can avoid them. If you don't want that/want a much shorter guide there is Aggro's [guide](https://evn.fandom.com/wiki/AgGro%27s_New_Pilot_Guide). Images taken from EVN wiki. This guide will cover several objectives:

- Decent money
- Decent ship
- Combat record
- Without using cheats/plugins or 3rd-pty profiles

## Experience

The game, in terms of a modern experience, hasn't aged well. You will need 3rd-pty hacks to get widescreen, and works better at lower resolutions since HiDPI wasn't really a thing in 2002, unless you have a big monitor. If you have an unregistered copy, many things are limited. Outfits, ships, boarding actions, storyline progress, modifying game files, and loading plugins. And a overpowered ship that shoots you down after the trial period. But Ambrosia Software is now defunct so you can't pay for it. It is highly suggested you somehow coax the game into thinking your game is registered otherwise your experience will be very bad. Also, a quicktime dependancy for an app on windows was acceptable in 2002, but now even apple have deprecated it. There is a quicktime dll stub pack that you can use for windows to avoid installing all of QT. Also, the accented characters for resource types have also not gone well for plaintext files over to windows, as mac & win default to different codepages.

## Plugins
The game also allows plugins to be installed. They can modify the game to add new ships, outfits, missions, and cheats, to completely replacing the game scenario. There are graphical enhancements like Colored_Targets & ShieldBubbles. I'll mention a few others that can improve your game experience throughout the guide. I'll also suggest the Neoplanets & Full screen map plugins, which make planets & maps larger, respectively. You can get plugins & guides from http://www.cytheraguides.com/archives/ambrosia_addons/evn/ . [ARPIA2](https://www.arpia.be/arpia2/) could be thought of a sequel to EVN since the author was inspired by EVN, and some of the EVN staff worked on ARPIA2 graphics. There are [some TCs](https://evn.fandom.com/wiki/Total_Conversions) .

## Mechanics

- To get a good ship, you need credits
- You can get credits by doing missions, trading, or mining.
	- You can do regular passenger/cargo, or business United/Sigma shipping missions. See story section for more details.
	- Trade commodities like food, medical, metal, etc. Buy low & sell high.
	- I have found mining to be tedious & unprofitable, and there's a risk of making ships mad at you should your mining laser accidentally hit them
- Unlock better outfits & ships by allying with a government and completing their storyline
- To start a storyline, you probably need a combat record
- To get a combat record, you need to destroy ships
- But if you destroy arbitrary ships you will prolly get hated by major government(s)
- Raising your rating with one government (even by destroying pirates) may decrese your rating with its enemies 
- If you get hated, ships of that government may attempt to destroy you & forbid you from landing, unless you pay a bribe
- The game auto-saves to your pilot file when you take off. It's advised to make regular pilot backups.
- If you are killed, just reload your pilot to revive them (unless you have strict play)
- If you manage to escape via escape pod when your ship is destroyed, your record with governments (good & bad) will be cleared, but your combat rating stays

## Shortcuts

Shortcuts are vital to playing the game. Make sure you memorize most of what's in the keyboard preferences so you can quickly react when things go awry. They're [apparently based on X-Wing](https://www.youtube.com/watch?v=oYMZQINXW_s&t=110) from 1993. There are also keys to activate services when you land so you can like, trade quicker. You can mostly have 2-3 dialogs onscreen simultaneously, so you can check your profile while you trade. Some shortcuts that aren't mentioned in the prefs:
- Shift-click to plan a route on the map
- Alt-click buy/sell during trading/outfitting to buy/sell the max amount
- Alt-Y to communicate w/ a planet while you have a ship selected
- 1-4 to select different planets in the system
- Having no target selected while calling attack will have your escorts attack all hostile ships

## Sense
- These things still make no sense in the game (EV Nova 1.0.10 w32). I don't think you can make plugins to fix all of this.
- The mission debriefings talk about payment into your account as if it was an entity that's not on your ship. However, when pirates board your ship, they can steal your credits as if your credits were on your ship.
- If you have Solar panels, no matter how sunny a day is or how long you spend unloading cargo on a planet, they will only recharge in space. You also get auto-recharging when you reach T2 in the Vell-os storyline, but fuel is still not free.
- If you bribe a planet to let you land and then target another ship, the planet will forget you paid, but credits have already been deducted from your account.
- Regular manoeuvering speeds up your ship forever (until you make a change). But Afterburner speeds up your ship only temporarily. 
- Missions only refresh when you land on a different planet, not every day
- EVN can't distinguish btw created escorts & launched/standalone ships. When you get the ability to create dart, hailing them will get responses like a regular ship.
- Slow ships as escorts magically move (but not turn) as fast as you do
- Customized ships revert to a default configuration & color when you make them escorts (might be a bug on w32)
- Ships come with cargo space, except when you buy them as fighters (c'mon, you can spend a few extra minutes to load cargo on your fighters right? it would make the game more intredasting with the possibility of losing cargo if your fighters die. This should be easy but tedious to implement)
- NPCs can seem to land & stay on unlandable planets, unlike yourself.
- Ships with 2 weapon exit points will always fire with both, even when theres only 1 weapon fitted (would need lots of conditional hacks to fix this, like a crons/mission/onbuy to give you another weapon if you buy a single weapon)
- And obviously, weapons in space make a lot of sounds, but you should hear almost nothing (p. much every fictional space work gets this wrong).
- Few more [here](https://www.deviantart.com/scout29/art/EV-Nova-Bloopers-62436985)


## Trading

![TradeCenter](https://vignette.wikia.nocookie.net/evn/images/5/56/TradeCenter.jpg)	![]()

I initially dismissed trading is not a very good way of making credits because there are ships in the game that you get the impression of having traded their entire lives but they never have more than anything than a heavy shuttle. But you can do much better than this in just a few hours.

- Buy Luxury goods on Europa (Sol), and sell them on Earth
- Medical supplies  on Earth (Sol) >  Equipment on Port Kane (Kania) > Luxury goods on Europa (Sol), modified Barry route

Those 2 are some trade routes I have used. You start out with a Shuttle, but you can hire Cargo Drone(s) when you feel comfortable. Used escorts can be cheaper. Move on to Terrapins, IDA Frigates, then Pegasi as you accumulate credits. A Leviathan is not suggested since "they hold 4x as much cargo as a Pegasus, but cost 6x as much" (EVula Survival Guide). Terrapins are terrible if you're driving them yourself because it's so frustrating to land 1. But not if it's being driven by the CPU. Keep in mind that you need some credits in reserve because you will need to pay your escorts daily. Otherwise they will defect and you will lose your cargo. When you get 10-20M cr, it's time to buy a good ship.

Old EVN guides may mention about a route by buying Opals from Thror and selling them on Thraine known as the imfamous "gefjon run". Unfortunately over a few patches from 1.01 - 1.05, pirates were added & the run removed.


## Ship

Different ships are different sizes & attributes, which influences their handling and weapon/cargo capacity. Taken from Sapphire's [Ship Guide](https://gamefaqs.gamespot.com/pc/562562-escape-velocity-nova/faqs/23469) , Many ship configurations fall into 1 of 2 categories:
1. Small & Fast Pocket Rocket, or
2. Big & slow battlestation

Small ships in general can't take many hits, but they're not annoying to land & manoeuver. Larger ships can take more hits & maybe better for close combat, but are more annoying to land & less manoeuverable. The only ships that seem to buck this trend (aka big but fast) are Vell-os or Polaris ships. They might also be inertialess. Inertialess ships take a bit of getting used to, but they're very easy to land since you don't need to turn & reverse, just brake.

Most Auroran & Fed ships are a bit boring since you see them so often. Vell-os ships are cool, fast-turning & powerful weapons. Rebel ships look cool with their green coloring. I used to drive a Pirate Enterprise/Manticore maybe with cheat plugs to make them go faster, but such a ship isn't really my style anymore. I don't like Polaris ships since they're dark & have highlighter coloring. I might discuss more about ships in the Story section.


## Equipment


## Outfits

![SB icon](https://vignette.wikia.nocookie.net/evn/images/e/ef/Nova_pict_5005.png)

I drive a Starbridge cuz you can load up on weapons to do decent damage, but still fast enough to make a quick escape (except from the smallest fighters). My preferred style is long-range combat cuz you stay out of the way of dangerous close-range weapons like the ion cannon & th.head lance, and the Starbridge can take a few, but not too many hits. So my guide will focus on such a setup. I will also focus on weapons that you can buy without any storyline. Here are common ships with rare equipment:

- IDA Frigate: Military IR jammer (Fed)
- Pirate Manticore: Ion Cannon (legal)
- Pirate Carrier: Quad Light Blaster Turret (legal)
- Pegasus, Used Good: Shield recharger (Fed)

This guide & my setup is influenced by EVN wiki & JoshTigerheart's [EVN Close Combat Guide](https://gamefaqs.gamespot.com/pc/562562-escape-velocity-nova/faqs/37758) . Consult those for a more comprehensive guide on weapons.  Many guns & outfits will make your ship slightly slower, but the effect is usually tiny and can be ignored for fast ships. You should try to get new & legal versions of equipment. New equipment won't degrade or implode, and legal equipment will pass scans. You have enough credits now. Good places to buy outfits:

- Earth
- Rimshot
- Tichel
- Rautherion
- Tuatha
- House centers in Auroran space
- Archenar will buy all your unwanted outfits.

### Offensive

If you have a small ship, buy the non-turret versions since they're cheaper & lighter. For larger ships, buy the turret versions since you can't turn fast enough (Josh's guide). I know Hellhound/Gravimetric missiles pack quite a punch, but I prefer not to buy consumable ammo weapons since you need to spend time refilling them. These weapons since they work at medium-long range. Josh says it's advisable to not use the 200mm Railgun since it does a lower damage/sec than 150mm.

- 2 Fusion Pulse Cannon
- 1 100mm Fixed Railgun
- 1 150mm Fixed Railgun

### Defensive
- 2 Matrix Steel, 3t ea: [EVN wiki](https://evn.fandom.com/wiki/Carbon_Fiber) says 1 of these is better than 3x Carbon Fiber, so I put it on. Apparently slows down your ship slightly (Josh's guide), and Price & mass of these scale up with ship size so best for smaller ships. Available from proper Auroran outfitters.
- 2 Carbon Fiber, 1t ea. To make use of the space left over.

### Sensor
- 1 Gravimetric Sensor: Makes the blobs on your radar bigger. I don't like the IFF sensor since while friendly ships are green & brighter, hostile ships are red and darker = harder to see.
- 1 Pirate Jammer: It doesn't work that well, but supposedly the best civilian jammer, and you don't need to go to Scheall to buy it. Viking has it. Apparently you can increase your jamming ability by combining different jammers.


### Fuel
- 2 Solar Panels: 3t ea. You should definitely get a fuel replenisher after you get a new ship, lest you get stuck in an uninhabited system. 1 panel would take too long to charge. A fission reactor would be better for larger ships. The sweet spot might be a Thorium reactor 8t, but you can only get that if you're in the Federation storyline.
- 1 Auto-recharger: also a must-have, saves you from pressing refuel on inhabited planets.
- 1 Afterburner: a must-have for any ship, a speed boost to zip away from projectiles & hostile ships during critical times. 

### Licenses

You need licenses to buy some things. If you're getting a Exotic Ships and Weapons License for the polaron/ion cannon, get the legal version. There is a fake forged version which doesn't work & strips your other licenses & a lot of credits.

### Upgrades
- Vectored Thrust
- Horizontal Booster
- 1 Port & Polish
- 1 Sigma Electrical Rewiring, 1 Sigma Mount Reinforcement, 2 Sigma Mass Addition: The sigma upgrades while expensive, are one of the only ways to upgrade certain aspects of your ship post purchase. You can unlock these by completing the 1st [Sigma mission. See below.]()


## Combat

To get hypergate access (and many storylines), you will need to have a combat record. Destroying arbitrary ships will prolly get you hated. You can destroy pirate ships (they tend to disable & loot), but you may get hated by pirates. But Harbor in Scheall is hostile by default. You can destroy Houseless Aurorans near/in Kipa. But although they don't have a legal rating, they can still deny you landing clearance.

You can kill Marauders instead. Marauders are also hated by all, but they don't have a planet. They tend to destroy rather than loot. In Wolf 359, a Marauders has a 10% chance of appearing. In Tichel, it's 20%, but it's also likely there are big fed botes that can take your kill.

![]()
![Board dialog](https://vignette.wikia.nocookie.net/evn/images/f/f3/Boarded_Pirate_Carrier.png)

When your ship gets down to 10% or 33% armor, you're disabled & pirates can board you can steal your credits. When you shoot down other ships to that level, you too can board ships to get their booty, or attempt to use them as escorts/your own. Fed ships tend to self-destruct rather than give up their stuff. You can improve on your capture odds by having a large ship crew &/ buying Marine Platoons. If you're shooting from long range & slow weapons it might be wise to start shooting slower as their armor lowers, since you don't want to destroy their ship. Boarding ships incurs a legal penalty. You can't board ships 2ce so might pay to shoot pirates so they don't board before you.

You can also save on fighter fees if you have an appropriate bay, by boarding/capturing, [apparently](https://evn.fandom.com/wiki/Thunderhead_Bay). You can capture specific variants like the *Light Destroyer class Thunderhead* with the imfamous Ion cannon. Finding & capturing such a ship is another story however.

**Flee & fight back aka "Monty Python Maneuver"**

These 2 strategies taken from the EVN wiki. If you have a small ship, you can't take many projectile hits, so it's wise to flee & wait till their missiles, rockets, etc run out. Then you can turn around & fight back from long range, while they run into your fire.

**Draw away, then land aka "Not the Nine O'clock News Maneuver"**

Mostly for landing on blockaded planets. Fly away from the planet, then in an arc, then fly back towards the planet. Hopefully there'll be less firing.

Most of the time I have caps lock on to speed up the game. But you can turn it off in times of need, like combat and landing in hostile areas.

**Escorts**

You can hire escorts to fight or freight from the bar. Cargo drones are very cheap. Although they can only take 1 hit, you can use them as 'meat shields' (EVN wiki). Or hire something more substantial with a gun like a shuttle or a few valkyries to defend you, possibly used. They will be defending you. Doesn't matter if they die, you live. If you care about daily expenses, you can use wormholes & hypergates to save on fees.

Now, you will be well-equipped to star a major storyline of the game.

## Story

If you want to start a particular storyline, see the excellent guide at https://www.arpia.be/walkthrough/ to see the mission requirements.

If you're ever in federation space a you're being chased by federation ships but don't think you've done anything wrong , it's time to head to auroran space. This really confused me the first time I encountered this situation.

If you have a mission to land on a hostile planet, they will waive the bribe and let you land anyway. But you generally can't choose the locations of missions, unless it's the Sigma deliveries. Those always end on Earth.

Your record with the Federation should be cleared after most storylines so don't worry too much if systems turn hostile for a while. Nonetheless, it may be helpful to kill a few baddies near Earth before/during/after the story to raise your rating. 


### United Shipping

If you hang out at a Fed bar, you'll eventually be offered the opportunity to work for United Shipping. Their missions can potentially pay well, especially the timed ones. As a perk, if you're outta fuel or need help, other shippers can help you for free.

### Sigma

![Pegasus](https://vignette.wikia.nocookie.net/evn/images/5/55/Nova_pict_5004.png)

Completing The sigma missions allow you to buy their ships, outfits, and hypergate access. I initially thought you needed cheats to get hypergate access but there is a proper way in-game. You will need a combat record of "Little Ability" to start the storyline, or "Fair Ability" to get the final hypergate mission. There may be delays of 30+ days between major missions. They start at the shipyard on Earth. Note that the final mission drops your legal rating with the Federation. If it was 0, then Earth will deny you landing & many systems will hate you, so it may help to raise your rating a bit so that you're not that hated after the final mission (but still not completely scot-free).

After the 1st mission, you'll get access to their wares. If you're driving a Pegasus/Leviathan yourself, you can do the bulk delivery missions which pay quite well. The Star Liner has one of the highest crew counts so it's good for capturing ships. It can also make an OK general ship if you upgrade it. If you're driving a Star Liner, you can do charter flights. Depending on the source/destination governments, your legal record with them may change. See [EVN wiki](https://evn.fandom.com/wiki/Star_Liner) . If you don't want to juggle your diplomacy, just don't do the missions.

The Bulk delivery missions are available if you have a Pegasus or bigger, but it's a slow ship. Here is the setup I suggest:

- Weapons:  6 100mm Fixed Railgun, Gravimetric Missile Launcher, 18 Gravimetric Missile, Sigma Mount Reinforcement, Sigma Mass Expansion, 2 Sigma Mass Addition
- Defensive: 2 Shield Recharger, Civilian IR Jammer, Civilian Radar Jammer, Pirate Jammer, 4 Carbon Fiber, Sigma Electrical Rewiring
- Handling:  2 Fission Reactor, Port & Polish, Vectored Thrust, Afterburner, Sigma Engine Tune-up
- Other: Gravimetric Sensors, Auto-recharger, , Horizontal Booster, 2 Marine Platoon

Many weapons make your ship slower, by a tiny amount. The Pegasus is already a slow ship so we don't want to make it any slower. The above weapons don't slow your ship at all, and the Gravimetric missiles are less likely to be jammed by Fed & Pirate jammers. The shield rechargers come from the Pegasus (used, good condition) ship & it's highly recommended to get that version of Pegasus. It really helps. Combining jammers apparently stacks their effects somewhat. Carbon armor doesn't slow your ship. Reactors speed up your ship by a small bit. You can add Polaris reactors if you have access. The handling upgrades w/o the reactors now make the Pegasus turn at a non-annoying speed, but acceleration & top speed is still lacking.

This setup was made to have the fastest Pegasus with only legal & common outfits. You may be up against Pirates with Ion cannons. Pirate Vipers should be gone almost instantly with the railguns. Pirate Starbridges will be gone in up to 5s. Manticore up to 10 (you will barely just retain a bit of armor). Spam the missiles as necessary. But you need to act quick to target and shoot, start the attack at range & finish it up close. Multiple pirates ganging up on you may not work. Running away may not work cuz you will may lose armor, while not gaining much distance. Or you can just add normal weapons which slow the ship down, or add an ion cannon. I was gonna suggest a light blaster & light canon to add more color to your spamming, but you need all the firepower you can get.

You may wonder why go through all the trouble of spending 7M on a slow ship just to do the sigmal bulk missions when you can drive a Starbridge, hire several Pegasi & do normal trading. Fair point. Ispz it is a bit pointless. But like anything equipped with railguns, you can take out much bigger ships at range like Fed DD/CV.

### Drop Bears

Drop Bears are an annoying quirk and will continue to annoy you after you finish the Fed, Rebel, or Pirate storylines. If you're in the Auroran storyline, they won't target you, and if you have T2 capabilities (in the Vell-os or Polaris storylines), you can fend them off. The general consequence of an attack is a few % credits stolen and 14 days lost. If you have daily pay, % of that is stolen too. Don't buy the repellent, it may increase the consequences/attacks, though there are plugs like sellableoutfits that make this less annoying.

### Probe

If you keep on entering Fed bars, you may eventually encounter some nervous scientists approaching you. You need to ferry their space probe to the Kontik system in return for good money. You will notice the Kontik system is very far away. You can jump there, or use wormholes.  Head towards Kontik and drop off the probe. Dunno if you can drop off the probe & collect palladium for sigma shipyards at Kontik, but it would certainly be more efficient.


### Vell-os

![Dart icon](https://vignette.wikia.nocookie.net/evn/images/f/f6/Nova_pict_5045.png)

EVN automatically upgrades your ship at the relevant missions in the Vell-os string, but I prefer the Dart since it's the fastest (and I change it back most times it switches). Hence, mission references to Arrow or Javelin might be wrong for me. You can change any time at a shipyard. Maybe it's a bit surprising that Vell-os ships can't cloak, given your amazing T0 abilities. But if you dislike certain outfits (aka capabilities), you need a plugin to make them sellable.

Passenger & cargo missions will pay more in a Vell-os ship for novelty reasons, but the dart cannot cargo. A dart has less shield than arrow/javelin, but more speed. So you might need to reload your pilot a few times. There's (surprisingly) little combat in this string, much of it happens in text.

After you finish the story, you will sometimes encounter a Bureau cell ambush. There's no penalty for refusing the mission, and there shuldn't be any for destroying their ships. It seems to be just a thing to pad your combat record.

### Polaris

- Again, it may help to have a good rating with the Federation during the early stages of the Polaris storyline since your rating will drop soon.
- Finding Mu'ar Haro is one mission when a red arrow won't show the destination. In Polaris space, keep on buying maps at outfitters. It's deep in Polaris space.
- The Polaris storyline has 2 branches, the A branch (which will give you the cloeaking organ only & possibly make the wriath hostile), and the B branch (which will give you the multi-jump organ too). This is chosen rather early, so make a backup if your pilot before you land on Mu'ar Haro in case you get the bad branch. Avoided with the AllGoodBranches plugin.

### Wild Geese
- "During an early Wild Geese mission, you'll get into a fight with a bunch of thugs. He won't die with this plug in place... At the end of the Wild Geese storyline, you'll have to take a peace proposal to the pirate leader McGowan." Also solvable, from the  AllGoodBranches plugin.

### Finish

When you finish a storyline, you will be teleported to the Se7vyn system where you can buy a Krestrel for 50M cr. I used to drive a Krestrel in EV (prolly obtained using cheat plugs & modded with a cheaty blue death ray), but there are more appealing ships in this game & my playing style has changed.  If you missed the opportunity to buy it, there are plugins that can take you back to Se7vyn. There are 5 other major storylines. Now you can try another one.

When you reach a combat rating of "Deadly" (by destroying lots of ships) you can try to dominate planets & systems. Domination yields a daily pay, but might make their governments try to kill you. To attempt domination, you hail a planet, and demand tribute. If you have the required combat rating, they'll send out their defense fleet, typically >100 ships. After you destroy them all, demand tribute again. Then they'll be dominated & pay up. 

You can also download more plugins to add more story. There are a few plugs which expand on the Kontik storyline, or even replace the whole universe.

### Others

There are some other minor storylines like Cunjo Hunt & Rock Band missions that can pay  some credits, but shouldn't affect your rating or other storylines. See side missions on the walkthrough.

## Conclusion
For more info on EVN mysteries like L1551, Kontik, and Kelariy, see [TWCB](https://evn.fandom.com/wiki/TWCB) and [Word of ATMOS](https://evn.fandom.com/wiki/Word_of_ATMOS) 

## Related
- [EVE-Online](https://www.eveonline.com/): A MMORPG with a much more complex economy and balance. Some ship names are the same as EVN, but look completely different. Some of them look like space stations with the stick & shaft aesthetic.
- [naev](https://store.steampowered.com/app/598530/Naev/): EV-inspired game
- [Endless Sky](https://endless-sky.github.io/): OS EV-inspired game
- [Cosmic Frontier Override](https://www.kickstarter.com/projects/cosmicfrontier/cosmic-frontier-override): Recreation of EVO, from its scenario creator, Peter Cartwright
- Other mobile games

## Appendix
### Changes

Moved to [EV Nova Appendix](https://github.com/junh1024/junh1024-Documents/blob/master/Games/EV%20Nova%20Appendix.md#changes) . Outlines changes from EV/EVO to EVN, but maybe interesting reading for new players.

### Music

- EV: [Face of the Enemy aka KT56-7](https://www.youtube.com/watch?v=lkq06k1JA4E) , production/library music, previously from Killer Tracks, now available from [UPM](https://www.universalproductionmusic.com/en-us/discover/albums/611/Drama-Volume-2) . EV starts the series with a bold, realistic-sounding theme. Though in the middle part, the orchestra smothers the rhythm section=bad. EVO in comparison, [sounds cheap](https://www.youtube.com/watch?v=WFIvLPF__L4).
- EV Galactic Scourge: [Prokofiev - Romeo & Juliet, Op. 64, Act II: No. 36, Finale. 2nd part.](https://www.youtube.com/watch?v=NOlhGc0d76c&t=74) Dunno exact version.
- EVN: [Gustav Holst - Mars](https://www.youtube.com/watch?v=PfL5w0FNnNw), played by Orcheste National de France, conducted by Lorin Maazel. My friend complains that this version is missing a bar at the start.
- For well-known classical suites like the 2 above, there's  >50 recordings of each, so it's important to also state the orchestra/conductor

The theme seems to be orchestral pieces with an emphasis on brass, perhaps as part of a suite. Apart from the OP music, EVN has been criticized for a lack of soundtrack. Russian review [via wikipedia](https://en.wikipedia.org/wiki/Escape_Velocity_Nova#Reception) . But there are some logical choices you can make. Obvious ones would be the rest of The Planets by Holst and Romeo & Juliet by Prokofiev. But there's also Richard Strauss' - An Alpine Symphony , [sample](https://www.youtube.com/watch?v=K3mKBjb0r0k) . All 3 works have several surround releases. If you want discrete, get Bernstein's Holst's Planets (but apparently the SACD release ruins the imaging of the original quad tape recording), and Ozawa's Strauss' Alpine. Haven't found a satisfactory discrete release for Romeo.

![pic](https://images-na.ssl-images-amazon.com/images/I/31Ge5zsGrvL.jpg)

### History

In 2002, EV Nova was released. I must've gotten a CD copy off Macworld or sth since 150mb was unthinkable to DL over dialup or school internet. I loved the OP music, and wanted to play it outside of EVN. I looked up the type/creator code. Oh, it's just MPEG/mp3. But what's it called? I posted a thread on the EV series/general ASW forum:

- me (as junh/junh1024): What's the name of the music used in EVN?
- A: Mars by Gustav Holst
- B: Why is this posted in the EV general, not EVN forum?
- C: $defends me posting in EV G
- me: thank you
- D: $maybe more replies, etc

My 1st ever forum post, done on a school library computer in class time. But

- Teacher: What are you doing online?
- Me: I'm trying to find out the name of a song used in a computer program (looking a bit apprehensive)

I let the trial expire, I think the CD was a 1.0x version so none of the codes I found on the net worked, and my serialbox was from 1999. Some of them mentioned this mythical MSJ place. And obv I had no way of paying as a kid.

Unrelated: mac software readmes come as simpletext documents, but some are read-only but others are editable. I wanted to edit readmes to make them neater & save space. The locked file attribute wasn't set for read-only docs so I was a bit puzzled. It wasn't until I had a look at the type/creator codes that I figured out why, the read-only ones had a type code of 'ttro'. After changing it to 'TEXT', I can finally edit them.

![Docmaker icon](https://cdn.discordapp.com/attachments/542719334678790144/762888706486566922/unknown.png)	![Docmaker icon](https://cdn.discordapp.com/attachments/542719334678790144/762864021631795231/Appdoc.png)

*Docmaker icon vs recreation from memory*

Docmaker was also a thing in the 90s, when PDFs weren't ubiquitous & you wanted to have something longer/more complex than a plain simpletext document, but wanted to make it readable on any mac. The solution was to make the document an app. I started a Docmaker document/app, but couldn't resume editing it again by double-clicking on it, cuz you can usually re-edit most documents by double-click. Didn't realize until a while later that cuz it's an app, it just simply opens as an app. To re-edit it, you need to use the Docmaker editor.

I've played EVN on & off over the last 18 years. Due to being unregistered, you can't use cheats in the form of plugins, so they must be a pilot file. I remember DLing a pilot for EV which had all planets dominated & an alien carrier. I then converted the pilot file to EVN format. EVN has a larger universe than EV, so only some planets are dominated. Domination yields a daily pay, so you can hire an escort w/o losing credits. I think I hired a pirate carrier (those are p.expensive).

due to neglect & money reasons, dad never purchased a mac for me past the hand-me-down 8600/300 (which was a slight upgrade over my 9600/200). I needed an upgrade for schoolwork, and I used another used Sony VAIO laptop. Dell optiplex GX260, iMac G5, iMac 2008. I built my own PC around 2009.

After the trial period, I let it expire & installed EV. I couldn't get much to happen, so I downloaded the Galactic Scourge plugin over 56k dialup with a download manager on my dad's 8600/300 powermac & played it on my 9600/200. Not sure how got it to my mac. Maybe Zip100 disk or CD-R. I remember driving a Hydra (cuz it's fast & powerful), and large freight courier ticks. Later on in the scenario, you can't complete some courier missions cuz the universe is splitting apart.


<img src="https://cdn.discordapp.com/attachments/542720777393274902/758167384644386848/Escape_Velocity_Galactic_Scourge_maybe.png" width="50%">

*Hydra, planet & Tick in : EV: Galactic Scourge (recreation from memory)*

In 2004, for tech class, we had to make a T-shirt with a design. He said "keep it simple". So I chose the shilouette of a Star liner. Dunno if I still have the T-shirt.

<img src="https://vignette.wikia.nocookie.net/evn/images/5/51/Star_Liner_Splash.png" width="20%">

Somewhen I started the Heeran storyline, not sure I finished it. In 2018 I started the vell-os storyline, and left it on hiatus. I also started the Fed storyline somewhen, but never finished it. I recall arresting a bunch of Mu'hari and working for "the right people".


In 2006, Apple switched to intel CPUs for their new PCs, so PPC apps needed to be emulated. I was pleasantly surprised that ASW released a UB version of EVN shortly afterwards.

In 2013, ASW had a [40% off sale](https://twitter.com/AmbrosiaSw/status/352825814330507266) , which I missed. EVN is $30 USD, but it would like double in my currency. I was hesitant to buy it. But maybe I should've cuz ASW was to fold a few years later.

In 2017, ASW went defunct. In 2020, Magia Record EN also closed shop due to "not enough whaling". Since MR is an online game, your saves are presumably inaccessible when the game closes. And due to the shaky relationship EN devs have with JP devs, there's no recourse like save transfers or pre-made saves at various points to ease the pain of lost progress (might also be hard due to content differences but anything can be overcome by willpower). In late 2020 there is another F2P game called Genshin Impact which encourages even more whaling so that'll prolly stay up longer.

OTOH, as EVN is an offline game & microsoft loves binary compatibility, it still functions in windows 10. You can convert plugins to rez, and even pilot files (but on mac). The mac UB version may be useless in a few years due to another arch shift, to ARM, and when rosetta 2 will be deprecated.


## 
Matt Burch owned a copy of [Elite](https://en.wikipedia.org/wiki/Elite_\(video_game\)) , which he'd never played cuz he lost the Lenslok protection device. But it had a very detailed manual. It left an impression on him and he finally made a game Escape Velocity as a college student, released in 199x which captured the spirit of elite. Its expandability with plugins created a community. Peter Cartwright made a scenario called Override which was published as a new game by ASW. In 2000s, a bunch of students from Australia created another scenario. Matt Burch returned to make many significant code updates, and the result is the EVN we know today. Matt would like to thank his parents for equipping him at a young age with the right tools.

https://lifeandtimes.games/episodes/files/pax-aus-19-ambrosia-sw-talk

## References
- Playing the game
- Inspecting game data with EVNEW
- Nova Bible
- Nova Reference
- EVN wiki
- GameFAQs guides as above



Started: late Sept 2020