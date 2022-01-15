# Setup with RP4, using Raspbian with Desktop

This Manual should guide you through a setup using a Windows PC to prepare the Raspberry Pi Image and then successfully start autodarts.
Its a fairly simple manual and you have to connect a Monitor, Keyboard and Mouse to your Raspberry to properly set it up.But you can disconnect it from your PC and put it over to the Raspberry if you don't have a second set of theese, you won't need it at the same time.

*Let's a go!*

___

# Needed:

## Physical
- Windows PC
- Raspberry Pi (4)  / *Monitor, Keyboard, Mouse
  - with connected Cameras to USB
- SD Card
- Card Reader

## Virtual
- LAN, or WLAN connection
- Raspberry Pi Imager - [click to download](https://downloads.raspberrypi.org/imager/imager_latest.exe)
- VNC Viwer Win 32/64 - [click to download](https://www.realvnc.com/download/file/viewer.files/VNC-Viewer-6.21.1109-Windows.exe) | *optional*

___

# Prepare SD Card:

- Put your SD Card in the Card Reader and connect it to your Windows PC
- Open Raspberry Pi Imager
<img src="images/piimager.jpg" width="30%" height="30%">

- Click on OS and select topmost option "Raspberry PI OS (32-bit)
<img src="images/piimageros.jpg" width="30%" height="30%">

- Click on SD-Card and select your SD-Card-Drive
- *for most of the time you only should see one drive to select*
<img src="images/piimagerdrive.jpg" width="30%" height="30%">

- Hit write!

This takes about 5 minutes, depending on your SD-Card and Card-Reader and if finished should tell you to take out the SD-Card
<img src="images/piimagefinished.jpg" width="30%" height="30%">

- Now you can insert it to your Raspberry Pi and fire it up.

___

# Prepare Linux Desktop:

- When your Raspberry Pi has started its greeting you with a friendly Setup-Wizard

<img src="images/piwiz.jpg" width="30%" height="30%">

- Make your way through this wizard and select your Wifi-Connection. Updates are not Mandatory at this point, as it would take some time and is not needed.
- Also you CAN change your Password, but unless you are sure how to use Linux and its console i would recommend to leave it as it is.

<img src="images/piwiz.jpg" width="30%" height="30%"> <img src="images/piwizcount.jpg" width="30%" height="30%"> <img src="images/piwizcountpw.jpg" width="30%" height="30%">
<img src="images/piwizwifi.jpg" width="30%" height="30%"> <img src="images/piwizupdate.jpg" width="30%" height="30%">

- After finishing the Setup-Wizard its absolutely mandatory to enable SSH first. This will be your connection to your Windows PC
- For this click on the Raspberry-Menu and got to "Preferences -> Raspberry Pi Configuration"
- In the configuration Window go to the "Interfaces"-Tab and enable SSH and if you like VNC
  - VNC is a virtual Desktop environment to be used with Windows *aka : nice to have feature*

<img src="images/piwizconfig.jpg" width="30%" height="30%"> <img src="images/piwizconfig2.jpg" width="30%" height="30%">

- Now you have finished your Linux and are able to control it from your Windows PC, or you can continue on this Raspberry Desktop
- As this is the Desktop Guide it continues on the Raspberry Pi Desktop

___

## Console work:

- Open up your Console / Command Prompt. Its the black little Button on the Start-Bar
<img src="images/console.jpg" width="30%" height="30%">

- It will open up and show you this prompt (depending on your username, if you had changed while setup)
<img src="images/consolep.jpg" width="30%" height="30%">

### Install OpenCV:
* Thanks to [this Guide](https://lindevs.com/install-precompiled-opencv-on-raspberry-pi/?fbclid=IwAR1sQwRH1FWbewNg4_Aomga-ZBbx3Di25C2mHrVqGTVxwiIKS31R0Pa8q5Y) i just had to copy it. *Shame on me*

- with open console type in, or copy over:

Download the .deb package from releases page of the repository:
```
wget https://github.com/prepkg/opencv-raspberrypi/releases/latest/download/opencv.deb
```
<img src="images/consoleocv1.jpg" width="30%" height="30%">

Execute the following command to install OpenCV:
```
sudo apt install -y ./opencv.deb
```
<img src="images/consoleocv2.jpg" width="30%" height="30%">

We can run opencv_version command to check version of OpenCV:
```
opencv_version
```
<img src="images/consoleocv3.jpg" width="30%" height="30%">

The .deb package is no longer needed, you can remove it:
```
rm -rf opencv.deb
```

- You have successfully installed OpenCV ( Ai - Camera - Future Shit)
- Next step is to install some USB - Utilities

### Install v4l-utils (and get your Camera-ID's):

- Open up your console and enter
```
sudo apt-get install v4l-utils
```
<img src="images/consoleov4l.jpg" width="30%" height="30%">

- after installing this you can list your USB-devices with the following command
```
v4l2-ctl --list-devices
```
<img src="images/consoleov4l2.jpg" width="30%" height="30%">

- Note down the first entry below your 3 cameras
  - In my case it's Video0 / Video 4 / Video2
  - Theese are your Camera ID's for later configuration in Board Manager

___

### Get Autodarts running

- Now your are ready to get the Autodarts - File
- Assuming you get your OK from the developer you should have the Download-Link
  - Otherwise contribute in the Discord Server and call out in the specific Channel that you are ready to go
  - You then will get the Download Link and your User-Credentials (aka: Board-ID and API-Key)
- In the console type follwing command to donwload the File:
```
wget *DOWNLAODLINK*
```
- Then unzip it with the following command:

*Important to change the specific filename if the version Changes!!!*
```
sudo unzip autodarts-0.15.5-pi-armv7l.zip -d /usr/local/bin/
```

- Create User-rights for Autodarts
```
sudo chmod +x /usr/local/bin/autodarts
```

- And now Finally:
```
autodarts
```
<img src="images/consoleauto.jpg" width="30%" height="30%">


## Cheering up - it's running!

- Continue with next Steps like Configuration or Calibration according to the Full Manual
  - [The Full Manual](https://github.com/autodarts/docs#readme)
- Best would be to get the Autodarts in the Autostart so that the program is running when you power on the Raspberry Pi
  -  [This Section of the Manual for Autodarts](https://github.com/autodarts/docs#setup-autostart-for-autodarts)



