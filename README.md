# saucelabs-vusb-gui
This project is an Open Source Virtual USB GUI for Sauce Labs Virtual USB. It provides a simple GUI to start an Android 
or iOS vUSB session with only a few clicks.

> **NOTE:** This project has been deprecated because the app has moved to the Sauce Labs Open Source Repository which you can find [here](https://github.com/saucelabs/saucelabs-vusb-app). The new GUI, as of version [`1.0.1`](https://github.com/saucelabs/saucelabs-vusb-app/releases/tag/v1.0.1), can now connect to the Sauce Labs Real Device Cloud instead of the Legacy RDC (TestObject)-cloud.


> **NOTE:**<br />
> Sauce Labs Virtual USB will only work if you are having Private devices in your Sauce Labs Real Device cloud

# Table of contents

1. [How to use](#how-to-use)
    - [Prerequisites](#prerequisites)
1. [Features](#features)
    - [Installing](#installing)
1. [TODO](#todo)
1. [Known VUSB GUI issues](#known-vusb-gui-issues)
1. [FAQ](#faq)
1. [Credits](#credits)

> **NOTE:**\
> Please check [FAQ](#faq) for most common issues

## How to use
### Prerequisites Android
To be able to work with Android you need to have the following on your local machine:

- JAVA added to your path
- Latest version of ADB installed on your machine
- (optional) Latest version of Android Studio installed on your local machine

There are enough tutorials on the internet that will explain you how to achieve the above.

### Prerequisites iOS
To be able to work with iOS you need to have a **Mac** and **XCODE** installed.

## Features
- Connect to a **new** VUSB session through the UI
- Change VUSB server settings through the UI
- Automatically connect to ADB
- use older versions of the vUSB runner
- Save logs into files
- Use some most used buttons to control the device from the right menu
- and many more!
 
### Installing
Download the latest version of the client from [here](https://github.com/wswebcreation/saucelabs-vusb-gui/releases).
After you have installed the client check the *Home* screen if there are no environmental issues, see below, 
if you have them please fix them and restart the app.

![Home](docs/assets/home.png)

Then go to *Settings* and fill the needed data. The first time you will see a screen like below

![Settings](docs/assets/settings.png)

You can adjust the server settings by scrolling down.

> **NOTE**\
> Check all the settings to see what you this Sauce Labs Virtual USB GUI can do for you!

When all *Settings* have been stored the *Device Catalog* can be used (if you didn't store the data properly clicking on 
the *Device Catalog* will automatically bring you back to the *Settings*).
You will see a screen like this.

![Device Catalog](docs/assets/device-searchbar.png)

You can't select a device because you first need to start the server, this can be done by clicking on the play-button. 
The screen will update and look like this.

![Server running](docs/assets/server-running.png).

To see the logs of the server click on the green icon, the logs can also be cleared like you normally would do with a terminal. 
The monitor can be closed by clicking on the cross.

![Server monitor](docs/assets/server-monitor.png)

You can easily search devices. Each word will be seen as an argument and the device needs to match all arguments.

![Search devices](docs/assets/device-search-results.png)

Connect to a device by clicking on the switch. After a few minutes the switch will change from `Connecting` to `Connected`,
see below.

![Device connected](docs/assets/device-connected.png)

When you now click on *LAUNCH LIVE TEST* a new window will be opened and a new fresh VUSB session will be started.

![VUSB session started](docs/assets/device-open-session.png)

The device needs to be connected to ADB to use the full power of Sauce Labs Virtual USB. You can do that automatically, 
Go to `Settings > AUTOMATICALLY CONNECT TO ADB`, or follow he steps below.

If you want to manually connect the device to your local machine then take the port number that is shown in the GUI and 
connect it with ADB like you normally would do.
In this case the device needs to be connected to port `7001` which leads to this command 

    adb connect localhost:7000

This will give you the opportunity to connect the device to for example Chrome and debug the website like this.

![Debug Chrome](docs/assets/device-connect-to-chrome.png) 

## Known vUSB GUI issues
- When you close a Live Testing session the VUSB session is also closed.

## FAQ
- [I'm not seeing any devices in the device catalog](#im-not-seeing-any-devices-in-the-device-catalog)
- [Why can't I see iOS devices, even though I have private iOS devices assigned to my account](#why-cant-i-see-ios-devices-even-though-i-have-private-ios-devices-assigned-to-my-account)
- [I'm getting al kinds of errors in my home screen telling me that `JAVA_HOME`, `ANDROID_HOME` and or `ADB` are not working](#im-getting-al-kinds-of-errors-in-my-home-screen-telling-me-that-java_home-android_home-and-or-adb-are-not-working)
- [Is this product build and maintained by Sauce Labs?](#is-this-product-build-and-maintained-by-sauce-labs)
- [Why is the source code not provided](#why-is-the-source-code-not-provided)
- [Cannot open Sauce vUSB app on Big Sur](#cannot-open-sauce-vusb-app-on-big-sur)
- [Cannot open Sauce vUSB app because it's "malicious software"](#cannot-open-sauce-vusb-app-because-its-malicious-software)
- [XCODE/Safari doesn't recognise my just connected iOS device over vUSB](#xcodesafari-doesnt-recognise-my-just-connected-ios-device-over-vusb)

### I'm not seeing any devices in the device catalog
Please make sure you have private devices assigned to your account. If you still can't see them file an issue 
[here](https://github.com/wswebcreation/saucelabs-vusb-gui/issues).

### Why can't I see iOS devices, even though I have private iOS devices assigned to my account
Virtual USB for iOS is in beta. You need to have two things to make this work:

- be at least on version [`0.4.0`](https://github.com/wswebcreation/saucelabs-vusb-gui/releases/tag/0.4.0), go to
**Settings** > **Server settings** > **SERVER VERSION** and select `Version 2.0-SNASHOT-5 !!iOS BETA!!`
- use a Mac, because vUSB relies on XCODE which will not work on Windows.

If that doesn't work I would advice you to contact your Sauce Labs Customer Success Manager.

### I'm getting al kinds of errors in my home screen telling me that `JAVA_HOME`, `ANDROID_HOME` and or `ADB` are not working
Make sure you have set up your environment for using Android on your local machine. Use Google as your biggest friend.

### Is this product build and maintained by Sauce Labs?
No, this product is build by myself because I wanted to learn building Apps with Electron and ReactJS. I thought that a 
simple UI for the Sauce Labs VUSB solution would be a nice project to start with.

### Why is the source code not provided
The source code will be provided with the next major `1.0.0` release

### Cannot open Sauce vUSB app on Big Sur
You may see a failure opening Sauce vUSB on Big Sur. This can be fixed by:

- opening a terminal 
- run the following command:
     
      xattr -rd com.apple.quarantine /Applications/SauceVusbClient.app 

Once done, this should let you open the Sauce vUSB GUI without any further issues.

### Cannot open Sauce vUSB app because it's "malicious software"
When trying to open the application, you might get an error from Mac saying that you can't open this software because it's 
downloaded from an external source and could be malicious software.

You can fix this by going to `System Preferences > Security & Privacy` and click on `Open Anyway`, see below

![Open Anyway](docs/assets/mac-blocked.png)

### XCODE/Safari doesn't recognise my just connected iOS device over vUSB
You'll need to exit Xcode/Safari before connecting to an iOS Virtual USB session (or relaunch it after connecting). 
Otherwise, the device won't show up.

## Credits
This app has been build with [electron-react-boilerplate](https://github.com/electron-react-boilerplate/electron-react-boilerplate).
