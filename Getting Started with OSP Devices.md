# Getting Started with OSP Devices
A Guide
Website: http://openspeechplatform.ucsd.edu/

## Abstract
This document describes how to set up and connect hardware devices to Open Speech Platform (OSP). This work is supported by:

* NIH  R33-DC015046:  Self-fitting  of  Amplification:  Methodology  andCandidacy
* NIH R01-DC015436:  A Real-time, Open, Portable, Extensible SpeechLab to University of California, San Diego.
* NSF IIS-1838830:  Division of Information & Intelligent Systems,  ”AFramework  for  Optimizing  Hearing  Aids  In  Situ  Based  on  PatientFeedback, Auditory Context, and Audiologist Input”
* The Qualcomm Institute  
  
Please visit [OSP Forum - Getting Started](http://openspeechplatform.ucsd.edu/forums/forum/getting-started/) to report issues and suggest improvements.

## Table of Contents
[1 Required Devices](#1-required-devices)  
[2 Installing Devices](#2-installing-devices)  
[3 Testing Devices](#3-testing-devices)  

&nbsp;
## Required Devices
If you have received OSP devices, below are the devices are needed.  
&nbsp;  
<mark class="yellowHighlight">Show and describe list of devices in a 2-Column Table</mark>
|   Device  |      Description      |                   Image of Device                   |
|:---------:|:---------------------:|:---------------------------------------------------:|
| Device #1 | Description of Device | ![placeholder image](pictures/placeHolderImage.png) |
| Device #2 | Description of Device |                                                     |
|           |                       |                                                     |

<!--<table class="tg yellowHighlight">
    <thead>
    <tr>
        <th class="tg-c3ow">Device</th>
        <th class="tg-c3ow">Description of device.</th>
        <th class="tg-c3ow">Image of Device</th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <td class="tg-0pky">Device #1</td>
        <td class="tg-0pky">Description of device.</td>
        <td class="tg-0pky"><img src="pictures/placeHolderImage.png" style="width: 200px;"></td>
    </tr>
    <tr>
        <td class="tg-0pky">Device #2</td>
        <td class="tg-0pky">Description of device.</td>
        <td class="tg-0pky"><img src="pictures/placeHolderImage.png" style="width: 200px;"></td>
    </tr>
    </tbody>
</table>-->

&nbsp;
## Installing Devices
<mark class="yellowHighlight">
    Describe steps needed to install the devices.
    <ol class="yellowHighlight">
        <li>Important disclaimers if there are parts of the device(s) that are not functioning at the moment, which will be fixed in the future (such as the "battery" buttons?)</li>
        <li>Powering on the device by charging it?</li>
        <li>Bringing up the hotspot, which should say "ospboard" and connecting it using the linaro username and password?</li>
        <li>Wired connectivity between left and right USB C-ports and the hearing aids?</li>
    </ol>
</mark>

1. Installing Fastboot (android utility)
2. While device is off, plug in the USB cable into the ADB port (Android Debug Port).
3. While pressing and holding mute button, turn on the device.
4. Open up the terminal and type in `fastboot devices
5. . It should display one line and the ID of the device, meaning you successfully booted it up in Fastboot mode.
6. Grab two files (location is TBD, on Bitbucket[up to date]/GitHub): one is going be labeled "boot-v7.img", other one is labeled "rootfs.simg"
7. Same folder as these two files, run the following commands: fastboot flash boot boot-v7.img, fastboot flash rootfs rootfs.simg
8. Once completed, restart the device with the headsets plugged in.
9. After boot, everything should be working.
10. Devices = Hearing aid devices (left and right BTE-RICs)
11. You should see a hotspot called "ospboard". On boot up, might take a moment.
12. Connect to hotspot using password "hearingaid".
13. Visit page using your browser "192.168.8.1:5000". Should get you to the Node.js pages. Without the ":5000" is where you get to the PHP pages.
14. Login to researcher page, change the gains to see effects on BTE-RICs. Confirm things are functioning, test to see if things are functioning.

<mark class="yellowHighlight">Topics Related to Dhruv's Questions and Dhiman's Answers
</mark>
1. I see that upon bringing up the device, it creates a hotspot named "ospboard". The ssid is password protected. Can you share the password? **Password: "hearingaid"**
2. I see two micro usb ports on the device labeled, "uart" and "adb". I take that uart usb port is to connect to shell over uart ? What's "adb" usb port for? **Uart is for the shell and ADB is for both charging the device and updating the linux kernel.**
3. I see 3 USB-C ports labeled, "left", "right" and "ephys". Left and Right ports are for connecting HA, what's "ephys" port used for **EPhys is an experimental port for our in house development of EEG devices; it has a high speed ADC that can be used for any analog devices.**
4. Also, if I were to ssh into the device via hotspot, what's the username and password? **Username: linaro Password: linaro**
5. There're also two LED indicators with "battery" and "speaker" sign. It doesn't light up as I turn on the device, is this behavior normal? **If there is a green light constantly on then the hearing aids are muted, in order to unmute press the speaker button. The battery button is not functional currently, it may be operational in a future firmware update.**
6. Which port is supposed to be used for charging the battery **The ADB port.**
7. May be all these questions are answered in some "getting started document" but I could not find it on github / bitbucket. If that's the case, can you point me to the right document? **We have to update your fork to get you the latest version of all documents and software. Let us know if you are able to get the devices running first we can have a zoom call if that will help.**


&nbsp;
## Testing Devices
<mark class="yellowHighlight">Describe steps needed to test the devices.
</mark>