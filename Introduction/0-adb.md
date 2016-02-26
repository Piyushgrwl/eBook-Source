## Setting up adb tool

Android Debug Bridge (adb) is a command line tool that allows the computer to communicate with attached electronic devices. We will be using adb tool to mostly capture screenshots of the mobile screen, simulate virtual touches and virtual swipes. 

These are the steps that you have to follow to setup adb tool.

**Step 1: Installation**

We will need Android SDK or ADB fastboot in order to be able to use the adb tool. In general, most people have Java JDK already installed, so you might not have to do anything here. But if you don't have it installed, install it.

**Step 2: Enable USB Debugging**

To use adb with your Android device, you have to enable USB debugging first. You will find this in the developer options menu inside settings. If the developer options menu is not available, go into about phone menu in settings and tap the build number seven times to enable developer options menu. 

Also, make sure that you accept RSA fingerprint message shown in the device when its connected for the first time.

**Step 3: Download adb tool files**

Download the files in the provided link. You should have these files in the directory that you are working, or you can add adb.exe to your path in environment variables.

Link: http://forum.xda-developers.com/showthread.php?p=48915118

**Step 4: Testing**

To test whether ADB is working properly, connect your Android device to your computer using a USB cable and run the following command in the command prompt. This should list the devices.

```
adb devices
```

Also run the following command on MATLAB

```MATLAB
system('adb devices')
```

The output of both the command should look similar to this if your Android device is connected properly and detected.

```C
List of devices attached  
T038509BHC	device
```

If your device is connected but nothing appears in the list, you'll need to install the appropriate drivers for your phone. You can find the drivers from Universal drivers (http://adbdriver.com/downloads/) or Android developers website (http://developer.android.com/tools/extras/oem-usb.html#InstallingDriver).

Open the Device Manager (click Start, type Device Manager, and press Enter), locate your device, right-click it and select Properties. You may see a yellow exclamation mark next to the device if its driver isn't installed properly. You might also have to force windows to use the installed drivers for your phone.

##### Basic ADB commands

Here are some commands that can be used with adb tool.

To pull the image into working directory.
```
adb pull 
```

To take a screenshot of the device connected.
```
adb shell screencap 
```

To tap on the screen at coordinates (x,y).
```
adb shell input tap x y
```

To swipe the screen from coordinates (x1, y1) to coordinates (x2,y2) with a delay of w milliseconds.
```
adb shell input swipe x1 y1 x2 y2 w
```

To remove screenshot that has been stored.
```
adb shell rm 
```

That's all you need to know about adb tool. Next, let us cover each of the approaches in detail.