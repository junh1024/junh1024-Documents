# Music Delivery Guide

![Dynamic_Vs_Compressed](https://cdn.shopify.com/s/files/1/0970/0050/files/Dynamic_Vs_Compressed.png)

image: same loudness, different dynamics.

## LUFS
- LUFS is NOT a peak specification. It is a loudness specification. Thus, very dynamic audio with high peaks, can have the same LUFS as very compressed audio with low peaks (see pic above)
- There are products that claim to limit your audio to X LUFS. But I don't trust them to fully preserve dynamics. 
- The best way to target LUFS imo, is to use a master gain FX & a meter to aim for your LUFS target. A few LUs over/under is acceptable due to variations over the program or song composition. The exception is Dolby Atmos where it should be under.
- Media platforms may have LUFS specifications. The platform will automatically turn down loud songs to meet their specifications, but not all platforms will turn up quiet songs.
- Do NOT export multiple specific LUFS-targeted files. The platform will check & may change the loudness (as above). Export ONE file for all platforms. The exception is for video-only platforms like YT & vimeo. Then you need 2 files. The video file should ideally be automatically generated from your audio-only file.
- Choose a sensible LUFS target for your program. As streaming is king nowdays, I suggest LUFS -15 to LUFS -12 for music. This may mean a headroom of 1 dB, or a gain reduction in your limiter of 1 dB. Ian Shepherd [suggests](https://productionadvice.co.uk/how-loud/) "no louder than -10 LUFS short-term at the loudest moments" which accounts for variations across songs and may roughly match the above. These strategies work unless you're deliberately mixing very loud songs with very soft songs in which case a vocal/dialog-centered approach needs to be used.

See also https://old.reddit.com/r/WeAreTheMusicMakers/comments/v8ktah/seeing_way_too_much_confusion_about_lufs/ and https://productionadvice.co.uk/no-lufs-targets/

Actual start: mid-Feb 2021
