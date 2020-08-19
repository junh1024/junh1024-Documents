# Adobe Premiere Pro & Sony Vegas with REAPER comparison

## Introduction

This comparison tries to cover various core aspects in-depth, and isn't intended to be a complete workflow guide. That will be covered in another document. Adobe Premiere Pro CS4 (Vx), Sony Vegas Pro 11, REAPER 4.52. I'm using slightly older versions cuz I'm of the belief that older=faster.

## Why

I've been using Premiere for 10+ years, and REAPER for 5+. I've tried my own workflows with various degrees of pain (cuz I use very complex & awkward workflows to achieve the best quality, so I seldom export final video using a NLE). I use Premiere cuz it's famous & sensible, Pro 1, ironically on a Mac through boot camp in 2009. REAPER is a no-nonsense DAW from the writer of Winamp (Justin Frankel). It's extremely powerful & flexible. It's a bare-bones from the start. Apart from the usual VSTs, but You can write scripts & custom audio Jeusonic Effects, and install extension. I had Vegas laying around for "that one project" in 2017, and thought I'd give it a spin. I'd previously dismissed it as an "old wives trick" that people use for making mashups for Youtube (cuz YT doesn't accept video-only, and if you have a hammer, everything looks like a nail), cuz I'm surrounded by people that do that. It was surprisingly usable if you enable certain features, but also has its downsides. 80%+

## Launch

Premiere launches in xxs flat, with no annoyances. Vegas OTOH, takes anywhere x-xxs, AND includes 1 modal & 1 non-modal dialogue to annoy you. If I wanted to upgrade my GPU, I *would've done so already* so stop pestering me. REAPER, as fast as always in 5s on a cold start w/VST.

## Transport

Premiere has instant scrub with audio. Vegas has slow, sticky scrub with audio (move the playhead), or a fast scrub with audio (move the line). REAPER also has a slow scrub, but you can jump to another position by clicking.

Saving stops transport in Premiere, but transport is unaffected by saving in Vegas & REAPER.

### Jump to next cut, marker
Premiere: buttons below monitor
Vegas: \[ & \] (on current track), ctrl-arrows
REAPER: ctrl-\[ & \] (globally), \[ & \] 

## Tools

Premiere has about 8 tools with separate, but clear functions & names. Separate tools for trimming & moving, cuts, slip edit, rolling edit.

Vegas OTOH, has about 4 tools with confusing names & functions. I need to cycle through tools and hope to get a tool that's least annoying for my current aime, and there's no direct shortcut for most tools. To cut, you need to have a clip selected, then press S. To slip, you alt-drag (I didn't look up any help for this for my 1st time, I tried the REAPER method, and to my surprise, it worked). To rolling edit, you ctrl-alt drag (I needed to look this up, it's an extra step on top of REAPER).

REAPER is tooless, and like Vegas, relies on keyboard & modifiers. To cut, it's also S. So if you want to make multiple cuts, it's click, S, click, S, click, S. In Premiere, it's much easier with R, click, click, click. This is 1 thing that could be quicker, though, there might be a script for this. Rolling edit is a welcome improvement from Vegas, the rolling cursor is activated by placing your mouse across 2 touching, but not overlapping clips. Looking at the release dates, Vegas was 1999 & REAPER was from 2006 so it looks like REAPER borrows some (sensible) things from Vegas.

One thing REAPER retains from Vegas which I wish would just go away, is this obscure feature called snap-offset. If you touch it, snapping can seem to behave odd.

Vegas & REAPER: 8 & 2 on the numpad move clips up & down tracks.

## Ripple

Premiere has ripple edit as a tool, though, I've never used it much. Vegas has 3 ripple modes. There's no shortcut, which is prolly not a problem as again, I don't use much. REAPER also has 3 ripple modes, which I do use a lot, alt-P cycles between the 3 modes (off, track, all). The 3 Vegas modes are perhaps better explained with REAPER.

## Resizing
Premiere  by default keeps the source res as it, so it may apprear matted or cropped
Vegas by default resizes the source to the project res

## Blending

If the source fps doesn't match the project fps, something's gotta give, the frames. Premiere by default duplicates or drops frames. Vegas by default blends frames, which gives a blurry effect to motion. The better choice depends on the direction of conversion, but as footage is commonly 24f & your project is 30f or meme 60f, blending & Vegas is prolly worse. You can disable this by doing xx, but countless videos on YT are ruined by Vegas defaults.

## Time

Premiere mostly supports frame-based formats like, frames, feet+frames, frame-based timecode. This isn't a problem if you use tools that understand frames, but is if you don't, like FFMFPEG. There's also a problem of drift as timecode slowly drifts away from true time. This may or may not be a problem depending on the length of your project.

Vegas & REAPER OTOH, support most of the above, and beats & bars, decimal-based time. The advantage of this is that you don't need to look at the audio waveform (often small) to see the beat, just the ruler. This is invaluable for music videos.

REAPER (apart from the esoteric f+f), supports multiple BPM and meters per project. While you have the occasional song that does both, it can be helpful for films where you have multiple songs with presumably multiple BPMs, and you need to layer new audio, based on music cues.

BPM & fps are set in project settings in Vegas & REAPER by pressing alt-enter.

Newer versions of Premiere have an enlarged waveform display by chopping it in half, which looks a bit strange IMO.

Time format

## Import

If you're like me, your source footage will most likely need manipulation to get accepted by your NLE. mkv & mp4 are containers which say nothing about what's inside, although it could be H264. If you have mkv files, (unless you pay for a mkv) you will need to remux it to mp4 with FFMPEG by going

 FFMFPEG -i "source.mkv" -vcodec copy -an "source.mp4"

which tells FFMFPEG to copy the video (-vcodec copy), remove the audio (-an) to a new file. This process should be quick as there's no recoding & no quality loss.

avisynth import plugins are available for 32-bit and 64-bit Premiere, so you don't need to remux mkv to mp4 (thus saving space). You just need to make a new .avs file with dss2("source.mkv") or ffvideosource("source.mkv"). You can optionally crop, resize, deinterlace, etc. If you have 64-bit Premiere, you will also need 64-bit avisynth & 64-bit ffvideosource.

## Thumbnails

Premiere supports full thumbnails, but with every zoom or edit it re-renders the thumbnails, which takes time. Even for trivial edits such as a slip.

Vegas supports full thumbnails, but only at close zoom levels. I caches thumbnails so if you're doing a small edit like a slip, it doesn't refresh all thumbs, but just shifts them.

REAPER doesn't do video thumbnails, but there are various hacky scripts to do this.

## Audio

Premiere "supports" lossy by converting it to WAV & loading that. It's stored in a persistent cache. You can't be clever by sing ADPCM if you want smaller sizes, as that doesn't seem to work. You will prolly get lossy audio from clients sooner or later, and there's no getting round a WAV conversion.

If you have audio in Premiere just for sync purposes (not for export), then you might get away with 24k/8b . Sure it won't sound as nice as 44/16, but at least it's 4x smaller. At <40k, dither isn't helpful as it will just add and redistribute the noise within the audible region, rather than the >20k region that's available with 44/16.

Vegas & REAPER OTOH, support lossy audio native, by making a small peak file, and no additional files. Vegas' peak files are smaller tho.

Premiere & Vegas: Importing stereo gives 1 clips, but importing surround gives 6 clips.
REAPER: Importing 1 file gives 1 clip, although in some situations, you may be prompted whether to convert it to multi mono.

## Surround

Yes you can make a 5.1 mix with Premiere & Vegas but since the 14 years 7.1 has existed, & not much has been added to either. REAPER has ReaSurround, but it's too complicated & doesn't work in an expected way so I made my own 5.1 & 15.1/7.1 panners. I guess the argument goes, If you really cared about your surround, you would've done it in another app. And so there's logic which does 7.1, Pro Tools (9.1), Nuendo (11.1), and my suite (15.1). Apart from Premiere adding shitty 1oA ambisonics support & this "custom channlization thing", hasn't done much. Since 2010, I do my main audio editing outside of a NLE. My audio usually requires many channels &/ complex DSP/routing.

For those working for film I have 2 main advice: 

- For editors: Try to do a surround mix even though "the sound guys" will do surround later. You'll prolly find that more of your work/intent is kept. From Evan Schiff's article ["5.1 Temp Mixing on Star Trek Into Darkness"](https://www.evanschiff.com/bd/articles/5-1-temp-mixes-on-star-trek-into-darkness).
- For mixers: take the time to [listen to what your director wants](https://blog.prosoundeffects.com/how-to-communicate-post-production-sound-with-directors), so that they feel heard. If you're unsure, you can ask. I'm working on a multi-year long project (I'm actually the one that wanted to do a surround re-mix), I have full creative freedom over panning, but they wanted a "full-on" surround experience, but if I'm doing any dialogue changes (like, for intelligibility) I should log those changes. I asked.




## Project

In Premiere, 1 project can have multiple sequences, so you could keep multiple versions of a video in different sequences, or use one as a scrap. In Vegas & REAPER, you only have 1 sequence.

Older versions of Premiere use a XML-based format, not that many tools accept it.
Newer versions of Premiere use a binary-based format, but can export FCP XML which seems to be a "standard".
Premiere also exports CMX 360 EDL, which uses frames or frame-based timecode, not that many tools accept it.

Vegas exports TXT EDL, which is always decimal-based time,

REAPER uses a lightweight XML-like format.

REAPER can directly import Vegas TXT EDL. Be default, only audio tracks are imported, but you can trick REAPER into also importing the video tracks by replacing the string "video" with "audio" in the TXT. Then, you will have video clips, and if the video files are compatible, you can see the video edits in REAPER.

There's no direct route from Premiere to REAPER, unless you use vordio (paid tool). The demo version can work, but it has a few limitations.

REAPER doesn't support AAF/OMF.

You may also find AATranslator helpful to convert projects between different DAW/NLEs, but keep in mind only basic things are converted (like, volume & pan).

## Export

If your Premiere is old enough (like Pro 1), you might be able to also export your video to avs, so you can use whatever you like.

Older versions of Premiere, like Vegas, render directly to the output file. Newer versions, however, use Adobe Media Encoder, which might save a bit of RAM, but AME might forget your encode if there's some crashing going on between PP & AME.

In Premiere, the export dialog (with its small text) offers various presets, you can customize and save presets within that 1 dialog. Vegas however, has nice large text showing its presets, but to customize them, you need to dive into another dialog. Even though the main dialog shows a * for a changed preset, you can't save it there. You need to go into the nested dialog to save it. I find this a little unintuitive.

## Conclusion

Premiere is still a sensible choice & prolly offers a less annoying editing experience and decent in-the-box rendering options. But, if you work with music videos a lot &/ REAPER, Vegas offers helpful features. Just set ruler to bars & beats, and turn off resample.
