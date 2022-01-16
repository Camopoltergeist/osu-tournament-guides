# OBS scene layout for osu!lazer tournament client
This guide explains how to setup your OBS scene for streaming with the osu!lazer tournament client.  
Your lazer client should have already been set up before this guide.

This guide assumes you use 1920x1080 Base (Canvas) Resolution and 1920x1080 Stream area resolution in the lazer tournament client.  
Check your base resolution in OBS Settings -> Video -> Base (Canvas) Resolution.

![OBS Settings Base Canvas Resolution](/imgs/obs_base_resolution.png)

## Creating Window Capture Source for lazer
You shoud have both the spectator client and osu!lazer tournament client running during this.

Create a new Window Capture source by clicking on the plus-icon on the bottom left of the sources view and then selecting Window Capture in opened menu.

Note: Do not use Game Capture as it will have problems with distinguishing which window is which after restarting the spectator client.

![OBS Add Source](/imgs/obs_sources.png)

You can name the source anything you want but for this guide we will use the name `lazer`.

In the opened properties menu, use the following settings:

![lazer properties](/imgs/obs_lazer_properties.png)

## Adding a Crop Filter
On the lazer tournament client window there are many buttons that should not be shown on stream. We will use a crop filter to hide them.

To add a crop filter right click on `lazer` in the sources view and select Filters.

![lazer filters](/imgs/obs_lazer_filters.png)

Press the plus-icon at the bottom left corner of the opened window and select Crop/Pad.

Use the following settings for the filter:

![lazer crop filter](/imgs/obs_crop_filter.png)

Note: These settings are for 1920x1080 Stream area resolution in lazer only. You will have to adjust if this is not the resolution you use.

## Adding Chroma Key and Color Key filters
The lazer tournament client uses a green screen to show the windows from the spectator client through the lazer client by making the lazer client transparent in specific areas. To achieve this we will use a combination of a Chroma Key filter and a Color Key filter. 

Add Chroma Key and Color Key filters as you did previously with the Crop/Pad filter.

Use the following settings for the Chroma Key filter:

![lazer chroma filter](/imgs/obs_chroma_key.png)

Use the following settings for the Color Key filter:

![lazer color filter](/imgs/obs_color_key.png)

## Creating Window Capture Sources for the spectator client windows
Add a new Window Capture Source. For this guide we will use the name `client 0`.

Use the following settings:

![spectator client settings](/imgs/obs_spec_client.png)

Right click on `client 0` in the sources view and select Transform -> Edit Transform.

![obs source transform](/imgs/obs_transform.png)

Use following settings:

![obs client transform](/imgs/obs_client_transform.png)

Things to note here:
- Position
	- Left number is X coordinate.
	- Right number is Y coordinate.
- Size
	- Left number is width.
	- Right number is height.
	- This will change based on how many players is on a team.
	- Use the values below for this.

Repeat this for other clients using the values below.

## Transform values for clients
Use the values for your current `TeamSize` in your spectator client's `tournament.cfg` file.

### `TeamSize: 1`
- Client 0
	- X: `0`
	- Y: `155`
	- Size: 
		- Width: `960`
		- Height: `720`
- Client 1
	- X: `960`
	- Y: `155`
	- Size:
		- Width: `960`
		- Height: `720`

### `TeamSize: 3`
- Client 0
	- X: `240`
	- Y: `155`
	- Size:
		- Width: `480`
		- Height: `360`
- Client 1
	- X: `0`
	- Y: `515`
	- Size: 
		- Width: `480`
		- Height: `360`
- Client 2
	- X: `480`
	- Y: `515`
	- Size:
		- Width: `480`
		- Height: `360`
- Client 3
	- X: `1200`
	- Y: `155`
	- Size:
		- Width: `480`
		- Height: `360`
- Client 4
	- X: `960`
	- Y: `515`
	- Size:
		- Width: `480`
		- Height: `360`
- Client 5
	- X: `1440`
	- Y: `515`
	- Size:
		- Width: `480`
		- Height: `360`