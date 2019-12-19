# saucelabs-vusb-gui
This project is an Open Source Virtual USB GUI for Sauce Labs Virtual USB. It provides a simple GUI to start an Android* VUSB session with only a few clicks.

> **NOTES:**<br />
> - iOS is in an early access mode, contact your Sauce Labs Customer Success Manager to learn more
> - Sauce Labs Virtual USB will only work if you are having Private devices in your Sauce Labs Real Device cloud
> - There is currently a **beta out for Windows**, please check [this](https://github.com/wswebcreation/saucelabs-vusb-gui/releases/tag/0.1.2.1-win-beta) release.

# Table of contents

1. [How to use](#how-to-use)
    - [Prerequisites](#prerequisites)
1. [Features](#features)
    - [Installing](#installing)
1. [TODO](#todo)
1. [Known VUSB GUI issues](#known-vusb-gui-issues)
1. [FAQ](#faq)
1. [Credits](#credits)


## How to use
### Prerequisites
This client currently only support Android. To be able to work with Android you need to have the following on your local machine:

- JAVA added to your path
- Latest version of ADB installed on your machine
- (optional) Latest version of Android Studio installed on your local machine

There are enough tutorials on the internet that will explain you how to achieve the above.

## Features
- Connect to a **new** VUSB session through the UI
- Connect to an **existing** session through the UI. This can be a running Appium session of a running manual session.
- Change VUSB server settings through the UI
 
### Installing
Download the latest version of the client from [here](https://github.com/wswebcreation/saucelabs-vusb-gui/releases), be aware of the fact that currently only Mac and Linux are supported.
After you have installed the client check the *Home* screen if there are no environmental issues, see below, if you have them please fix them and restart the app.

![Home](./assets/home.jpg)

Then go to *Settings* and fill the needed data. The first time you will see a screen like below

![Settings](./assets/settings.jpg)

You can adjust the server settings by scrolling down.

When all *Settings* have been stored the *Device Catalog* can be used (if you didn't store the data properly clicking on the *Device Catalog* will automatically bring you back to the *Settings*).
You will see a screen like this.

![Device Catalog](./assets/device-searchbar.jpg)

You can't select a device because you first need to start the server, this can be done by clicking on the play-button. The screen will update and look like this.

![Server running](./assets/server-running.jpg).

To see the logs of the server click on the green icon, the logs can also be cleared like you normally would do with a terminal. 
The monitor can be closed by clicking on the cross.

![Server monitor](./assets/server-monitor.jpg)

You can easily search devices. Each word will be seen as an argument and the device needs to match all arguments.

![Search devices](./assets/device-search-results.jpg)

Connect to a device by clicking on the switch. After a few minutes the switch will change from `Connecting` to `Connected` and the device will get an `In Use` badge, see below.

![Device connected](./assets/device-connected.jpg)

When you now click on *LAUNCH LIVE TEST* a new window will be opened and a new fresh VUSB session will be started.

![VUSB session started](./assets/device-open-session.jpg)

If you want to connect the device to your local machine then take the port number that is shown in the GUI and connect it with ADB like you normally would do.
In this case the device needs to be connected to port `7001` which leads to this command 

    adb connect localhost:7001

This will give you the opportunity to connect the device to for example Chrome and debug the website like this.

![Debug Chrome](./assets/device-connect-to-chrome.jpg) 

## TODO:
- [ ] Verify that the device connection is really killed
- [x] Sort the devices, they are now only shown based on how we get them with the API call
- [x] Add a generic notification/error handler
- [ ] Implement proxy for getting the data from the API through a proxy
- [ ] Some other stuff that I don't know now =)

## Known VUSB GUI issues
- A VUSB connection will only stay alive for max 5 minutes through the GUI
- When you close a Live Testing session the VUSB session is also closed.

## FAQ
### I'm not seeing any devices in the device catalog
Please make sure you have private devices assigned to your account. If you still can't see them file an issue [here](https://github.com/wswebcreation/saucelabs-vusb-gui/issues).

### Why can't I see iOS devices, even though I have private iOS devices assigned to my account
Virtual USB for iOS is in an early access mode. This app doesn't support that yet. Please contact your Sauce Labs Customer Success Manager to learn more about VUSB for iOS.

### I'm getting al kinds of errors in my home screen telling me that `JAVA_HOME`, `ANDROID_HOME` and or `ADB` are not working
Make sure you have set up your environment for using Android on your local machine. Use Google as your biggest friend.

### Is this product build and maintained by Sauce Labs?
No, this product is build by myself because I wanted to learn building Apps with Electron and ReactJS. I thought that a simple UI for the Sauce Labs VUSB solution would be a nice project to start with.

### Why is the source code not provided
The source code will be provided in a few weeks.

## Credits
This app has been build with [electron-react-boilerplate](https://github.com/electron-react-boilerplate/electron-react-boilerplate).
