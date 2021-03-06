# OSP \- EWS Getting Started Guide - Release 2020a
Website: http://openspeechplatform.ucsd.edu/

## Abstract
This document describes steps to download, build, install and test the browser-based Embedded Web Server (EWS) for the Open Speech Platform (OSP) Release 2020a software. This work is supported by:

* NIH  R33-DC015046:  Self-fitting  of  Amplification:  Methodology  andCandidacy
* NIH R01-DC015436:  A Real-time, Open, Portable, Extensible SpeechLab to University of California, San Diego.
* NSF IIS-1838830:  Division of Information & Intelligent Systems,  ”AFramework  for  Optimizing  Hearing  Aids  In  Situ  Based  on  PatientFeedback, Auditory Context, and Audiologist Input”
* The Qualcomm Institute  
  
Please visit [OSP Forum - Getting Started](http://openspeechplatform.ucsd.edu/forums/forum/getting-started/) to report issues and suggest improvements.

## Table of Contents
[1 OSP Installation](#1-osp-installation)   
* [1\-1 Requirements for OSP](#1-1-requirements-for-osp)
    * [1\-1\-1 Computer and Audio Requirements](#1-1-2-computer-and-audio-requirements)
    * [1\-1\-2 Installation Requirements](#1-1-3-installation-requirements)
* [1\-2 Download and Installation Steps](#1-2-download-and-installation-steps)
* [1\-3 Connecting Your Audio Device](#1-3-connecting-your-audio-device)
    * [1\-3\-1 On Mac Computers](#1-3-1-on-mac-computers)
    * [1\-3\-2 On Linux Computers](#1-3-2-on-linux-computers)

[2 OSP Package Testing and Validation](#2-osp-package-testing-and-validation)
* [2\-1 Test RT\-MHA](#2-1-test-rt-mha)
* [2\-2 Test EWS \(Node\.js Version\)](#2-2-test-ews-nodejs-version)  
* [2\-3 Test EWS \(PHP Version\)](#2-3-test-ews-php-version)  

[3 OSP Development\: EWS \(Node\.js version\)](#3-osp-development-ews-nodejs-version)

&nbsp;  
## 1 OSP Installation
##### \[[back to table of contents](#table-of-contents)]
&nbsp;   
This section describes:  
1. Computer requirements and software application knowledge needed to install the Open Speech Platform (OSP) software.
2. Actual steps to download and install files needed to run OSP.  

Installation time may take ~30−90 minutes, depending on your computer, internet download speeds, and any installation errors that you may encounter and resolve.

Before proceeding, know that OSP is composed of two main components, which are described below and referenced later in this guide. 
* **Real Time Master Hearing Aid (RT-MHA)** - This is the hearing
aid algorithm which takes the audio from the environment and modifies
it for the listeners specific prescription.
* **Embedded Web Server (EWS)** - This is a process, represented as a graphical user interface on any web browser enabled device which can control the RT-MHA algorithm. There are two flavors of EWS available in this release written in two different programming languages. The NodeJS version is currently being developed and will replace all of the functionality found in the PHP version.

&nbsp;   
### 1\-1 Requirements for OSP
&nbsp;

#### _1\-1\-1 Computer and Audio Requirements_

1. **Operating System**: Either a Mac or a _debian-based_ Linux
machine (such as Ubuntu or Linaro) will suffice.
2. **Processor**: Equivalent to an Intel Core i5 processor.
3. **Memory/RAM**: At least 8GB or more.
4. **Free Storage Space**: At least 2GB or more
5. **Audio**: Your computer’s built-in microphone and speakers. Preferable if have a working device, such as a headset or pair of wired headphones.

 See figures [1.1](#figure1-1) and [1.2](#figure1-2) below as a reference for requirements #1 to #4.

<br>
<figure id="figure1-1">
    <figcaption class="figcaption">Figure 1.1: Example of system requirements for a MacOS computer.</figcaption>
    <img src="pictures/EWSPics/MacSystemReq1.png" style="width: 500px;">
</figure>
<br>
<figure id="figure1-2">
    <figcaption class="figcaption">Figure 1.2: Example of system requirements for a Linux computer on Ubuntu.</figcaption>
    <img src="pictures/EWSPics/LinuxSystemReq1.jpg" style="width: 500px;">
</figure>
<br>

To check if your computer meets these specifications...
* **On Mac**
    1. Click on the Apple menu icon at the top of your screen.
    2. In the dropdown menu, choose "About This Mac". The specifications should look similar to Figure [1.1](#figure1-1).  
    For more information, see how [Apple explains computer specifications](https://support.apple.com/en-us/HT203001).
&nbsp;

* **On Linux**  
You may need to use a terminal that accepts command
lines to figure out the specifications. Figure [1.2](#figure1-2) is a reference of what the specifications look like on Ubuntu 18.04.1, though this may appear differently for different Linux systems.  

    You check out this Stack Exchange post for answers related to Ubuntu: [askUbuntu - How do I check system specifications?](https://askubuntu.com/questions/55609/how-do-i-check-system-specifications)

After the installation, to verify that the system can deliver audio output,
**you need some way to input and output audio**, which is why having a device or your computer speakers/microphone **that isn't muted** is important. 

#### _1\-1\-2 Installation Requirements_
Finally, these are the additional applications and tools needed to successfully
install OSP
1. **Command Terminal**: You will need to know how to operate the
command terminal with working knowledge of basic terminal commands
and features. This is to navigate through different folders and operate
OSP after installation. Fortunately, this guide will cover all of the
commands needed, as long as you follow the steps in order.
2. **GitHub and git**: Our files are stored online via our GitHub page.
You will need to install git within the terminal, if this hasn’t been
done already.
&nbsp;

### 1\-2 Download Files from OSP

<ol>
    <li><b>Open the terminal application.</b></li>
        <ol class="letteredList">
            <li><i>On Mac</i>, you can go to <code>Applications</code> within your Finder and type in the search bar "terminal". It should appear as a thumbnail that looks like a black box</li>
            <li><i>On Linux</i>, there are many methods to open the terminal. An article on How-To Geek’s website covers this:<a href="hhttps://www.howtogeek.com/howto/22283/four-ways-to-get-instant-access-to-a-terminal-in-linux/" target="_none"> Four Ways to get Instant Access to a Terminal in Linux.</a></li>
        </ol>
    <li>
        <b>Download the 2020a Release .zip file from GitHub</b>: On your browser, navigate to <a href="https://github.com/nihospr01/OpenSpeechPlatform-UCSD" target="_none">https://github.com/nihospr01/OpenSpeechPlatform-UCSD</a> to download the latest release (see Figure <a href="#figure1-3">1.3</a>).
            <br><br>
                <figure id="figure1-3">
                    <figcaption class="figcaption">Figure 1.3: On <a href="https://github.com/nihospr01/OpenSpeechPlatform-UCSD" target="_none">Github</a> Click on the green "Code" button, then the "Download ZIP" button to retrieve the installation files on your computer.</figcaption>
                    <img src="pictures/EWSPics/zipFileDownload.png" style="width: 500px;">
                </figure>
            <br><br>
        <ol>
           <li><i>MacOS computers</i> support opening .zip files. Once you download the .zip file, go to the "Downloads" within Finder and open the .zip file. It should appear unzipped as a folder with the same name.</li>
            <li>For <i>Debian-based Linux computers</i>, go to the terminal and enter <code>sudo apt install unzip</code>.</li>
        </ol>
    </li>
    <li>After doing the git clone command or downloading and extracting the .zip file, enter the command <code>cd OpenSpeechPlatform-UCSD/Software/Build-Scripts</code>, to navigate to a folder named <code>Build-Scripts</code> before proceeding to the next steps of the installation. You will install OSP’s software packages needed within this folder.
    </li>
    <li>
        The zip file will be downloaded to your <code>Downloads</code> directory.  Open a terminal and unzip it.  (If <code>unzip</code> is not installed, you can install it with <code>sudo apt install unzip</code>)
    </li>
</ol>

```
> unzip ~/Downloads/OpenSpeechPlatform-UCSD-master.zip 
Archive:  /home/mmh/Downloads/OpenSpeechPlatform-UCSD-master.zip
2f0d1eb27751e6a31be637c7f63eb9a9cbe5efb0
   creating: OpenSpeechPlatform-UCSD-master/
  inflating: OpenSpeechPlatform-UCSD-master/.gitignore  
...
```

Now go into the directory and install the software using one or both of the following commands: 
* `./install_all_njs` - This command will install the Node.js version of EWS web apps in the folder path "/usr/local". It is recommended to use this version as it represents the latest of the OSP software, and it will also have continued support for OSP software updates.  
* `./install_all_php` - This command will install the PHP/Laravel version of EWS web apps in the folder path "/usr/local". This is an older version of the OSP software and should only be used if you wish to take advantage of older features of OSP, such as the "Goldilocks". 


```
> cd OpenSpeechPlatform-UCSD-master/Software/Build-Scripts/
~/OpenSpeechPlatform-UCSD-master/Software/Build-Scripts 
> ./install_all_njs
[follow directions]
 ~/OpenSpeechPlatform-UCSD-master/Software/Build-Scripts 
> ./install_all_php 
[follow directions]
```

This will install the PHP and Nodejs web apps in /usr/local.  You will be prompted
for your password so the installation script can write into that directory.
<mark class="yellowHighlight"><b>End of Martin's notes?</b></mark>

&nbsp;
### 1\-3 Choosing the Installation Method
Defined below are two main components of OSP.  
* **Real Time Master Hearing Aid (RT-MHA)** - This is the hearing
aid algorithm which takes the audio from the environment and modifies
it for the listeners specific prescription.
* **Embedded Web Server (EWS)** - This is a process, represented as a graphical user interface on any web browser enabled device which can control the RT-MHA algorithm. There are two flavors of EWS available in this release written in two different programming languages. The NodeJS version is currently being developed and will replace all of the functionality found in the PHP version.

Below are the available options to go about the installation process.
1. [**Installing Everything - RT-MHA and Node\.js version of EWS**](#1-3-1-installing-everything---rt-mha-and-nodejs-version-of-ews)   
This is the latest version of OSP. Future releases will completely adopt
Node.js.
2. [**Installing Everything - RT-MHA and PHP version of EWS**](#1-3-2-installing-everything---rt-mha-and-php-version-of-ews)  
This is the legacy version of OSP, which will eventually not be used in
future releases. This version still has the \Goldilocks" page.
3. [**Installing/Updating just the RT-MHA**](#1-3-3-installingupdating-just-the-rt-mha)
4. [**Installing/Updating just the Node\.js version of EWS**](#1-3-4-installingupdating-just-the-nodejs-version-of-ews)
5. [**Installing/Updating just the Node\.js version of EWS**](#1-3-5-installingupdating-just-the-php-version-of-ews)  

Before you beginning any of these installation methods, here are additional disclaimers:
* In the terminal, **be sure that you have already navigated to
the** `Build-Scripts` **directory**. Otherwise you will not be able to
properly install the files. The file path to the `Build-Script` directory
should be `OpenSpeechPlatform-UCSD/Software/Build-Scripts/`, (see Step 4 of Section 1.2).
* **If you are using Ubuntu, you may have to manually install
the latest version of a software package related to Node.js
called** `node-pre-gyp` as well as the `npm` package** to resolve
installation issues and error messages in advance. This step will eventually be fixed in a future release
&nbsp;
#### _1\-3\-1 Installing Everything \- RT\-MHA and Node.js version of EWS_

<ol>
    <li>Run the command <code>./install_all_njs</code>, which does the following:</li>
        <ol class="letteredList">
            <li>Identify the operating system (OS) on your computer { currently OS X, Debian and Redhat/Fedora based Linux (It will work with apt-get and yum package managers).</li>
            <li>Install all the prerequisite software packages.</li>
            <li>Build and install RT-MHA as well as the Node.js version of EWS.</li>
        </ol>
    <li>To check whether the system has successfully installed in your system:
        <ol class="letteredList">
            <li>In the current terminal, run <code>osp</code>, this should start running the OSP.</li>
            <li>In a separate terminal run <code>ews-backend</code>. This should start running the backend of the Node.js version of EWS, this backend will also have the frontend built-in.</li>
            <li>Open a Browser window and type the URL <a href="localhost:5000" target="_none">localhost:5000</a>. This will open the webpage to the NodeJS version of EWS.</li>
        </ol>
    </li>
</ol>

&nbsp;
#### _1\-3\-2 Installing Everything \- RT\-MHA and PHP version of EWS_

<ol>
    <li>Run the command <code>./install_all_php</code>, which does the following:</li>
        <ol class="letteredList">
            <li>Identify the operating system (OS) on your computer { currently OS X, Debian and Redhat/Fedora based Linux (it will work with apt-get and yum package managers)</li>
            <li>Install all the prerequisite software packages.</li>
            <li>Build and install RT-MHA as well as the PHP version of EWS.</li>
            <li>Finally, it installs osp in <code>/usr/local/bin/osp</code> and a script to invoke ews in <code>/usr/local/bin/ews</code>.</li>
        </ol>
    <li>To check whether the system has successfully installed in your system:
        <ol class="letteredList">
            <li>In the current terminal, run <code>osp</code>, this should start running the OSP.</li>
            <li>In a separate terminal run <code>ews</code>. This should start running the PHP version of EWS.</li>
            <li>Open a Browser window and type the URL <a href="localhost:8080" target="_none">localhost:8080</a>. This will open the webpage to the PHP version of EWS.</li>
        </ol>
    </li>
</ol>

&nbsp;
#### _1\-3\-3 Installing/Updating just the RT\-MHA_

1. **This step is only needed if you are installing RT-MHA for the first time.** Run the command `./pre_req_all`, which command will identify your OS install all the necessary prerequisite packages in your system.
2. Run the command `./libosp`, which installs the librtmha and RT-MHA in your system.
3. To check whether the RT-MHA has successfully installed in your system, In the current terminal, run `osp`, this should start running the RT-MHA.

&nbsp;
#### _1\-3\-4 Installing/Updating just the Node.js version of EWS_

1. **This step is only needed if you are installing this version of EWS for the first time.** Run the command `./pre_req_all`. This command will identify your OS install all the necessary prerequisite packages in your system
2. Run the command `./ews_njs`. This will install the Node.js version of EWS on your system.
3. To check the EWS installation run `ews-backend` on the terminal, You can open a Browser window and type the URL [localhost:5000](localhost:5000). This will open the webpage to the Node.js version of EWS.

&nbsp;
#### _1\-3\-5 Installing/Updating just the PHP version of EWS_

1. **This step is only needed if you are installing this version of EWS for the first time.** Run the command `./pre_req_all`. This command will identify your OS install all the necessary prerequisite packages in your system
2. Run the command `./ews_php_public`. This will install the PHP version of EWS on your system.
3. To check the frontend run `ews` on the terminal, You can open a Browser window and type the URL [localhost:8080](localhost:8080). This will open the webpage to the PHP version of EWS.

&nbsp;
### 1\-4 Connecting Your Audio Device 
**Note**: For Mac computers, the default audio input and output built into
the computer is sufficient for testing the audio. You do not have to follow these steps to connect your audio device, but it is recommended to do so.

In your terminal, run the command `osp`, which implements the RT-MHA functions.  You can run it from any directory.

&nbsp;
```
~/OpenSpeechPlatform-UCSD-master > osp
Done
Done
TCP Server created
ALSA lib pcm_dsnoop.c:641:(snd_pcm_dsnoop_open) unable to open slave
ALSA lib pcm_dmix.c:1089:(snd_pcm_dmix_open) unable to open slave
ALSA lib pcm.c:2642:(snd_pcm_open_noupdate) Unknown PCM cards.pcm.rear
ALSA lib pcm.c:2642:(snd_pcm_open_noupdate) Unknown PCM cards.pcm.center_lfe
ALSA lib pcm.c:2642:(snd_pcm_open_noupdate) Unknown PCM cards.pcm.side
ALSA lib pcm_oss.c:377:(_snd_pcm_oss_open) Unknown field port
ALSA lib pcm_oss.c:377:(_snd_pcm_oss_open) Unknown field port
ALSA lib pcm_usb_stream.c:486:(_snd_pcm_usb_stream_open) Invalid type for card
ALSA lib pcm_usb_stream.c:486:(_snd_pcm_usb_stream_open) Invalid type for card
ALSA lib pcm_dmix.c:1089:(snd_pcm_dmix_open) unable to open slave
Input device # 10
  Name: default
  Channels = 2
  LL: 0.00868481 seconds
  HL: 0.0348073 seconds
Output device # 10
  Name: default
  Channels = 2
  LL: 0.00868481 seconds
  HL: 0.0348073 seconds

Input latency: 0.002
Output latency: 0.003
```
&nbsp;

At this point, you should be able to talk into your microphone and hear the sound played back in your headset (or computer speakers) with a very small delay.  If that does not happen, something is wrong. Hit Control-C on your keyboard a couple of times to exit OSP. Run `osp` again within your terminal to restart it.

If, after several tries, if it does not start, you need to check what audio input and output you want to use.  `osp` attempts to use the Linux system defaults. You can run the `pa_devs` command to get a detailed list of inputs and outputs available on your system.

To change the input and output to connect OSP with:
1. **On MacOS**\: Run the command `osp --input channel x --output channel y`, where `x` is the number associated with the input channel and `y` is the number associated with the output channel.
2. **On Linux**\: Run the command `osp --input device x --output device y`, where `x` is the number associated with the input device and `y` is the number associated with the output device.


When you know what device you want to use, you can rerun `osp` with those devices.

```
> osp --input_device 9 --output_device 9
TCP Server created
ALSA lib pcm_dsnoop.c:641:(snd_pcm_dsnoop_open) unable to open slave
ALSA lib pcm_dmix.c:1089:(snd_pcm_dmix_open) unable to open slave
ALSA lib pcm.c:2642:(snd_pcm_open_noupdate) Unknown PCM cards.pcm.rear
ALSA lib pcm.c:2642:(snd_pcm_open_noupdate) Unknown PCM cards.pcm.center_lfe
ALSA lib pcm.c:2642:(snd_pcm_open_noupdate) Unknown PCM cards.pcm.side
ALSA lib pcm_oss.c:377:(_snd_pcm_oss_open) Unknown field port
ALSA lib pcm_oss.c:377:(_snd_pcm_oss_open) Unknown field port
ALSA lib pcm_usb_stream.c:486:(_snd_pcm_usb_stream_open) Invalid type for card
ALSA lib pcm_usb_stream.c:486:(_snd_pcm_usb_stream_open) Invalid type for card
ALSA lib pcm_dmix.c:1089:(snd_pcm_dmix_open) unable to open slave
Input device # 9
  Name: pulse
  Channels = 2
  LL: 0.00868481 seconds
  HL: 0.0348073 seconds
Output device # 9
  Name: pulse
  Channels = 2
  LL: 0.00868481 seconds
  HL: 0.0348073 seconds

Input latency: 0.002
Output latency: 0.003
```
&nbsp;

As an example, Figure [1.4](#figure1-4) shows the command issued as `osp --input device 6 --output device 6` on a Linux terminal, where `6` is the value associated to the connected audio device.

<br>
<figure id="figure1-4">
    <figcaption class="figcaption">Figure 1.4: List of devices displayed by running the <code>pa_devs</code> command.</figcaption>
    <img src="pictures/EWSPics/osp-4.png" style="width: 500px;">
</figure>
<br>

&nbsp;  
## 2 OSP Package Testing and Validation
##### \[[back to table of contents](#table-of-contents)]
This chapter describes how to check that the installed software package(s) for OSP are working properly.

&nbsp;    
### 2\-1 Test RT\-MHA
You can interact with RT-MHA from the command line interface (CLI) to display and change the HA state. **Please make sure that the audio device is connected and that you can hear sound from the device. Otherwise, go back to section 2.1 to connect the device.**

<ol>
    <li>Do not wear the audio device for now.</li>
    <li>Open or navigate to your terminal and enter the command osp. The terminal should show results similar to Figure <a href="#figure2-4">2.4</a>
        <br><br>
        <figure id="figure2-4">
            <figcaption class="figcaption">Figure 2.4: Output of the terminal when you issue <code>osp</code> command.</figcaption>
            <img src="pictures/EWSPics/osp-1.png" style="width: 500px;">
        </figure>
        <br><br>
    </li>
    <li>To familiarize you with the initial commands that OSP has, please
enter the following series of commands and steps in the terminal.</li>
        <ol class="letteredList">
            <li><code>-p</code> This command will print the <i>complete state</i> of RT-MHA. In the terminal messages above, notice that the gain on the left and right channels is -20 dB, to account for overall gain of RT-MHA.</li>
            <li><code>--gain -15</code> This command, with a value of -15, will set the system volume to -15 dB. By default, the gain is set to -20 dB. By entering this command, you are making RT-MHA louder by 5 dB. The -15 value can be changed to a different value.</li>
            <li>Type in <code>-p</code> to see the changed gain values. Your terminal should look similar to Figure <a href="#figure2-5">2.5</a>.
                <br><br>
                <figure id="figure2-5">
                    <figcaption class="figcaption leftAlign">Figure 2.5: Terminal messages that show the output of values before and after executing the <code>--gain -15</code> command. Before the command, gain is set to -20 dB by default, -15 dB after the command is executed. Remember that you can view these values by using the -p command, as shown.</figcaption>
                    <img src="pictures/EWSPics/osp-3.png" style="width: 500px;">
                </figure>
                <br><br>
            </li>
            <li><code>-h</code> This command should help you experiment with RT-MHA by generating a list of commands that you can use within OSP, shown in Figure <a href="#figure2-6">2.6</a>.
                <br><br>
                <figure id="figure2-6">
                    <figcaption class="figcaption">Figure 2.6: High level commands for OSP using the command line interface (CLI).</figcaption>
                    <img src="pictures/EWSPics/osp-2.png" style="width: 500px;">
                </figure>
                <br><br>
            </li>
            <li><b>Before you proceed with the next step, be careful to not put the gain too high, otherwise your ears may start ringing. You may need to change the numerical value in the command to a lower value instead of -15.</b> Wear the audio device and make sure the audio output connection is stable. Enter the command <code>--gain -15</code> again and listen for external audio stimuli. This is how you know that RT-MHA is working.</li>
            <li>The last command to enter is <code>-q</code>, which will quit OSP.</li>
            <li>If, after starting OSP, you cannot hear yourself when talking into the microphone , hit <code>^C</code> to exit OSP. Restart OSP and try again. If it fails several times, try a different input/output audio device.</li>
        </ol>
</ol>

&nbsp;   
### 2\-2 Test EWS \(Node\.js Version\)
1. For testing EWS, open two terminals side by side.
2. In the first terminal, type `osp`. In the second terminal, type `ews`.
3. Open a browser, such as Chrome. Enter `localhost:5000` in the search bar. You will see the landing page as shown in Figure [2.7](#figure2-7).

<br>
<figure id="figure2-7">
    <figcaption class="figcaption leftAlign">Figure 2.7: EWS (Node.js) Landing Page. You should see "Researcher Login" and "Listener Login", with input fields for "Researcher ID" and "password" and a red "Sign Up" button in the upper right corner.</figcaption>
    <img src="pictures/EWSPics/nodejsLandingPage.png" style="width: 500px;">
</figure>
<br>

4. Proceed to make a new Researcher account by clicking on the "Sign Up" button. You should be able to enter a new name for your account as "Researcher ID" and a password to securely access your account. **Be sure to save your credentials in a place where you can remember them, as OSP does not currently have a feature to help you retrieve back your password!**

5. Login using your new credentials. You should successfully be logged in if your landing page looks like Figure [2.8](#figure2-8).

<br>
<figure id="figure2-8">
    <figcaption class="figcaption leftAlign">Figure 2.8: Once logged in, "Listener Management" is the page you should see. This page is under "Admin" in the left side of the screen.</figcaption>
    <img src="pictures/EWSPics/listenerManagement.png" style="width: 500px;">
</figure>
<br>

6. On the left side of the screen, you should see a list of text incorporating different aspects of EWS. Click on "Researcher Page", you should see many different settings, as Figure [2.9](#figure2-9) depicts.

<br>
<figure id="figure2-9">
    <figcaption class="figcaption leftAlign">Figure 2.9: "Researcher Page". By default, you should see many controls and a table containing different audio parameters (cr, g50, mpo, etc.) and frequency band values (250 to 8000 Hertz).</figcaption>
    <img src="pictures/EWSPics/researcherPageNodejs.png" style="width: 500px;">
</figure>
<br>

<mark class="yellowHighlight">
<b>Copied from section 2-3.</b><br><br>
7. You should be within the "Amplification" page. Pay attention to the
settings area labeled "Control via", which have buttons to toggle either
"G50/G80" or "CR/65". Choose "CR/G65".<br><br>
8. You can now change gains in individual bands by entering numerical
values for individual cells in the G65 row. In the G65/All cell, enter 5
for the value. You should see new values for RT-MHA highlighted.<br>
9. Wear your connected audio device. Press the "Transmit" button below
and listen. Your audio experience should be similar to when you entered
the `--gain -15` command in the terminal.<br><br>
10. Navigate to the terminal where you entered the osp command. Enter
`-p`. You will notice values for the different settings for both the left
and right audio channels: overall gain is -20, compression ratio (CR) is
1, and G65 is 5.<br><br>
11. Navigate back to the Researcher Page on your browser. You should still
be in the Amplification section. Navigate to the 3 cells corresponding
to the G65 row and columns 250, 500, and 1000. Enter -15 for each
cell. By setting this value for the 3 cells, you are setting a -15 dB
attenuation for the 250, 500, and 1000 Hz frequencies.<br><br>
12. Press the "Transmit" button below and listen. As a result of changing
these values, you will notice that the low frequency noise is significantly reduced. Depending on the headsets you are using, your experience might be different.
</mark>

&nbsp;  
### 2\-3 Test EWS \(PHP Version\)

1. For testing EWS, open two terminals side by side.
2. In the first terminal, type `osp`. In the second terminal, type `ews`.
3. Open a browser, such as Chrome. Enter `localhost:8080` in the search bar. You will see the landing page as shown in Figure [2.8](#figure2-8).
    
<br>
<figure id="figure2-8">
    <figcaption class="figcaption leftAlign">Figure 2.8: OSP Landing Page. Some of the apps are not yet connected to RT-MHA, but included here for early feedback on the user interface. These in progress web-apps are 4AFC and AB Task apps.</figcaption>
    <img src="pictures/EWSPics/LandingPage.png" style="width: 500px;">
</figure>
<br>

4. There are several blue-green buttons with labels. Navigate and click the one labeled "Researcher Page". What you should see is the Researcher
Page interface, similar to Figure [2.9](#figure2-9).

<br>
<figure id="figure2-9">
    <figcaption class="figcaption leftAlign">Figure 2.9: OSP Researcher Page. You can change Amplification, Noise Management and Feedback Management values from the first, second, and third tabs, respectively.</figcaption>
    <img src="pictures/EWSPics/ResearcherPage.png" style="width: 500px;">
</figure>
<br>

5. You should be within the "Amplification" page. Pay attention to the
settings area labeled "Control via", which have buttons to toggle either
"G50/G80" or "CR/65". Choose "CR/G65".
6. You can now change gains in individual bands by entering numerical
values for individual cells in the G65 row. In the G65/All cell, enter 5
for the value. You should see new values for RT-MHA highlighted.
7. Wear your connected audio device. Press the "Transmit" button below
and listen. Your audio experience should be similar to when you entered
the `--gain -15` command in the terminal.
8. Navigate to the terminal where you entered the osp command. Enter
`-p`. You will notice values for the different settings for both the left
and right audio channels: overall gain is -20, compression ratio (CR) is
1, and G65 is 5.
9. Navigate back to the Researcher Page on your browser. You should still
be in the Amplification section. Navigate to the 3 cells corresponding
to the G65 row and columns 250, 500, and 1000. Enter -15 for each
cell. By setting this value for the 3 cells, you are setting a -15 dB
attenuation for the 250, 500, and 1000 Hz frequencies.
10. Press the "Transmit" button below and listen. As a result of changing
these values, you will notice that the low frequency noise is significantly reduced. Depending on the headsets you are using, your experience might be different.

<br>
<figure id="figure2-10">
    <figcaption class="figcaption leftAlign">Figure 2.10: OSP Web Apps in Console Mode. If you are using a browser such as Chrome, you can right click in the browser window and choose Inspect. In this mode, you can view exchange of information between RT-MHA and the app. You can also change the app to be formatted for laptop and mobile devices using the Toggle Device Toolbar icon.</figcaption>
    <img src="pictures/EWSPics/Console_mode.png" style="width: 500px;">
</figure>
<br>

&nbsp;
## 3 OSP Development\: EWS \(Node.js version\)
##### \[[back to table of contents](#table-of-contents)]

**Note** - This chapter is still a work in progress and will be more complete in the next release.

This section is useful if you want to perform development on the Node.js
version of the EWS. **Please make sure that you have all the necessary
packages installed in your computer before moving forward with
this section. Otherwise, go back to [1.3.1](#1\-3\-1-installing-everything-\--rt\-mha-and-nodejs-version-of-ews) or [1.3.4](#1\-3\-4-installingupdating-just-the-nodejs-version-of-ews) to either install
OSP and EWS - Node.js version or just EWS - Node.js version.**

Now you have the following options:  
1. **Executing the Compiled Node\.js Backend**  
Run the command `./ews njs`. This will install the Node.js version of EWS on your system (which also contains the frontend) and will automatically execute the Node.js backend.
2. **Executing just the Node\.js backend**  
Run the command `ews-backend`. This will execute the Node.js backend
from the `/user/local/bin` directory where it has been installed.
3. **Executing just the Node\.js frontend**
Run the command `ews-frontend`. This will execute the Node.js frontend
from the local `/osp-release-staging/Software` directory.
4. **Executing the Node\.js backend in development mode**  
Run the command `ews njs dev`. This will execute the Node.js backend
in live development mode(using watch), any changes you make to the
backend will be instantly reflected live in the webpages and recompiled
to the backend \(**Note: This code will not compile the frontend
into the backend, for that you will need to run the script in
step 1**\)
&nbsp;   
