---
title: FAQ
author: Steve_Mutter
lang: en
weight: 60
aliases:
  - /faq
draft: false
---

{{< tabs "Install Tab" >}}
{{< tab "General" >}}
# General
{{< expand "What options do I have if I want an Autodarts system?" "..." >}}

As the saying goes, "Many roads lead to Rome." Since Autodarts is still a DIY project, you can either build the system from scratch on your own or seek help at specific points if you don't have the means to implement something. Please make sure to gather information here on http://docs.autodarts.io/ or on our Discord Server about the system. Many questions can already be clarified in the [⁠first-steps](https://discord.com/channels/802528604067201055/930453872391110727) or using the search function.

Option No. 1:
You want to do as little as possible yourself.
Wait until the Autodarts Vision Package is available. (Please note that a PC is not included in the package.)

Option No. 2:
You order the hardware yourself and print the camera and LED ring mounts yourself.
You can also have the mounts printed if you don't have a 3D printer. There is a free set of files in the 
[⁠3D-printing](http://docs.autodarts.io/3d-printing/) area. For more Designs you could also Search [⁠3DCults](https://cults3d.com/) or [⁠Thingiverse](https://www.thingiverse.com/).

Option No. 3:
You order the hardware yourself and build mounts for cameras and LED ring yourself.
As long as the alignment and distance of the cameras are correct, other solutions can also work, as Autodarts is designed to have as few or no hardware-based limitations as possible.

In any case, please inform yourself beforehand!
A good place to start is here:
http://docs.autodarts.io/getting-started/

{{< /expand >}}
{{< expand "Can I use a Raspberry Pi 4 with a monitor?" "..." >}}

In general, it is **not** recommended to use a Raspberry Pi 4 with a monitor. Even if you overclock and install active cooling, it could function on the bleeding edge.

{{< /expand >}}
{{< expand "Is the Raspberry Pi 5 supported by Autodarts?" "..." >}}

In general, Raspberry Pi 5 is tested and working. It can be used with a monitor. You need to use the original power supply and ensure active cooling.

{{< /expand >}}
{{< expand "Which operating system do I need to install Autodarts?" "..." >}}

There should be as few restrictions as possible to enable access to Autodarts for as many people as possible. The following operating systems are supported:

    Linux (Every Ubuntu/Debian based distribution should work)
    Windows (BETA)
    MacOS (BETA)
    RaspberryPI OS

Please choose your preferred operating system based on your skills. In the future, efforts will be made to simplify the installation and usage of Autodarts even further.

{{< /expand >}}
{{< expand "Can I Install the cameras a different way" "..." >}}

It is recommended to use the orientation as shown in the [Camera Position](https://docs.autodarts.io/getting-started/camera-positioning/) guide. The view of the most played field (20) is better for all three cameras. If you position a camera over the 20, there is a slight chance that a dart can block the view and the recognition won't work as well. However, it is up to you where you position the cameras, as long as they are 120° apart.

{{< /expand >}}
{{< expand "I only see pictures of 2 cameras in the Board Manager. What can I do?" "..." >}}

- Test if all three cameras are working by connecting them one by one to ensure there is no defective hardware.
- Ensure you use different USB buses for the cameras. (At least 2 different ones)
- Use an active USB-hub to provide enough/more power for the cams.
- Try to reduce the resolution in your board manager, 800x600 is absolutely fine.
- You could try to use the UVC Hack, if you are on Linux.

{{< /expand >}}
{{< expand "Where can I download Autodarts" "..." >}}

For the newest Release please visit our GitHub Repository:

[⁠Autodarts on GitHub](https://github.com/autodarts/releases/releases)

{{< /expand >}}
{{< expand "How to install Autodarts?" "..." >}}

Please follow the instructions referred to your operating system at:

[⁠Installation](http://docs.autodarts.io/getting-started/installation/)

{{< /expand >}}
{{< expand "What do I have to do after the first installation?" "..." >}}

Create an Account at:
https://play.autodarts.io/

Register a new board.
You will receive a Board IDand an API Key.
Please copy both keys, as you will need them during the first startup

Then follow the instructions at:
[⁠First Startup](http://docs.autodarts.io/getting-started/first-startup/)

{{< /expand >}}
{{< expand "Do I need an active internet connection to play Autodarts?" "..." >}}

Yes, since darts is a competitive game and we've made it possible to play against players from all over the world, you need an active internet connection. Even if you want to play locally against your friends, it's necessary because of the structure Autodarts is built on.

{{< /expand >}}
{{< expand "Can I play locally with my friends?" "..." >}}

Yes, you can play locally with your friends or against bots; just add them during the game creation process.

{{< /expand >}}

<!-- {{< /tab >}} -->
<!-- {{< tab "Linux" >}} -->

# Linux

<!-- {{< /tab >}} -->
<!-- {{< tab "Windows" >}} -->

# Windows

<!-- {{< /tab >}} -->
<!-- {{< tab "macOS" >}} -->

# macOS

<!-- {{< /tab >}} -->
{{< /tabs >}}
