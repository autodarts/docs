---
title: Distortion
author: Steve_Mutter
lang: en
weight: 6
---

{{<hint type=warning icon=gdoc_error_outline >}}
**Earlier versions only.** Board Manager is the browser interface of Autodarts 0.x and is not supported from version 2 on. In version 2, everything it did is in the [Autodarts Desktop](/Autodarts-Desktop/) window, or on the `autodarts` terminal screen of a headless install (see [Installation](/getting-started/installation/)).
{{< /hint >}}

{{<hint type=info icon=gdoc_info_outline >}}
Distortion correction is necessary only when your cameras exhibit significant distortion. Distortion means the pictures taken by your cameras are warped in some way. Please note that starting from version 0.24.0, the algorithm takes care of possible distortion in your camera lens. That means, with software versions above 0.24.0, you do not have to manually adjust distortion if needed.
{{< /hint >}}

{{<hint type=important icon=gdoc_error_outline >}}
For OV9732, Mortek MC 920 or ELP OTG HD 5mp Cameras distortion is **not** needed. 
{{< /hint >}}

The calibration process is performed directly through the Board Manager within the Distortion tab.

First, calibrate your cameras. If the Dartboard spider does not match, then proceed with the distortion calibration.

- Print out the calibration chessboard (https://github.com/opencv/opencv/blob/4.x/doc/pattern.png)
- Check if your printed chessboard matches the dimensions of 25 by 25.
- Glue down the printed chessboard onto an even surface.


Now, you can begin generating the distortion through the Board Manager. This process needs to be completed for all of your cameras. Simply navigate to the Distortion Tab within your Board Manager, choose your camera, and click on Calibrate. Adjust the chessboard within the blue marked ellipse until you achieve 95% coverage. Once you have sufficient coverage, the system will calibrate the cameras. Once the process is complete, click the save button and proceed to the next camera.

