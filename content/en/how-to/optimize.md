---
title: Optimize
author: Steve_Mutter
lang: en
weight: 2
draft: true
---

Here, you will find some tips and tricks to get the most out of your system

{{< tabs "Install Tab" >}}
{{< tab "Raspberry Pi Tuning" >}}

###### Memory Split

There is an SDRAM semiconductor memory on the Raspberry Pi, which is used as "shared memory". This means that the main memory of the CPU and the graphics memory of the GPU have to share the storage capacity of the SDRAM chip. On the software side, you can set how much memory should be allocated to the graphics memory of the GPU. By default, the GPU memory is set to 64 MB. The rest of 256, 512 or 1024 MB is then available for the main memory. t depends what you do with the Raspberry Pi. Basically you could say that if you can do without a graphic output, then you could set the graphics memory to 0 MByte. But it is not that easy. To boot the Raspberry Pi, the GPU needs at least 16 MB of graphics memory. You can't do less.

If you don't need the window manager because you are running the Raspberry Pi as a server or gateway, for example, then you can reduce the memory for the GPU. At least 16 MB.

The default value for Raspbian is 64 MB. If you use the graphical window manager, like LXDE, on the Raspberry Pi, then you shouldn't change anything about it. That's a reasonable value. Because some features cannot be used if there is not enough graphics memory.

Media centers, like Kodi, only work with higher values. Depending on how much physical memory is available with 128 or even 256 MB. As soon as you have video or graphics-heavy applications, this is recommended. In general, the CPU cores should have as much RAM as possible. But if the GPU runs out of memory, then there will be speed issues. For example jerky videos.

> Memory Split via Build in Configuration Tool:

```
sudo raspi-config
```

In “Advanced Options" there is the menu item "Memory Split". There you can set the memory size for the GPU. The lowest possible value is "16" MB. Recommended 64MB (still stable to work as desktopversion).

> Memory Split via Configfile:

```
sudo nano /boot/config.txt
```

Search for Line "gpu_mem=" and replace the Value with 64

```
gpu_mem=64
```

Change takes effect after reboot

```
sudo reboot now
```

{{< /tab >}}
{{< tab "Raspberry Pi Overclocking" >}}

{{< hint type=warning icon=gdoc_fire >}}

###### THE OVERCLOCK SETTINGS WILL SET THE WARRANTY BIT, AND YOU MAY LOOSE WARRANTY. DO NOT OVERCLOCK WITHOUT ACTIVE COOLING! DO THIS AT YOUR OWN RISK!

{{< /hint >}}
For medium boosting open Configfile:

```
sudo nano /boot/config.txt
```

Search for Line "over_voltage=" and "arm_freq=". Replace the values

```
over_voltage=6
arm_freq=2000
```

For maximum performance use this config

```
force_turbo=1
over_voltage=8
arm_freq=2100
gpu_freq=750
```

Change takes effect after reboot

```
sudo reboot now
```

Note: The overclock settings should be under an [all] statement or - even better -
under the appropriate selector for your Raspberry Pi, e.g. [pi4]. If you also share
the microSD card between your Pis, the overclock settings will only be applied to a
Pi that can actually use it.

![](https://github.com/SteveMutter/autodarts-Community-Docs/blob/main/source/image10.png)

More about Overclocking:

```
https://buyzero.de/blogs/news/raspberry-pi-ubertakten-pi-4-pi-400-pi-3b
```

###### USB Voltage limitation

As is well known, USB devices are almost without exception powered by the USB to whose host they are connected. No matter if USB hard disk, USB stick, WLAN adapter, mouse or keyboard. When it comes to power consumption, these devices are sometimes quite ruthless, which is no problem at the USB ports of a standard PC. Officially, USB 1.1 only allows 100 mA and USB 2.0 only 500 mA. Despite these limits, motherboard manufacturers don't give themselves the nerve to install weak USB ports. In practice, USB devices can draw much more than 100 or 500 mA. On a Raspberry Pi, powering the USB ports is a tricky business. If mouse and keyboard and maybe the odd USB stick are connected, then it's not a problem. But if you work with external hard drives or power-hungry WLAN adapters, then the power supply of the Raspberry Pi breaks down. This is not directly related to the Raspberry Pi, but to its power supply from a plug-in power supply, which is often a charger and not a real power supply. This is then quickly overwhelmed with the considerable current draw of several USB devices. For this reason, it is generally recommended that USB devices
are connected to the Raspberry Pi via an active USB hub. An active USB hub has its own power supply through which it can provide power to the connected devices. Starting with the Raspberry Pi model B+, the power supply is much more stable, especially via the USB for external devices. The B+ model also introduced a parameter that controls how much power USB devices are allowed to draw from the USB port in total. By default, the total current from the USB ports is limited to 600 mA. This limit exists to prevent the Raspberry Pi from becoming unstable and shutting down when a USB device is power hungry. In this case only the USB is switched off. In total, the Raspberry Pi is allowed to pass 1.2 A (1,200 mA) to the USB devices when the limit is lifted. However, this only makes sense if the power supply is also correspondingly powerful. To raise the current limit from 600 mA to 1,200 mA a corresponding boot parameter must be set.

Open Configfile:

```
sudo nano /boot/config.txt
```

Search for Line "max_usb_current="

```
sudo nano max_usb_current=1
```

Change takes effect after reboot

```
sudo reboot now
```

###### Boot from SSD

Enable Raspberry Pi to boot from a USB drive. The Raspberry Pi in question has to be booted once with Raspbian from an SD card.

Open Configfile:

```
sudo nano /boot/config.txt
```

Search for Line "program_usb_boot_mode="

```
program_usb_boot_mode=1
```

> Now it is important to reboot the Raspberry Pi once, so that it takes over this setting.

```
sudo reboot now
```

After that check if the parameter is set correctly.

```
vcgencmd otp_dump | grep 17:
```

Output should be:

```
17:3020000a
```

Then you can shutdown the Raspberry Pi and remove the SD card.

> Prepare USB Drive

Usually you have a set up system on a SD card. You have to save the content to an image file and then write it to the USB drive. Start up Raspberry Pi with USB drive It is important that the SD card is removed. It is privileged during the boot process. Booting from a USB drive is only possible if no SD card is inserted. Plug the USB drive with the described image into a free USB port and start the Raspberry Pi. It should then boot from the USB drive. If the drive has an activity LED, it should blink after a few seconds. This is a good sign. Troubleshooting If the Raspberry Pi doesn't seem to be booting, you should at least start it up on a monitor to check the boot process. Problems should only occur if the connected USB devices draw too much power when turned on, or if the drive controller takes too long to come on line. There is a solution for both.

{{< /tab >}}
