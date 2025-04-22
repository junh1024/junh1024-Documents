# VoiceMeeter Uses

## Introduction 
VoiceMeeter is a Windows software for mixing and routing audio between applications and hardware. This document will show a few situations where VoiceMeeter would be useful. VoiceMeeter standard edition is fine for most situations, but sometimes VoiceMeeter Banana is needed. Installing Banana edition also includes the standard edition.

## Mixing in Dolby Atmos using an integrated sound card

When mixing in Dolby Atmos, DAWs sometimes refuse to use your sound card because the buffer size isn't a multiple of 512. We can easily fix this with VoiceMeeter. 

1. Set your DAW output to VoiceMeeter Output
2. Set your DA renderer to Binaural if using headphones, or 5.1/7.1 if using that physical speaker layout
3. Open VoiceMeeter. 
4. Set VoiceMeeter Virtual Input to Bus A,
5. set the hardware output A1 to your physical device, be it speakers or headphones

Now, your DAW will be able to output to VoiceMeeter. This works for up to 7.1.

## Recording Meeting Audio 
We assume that you're listening to the meeting via headphones, not speakers. Otherwise, there would be feedback issues with your microphone picking up speaker output.

1. Open VoiceMeeter Banana. 
2. In Hardware Input 2, select your physical input device, which would be your microphone. 
3. In the IntelliPan panel, right-click the display to make sure that position is active, then pan the knob to the left. Your microphone will now be on the left. 
4. Set the system output device to VoiceMeeter Input. 
5. In the Virtual Input line, move that pan knob to the right. Other meeting participants will now be on the right. 
6. In Hardware Input 2, click A2 to send to the A2 bus, with all other sends disabled. In Virtual Input, click Send to A1, A2 with all other sends disabled. 
7. Right-click the cassette tape icon and enable Post Output Recording for physical bus A2. I have found 44k and 128k MP3 recordings to be acceptable. 
8. Set Hardware Out A1 to headphones. All other hardware outputs are disabled. 
9. Press Record in VoiceMeeter and check the level meters. This setup ensures that both your microphone and other participants are recorded, but only you hear the other participants on your headphones, as you are already physically hearing yourself when you're speaking.

## Adding Monitoring Effects to Audio Using Reaper as a VST3 Host 

1. Open VoiceMeeter. 
2. Set the system output device to VoiceMeeter Input. 
3. In the Virtual Inputs line, click B to send to Virtual Out. Audio in the Virtual Out Bus will automatically route to the VoiceMeeter Output Recording Device. 
4. Open Reaper. 
5. Open Reaper Preferences. 
6. In the Audio and Device page, set the input device to VoiceMeeter Output and the output device to Headphones. 
7. Create a track in Reaper. 
8. Insert your effects. 
9. Right-click on the recording icon on the track and select Input Stereo/Input 1 and Input 2. 
10. Enable Record Monitoring on the track for recording. 

## Combining laptop and desktop speakers for a better experience

My situation is unique - a mono USB speaker with some bass and stereo laptop speakers with no bass. Combining them to achieve a stereo image with a full-ish frequency response is possible with VoiceMeeter.

1. Launch VoiceMeeter 
2. In VoiceMeeter, set Hardware Out A1 to Speakers (laptop speakers) and Out A2 to headphones (USB speaker). 
3. Point the USB speaker face down into a cloth to remove high frequencies.
4. Set the windows sound output device to Speakers and adjust volume to a comfortable level
5. Set the windows sound output device to headphones and adjust volume to a comfortable level
6. Set the windows sound output device to VoiceMeeter Input. 
7. Set the VoiceMeeter EQ to bass boost +5dB, mid -5dB, treble +5dB. Or your own values to taste.
8. Repeat steps 4 to 7 as needed
9. In VoiceMeeter system settings, adjust the Monitoring Delay of A1 to taste. For me, 22ms was the sweet spot.
