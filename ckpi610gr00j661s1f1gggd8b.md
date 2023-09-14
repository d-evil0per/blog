---
title: "Android Screencasting using shell scripting."
seoTitle: "Android Screencasting using shell scripting."
seoDescription: "Android screen casting, How to cast mobile screen on laptop, How to screencast my mobile screen. Mobile Screencast."
datePublished: Fri Jun 04 2021 10:09:16 GMT+0000 (Coordinated Universal Time)
cuid: ckpi610gr00j661s1f1gggd8b
slug: android-screencasting-using-shell-scripting
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1622793837913/_XZ7nh6A-.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1622793962220/DrcfYvxuv.jpeg
tags: streaming, bash, shell, 2articles1week

---

2 years ago, We all had a craze of opening a youtube channel for streaming mobile games. I remember playing PUBG a lot those days and wanted to stream my gameplay on my channel. The only hurdle I faced was how can I stream it for free with HD graphic. There were a lot of options that I could have been used. I might have used mobile streaming apps, Emulator with OBS studio, etc. But I choose to code. So, I came up with the Idea of Creating a (.bat) file for windows and a (.sh) file for Linux to Screencast my mobile to my laptop/desktop for streaming my gameplay. But As we know `Happiness too has an expiry date`.  On September 2, 2021, **PUBG Mobile was banned in India** due to data privacy concerns under Section 69A of the Information Technology Act.  Well, `Every night has a morning`. recently news came `BATTLEGROUNDS MOBILE INDIA Pre-Registrations to start from 18th May on Google Play Store.` I thought if it gets unbanned then a lot of people will again start their streaming. And Among them, many of them will face the same issue that I faced when I have started streaming. So, Let me tell you my secret of screencasting in this article.

## Juggad 

- Some Phone setups.
- We will need **Android Debug Bridge (ADB)** to be installed in our system.
- We will need to install **scrcpy**, which allows displaying and controlling Android devices connected via USB or wireless, from a macOS, Windows, or Linux desktop. 
- Last but not least, Bunch of Commands.

## Phone Set-up

1. Launch the Settings application on your phone.
2. Tap the About Phone option generally near the bottom of the list.
3. Then tap the Build Number option 7 times to enable Developer Mode. You will see a toast message when it is done.
4. Now go back to the main Settings screen and you should see a new Developer Options menu you can access.
5. Go in there and enable the USB Debugging mode option.
6. You are partially done with the phone setup process. Next up, you will need to scroll below and follow the rest of the instructions for your particular operating system.

## Android Debug Bridge (ADB)

We need to install this in our system, Let's check how to install it on all popular OS.

#### Windows
-  [Download the Android SDK Platform Tools ZIP file for Windows](https://dl.google.com/android/repository/platform-tools-latest-windows.zip)
- Extract the contents of this ZIP file into an easily accessible folder (such as C:\platform-tools)
- Open Windows Explorer and browse to where you extracted the contents of this ZIP file
- Then open up a Command Prompt from the same directory as this ADB binary. This can be done by holding Shift and Right-clicking within the folder then click the “Open command window here” option. (Some Windows 10 users may see “PowerShell” instead of “command window”.)
- Connect your smartphone or tablet to your computer with a USB cable. Change the USB mode to “file transfer (MTP)” mode. Some OEMs may or may not require this, but it’s best to just leave it in this mode for general compatibility.
- In the Command Prompt window, enter the following command to launch the ADB daemon: 
```
adb devices
```
- On your phone’s screen, you should see a prompt to allow or deny USB Debugging access. Naturally, you will want to grant USB Debugging access when prompted (and tap the always allow check box if you never want to see that prompt again).
- Finally, re-enter the command `adb devices`. If everything was successful, you should now see your device’s serial number in the command prompt (or the PowerShell window).

#### Linux or  MacOS

[Download the Android SDK Platform Tools ZIP file for Linux.](https://dl.google.com/android/repository/platform-tools-latest-linux.zip) if you are using a Linux machine or  [Download the Android SDK Platform Tools ZIP file for macOS.](https://dl.google.com/android/repository/platform-tools-latest-darwin.zip), if you are on Mac.

- Extract the ZIP to an easily accessible location (like the Desktop for example).
- Open a Terminal window.
- Enter the following command: cd /path/to/extracted/folder/
This will change the directory to where you extracted the ADB files.
- So for example: cd /Users/Doug/Desktop/platform-tools/
- Connect your device to your machine with your USB cable. Change the connection mode to “file transfer (MTP)” mode. This is not always necessary for every device, but it’s recommended so you don’t run into any issues.
- Once the Terminal is in the same folder your ADB tools are in, you can execute the following command to launch the ADB daemon: 
``` 
./adb devices
```
- Back on your smartphone or tablet device, you’ll see a prompt asking you to allow USB debugging. Go ahead and grant it.
- Finally, re-enter the command `./adb devices`. If everything was successful, you should now see your device’s serial number in the Terminal window output.

## SCRCPY  Setup

#### Windows Setup For SCRCPY :
  Please Download or clone the scrcpy from the github and follow the steps: https://github.com/Genymobile/scrcpy
  For Windows, for simplicity, prebuilt archives with all the dependencies (including adb) are available:
   * scrcpy-win32-v1.11.zip from https://github.com/Genymobile/scrcpy/releases/download/v1.11/scrcpy-win32-v1.11.zip
      * (SHA-256: f25ed46e6f3e81e0ff9b9b4df7fe1a4bbd13f8396b7391be0a488b64c675b41e)
   * scrcpy-win64-v1.11.zip from https://github.com/Genymobile/scrcpy/releases/download/v1.11/scrcpy-win64-v1.11.zip
      * (SHA-256: 3802c9ea0307d437947ff150ec65e53990b0beaacd0c8d0bed19c7650ce141bd)

#### Linux

- On Debian and Ubuntu 20.04
```
sudo apt install scrcpy
```
- A snap package is also available (For Ubuntu version < 20.04)
```
sudo snap install scrcpy
```

#### MacOS
- The application for macOS is available in Homebrew. Just run to install it.
```
brew install scrcpy
```

## Commands

- I'm using Linux so let's create a (.sh) file as  `Andmirror. sh`.
- We can cast the screen either using USB or Wifi, So let's ask the user to put the input and we will check the user input and will execute according.
```
#!/bin/bash
read -p "Connect Over 1.USB OR 2.WIFI (1/2):" type
if [ $type == 1 ]
then
        echo Connecting via USB
else
        echo Connecting Over Wifi
```
- Now let's add the logic, If the user chooses to connect via USB then we will list all the USB devices and connect using scrcpy. then the code will become something like this.

```
#!/bin/bash
read -p "Connect Over 1.USB OR 2.WIFI (1/2):" type
if [ $type == 1 ]
then
        echo Connecting via USB
        adb devices
        echo "***********************************"
	    echo Intializing Scrcpy...
        scrcpy -b15M -m2240

else
        echo Connecting Over Wifi
```
- in the above script, We Listed the connected devices and Connected using scrcpy with a bit-rate of 15 Mbps and Max-Size 2240px. You can change this parameter according to your requirement. To know more about it check this  [GenyMobile Scrcpy repo](https://github.com/Genymobile/scrcpy).

- Now let's add the script for `Connection Over Wifi`.

```
#!/bin/bash
read -p "Connect Over 1.USB OR 2.WIFI (1/2):" type
if [ $type == 1 ]
then
	echo Checking Connected Devices
	adb devices
	echo Intializing Scrcpy...
	scrcpy -b15M -m2240
else

	echo Make Sure Your device and this system are in the same network.
	echo Please plug your USB device and hit Enter
	read var1 


	echo Checking Connected Devices
	adb devices

	read -p "Enter the Port number:" Port

	adb tcpip $Port
	echo Restarting TCPIP in Port $Port

	echo Please Unplugged your USB device and hit Enter
	read var2
	
	read -p "Enter the IP Address:" IP

	echo Connecting $IP:$Port
	adb connect $IP:$Port

	echo Intializing Scrcpy...
	scrcpy -b15M -m2240
fi
```
- To Connect over Wifi, Your phone should be connected to the same network as your laptop is connected with. 
- You can find your phone IP address under the Wifi settings.
- You can provide any port number except some ports that are dedicated for some protocols such as 21,80,8080, etc. You can check this  [link](https://en.wikipedia.org/wiki/List_of_TCP_and_UDP_port_numbers)  for more information.
- we used  `adb tcpip $Port` to activate the following port.
- we used both IP and port, `adb connect $IP:$Port` to connect with the phone.
- Once it's connected, We used `scrcpy -b15M -m2240` to cast the screen.

## Bonus Points

- To make it easy, I have already created the (.sh) file for Linux and (.bat) file for windows in my  [GitHub Andmirror repo](https://github.com/d-evil0per/andmirror).
- For Linux users, You don't need to install anything just run the `andmirrior.sh` file. It will automatically install everything in your system if your system doesn't have those package installed already. if you have already installed `ADB` and `Scrcpy` then just follow the instructions in the terminal.
- for windows users, Please follow all the installation steps from above and run the `andmirror.bat` file from the repo.
- you can also record the screen using `scrcpy` just check this link [GenyMobile Scrcpy repo](https://github.com/Genymobile/scrcpy).
- If you want to know how to run this you can check my old [youtube video](http://www.youtube.com/watch?v=0Ca8CCs95XY) that contains the steps and process of casting the screen. The video Language is  `Hi-IN` 
If you are comfortable with it please watch it, you will get more clarification in the process.



