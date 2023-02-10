---
title: "General Errors"
draft: true
language: "English"
author: "Steve_Mutter"
weight: "2"
lang: "en"
---

## General Errors

{{< tabs "Install Tab" >}}
{{< tab "Connect/Disconnect" >}}

# Connect / Disconnect

## Rapid Connect / Disconnect after first Config

{{< hint type=note icon=gdoc_error_outline >}}
If your connection is repeatedly being disrupted and then reconnecting, and you are still able to access the configuration page, make sure that you are using a stable 2.4GHz Wi-Fi network connection. Using a 5GHz network may cause issues.
{{< /hint >}}

If you have recently set up your system and after configuring it through the Board Manager, the board is connecting and disconnecting <u>once per second</u>, it is likely that you forgot to specify a value for the camera resolution. To resolve this issue, you need to manually set the resolution in the configuration file.

You can do this by open the Configfile with this command:

```
sudo nano ~/.autodarts/config.cfg
```

{{< hint type=note icon=gdoc_error_outline >}}
The .autodarts folder is a hidden folder, so if you are trying to access it through your desktop environment, make sure that you have enabled the option to view hidden folders
{{< /hint >}}

Add the values for Resolution in the [cam] section (If you are unsure of the resolutions supported by your camera, try using 800x600)

```
width           = 800
height          = 600
```

For your initial setup, your configuration file should resemble the following

```
[auth]
board_id = Your-Board-ID
api_key  = Your-API-Key

[cam]
cam1_usb_device = /dev/video0
cam2_usb_device = /dev/video2
cam3_usb_device = /dev/video4
width           = 800
height          = 600
fps             = 30
```

{{< hint type=note icon=gdoc_error_outline >}}
The config.cfg file is dynamically generated based on your Board Manager settings, and its appearance will change if you make any modifications. The aforementioned values are a suitable starting point for initial setup, and should not be altered unless you encounter the error described above.
{{< /hint >}}

{{< /tab >}}

{{< tab "FPS" >}}

# If you are experiencing instability or low FPS, there could be many causes. Please follow the instructions to ensure that you achieve stable FPS

> Your System is too weak!

- Please make sure that your hardware meets the specified specs

> Your LED Ring is too bright

- First, make sure that your cameras are not facing directly towards the LED lights
- Lower the brightness of your LED lights by using a dimmer

> Resolution is too high

- Your system is unable to handle the camera's resolution, try lowering the resolution

> Voltage drop (Raspberry Pi only)

- Make sure you are using the original Raspberry Pi power supply, as even power supplies with similar or better specifications can cause problems. This has been roughly tested

> Poor Camera Image

- Try to adjust your camera image optimally using guvcview. As each camera is different, there are no standard settings. Start by playing around with the settings. If you get stuck, you can find help from experienced users on the Discord server. <u>There are many examples from the community for different camera types. Please use the search function before asking for help. There is surely already a discussion about the settings for the type of camera you are using. If not, please keep in mind the principle of "Think first, then ask questions.</u>

> If only one Camera drop frames

- This could be a hardware issue. Check to make sure that your camera or its cable is not damaged.
- If you are using Raspberry Pi please ensure you set Motion Scale to `4`

{{< /tab >}}

{{< tab "Slow System" >}}

# If your system is slow or you are experiencing crashes

> Your System is too weak!

- Please make sure that your hardware meets the specified specs

> Voltage drop (Raspberry Pi only)

- Make sure you are using the original Raspberry Pi power supply, as even power supplies with similar or better specifications can cause problems. This has been roughly tested

> Resolution is too high

- Your system is unable to handle the camera's resolution, try lowering the resolution

> Temperature

- Make sure that your system is not overheating. If you are using a Raspberry Pi, you should use active cooling.

> CPU Load

- Check your CPU load. If it's above 90%, try reducing the resolution, disabling the desktop environment, and disabling all non-essential processes

{{< /tab >}}

{{< /tabs >}}
