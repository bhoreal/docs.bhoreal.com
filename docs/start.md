Welcome
=====
	
Thank you! :)
---

![Bhoreal](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal.jpg)

Hi! You are probably visiting this page because you have just get a Bhoreal controller or you are thinking about getting one.

If you are one of the former group, congratulations on being the owner of a brand new Bhoreal controller! The Bhoreal team wants to thank you for purchasing a controller, joining the community and taking part on this adventure.

If you are one of the latter, thanks a lot for your interest in Bhoreal. We are eager for users who have a similar approach to the understanding and development of open source tools. We would like to invite you to join our community! 

You can also check this project in [GitHub](https://github.com/bhoreal/bhoreal) if you want.

In any case, thank you for being here.

About <a name="about"></a>
---

All Bhoreal control interfaces have a minimalist design. Its external appearance is extremely simple, with a square shape and backlit buttons, without icons or marks. They don’t generate sounds by itself. They’re a blank slate, without any autonomous function. You have to connect them to a computer and associate them to a software in order to work. When you connect Bhoreal controller to a computer, begins a startup test program and the buttons blink. Each button has its own LED and surprise! They’re RGB!

Open Source philosophy is present in both hardware and software design. The firmware is Open Source and all the documentation is released under Creative Common licenses. We love Open Source and we hope you love it too!

About this documentation <a name="about-docu"></a>
---

This is the support page for Bhoreal documents. You can find here all the information you need to get to know all about your controller. You can test if it works correctly as soon as you take it out from the box, also reprogram the firmware in order to use Bhoreal with your favorite software applications. 

A document with these features is too large, so we decided to divide it into seven groups of general interests: **GETTING STARTED**, **HARDWARE**, **FIRMWARE**, **SOFTWARE**, **COMMUNICATION**, **PROGRAMMING** and **CASES**.

These big big groups are divided into more specific subgroups. For example, if you want to know more about the LEDs that are used for a Bhoreal controller, you should go to **HARDWARE** section. If you want to know how to work the serial protocol of Bhoreal, you need to go visit **COMMUNICATION** section.  

There is also a general section of **TROUBLESHOOTING** where you can find the solutions for the most common problems that you may be faced with, when you start to use a Bhoreal controller. 
This is not a finished document and will be modified in parallel with the project evolution. It will be very welcome any kind of comment related to improve the contents or the structure itself.  


Contributions <a name="contrib"></a>
---

This documentation is managed by Bhoreal, but supported by the community. We welcome contributions such as:

- Edits to improve grammar or fix typos
- Additional annotated examples for others to follow
- Additional content that would help provide a complete understanding of the Bhoreal controller

Making a contribution is as simple as forking this [repository](https://github.com/bhoreal/docs.bhoreal.com/tree/master/docs), making edits to your fork, and contributing those edits as a pull request. For more information on how to make a pull request, see [github help](https://help.github.com/).

Atributions
---

Some of this documentation is derived from the Arduino documentation, as the Arduino language and libraries. 

This documentation is built using Flatdoc, an awesome tool for building beautiful documentation from simple Markdown files. Some template features are based on the Spark project documentation by Spark Labs, Inc.


License <a name="licens"></a>
---

All the contents on this page are published under a Creative Commons license: 

Creative Commons Attribution - Non Comercial - Share Alike 3.0 License (CC BY-NC-SA 3.0).

You must give **appropriate credit**, provide a link to the license, and **indicate if changes were made**. You may do so in any reasonable manner, but not in any way that suggests the licensor endorses you or your use.

You can **not** use the material for a **commerical purpouse**.

If you remix, transform of develop from this material, you may distribute your contributions under the **same license as the original**.

To learn more about this license and others visit: http://creativecommons.org/licenses/

<div id="licenseImage1"></div>

Getting Started
=====
<a name="connect-usb"></a>
Connect via USB 
---

Connect your Bhoreal Mini to a computer using a micro USB cable, which is used for the most of smartphones or cell phones. In any case, be assured that the micro USB cable you use allows the device load such as the data transfer. 

The device will be charged by USB connection, and as soon as connect it, the boot sequence will be run. This boot sequence is a gradient color wheel HUE.

Once your controller is switched on, it’s ready for use through some application or software pack, which is compatible with MIDI and *Serie* protocol.


![Bhoreal](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_minis_usbconnection.jpg)

<a name="testapp"></a>
Open Bhoreal Test App 
---

You can download the test application on the following link to check if your Bhoreal works correctly and understand the communication protocol in the best way:

[MAX patch for test Bhoreal](https://github.com/bhoreal/bhoreal/blob/master/software/test_app/Bhoreal%20MINI%20-%20Test%20LED.maxpat)

<a name="midiport"></a>
Select the MIDI port 
---

The Bhoreal Test application uses MIDI protocol to communicate with the hardware. We need to open a corresponding midi port to send and receive MIDI from Bhoreal. Bhoreal is an Arduino based project and the MIDI port appears under the name of “Arduino Leonardo”. Once the MIDI port is selected the device is ready to send and receive data. 

![Bhoreal](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_testapp_1.jpg)

In the test application, the MIDI input is configured to receive from any device, but you should double-click on *noteout* and select “Arduino Leonardo” as mentioned.

![Bhoreal](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_testapp_2.jpg)

<a name="playcolor"></a>
Play with color 
---

The test application works as a MIDI monitor where you can see the messages that "you’re sending" when you press a button or move the slider (*notein* and *ctlin*). Also you can generate a sweep sequence that scans the LED screen using the same colors as the boot sequence, just toggle the "[X]" button above *metro 200*. Here we can see how the [MIDI](#com-midi) protocol works, which is detailed in the [communication section](#com-protocol). 

![Bhoreal](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_testapp_3.jpg)

There is an other Bhoreal Test application you can download [here](https://github.com/bhoreal/bhoreal/blob/master/software/test_app/Bhoreal%20MINI%20-%20Test%20LED.maxpat), where you can play with the different MIDI messages the Bhoreal can receive for LED color change. 

![Bhoreal](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_testapp_4.jpg)


Go further!
---

If you want to learn more about your Bhoreal device, you can keep reading the following sections where we will explain you with details about the [hardware](#hardware) and its components, how to install the [programming environment](), the [communication protocols](#com-protocol), the [programming languages]() and the most important functions of the [firmware](#firmware), with dozens of examples that third-party software uses. 


<a name="com-protocol"></a>
Communication Protocol 
=====

Bhoreal can use two communication protocols: Serial and MIDI, 
but the MIDI protocol is the prior and will be used for the most of available applications. 

Now, we will show you the current command document, these commands can be expanded in the future adapting the user's needs. 

Also it's possible that each person could use their own code and commands as open firmware is used, and anyone can access to the code. 

If someone develops something interesting in this sense, we’d like to ask them to share it with the rest of the community, using any of the available tools or by making full requests to this documentation. 



<a name="com-serial"></a>
Serial 
---

The Serial communication - also known as RS-232 - is based in the serial transmission of information through a bidirectional data cable. The communication is asynchronous with 8 bit packages and always needs an additional bit for the synchronization. This makes high velocities can not be reached, being 115200 Bd (bauds) the higher one recommended for Bhoreal.

Bhoreal uses the same serial protocol as Arduino to communicate with the programming tool, this protocol is always used whenever a firmware update is done. Bhoreal serial port levels are TTL, that is to say, the ‘0’ logic corresponds to 0 volts and the ‘1’ logic corresponds to 5 volts on the bus. 

To activate the serial communication with Bhoreal it’s necessary to turn on the firmware flag, which comes disabled by defect. This is because the communication becomes a bit slower when the MIDI and the Serial are used simultaneously. Therefore, the users are free to select a communication port or any other port, simply turning on these flags (`#define  SERIAL_ENABLE` and `#define  MIDI_DEBUG`at the beginning of *Bhoreal.h*). 

```
#include <Arduino.h>
#include <Wire.h>
#include <avr/pgmspace.h>

#define  MINI  			0  //Matrix size
#define  SLIM  			1  //Matrix size
#define  SLIMPRO  		2  //Matrix size

#define  SERIAL_ENABLE  1
#define  MIDI_DEBUG     1
#define  SERIAL_DATA    0

#define  TOOFULL 		100

#define  MODEL  MINI 		//Model
//#define  MODEL  SLIM 		//Model
//#define  MODEL  SLIMPRO 	//Model
```

Next, we will show the available serial commands:

![Bhoreal](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_serialprotocol_table.jpg)


<a name="com-midi"></a>
MIDI 
---

The MIDI communication is a specific serial protocol which were started to use in the 80’s, to communicate among digital musical instruments. The MIDI protocol has many followers maintaining the compatibility with the most of audio/video softwares in real time. 

The MIDI in Bhoreal is *Compliant USB MIDI*. This means it works with a standard library that doesn’t require external drivers, which makes very easy the installation. Plug and play!

The compatibility of Bhoreal with *MIDI USB Compliant*, unlike to Arduino, is because of the use of a specific *Hardware Core* that enables the MIDI functions on the firmware. For that, we’ve relied on the open source project ARCORE. Check out the installation section of [programming environment]() for more information.  

Next, we will show the available MIDI commands:

![Bhoreal](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_MIDI-table.jpg)


<a name="hardware"></a>
Hardware 
=====

Mini
---

![Bhoreal](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_minis.jpg)
![Bhoreal](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_mini_front.jpg)
![Bhoreal](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_mini_back.jpg)

<a name="microcontroller"></a>
### Microcontroller

![Bhoreal](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_mini_back_microcontroller.jpg)

The Bhoreal Mini Slim uses the ATmega32U4 microcontroller for its processing power. You can download the datasheet [here](http://www.atmel.com/Images/Atmel-7766-8-bit-AVR-ATmega16U4-32U4_Summary.pdf).

Some of its key features are as follows:

- 16Mhz operating frequency
- 12 KB of Flash memory
- 8-bit AVR
- 2.5 KB of SRAM
- 10 bit ADC
- USB 2.0 full-speed interface
- USART, SPI and I2C interfaces
- JTAG Debug mode

<a name="transistors"></a>
### Transistors

![Bhoreal](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_mini_back_transistor.jpg)

There are two transistors on the PCB that have a very important role for the electronic operating: Q1 and Q2. Those *Mosfests* are in charge of the screen refresh control. Since the consumption of the LED matrix to maximum intensity exceeds the maximun the USB port allows (500 mA), we’ve chosen the strategy of multiplexing the screen control. 
For that, we’ve made two groups of independent LEDs, which are controlled by Q2a and Q2b, they alternate to divide into two the consumption and the light intensity. Q1 is a control signal investor that acts on Q2b, while Q2a is connected directly to this signal. This frequency is controlled by firmware and is very high, so we couldn't notice the blinking of the screen. This is possible because the WS2812 has two independent VCC lines, one for the LED and the other for the digital driver WS2811, embed in the LED capsule.

<a name="fuse"></a>
### Fuse

![Bhoreal](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_mini_back_fuse.jpg)

The Bhoreal Mini Slim board has a resettable polyfuse that protects your computer's USB ports from shorts and overcurrent. Although most computers provide their own internal protection, the fuse provides an extra layer of protection. If more than 500 mA is applied to the USB port, the fuse will automatically break the connection until the short or overload is removed.

<a name="icsp"></a>
### ICSP

![Bhoreal](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_mini_back_icsp.jpg)

The connector *In Circuit Serial Programming* or commonly called ICSP allows to reprogram the microcontroller ATmega32U4 from a compatible external programmer. This method allows to restore the device bootloader completely or update it, if it’s necessary.  

<a name="leds"></a>
### LEDs 


![Bhoreal](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_mini_front_led.jpg)

Bhoreal Mini incorporates 16 SMD RGB digital LEDs and 2 yellow LEDs for signals. In case of RGB digital LED, the used model is the WS2812 with 6 pins. They stand out because of the use of the control chip wS2811, embed within the LED, simplifying a lot the external electronics and the space the boards occupy. 
This type of digital LEDs are waterfall direccionables. The data is transferred one by one through the DIN and DOUT pins, which work as a high-speed serial port, so, for the control of microcontroller, it only needs a data pin.
The data refresh frequency is 800Kbps. The power for the LEDs and the control chip is splitted, and that allows a very fast multiplexing of the LEDs, therefore, an optimization of energy consumption.

There are also two yellow LEDs on the Board to show the state of serial and MIDI communication port.

You can download the datasheet [here](http://dlnmh9ip6v2uc.cloudfront.net/datasheets/Components/LED/WS2812.pdf).

Features:

- Viewing angle: 120 degrees
- Red: (620-630nm) @ 550-700mcd
- Green: (515-530nm) @ 1100-1400mcd
- Blue: (465-475nm) @ 200-400mcd

Forward Voltage: 

- Red: 1.8-2.2V
- Green: 3.0-3.2V
- Blue: 3.2-3.4V

<a name="usbport"></a>
### USB port

![Bhoreal](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_mini_front_usb.jpg)

Bhoreal Mini has a Micro USB connector that enables the connectivity between the device and the USB communication port. Simply connect it to a computer with a micro USB cable to get started.

<a name="pads"></a>
### Pads

![Bhoreal](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_mini_front_pad.jpg)

The translucent silicon keypad has 16 buttons and is based on the original design of Sparkfun, and considering the perfect function with SMD WS2812 LED which are used for the Bhoreal board.
Each one of the buttons has a conductive ring at the bottom that works as a switch when the conductive surfaces of the PCB is slightly pressed. 

There are two keypad models adapted the different type of LEDs. 

<a name="slider"></a>
### Slider

![Bhoreal](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_mini_front_slider.jpg)

Bhoreal Mini Slide version has a 60mm slide potentiometer. With this slider you can send the lineal position datas in real time through the USB port, or interact with LED matrix. 

You can download the datasheet [here](http://www.alps.com/prod/info/E/PDF/Potentiometer/SlideGeneral/RS__1/RS__1.PDF).

Features:

- ALPS RS6011YA6009
- 10 kOhms Linear potentiometer
- 9 mm W x 75 mm L


<a name="reset"></a>
### Reset

![Bhoreal](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_mini_front_reset.jpg)

The Reset push button allows to reset the microcontroller and to reboot the firmware. This button activates the Reset circuit which is 100% compatible with Arduino Leonardo. 

<a name="iopins"></a>
### I/O Pins

![Bhoreal](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_mini_front_iopins.jpg)

Bhoreal Mini has expanding pins that allows to extend the board’s possibility - adding sensors, actuators or other Bhoreal devices to communicate among them. The expanding socket consists of 5 analogue/digital inputs that correspond to the microcontroller pins [A0-A4], a 5V power line and GND. Those pins can be configured as digital outputs when is required. 

You have to take into account the consumption during the use of LED matrix, and limit the expanding port consumption in every case to avoid the overloading of USB port.  

Features:

[ VCC  A0  A1  A2  A3  A4  GND ]  

<a name="layout"></a>
### Layout

![Bhoreal](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_mini_layout.jpg)

"Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."

<a name="scheme"></a>
### Schematics

![Bhoreal](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_mini_schematics.jpg)


<a name="eagle"></a>
### Eagle file

![Bhoreal](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_mini_eagle.jpg)

(license)

<a name="slim"></a>
Slim
---

coming soon!

<a name="slimpro"></a>
Slim Pro
---

coming soon!


<a name="firmware"></a>
Firmware
=====

Here is an [example](https://github.com/bhoreal/bhoreal/blob/master/firmware/bhoreal_slim_midi/bhoreal_slim_midi.ino) of the Firmware, taken from Github.

```
#include <Arduino.h>
#include "Bhoreal.h"

// Serial data transfer rate
#define BAUD 57600

Bhoreal Bhoreal;

void setup() {
  //Bhoreal.begin(SLIM, BAUD);
  Bhoreal.begin(BAUD);
  // Run the startup animation
  Bhoreal.startup();
}
  
void loop () {
  // Turn on the lights
  Bhoreal.midiRefresh();
  // Check the button states
  Bhoreal.checkButtons();
  // Check and report the ADC states, if necessary
  Bhoreal.checkADC();
}
```

### Uploading (Bhoreal MINI Programming Tutorial)
---

Each one of the following pictures responds to a point of the tutorial, in the same order. First picture shows what poin 1 tells, the second one for point 2, etc.

- 1. **Connect the ISP programmer to the computer**
Go to device administrator panel and check the device. See picture. In Windows7 the correct driver is not installed, so it’s necesary to do it before to connect.

![Bhoreal Firmware Uploading](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_firmwaretut_01.jpg)

- 2. **Update controller**
Go to properties and click the update controller button.

![Bhoreal Firmware Uploading](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_firmwaretut_02.jpg)

- 3. **Install the drivers**
Download to the desktop the drivers from this [link](https://github.com/bhoreal/bhoreal/blob/master/firmware/avrispmkii_libusb-win32_1.2.1.0.zip) and select the folder shown in the picture.

![Bhoreal Firmware Uploading](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_firmwaretut_03.jpg)

- 4. **Check the device installed**
Connect again the ISP programmer and check now the device configured correctly in the software.

![Bhoreal Firmware Uploading](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_firmwaretut_04.jpg)

- 5. **Connect the micro USB**
Connect a micro USB wire to the computer.

![Bhoreal Firmware Uploading](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_firmwaretut_05.jpg)

- 6. **Check the Microcontroller**
Go to device administrator and check if the microcontroller is detected by the system.

![Bhoreal Firmware Uploading](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_firmwaretut_06.jpg)

- 7. **Download the Arduino development software**
Go to this [link](http://downloads.arduino.cc/arduino-1.0.6-windows.exe) and download the windows installer version.

![Bhoreal Firmware Uploading](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_firmwaretut_07.jpg)

- 8. **Setup the software**
Install and open the software. After that, go to tools/boards and select *Arduino Leonardo*.

![Bhoreal Firmware Uploading](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_firmwaretut_08.jpg)

- 9. **Setup the software**
Go to tools/programmer and select *AVRISP mkII*

![Bhoreal Firmware Uploading](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_firmwaretut_09.jpg)

- 10. **Upload the firmware**
Then, prepare the ISP connector as you see in the picture. You can use a 2x6 pin array male-male.

![Bhoreal Firmware Uploading](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_firmwaretut_10.jpg)

- 11. **Upload the firmware**
Connect the ISP connector the same way as the picture, and check if the green led of the ISP mkII is activated. Maybe you have to press laterally a little bit the  ISP to ensure that there's a good contact in all the pins. Only it’s necessary a small pressure or pull the wire, like the picture.

![Bhoreal Firmware Uploading](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_firmwaretut_11.jpg)

- 12. **Upload the firmware**
Then you have to find the firmware folder and open it into the programm. Go to file/open and find the file **bhoreal_slim_mini_test.ino**
After this, click in file again and click into **upload using programmer** option. The programming will start. During the process yo have to see some leds blinking in the programmer.

![Bhoreal Firmware Uploading](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_firmwaretut_12.jpg)

- 13. **Upload the firmware**
If all is ok the firmware has to be uploaded correctly. Check the message of *Done Uploading!*.

![Bhoreal Firmware Uploading](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_firmwaretut_13.jpg)

- 14. **Final test**
Thats it!
if all the process is ok you have to see the screen test with Red, Green, Blue and white transition. At this point is recommended to wait some minutes because some times the damages LEDs stop to working with high temperature.
After check you can go to the next board and come back to the point 11 of this tutorial.

![Bhoreal Firmware Uploading](https://raw.githubusercontent.com/bhoreal/docs.bhoreal.com/master/docs/images/bhoreal_firmwaretut_14.jpg)

### Code
---
coming soon!

### Libraries
---
coming soon!

### Atributions
---
coming soon!


Software
=====

### Processing

cooming soon!

### Pure Data

cooming soon!

### Max

cooming soon!

Case
=====

Mini
---
Slim/Slim Pro
---


Troubleshooting
=====

Test de subida y sincronizacion! Alex Github!!!
