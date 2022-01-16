# Using VB-Cable to broadcast game sounds through Discord for commentators
This guide explains how to install and setup VB-Cable so that commentators can listen to the game sounds through Discord.

This guide is only for OBS Studio. This will not work for Streamlabs.

## Installing
Get VB-Cable from [here](https://vb-audio.com/Cable/).

Extract the zip folder anywhere and run VBCABLE_Setup_x64.exe.

## Verifying install
To verify install, go to Settings -> System -> Sound -> Sound Control Panel.
![Sound Control Panel in settings](/imgs/sound_settings.png)

Make sure that you can see CABLE Input in the Playback tab and CABLE Output in the recording tab.

![Sound Control Panel Playback tab](/imgs/sound_playback.png)
![Sound Control Panel Recording tab](/imgs/sound_recording.png)

If you can see them, you have successfully installed VB-Cable.

## Using the VB-Cable to get audio from the game
Open your spectator client (non-lazer tournament client) without the tournament.cfg file present. 

In the options go to Audio -> Devices -> Output Device and select CABLE Input.
Audio compatibility mode is also recommended.

![osu audio options](/imgs/osu_audio.png)

## OBS Studio settings
In OBS open settings -> Audio -> Global Audio Devices -> Desktop Audio 2 and select CABLE Input.

![obs audio options](/imgs/obs_settings.png)

Open Advanced Audio Properties.

![obs advanced audio properties](/imgs/obs_advanced_audio.png)

Set Desktop Audio 2's Audio Monitoring to Monitor Only (mute output).

![obs advanced audio monitoring](/imgs/obs_advanced_audio_2.png)

## Streaming to Discord
Right click on the preview and select Windowed Projector (Preview).

![obs advanced audio monitoring](/imgs/obs_preview.png)

Resize the new window to a proper size or the Discord stream will be very blurry.

Stream the window through Discord.
