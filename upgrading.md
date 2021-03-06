---
title: Upgrading
prev: progmodel
current: upgrading
next: sleep
published: true
---


Before using Ardhat, make sure you have upgraded to the latest supported version of your host operating system and apps.

If using Ardhat on a Raspberry Pi, see [this guide](https://www.raspberrypi.org/documentation/raspbian/updating.md) on the foundation website.

## Updating the bootloader

The bootloader used in {{<ardhat>}} is a modified version of Optiboot, and is loaded at the factory together with a default [Sketch](https://github.com/Ardhat/ArdhatFirmata)  that runs [Firmata](https://github.com/firmata/protocol) and also manages the Navigation switch and LED.

If required, this bootloader and app can be replaced using the following procedure:

1. Download the ArdhatCloner Sketch from [here](https://github.com/Ardhat/ArdhatCloner)
2. Using the instructions provided in the Sketch, connect an Arduino or compatible processor to the Ardhat ICSP (you can use some simple jumpers as shown in the image below)

<img align="center" src="/media/ArdhatProg.jpg">


3. Install the ArdhatCloner sketch on the Arduino.
4. Restart the Arduino, and the ArdhatCloner sketch will install the latest bootloader and factory default app from the included data.h


<div class="note">
  <h5>Preloading custom apps</h5>
  <p>If you want to load a custom app in place of the factory app, use <a href="https://github.com/jcw/jeelib/blob/master/examples/Ports/isp_prepare/hex2c.tcl">hex2c.tcl</a> which is also included in the ArdhatCloner repository. This handy utility, from JC Wippler of <a href="http://jeelabs.org/">Jeelabs</a> fame, creates a single data.h file from multiple .hex files, which can be used to replace the default data.h</p>
</div>




