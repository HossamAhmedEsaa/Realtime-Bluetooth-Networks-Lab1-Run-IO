# Realtime-Bluetooth-Networks-Lab1-Run-IO

Lab 1 of *UTAustinX: UT.RTBN.12.01x Realtime Bluetooth Networks* at the open online course platform *edX* targets on experiencing the task management without interrupts or RTOS. The course was created by Dr. Jonathan Valvano and Dr. Ramesh Yerraballi at the University of Texas at Austin.

## Objectives

1. Prepare hardware devices

2. Set up software environment

3. Run tasks at desired frequencies

## Hardware Preparation

- Texas Instruments EK-TM4C123GXL LaunchPad with TM4C123GH6PM microcontroller

- Texas Instruments Educational BoosterPack MKII (BOOSTXL-EDUMKII)

The two hardware devices are required for this lab. Unfortunately, the TM4C123 LaunchPad connects PB6 to PD0, and PB7 to PD1. To run the project correctly, resistors R9 and R10 **MUST** be removed beforehand.

## Software Preparation

- Keil IDE

- TExaS software

- LaunchPad drivers

Complete installation instruction can be found [HERE][link1].

#### Install Keil IDE

This [slide][link2] shows how to download and install Keil uVision IDE v5.2. Go to [https://www.keil.com/demo/eval/arm.htm][link3] and fill out the form with your information and device information as TI Cortex-M4. Download **mdk521A.exe** and install it at some place which is easy to find, such as **C:\Keil**.

#### Install TExaS

Test Execute and Simulate or TExaS includes debugging applications and starter projects. The grader is embedded into the lab starter projects, which you can see as TExaS.o object files. The application TExaSdisplay provides a simple oscilloscope function, interacts with serial port running on the LaunchPad.

Download TExaS for Lab 1, 2, 3, 4, 5 [HERE][link4]. Download TExaS for Lab 6 [HERE][link5]. Keil must be installed before installing TExaS. Then you will find TMC123 starter projects in the **C:\Keil\TM4C123Valvanoware** folder.

#### Install LaunchPad Drivers

After installing Keil and TExaS, you will need to install Windows 7 drivers for the TM4C123 LaunchPad. Detailed instruction is [HERE][link6].

## Demostration

In the demostration, ***Time*** counts every second. Accelerometer measures the rotation of the device and adds to ***Step***. Microphone performs the environmental ***Sound*** measuring. Tilting light sensor towards the light source or shading the sensor by a finger changes the ***Light*** intensity measured. Switching between different mode by pushing the button.

![Lab 1 Demo Video][gif1]



[//]: # (References)
[link1]: http://edx-org-utaustinx.s3.amazonaws.com/UT601x/RTOSdownload.html "SW Installation Instruction"
[link2]: http://edx-org-utaustinx.s3.amazonaws.com/UT601x/RTOSKeilInstall.htm "Keil 5.2 Installation"
[link3]: https://www.keil.com/demo/eval/arm.htm "Register Keil"
[link4]: http://edx-org-utaustinx.s3.amazonaws.com/UT601x/RTBN_Install.exe "TExaS Download Part 1"
[link5]: http://edx-org-utaustinx.s3.amazonaws.com/UT601x/RTBN_Installpart2.exe "TExaS Download Part 2"
[link6]: http://edx-org-utaustinx.s3.amazonaws.com/UT601x/InstallDrivers7.htm "LaunchPad Drivers Installation"
[gif1]: examples/lab-1-demo.gif "Lab 1 Demo Video"
