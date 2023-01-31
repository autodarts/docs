---
title: "Troubleshooting"
draft: true
language: "English"
author: ""
weight: "1"
lang: "en"
---


[comment]: <> (Fact Check / Is this still up to date?)

## Error “could not initialize board: could not warm up cam X”

{{< tabs "Install Tab" >}}
{{< tab "Linux" >}}
# Linux UVC Hack

### Error "could not initialize board: could not warm up cam X"

If you get this error, there is a way to fix it and then boot the board.

First you need to find out what kernel version you have.
```
uname -r
```  
You will get an output like "5.4.0-94-generic". You have to do the following steps based on your kernel version!
Go to the website and copy out the link with the ending ".tar.gz" to your kernel version (scroll down):

https://mirrors.edge.kernel.org/pub/linux/kernel/v5.x/

Then enter the following commands based on your kernel version:
```
wget https://mirrors.edge.kernel.org/pub/linux/kernel/v5.x/linux-5.X.tar.gz
tar -xf linux-5.X.tar.gz
cd linux-5.X/drivers/media/usb/uvc/
nano uvc_video.c
```

Now you need to add code to the file. This must be added at a specific location in the file. Most of the time you will find the entry point at line 200.

Press CTRL + SHIFT + _ and enter 200. Enter again.

Now find the place with the code

        bandwidth = max_t(u32, bandwidth, 1024);

        ctrl->dwMaxPayloadTransferSize = bandwidth;
}

Enter the following code after the " } ":
```
if (format->flags & UVC_FMT_FLAG_COMPRESSED) {
ctrl->dwMaxPayloadTransferSize = 0x300;
    
}
```   
The result should look like this:
```
                    bandwidth = max_t(u32, bandwidth, 1024);
    
                ctrl->dwMaxPayloadTransferSize = bandwidth;
        }
            
        if (format->flags & UVC_FMT_FLAG_COMPRESSED) {
        ctrl->dwMaxPayloadTransferSize = 0x300;
            
        }
    
}

static size_t uvc_video_ctrl_size(struct uvc_streaming *stream)
```

Be careful and pay attention to the correct formatting of the input!

Then save the file with CTRL + O, Enter.
Close the file with CTRL + X.




{{< /tab >}}

{{< tab "Raspberry Pi" >}}

## Raspberry Pi users only:

You still need to run this command before continuing:

    sudo apt-get install raspberrypi-kernel-headers

Now build the new kernel files:

    sudo make -C /lib/modules/$(uname -r)/build M=$(pwd) modules
    
The output should look like this:

    pi@autodarts:~/linux-5.4/drivers/media/usb/uvc$ sudo make -C /lib/modules/$(uname -r)/build M=$(pwd) modules
    [sudo] password for pi: 
    make: Entering directory '/usr/src/linux-headers-5.4.0-94-generic'
      CC [M]  /home/pi/linux-5.4/drivers/media/usb/uvc/uvc_driver.o
      CC [M]  /home/pi/linux-5.4/drivers/media/usb/uvc/uvc_queue.o
      CC [M]  /home/pi/linux-5.4/drivers/media/usb/uvc/uvc_v4l2.o
      CC [M]  /home/pi/linux-5.4/drivers/media/usb/uvc/uvc_video.o
      CC [M]  /home/pi/linux-5.4/drivers/media/usb/uvc/uvc_ctrl.o
      CC [M]  /home/pi/linux-5.4/drivers/media/usb/uvc/uvc_status.o
      CC [M]  /home/pi/linux-5.4/drivers/media/usb/uvc/uvc_isight.o
      CC [M]  /home/pi/linux-5.4/drivers/media/usb/uvc/uvc_debugfs.o
      CC [M]  /home/pi/linux-5.4/drivers/media/usb/uvc/uvc_metadata.o
      CC [M]  /home/pi/linux-5.4/drivers/media/usb/uvc/uvc_entity.o
      LD [M]  /home/pi/linux-5.4/drivers/media/usb/uvc/uvcvideo.o
      Building modules, stage 2.
      MODPOST 1 modules
      CC [M]  /home/pi/linux-5.4/drivers/media/usb/uvc/uvcvideo.mod.o
      LD [M]  /home/pi/linux-5.4/drivers/media/usb/uvc/uvcvideo.ko
    make: Leaving directory '/usr/src/linux-headers-5.4.0-94-generic'

If you received an error, you may have used the wrong kernel version.

Now execute the following commands to load the files temporarily in the kernel:

    sudo rmmod uvcvideo
    sudo insmod uvcvideo.ko
    
If you receive the following error message after entering the second command, you must disable Secure Boot. You can find the instructions here (Use Method 2): https://wiki.ubuntu.com/UEFI/SecureBoot/DKMS 

    insmod: ERROR: could not insert module uvcvideo.ko: Operation not permitted

If everything went well, start autodarts now. The cameras should now be loaded.

In this case, we have to write the change permanently into the system.
    
Enter the following commands:

    sudo rmmod uvcvideo
    sudo mv /lib/modules/$(uname -r)/kernel/drivers/media/usb/uvc/uvcvideo.ko /lib/modules/$(uname -r)/kernel/drivers/media/usb/uvc/uvcvideo.ko.bak
    ls -al /lib/modules/$(uname -r)/kernel/drivers/media/usb/uvc
    
If the output looks like this, continue:

    drwxr-xr-x  2 root root   4096 Jan 14 10:56 .
    drwxr-xr-x 31 root root   4096 Jan 13 12:38 ..
    -rw-r--r--  1 root root 164145 Jan  6 21:56 uvcvideo.ko.bak
    
Enter the following commands based on your Kernel version:

    sudo cp ~/linux-5.X/drivers/media/usb/uvc/uvcvideo.ko /lib/modules/$(uname -r)/kernel/drivers/media/usb/uvc/uvcvideo.ko
    
To verify that the file was copied correctly, enter the following command again:

    ls -al /lib/modules/$(uname -r)/kernel/drivers/media/usb/uvc
    
The output should now be displayed in the same way:

    drwxr-xr-x  2 root root   4096 Jan 14 10:57 .
    drwxr-xr-x 31 root root   4096 Jan 13 12:38 ..
    -rw-r--r--  1 root root 161608 Jan 14 10:57 uvcvideo.ko
    -rw-r--r--  1 root root 164145 Jan  6 21:56 uvcvideo.ko.bak
    
Finally, execute this command, after which the changes have been applied and are retained even after a restart of the system:

    sudo insmod /lib/modules/$(uname -r)/kernel/drivers/media/usb/uvc/uvcvideo.ko

{{< /tab >}}
{{< /tabs >}}