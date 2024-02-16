---
title: Distortion
author: Steve_Mutter
lang: en
weight: 6
---

Distortion correction is necessary only when your cameras exhibit significant distortion. The calibration process is performed directly through the Board Manager within the Distortion tab.

First, calibrate your cameras. If the Dartboard spider does not match, then proceed with the distortion calibration.

- Print out the calibration chessboard (https://github.com/opencv/opencv/blob/4.x/doc/pattern.png)
- Check if your printed chessboard matches the dimensions of 25 by 25.
- Glue down the printed chessboard onto an even surface.


Now, you can begin generating the distortion through the Board Manager. This process needs to be completed for all of your cameras. Simply navigate to the Distortion Tab within your Board Manager, choose your camera, and click on Calibrate. Adjust the chessboard within the blue marked ellipse until you achieve 95% coverage. Once you have sufficient coverage, the system will calibrate the cameras. Once the process is complete, click the save button and proceed to the next camera.

