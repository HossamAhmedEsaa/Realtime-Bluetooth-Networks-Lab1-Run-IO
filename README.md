# Realtime-Bluetooth-Networks-Lab1-Run-IO

Lab 1 of *UTAustinX: UT.RTBN.12.01x Realtime Bluetooth Networks* at the open online course platform *edX* targets on experiencing the task management without interrupts or RTOS. The course was created by Dr. Jonathan Valvano and Dr. Ramesh Yerraballi at the University of Texas at Austin.

## Objectives

1. Prepare hardware devices

2. Set up software environment

3. Run tasks at desired frequencies

## Hardware

- Texas Instruments EK-TM4C123GXL LaunchPad with TM4C123GH6PM microcontroller

- Texas Instruments Educational BoosterPack MKII (BOOSTXL-EDUMKII)

The two hardware devices are required for this lab. Unfortunately, the TM4C123 LaunchPad connects PB6 to PD0, and PB7 to PD1. To run the project correctly, resistors R9 and R10 **MUST** be removed beforehand.

## Software

- Keil IDE

- TExaS software

- LaunchPad drivers

Complete installation instruction can be found [HERE][link1].

This [slide][link2] shows how to download and install Keil uVision IDE v5.2. Go to [https://www.keil.com/demo/eval/arm.htm][link3] and fill out the form with your information and device information as TI Cortex-M4. Download **mdk521A.exe** and install it at some place which is easy to find, such as **C:\Keil**.


[//]: # (References)
[link1]: http://edx-org-utaustinx.s3.amazonaws.com/UT601x/RTOSdownload.html "SW Installation Instruction"
[link2]: http://edx-org-utaustinx.s3.amazonaws.com/UT601x/RTOSKeilInstall.htm "Keil 5.2 Installation"
[link3]: https://www.keil.com/demo/eval/arm.htm "Register Keil"
