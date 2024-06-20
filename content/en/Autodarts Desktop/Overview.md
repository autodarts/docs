---
title: Overview
author: Steve_Mutter
lang: en
weight: 2
draft: false
---

Here, you will get an overview of all the functions within the Autodarts Desktop Client.


## Menu Bar
On the top right, you'll find the menu bar with the following menus:

![Menu Bar](/Autodarts-Desktop/images/14_menue_bar.png) </br>
- Home (The "House" Icon) </br>
    will open the Home screen </br>

- Vision (The "Eye" Icon) </br>
    will open the vision overview (helpfull for debugging) </br>

- Configuration (The "Gear" Icon) </br>
    will open the camera configuration menu </br>

- User menu (Click on your name) </br>
    will open a sub menu </br>

## Home
![Menu Bar](/Autodarts-Desktop/images/17_home.png) </br>

On the right hand side the Home screen will show you the different board states (Throw, Takeout, Takeout detection) and the recogniced darts.

On the left-hand side, you will find controls (Restart, Stop, Reset), information about the software version, and the ability to check for updates. There's an option for Automatic Detection Updates and some external links that will direct you to play.autodarts.io, the documentation, and the official Discord server.

## Vision
{{<hint type=info icon=gdoc_info_outline >}}
The Vision screen is for debugging purposes and will replace the previous Board Manager.
{{< /hint >}}
You can choose between the "Motion Detection" or the "Dart Detection" tab. The motion tab will display the motion within your board, and the dart tab will show you the detected darts from all camera angles for each camera.
![Vision Motion](/Autodarts-Desktop/images/10_vision_motion.png) </br>

![Vision Dart](/Autodarts-Desktop/images/11_vision_dart.png) </br>

## Configuration
In the Configuration, you will find all necessary options for your cameras and calibration settings known from the setup process. Here you can choose your cameras, change the resolution, frames per second, and the camera standby time.
{{<hint type=info icon=gdoc_info_outline >}}
Please note that starting from version 0.24.0, the algorithm takes care of possible distortion in your camera lens. That means, with software versions above 0.24.0, you do **not** have to manually adjust distortion if needed.
{{< /hint >}}
Below each camera you will find four buttons with the following abilitys:

- The double arrow icon will flip your camera by 180 degrees.

- The magic wand icon will calibrate the camera.

- The left arrow icon will move the red "20" mark one field to the left.

- The right arrow icon will move the red "20" mark one field to the right.

At the bottom, you have the ability to enable "automatic calibration" and calibrate all cameras at once with the "Calibrate" button.

![Configuration](/Autodarts-Desktop/images/18_configuration.png) </br>

## User Menu
![User Menu](/Autodarts-Desktop/images/15_user_options.png) </br>

If you click on your account name, a submenu opens. Within this menu, you can reset the Autodarts Desktop client or sign out from your account.

{{<hint type=important icon=gdoc_info_outline >}}
Resetting the Autodarts Desktop Client will purge the entire configuration, and you will have to start from scratch.
{{< /hint >}}

## Bottom Information Bar
![Bottom Menu](/Autodarts-Desktop/images/19_bottom_menu_bar.png) </br>

Within the Bottom Information/Menu bar, you get real-time information about Autodarts. On the left side, you see the current status of your Board, and with the three buttons, you can restart the detection, stop the detection, or reset your Board.
On the right side you get some detailed iformation about the client

![FPS Overall](/Autodarts-Desktop/images/20_overall_fps.png) </br>
Show the FPS over all 3 cameras

![FPS per Cam](/Autodarts-Desktop/images/21_fps_per_cam.png) </br>
Show the frames per second (FPS) for each camera individually.

![Ram usage](/Autodarts-Desktop/images/22_ram_usage.png) </br>
Show the actual usage of RAM.

![CPU usage](/Autodarts-Desktop/images/23_cpu_usage.png) </br>
Show the actual usage of your CPU. If you have more than one physical core, it shows the overall usage across all cores, so it can be over 100%.

![Autodarts Desktop Version](/Autodarts-Desktop/images/24_add_version.png) </br>
Show the actual Version of the Autodarts Desktop Client.

![Detection Version](/Autodarts-Desktop/images/25_autodarts_detection_version.png) </br>
Show the actual Version of the Autodarts Detection Software.

![Bug Button](/Autodarts-Desktop/images/26_logs.png) </br>
If you click on this "Bug" icon, you will access detailed logging information for debugging purposes.

![Logs](/Autodarts-Desktop/images/27_logs.png) </br>

