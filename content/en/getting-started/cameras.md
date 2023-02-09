---
title: "Cameras"
draft: true
language: "English"
author: "Steve_Mutter"
weight: "1"
lang: "en"
---

[comment]: <> (Fact Check | TO DO)
[comment]: <> (Spelling | DONE)

Autodarts supports a wide range of webcams. However, it is not recommended to just buy the cheapest cameras available. Based on the experiences of the community, we have already curated a selection of suitable cameras.

###### First, here are a few factors to consider when choosing a camera.

> FOV - The Field of View should be between 80° and 110°

> Lenses should have no Distorsion

> Low  Power Consumption

> Length of the cable (the shorter the cable, the less voltage drop)

> Stable Framerate around 30FPS

> Most systems are played between resolutions of 640x480 to 1280x720 (Higher resolutions currently have almost no effect on accuracy)

![Boards by Resolution](/statistics/images/boards_by_resolution.png)

With most cameras, it is relatively easy to exchange the lenses afterwards to achieve the desired field of view. 

Many cameras have distortion, but this can be compensated for with the right lenses. We also offer software that can be used to improve the distortion.

When considering power consumption, it is important to check the USB standards and the manufacturer's information for the platform you want to play on. In some cases, using external USB hubs with their own power supply could help.

| Specification | Voltage | Amperage | Power
| --- | --- | --- | --- |
| USB 1.0/1.1 | 5V | 100mA | 0,5W
| USB 2.0 | 5V | 500mA | 2,5W
| USB 3.o/3.1 | 5V | 900mA | 4,5W

There are even more factors that can play a role when it comes to cameras. However, these are the most important. Here are a few examples from the community that are already being used by our users and delivering good results.


[comment]: <> (| Manufacture | FOV | 30FPS @ 800x600 | 30FPS @ 1024x768 | Link)
[comment]: <> (| --- | --- | --- | --- | --- |)
[comment]: <> (| ELP USB Camera | 75° | &check; | &check; | https://tinyurl.com/3cme9664)
[comment]: <> (| MOERTEK MC920 Streamcam | 85° | &check; | &check; | https://tinyurl.com/2bh6wnc7)
[comment]: <> (| Pasonomi*¹ | 110°  | &check; | &check; | https://tinyurl.com/2p9fverc)
[comment]: <> (| Logilink UA 0378 | 100° | &check; | &check; | https://tinyurl.com/7m7ntyd3)
[comment]: <> (| ELP OTG Wide Angle | 100° | &check; | &check; | https://tinyurl.com/y4emp7yt)


[comment]: <> (| Manufacture | Description | Requires "distorsion.json" | Platform | Kernel Hack)
[comment]: <> (| --- | --- | --- | --- | --- |)
[comment]: <> (| Aukey | PC-LM1E | X | Raspberry Pi 4 | X)
[comment]: <> (| MOERTEK | MC920 Streamcam | X | Raspberry Pi 4 )
[comment]: <> (| MOERTEK | MC920 Streamcam | X | Fujitsu Futro 920s 414GC | X)
[comment]: <> (| ELP | 2MP USB Cameramodule 1080P H.264 Webcam Low Light 100° | X | X )
[comment]: <> (| Waveshare | 2MP USB Cameramodule OV2710 145° | &check; | Raspberry Pi 4 | &check;)
[comment]: <> (| Waveshare | 2MP USB Cameramodule OV2710 100° | X | Raspberry Pi 4 |&check;)
[comment]: <> (| Pasonomi | 110°  | &check; | Raspberry Pi 4 | X)
[comment]: <> (| VESSTT | Webcam 1080P | &check; | Raspberry Pi 4 | X)
[comment]: <> (| IRARUCQ | Webcam 2K | &check; | Raspberry Pi 4 | X)
[comment]: <> (| Nortec | 1080P | &check; | Mac Mini | X)
[comment]: <> (| Nortec | 1080P | &check; | Ubuntu Desktop | X)
[comment]: <> (| Arducam | 8MP IMX219 Cameramodule | X | Raspberry Pi 4 | X)
[comment]: <> (| Lycander | USB Webcam | &check; | Asus eeePC 1012p | X)
[comment]: <> (| ZYXH | OV9732 Cameramodule 100° | X | Raspberry Pi 4 | X)
[comment]: <> (| Garosa | OV3660 Cameramodule 110° | X | Raspberry Pi 4 | X)
[comment]: <> (| ZYXH | OV9732 Cameramodule 100° | X | Raspberry Pi 4 | X)
[comment]: <> (| Logilink | UA 0378 100° | &check; | Raspberry Pi 4 | X)



[comment]: <> ({{< hint type=hint icon=gdoc_info_outline >}})
[comment]: <> (X = Is not needed | &check; = Is needed)
[comment]: <> ({{< /hint >}})

# Camera Comparison

| Stars [0-4]|Scal [1-5]|Picture|Company|Type|Price [EUR]|FOV [°]|Distortion|Overexposure|Settings|Autofocus|Pro|Contra|Info|
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|4|1+|![img](/camera-comp/images/elp_otg.png)|ELP|OTG HD 5mp|60|100|None|None|Manual|No| hard + heavy / absolutely high quality / no need for distortion.json / very solid housing / 3m USB 2.0 cable / tiny + small / very high quality CMOS Lense |expensive|purchase recommendation with small problems|
|4|1.5|![img](/camera-comp/images/mortek_mc920.png)|MOERTEK|MC920 1080P HD|8 - 18|85|Nearly none|No|Auto|Yes|very solid / looks like Logitech C920 / high quality packaging / own homepage / big company in china / very cheap / no need for distortion.json||purchase recommendation|
|3|2.5|![img](/camera-comp/images/ahnunva_c5.png)|Ahnunva C5|HD 2K 1080P|23|130|little|little|Manual|No|tiny + small / solid worked|needs >40cm distance from board / problems with manual focus / needs distortion.json||
|2|3.5|![img](/camera-comp/images/anke_power.png)|Anke Power|1080P HD|16|110|Yes|No|Auto|Yes|massive + stable|still too mutch distortion / too expensive / needs distortion.json|no purchase recommendation|
|1|4|![img](/camera-comp/images/irarucw_2k.png)|IRARUCW|2K HD|16|120|Yes|No|Auto| Yes|| needs >45cm distance from board||
|1|5|![img](/camera-comp/images/aode_1080.png)|AODE|1080 HD USB 2.0|10|90|Yes|Yes|Auto|Yes| massive + stable| still too mutch distortion / too expensive / USB problems (defect)|no purchase recommendation|




###### Cameras that doesn't work properly

| Manufacture | Link
| --- | ---|
| Rollei R-Cam 100 | https://tinyurl.com/mwj7uvrd 
| Makoty Webcam | https://tinyurl.com/4e5pmtjy
| GuangTouL Webcam | https://tinyurl.com/3dek8m2a