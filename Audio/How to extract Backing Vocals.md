# How to extract Backing Vocals

## Introduction
Let's say an artist gives you a vocal stem, but you need to separate LVs & BVs. I will group a few approaches, separated by time & difficulty. Try approaches starting from the top, first. Ideally, methods within each group will sound similar.

## FFT Imaging, extract sides
- 1A. In Audacity, Effect > Vocal Reduction > Remove Center . Or,
- 1B. Using the [AOM Stereo Imager D](https://aom-factory.jp/products/stereo-imager-d/) VST, turn off auto-gain & turn down center
- 1C. In Audition, use [Center Channel Extractor](https://helpx.adobe.com/audition/user-guide.html/audition/using/stereo-imagery-effects.ug.html) in "Center" mode to extract the side

## FFT Imaging, extract out of phase
- 2A. In Audition, use Center Channel Extractor in "Surround" mode, or use [my project]( https://cdn.discordapp.com/attachments/397574988657328132/774936964469358592/BV_project.sesx) , or
- 2B. In REAPER, install my Reaper-Surround suite, then use [my project]( https://cdn.discordapp.com/attachments/397574988657328132/774559955038371880/V3_Upscale_51_WGeneric.RPP) to export 6ch. Keep & discard the channels as you like.

## FFT Melodic extraction
- 3A. Use my [Melodyne Quickstart](https://github.com/junh1024/junh1024-Documents/blob/master/Audio/Melodyne%20Quickstart.md#introduction) guide, or
- 3B. Use [Hit n Mix Infinity](https://hitnmix.com/)