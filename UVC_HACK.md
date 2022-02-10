# UVC HACK

## Situation
The USB port sometimes is a nasty piece of hardware. It can cause you to pull your hair. In the case of "autodarts" one connects its camera's through USB to their device with its Operating System (=OS). This can be a Desktop/Laptop/RaspberryPi/etc..

In the chain of USBs and in Architecture, many devices only have 1 USB bus. Even if it has multiple connectors for multiple peripherals.

### So what do some people experience? 
Some of us buy peripherals (cameras) that claim the USB bus is totally in bandwidth. It is not by any means responsive to configs or other interventions made by software.

## Notification
Some OS and hardware have USB3.0 busses, and if you are lucky, they can handle the resolution and framerate. But most of us are not so lucky. For the last category, people can try to implement the 'hack'. We do not support Windows OS at this time. Then we recommend using a Virtual Machine with a Ubuntu 20.04.3 or higher 64-bit. Also, use the USB3.0 connectors and also use a USB3.0 hub. But you could try it with USB2.0, but then it can be the case you have to use a lower resolution and frames per second.

## Solution
So we could try to fix this situation in the camera's, but then we should have to flash the firmware and that is something most vendors do not like us to mess with.

So we could try to fix it in software like OpenCV or GStreamer. But that is sadly not supported.

So we have to fix this in the Operating System and their driver.

### Ubuntu/debian like OS-ses
#### Step 1
You have to prepare the system to place the correct files, exactly matching your OS.

##### Downloading source
```
cd /usr
sudo mkdir kernel
cd kernel

/* Remove the # in front of the 'deb-src' lines */

sudo nano /etc/apt/sources.list

/* After that reload your new sources /*

sudo apt-get update

/* Getting the source */

sudo apt-get source linux-image-unsigned-$(uname -r)
sudo apt-get build-dep linux-image-unsigned-$(uname -r)
```

##### Making a separate folder for building the new driver
```
sudo mkdir /usr/uvchack
cd /usr/uvchack
sudo cp -R ../kernel/linux-x.x.x/drivers/media/usb/uvc .
sudo chmod -R 777 uvc
cd uvc
```

##### Backup and change the Makefile
```
sudo cp Makefile Makefile.bak
sudo nano Makefile
```

##### Copy & paste this exact code in the Makefile
```
# SPDX-License-Identifier: GPL-2.0
aauvcvideo-objs  := uvc_driver.o uvc_queue.o uvc_v4l2.o uvc_video.o uvc_ctrl.o \
                  uvc_status.o uvc_isight.o uvc_debugfs.o uvc_metadata.o

ifeq ($(CONFIG_MEDIA_CONTROLLER),y)
aauvcvideo-objs  += uvc_entity.o
endif

obj-$(CONFIG_USB_VIDEO_CLASS) += aauvcvideo.o

all:
        make -C /lib/modules/$(shell uname -r)/build/ M=$(PWD) modules

clean:
        make -C /lib/modules/$(shell uname -r)/build/ M=$(PWD) clean
```

##### Change the uvc driver
```
sudo nano uvc_video.c
```

##### Search CTRL+W for fixup
At the end of the uvc_fixup_video_ctrl place this code element:
[One could also try 0x400]
```

        if (format->flags & UVC_FMT_FLAG_COMPRESSED) {
                ctrl->dwMaxPayloadTransferSize = 0x300;
        }
```

##### Clean the driver and build it
```
make clean
make
```

!! Your cams have to be connected to a USB, so the video driver is loaded

##### Remove old module
```
sudo rmmod uvcvideo
```

##### Load new module
```
cd /usr/uvchack/uvc
sudo insmod ./aauvcvideo.ko quirks=0x80
```

##### Check if module is loaded
```
cat /proc/modules
```

##### Check if 3 cams are connected [6 entries]
```
ls /dev/video*
```
