[B][SIZE=3]
# REAPER Dolby ADM proposal 3

NEW Proposal 3, masterless & implicit (or masterful)[/SIZE][/B]

[B]## Changelog[/B]

3.3: in progress - intelligent squashing of tracks, reorganize 
3.2: RSP tweaks
3.1: add masterful approach
3.0: initial proposal, separate "unified RSP" from main proposal

[B][SIZE=3]# MAIN PROPOSAL [/SIZE]
Reasurroundpan[/B] 

The output layout when doing DA, is thus, now a monitoring layout and not directly affecting Atmos. RSP can be inserted on tracks, or master. 

RSP has a NEW menu/menu widget under the existing output layout for setting DA mode. Input channels sets the elements available for Atmos panning/use, and also sets the object type, if a object mode was chosen (see below). The Dolby Atmos mode has these options:

[LIST]
[*] Dolby Atmos Off. Current behavior, or can be used as a send to Atmos bed or another instance of RSP.
[*] Bed 2.0, Bed 30, Bed 51, Bed 71, bed 712 layouts. These are valid options in the Atmos Renderer. LFE-less versions of 5x/7x exist, but are seldom used, esp for RPR/SMPTE contexts, hence are not included to simplify the menu.
[*] Bed 714 . This is actually implemented as 71 + 4 objects due to DDM. This is an important feature to avoid 712ism, where anything routed to a 712 bed has no height depth & sounds un spacious.
[*] Bed 71 + multi objects (1st 8 inputs bed, rest are obj)
[*] reserved 
[*] Object (mono), sets input chans to 1
[*] Object (stereo), sets input chans to 2
[*] Object (multi), no change to input chans 
[*] reserved 
[/LIST]

If a obj config is chosen, gain, LFE, delay, is locked to 0. The divergence control in RSP now controls the size of Atmos objects.

If a bed is chosen, they should be larger & transparent on the graphics to show bed sounds are more diffuse & may array. If a obj is chosen, the should be smaller to show obj sounds are pinpoint.

[CODE]We want to encourage mixers to use objs more since beds don't really scale up on home soundtracks. 
Is separate bed/obj visualization parameters good for encouragin obj use Or Can you think of a better way? **[/CODE]

RSP has a NEW smaller menu beside the DA mode menu, which shows $numtotal/128, and expands to 3 read-only menu items, which show element counts:
[LIST]
[*] $num_bed bed elements (total bed channels in rpp, preferably non-empty)
[*] $num_obj object elements/118 (total obj channels in rpp, preferably non-empty)
[*] Total $num_total elements/128 (approx)
[/LIST]

[B]Keep in mind DDM specs have a obj limit of 118 & element limit of 128[/B]

[B]## Render dialog[/B]
[LIST]
[*] "Dolby ADM" is a new option in this dialog.
[*] Sample format is 48/24 only, other options might be available in the future like 48/16.
[*] NEW menu w/ 2 options:
[*]> ADM from Master
[*]> ADM from Stems (default & 2nd option)
[*]> Read-only display: $num_total elements/128 (approx)
[*] When render is pressed && $num_total > 128 || num_obj > 118, A new dialog "Dolby ADM render may fail due to high element count, $num_total > 128 , continue? Yes | No (default button)"
[*] If there is no RSP on master, despite "ADM from Stems" selected, A new dialog "Cannot find Reasurroundpan on master. OK (default button)"
[/LIST]

[B]## Render infrastructure[/B]
[LIST]
[*] If ADM from master, audio is collected pre-pan from master RSP.
[*] If ADM from stems, All tracks at the top level w/a master send excl empty tracks will be collected. This is now defined as "Any track(s)" for below.
[*] If the collection run is done to disk, it should be done to temp FLAC/WV to minimise disk usage.
[*] All volume envs are applied due to DDM
[*] Any track/channels with RSP instance & a defined DA bed config will be rendered with the pan law set in each RSP.
[*] Any track with RSP instance, but not a DA mode set will be converted to objects.
[/LIST]

Rationale: This approach maximises separation, since ADM can potentially be edited further.

For tracks w/ no RSP instance, 
[LIST]
[*] Any tracks 2-wide will be converted to a 20 bed respectively 
[*] Other widths will error since there's no 100% correct & reliable way to guess layout of arbitrary width tracks w/ no RSP.
[/LIST]

After the collection run, The assembly run will consolidate all the audio add pan automation metadata, only fully empty beds (comply to ADM?) & empty objects will not be included. Track order/ID is implicit from RPP track order. Object names will be taken from Tracks. If there are too many elements, the Export process will error "Too many elements, please send more tracks to beds, &/ consolidate beds to less beds". It will not auto consolidate to beds . For beds the name is $track-$chanprefix, For objects, the obj name is $track-$lettercounter. Examples:
[LIST]
[*] Music-L
[*] Music-R
[*] Music-C

[*] Birds-A
[*] Birds-B
[/LIST]

[B]## File Menu[/B]
A new item "Create project from Dolby ADM" exists. A new track is created, with the ADM on it, which sends beds & objects to new component tracks. New mono wavs are NOT created on disk (unlike EAR import). (Rationale: This is fastest & most efficient. This send approach offers the lower resource usage than multi clips on multi tracks.)

Bed tracks up to N width are created, track type is from ADM config, deriving track name from ADM channel name, w/o prefix. 714 tracks are derived by naming since 714 bed is a custom type.
Object tracks are typed from ADM config, deriving track name from ADM channel name, w/o prefix. Objects are grouped into tracks of N width via naming.
ADM channels w/ unrecognized suffixes are routed to new tracks.

[B][SIZE=3]# SECONDARY PROPOSALS [/SIZE][/B] 

[B]## LFE/BMS AT Outputs for master track dialog[/B]
[LIST]
[*]HW out is searched for a 3/4>* out or 4>* out.
[*]A checkbox [.] LFE > Sub monitoring levels appears on that 
[*]If a stereo output is checked, 3/4>* out is split into 2 mono outs.
[*]In both cases, a (new) 4>* out is boosted by 10dB on a slider.
[*] When the checkbox is unchecked, it goes back to 0.
[/LIST]

In most cases for RPR, ch4 is LFE. But HW sub could be routed to any ch.

Rationale: Dolby Atmos (DA) rendering includes bass management system (BMS). BMS should, at the very least, boosts LFE by 10dB to become the sub output, which is applied ONLY to monitoring, and NOT the soundtrack. BMS Optionally includes bass redirecting bandsplit filters for the rest of the chans, we can skip that for a simple implementation.

[CODE] Can you think of another/better way to implement BMS for RPR? Is it needed?** [/CODE]

[B]## unified RSP settings[/B]

### Project Settings Dialog
The PS dialog, Advanced tab, has a NEW section called surround. New settings:
[LIST]
[*] Surround pan law: all options available in RSP. The default is -3dB.
[*] Output layout: all options available in RSP (custom is grabbed from the master/1st RSP instance ). The default is 5.1.
[/LIST]

We do need 2 different pan law settings, since they apply in different contexts, and 20 pan law has some unintuitive & undesireable consequences such as affecting volume reduction of track folders.

### Reasurroundpan
[LIST]
[*] Pan law has a NEW option & default, called "Project default", the actual value which is set in Project settings (PS). 
[*] The output layout has a NEW option & default, called "Project default", the actual value which is set in Project settings (PS).
[/LIST]

This is similar to the Reapitch philosophy, and would go a huge step towards a definitive "master" layout as per other DAWs. 

[CODE]Do we need unified settings across all RSP?** [/CODE]

[B]## Render infrastructure intelligent squashing of tracks - WIP [/B]
RD: 
[LIST]
[ *] when render is pressed:
[*] If there is a track width higher than the highest online top-level RSP speaker layout selected, when render is pressed, error "track layout of tracks could not be determined, please insert reasurroundpan on the following: $listoftracks OK"
[*] When there are too many elements, "The following tracks may be consolidated to fewer beds/objects, continue? $listoftracks OK(default)|cancel"
[/LIST]

RI: 
Any other tracks will be assumed a linear subset of the highest online top-level RSP speaker layout selected OR PS monitoring layout . If track & monitoring layout is an exact subset/match of 71/712/714, it will be converted to 71/712/714, otherwise, objects. TEMPOBJ/TEMPBED will be suffixed to those tracks. 

Rationale: no RSP tracks go directly to speakers. For non-RSP tracls, It is assumed that these tracks will sound correct to the user, hence  assumption of "linear subset of RSP/PS".

During the collection pass, 2 stats on tracks w/ NO RSP is collected.
[LIST]
[*] When audio activity begins on the track
[*] When audio activity ends on the track
[/LIST]

There are 5 internal modes for track reduction. It is possible to know what mode to select to hit the 118o &128 element target due to the stats above.

Tracks are considered candidates for reduction/combination, ONLY if they are adjacent, the same track width, color, folder status, #sends. 

There should be pre-runs/tests to get the best alphabetical organization for track combination (based on 1st letter of track), rather than just the previous constraints. Like, if there are Vox, Bass, Drum1, Drum2, Drum3, Drum4, tracks, & mode 5 is selected, track combination should not be[ Vox, Bass, Drum1, Drum2] [Drum3, Drum4] even though there are tracks combined in groups of 4 in order, but should be [Vox, Bass,], [Drum1, Drum2, Drum3, Drum4] since we can clearly see there is an alphabetical link for the drum tracks. Since organization can vary depending on strategy, the number of tracks combined on average should be >= $target-1.


[LIST]
Track reduction mode:
[*]> Off
[*]> Mode 1: 2 tracks are combined, but ONLY if audio does not overlap, AND when combined, audio must follow the same order of tracks. Like, track A audio must precede track B audio in the source audio AND combined track.
[*]> Mode 2: 2 tracks are combined, but ONLY if audio does not overlap. No constraints on original order.
[*]> Mode 3: 2 tracks are combined. No constraints on overlap or order.
[*]> Mode 4: (up to) 4 tracks are combined, but ONLY if audio does not overlap. No constraints on order.
[*]> Mode 5: (up to) 4 tracks are combined, any overlap & order.
[*]> Mode 6: (up to) 6 tracks are combined, any overlap & order.
[*]> Mode 7: (up to) 8 tracks are combined, any overlap & order.

[/LIST]

[CODE]Do we need intelligent track reduction to hit 128? This is a sophisticated approach to attempt to maintain some order, but There is no guarantee that the reduction is logical, or correct layout has been assumed. Or should it just error? ** [/CODE]

[CODE]Schwa, is this doable, or should I make it less complex? [/CODE]

[B]]## New speaker layouts[/B]

[LIST]
[*] 7.1.6
[*] 9.1.2
[*] 9.1.4
[*] 9.1.6
[/LIST]

Channel order for 716: 71 AND, height front, height side, height back
Channel order for 9xx: 71 AND, front wide, height front, height side, height back. Wide is halfway btw front & sides.

These can be implemented as cubular/square layouts. Don't need the circle/ITU layouts.

[CODE]Do you want/need these new layouts?[/CODE]

[B]"## RSP Naming/layout changes"

HAS MOVED to [url]https://forums.cockos.com/showpost.php?p=2473980&postcount=74[/url] due to character limit.
[/B]

[B] ## Remarks [/B]
RSP now allows a masterless or masterful approach to DA.

I would prolly only use a masterful approach + static obj, since in RSP, circular panning isn't really automatable & canonical speaker angles differ btw circular & cubular.

But a full OBA approach could work for other people.