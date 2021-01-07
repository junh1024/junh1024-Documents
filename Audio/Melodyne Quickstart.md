# Melodyne Quickstart

## Introduction
Melodyne is a tool for pitch editing and extracting melodic material, particularly vocals. It also claims to be a DAW. It analyzes the music and notes are displayed as blobs. It can be used for pitch correction of lead vox, but if you want that you'll probably stick a auto-tune in your DAW.

The actual use of Melodyne is hence for manipulating polyphonic material. But with analyzing polyphonic material there will be errors. Unfortunately, the manual shoves this very important info at the back. I'll show you what you need to get started quickly. This Quickstart is aimed at Melodyne 4. You will need the Studio Edition for the multi-track capability.

## Competitors
In the spectral editing arena, we have:
- Very manual: Adobe Audition & Izotope RX, good for small, quick edits
- Quite manual: ISSE & spectralayers, good for percussion and areas you can draw a box around
- Quite automatic newface: Hit n mix Infinity, this is a direct competitor to Melodyne, but I was unimpressed & didn't figure it out

## Scenario
Let's say you an artist overdubbed some BVs on a hardware sampler and there are no separate parts (real scenario). You can't further separate it by stereo means. You can also use Melodyne to separate LVs from BVs even in mono, as it works completely in the frequency domain (not stereo imaging).

## Instructions
1. You want to give Melodyne the optimal starting materials. If L & R have separate notes & you import them as a stereo pair, Melodyne will analyze it holistically & you'll get crap results. Split the stereo & import on separate tracks if they have quite different notes. Set the BPM of the song in the box to the right of the metronome icon. Drag your WAV files to start at time 1 into the top pane.
2. The analysis will be somewhat WRONG, particularly on polyphonic stuff. Enter "note assignment mode" with ctrl-shift-N, or click on the spanner icon. Rows will now glow yellow. The display well outline potential notes with hollow blobs. You can enter & exit note assignment mode as many times as you like. In "note assignment mode" , NO audio is changed, only the notation of the audio. We are fixing notation mistakes due to analysis errors. This is important to do now, so that when we actually edit & delete/separate notes, the right notes will be edited.
![pic](https://assets.celemony.com/assets/d/6/b/asset-core-resize-4748132252132040362.3b.png)
3. Press a note to solo that note. Click at the top of the ruler in the lower editing pane & press space to play to hear the notes of the audio. Unfortunately, Melodyne doen't offer an option to return playhead to start position. You may need to File > Preferences > Audio, choose the DirectX audio device and change the buffer size so that playback doesn't sound glitchy.
4. Use the scroll bars. Middle-drag on a bar to scroll, or drag the edges to zoom.
5. Double-click on blobs to deactivate wrong notes, and double-click hollow blobs to activate missed notes. You can draw a box around multiple notes to batch change them. Energy will be redistributed to other notes. Alt-drag a blob to redistribute its pitch.
6. You can drag the brackets around the notes to change the length of notes, but that's not suggested as weird things can happen. The view of blobs may now differ between normal mode & note assignment mode.
7. You can save your Melodyne project at any time with ctrl-S. It's advised to make several copies of your projects at different points as it's not always possible to undo steps.
8. Once you are happy that the notation is correct, you can exit "note assignment mode" with ctrl-shift-N. Save/copy your project. The rows will now turn grey.
![pic](https://assets.celemony.com/assets/6/d/a/asset-core-resize-6358423520247063988.5b.png)
9. In the top track pane, right-click on your corrected track and duplicate it. You can rename your tracks in the bottom left pane in the track tab if you wish.
10. In the track pane, for the top track, make sure that the orange mini-blob on the left is highlighted, and on the bottom track, there are no highlights around any mini-blobs. This ensures you are editing on only the top track.
![pic](https://assets.celemony.com/assets/c/e/9/asset-core-resize-4753951566654993931.png)
11. You should be exited out of "note assignment mode" as per step 8. You will now be making changes in "editing mode". In this mode, edits WILL change the audio.
12. Delete some notes on the bottom editing pane. If you are separating BVs, I suggest deleting the top notes and saving only the bottom note. This style is a bit counter-intuitive, but I think it can give a better result. Alternatively, you can do the reverse.
13. Activate the bottom track, by making sure that the only highlighted mini-blob is on the bottom track.
14. Delete the notes that you didn't delete in the previous 2 steps.
15. Repeat steps 9-14 as necessary, making enough tracks to have 1 simultaneously note on each track.
16. File > Export, - Individual file, Export.
