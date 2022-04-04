[B][SIZE=3]
# REAPER ADM proposal 3.4
[/SIZE][/B]

[B]## Changelog[/B]
3.5: More Pan, EDM Element types.
3.4: simplify, refine other sections, redo intelligent squashing of tracks. DDM/EDM variety.
3.3: in progress - intelligent squashing of tracks, reorganize
3.2: RSP tweaks
3.1: add masterful approach
3.0: initial proposal, separate "unified RSP" from main proposal

DDM = Dolby ADM
EDM = EBU ADM

[B][SIZE=3]# MAIN PROPOSAL [/SIZE]
[/B] 

BASICS:
[LIST]
[*] Any track that is 2ch or 6ch wide with NO RSP is automatically converted to a 2.0 or 5.1 bed.
[*] Any track with a RSP on it obeys the RSP settings (see later).
[*] If there is no master RSP, there must be RSP on any track with any width other than 2/6ch, otherwise the track layout is too AMBIGUOUS.
[*] If there is a master RSP, you can have track with any width, since any track's layout is just a linear subset of what's defined on the master RSP.

[/LIST]

[B][SIZE=3][/SIZE]
Reasurroundpan[/B] 

The output layout when doing DA, is thus, now a monitoring layout and not directly affecting Atmos. RSP can be inserted on tracks, or master. If the FXIO pin routing is modified, RSP receives re-routed audio as expected.

RSP has a NEW menu widget near the existing output layout for setting DA mode. Input channels sets the elements available for Atmos panning/use, and also sets the object type, if a object mode was chosen (see below). The Dolby Atmos mode has these options:

[LIST]
[*] Dolby Atmos Off. Current behavior, or can be used as a send to Atmos bed or another instance of RSP.
[*] Bed 2.0, Bed 3.0, Bed 5.1, Bed 7.1, Bed 7.1.2 layouts. These are valid options in the Atmos Renderer. LFE-less versions of 5x/7x exist, but are seldom used, esp for RPR/SMPTE contexts, hence are not included to simplify the menu.
[*] Bed 7.1.4 (Recommended minimum), Bed 914, Bed 916 . This MAY be implemented as 71 + N objects due to ADM. This is an important feature to avoid 712 syndrome, where anything routed to a 712 bed sounds un-spacious & won't scale up or down at home.
[*] Bed 71 + multi objects (1st 8 inputs bed, rest are obj)
[*] reserved 
[*] Object (mono), sets input chans to 1
[*] Object (stereo), sets input chans to 2
[*] Object (multi), no change to input chans 
[*] Follow options:
[*] Follow clip pan. Instead of taking pan automation from RSP, it is taken from clips on the track.
[*] Follow track pan. Instead of taking pan automation from RSP, it is taken from track pan.
[/LIST]

If a obj config is chosen, gain, LFE, delay, is locked to 0. The divergence control in RSP now controls the size of Atmos objects.

If a bed is chosen, they should be larger & transparent on the graphics to show bed sounds are more diffuse & may array. If a obj is chosen, the should be smaller to show obj sounds are pinpoint. We want to encourage mixers to use objs more since beds don't really scale up on home soundtracks. 

RSP has a NEW smaller near beside the DA mode menu, which shows $num_total elements, and shows the following info. If the DDM/EDM LV4 Compat Flimits are exceeded, a star * appears.

[LIST]
[*] $num_bed bed elements (total bed channels in rpp, preferably non-empty)
[*] $num_obj object elements (total obj channels in rpp, preferably non-empty)
[*] Total $num_total elements (approx)
[*] 4th item will appear: Conforms to Dolby ADM limits, OR Dolby ADM limits exceeded, objects may be reduced automatically.
[*] 5th item: Conforms to EBU ADM $LEVEL, OR EBU ADM compatiblity may be low due to very high objects, objects may be reduced later (defined later)
[/LIST]

RSP has a NEW menu which you can select the Element type:

[LIST]
[*] Universal ADM categories: _grey menu item
[*] None/Unknown
[*] Dialog
[*] Music
[*] Effect
[*] EBU ADM extended categories: _grey menu item
[*] Complete Main
[*] Bed (Mixed)
[*] LFE
[*] Voice Over
[*] Spoken Subtitle
[*] Audio Description
[*] Commentary
[*] Hearing Impaired
[*] Emergency
[*] Language: _grey menu item
[*] Chinese, Dutch, English, Finnish, French, German, Hindi, Italian, Japanese, Korean, Norwegian, Polish, Portuguese, Russian, Spanish, Swedish, Arabic, Turkish, Vietnamese, Indonedian, Tagalog, Interlingua
[/LIST]



[B]## Render dialog[/B]
[LIST]
[*] "ADM BWF" is a new option in this dialog.
[*] Sample format is lock to 48/24 only, other options might be available in the future like 48/16.
[*] New "Type" Menu: Dolby ADM, or EBU ADM for Broadcast. Difference: 714 beds are real in EDM, faked in DDM. Volume envelopes are applied to waveform in DDM, but not EDM.
[*] New "$LEVEL" Menu: DDM : Default. EDM - 5 options: Level 1 (32 elements),  Level 2 (64 elements),  Level 3 (128 elements),  Level 4 Compatibility  (1024 elements), Unbounded (unlimited elements). See https://tech.ebu.ch/docs/tech/tech3392.pdf &  https://github.com/ebu/ebu_adm_renderer/issues/43
[*]> Read-only display: $num_total elements/$LEVEL_LIMIT (approx)
[*] When render is pressed & limits are exceeded, A new dialog "ADM render may automatically reduce elements due to high element count , and may fail. Continue? Yes | No (default button)"
[*] If there is no RSP on master, despite track layouts too AMBIGUOUS (see Basics section), A new dialog "Track layouts for some tracks too ambiguous. Please insert Reasurroundpan on the following tracks, or the master. $LISTOFTRACKS . OK (default button)"
[/LIST]

[B]## Render infrastructure & intelligent squashing of tracks[/B]
[LIST]
[*] All tracks at the top level w/a master send excl empty tracks will be collected. This is now defined as "Any track(s)" for below.
[*] Collection run is done to disk, it should be done to temp FLAC/WV to minimise disk usage.
[*] All volume envs are applied due to DDM
[*] Any track with RSP instance & a defined DA bed config will be rendered with the pan law set in each RSP.
[*] Any track with RSP instance, but not a DA mode set will be converted to objects.
[/LIST]

After the collection run, The assembly run will consolidate all the audio & add metadata, only fully empty beds & empty objects will not be included. Track order/ID is implicit from RPP track order. Object/bed names will be taken from Tracks.

During the collection pass, 2 stats on tracks w/ NO RSP is collected.
[LIST]
[*] When audio activity begins on the track
[*] When audio activity ends on the track
[/LIST]

Any ADM created must fit within DDM/EDM limits. If they do not, tracks may be combined.

[LIST]
[*] Tracks are considered candidates for reduction/combination, ONLY if they are adjacent, the same track width, color, folder status, #sends. 
[*] Beds can be combined to beds, and objects to objects. Any object automation is also combined.
[*] Tracks are combined ONLY if they do NOT have overlapping audio
[*] Tracks are combined starting from the 2 adjacent that have the least activity. Continuing through the list of tracks. If this is not enough to hit the limits, then 3, 4, up to a maximum of 5 etc. After 5, then ADM assembly will fail with a dialog "Too many elements, please reduce number of top-level tracks"
[*] This approach accomodates that ADM should be organized & may be edited further, and would not be too annoying to un-combine at a max of 5 sub-tracks per ADM track.
[/LIST]

[B]## File Menu[/B]
A new item "Create project from ADM" exists in the EAR suite (could we combine RPR native import with this?). A new track is created, with the ADM on it, which sends beds & objects to new component tracks. New mono wavs are NOT created on disk (unlike EAR import). (Rationale: This is fastest & most efficient.)

Bed & object tracks are created according to ADM. Any faked >712 beds are converted to real beds.

[CODE]**Is loading ADM directly OK, or do you want new files created?** [/CODE]

[B][SIZE=3]# SECONDARY PROPOSALS [/SIZE][/B] 

[B]## LFE/BMS AT Master HW Out[/B]
[LIST]
[*]HW out is searched for a 3/4>* out or 4>* out.
[*]A checkbox [.] "Correct LFE > Sub monitoring levels" appears on that 
[*]If a stereo output is checked, 3/4>* out is split into 2 mono outs.
[*]In both cases, a (new) 4>* out is boosted by 10dB on the volume slider.
[*] When the checkbox is unchecked, 10dB is subtracted from slider.
[/LIST]

Rationale: Dolby Atmos (DA) rendering includes bass management system (BMS). BMS should, at the very least, boost LFE by 10dB to become the sub output, which is applied ONLY to monitoring, and NOT the soundtrack. BMS Optionally includes bass redirecting bandsplit filters for the rest of the chans, we can skip that for a simple implementation.

[CODE]**Do you want LFE/BMS AT Master HW Out?** [/CODE]

[B]## unified RSP settings[/B]

### Project Settings Dialog
The PS dialog, Advanced tab, has a NEW section called surround. New settings:
[LIST]
[*] Surround pan law: all options available in RSP. The default is -3dB.
[*] Output layout: all options available in RSP (custom is grabbed from the master/1st RSP instance ). The default is 5.1.
[/LIST]

We do need 2 different pan law settings, since they apply in different contexts, and 2.0 pan law has some unintuitive & undesireable consequences such as affecting volume reduction of track folders.

### Reasurroundpan
[LIST]
[*] Pan law has a NEW option & default, called "Project default", the actual value which is set in Project settings (PS). 
[*] The output layout has a NEW option & default, called "Project default", the actual value which is set in Project settings (PS).
[/LIST]

This is similar to the Reapitch philosophy, and would go a huge step towards a definitive "master" layout as per other DAWs. 

[CODE]**Do you want unified RSP settings?** [/CODE]
