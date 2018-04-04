# Realtime-Bluetooth-Networks-Lab1-Run-IO

Lab 1 of [*UTAustinX: UT.RTBN.12.01x Realtime Bluetooth Networks*][link0] at the open online course platform *edX* targets on experiencing the task management without interrupts or RTOS. The course was created by Dr. Jonathan Valvano and Dr. Ramesh Yerraballi at the University of Texas at Austin.

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

## Run the Project

Clone this repository into **C:\Keil\TM4C123Valvanoware** folder and open Lab1 project in Keil.

In the main task of *Lab1.c*, tasks run at their scheduled rates.

| Task        | Function                | Rate (Hz) |
| :---------- | :---------------------- | :-------- |
| Task0       | Sample microphone       | 1000      |
| Task1       | Sample accelerometer    | 10        |
| Task2       | Sample light            | 1         |
| Task3       | Check button            | 10        |
| Task4       | Update plot on LCD      | 10        |
| Task5       | Update text on LCD      | 1         |

*TExaSdisplay*, which is in the **C:\Keil\TM4C123Valvanoware** folder as well, can be used as a logic analyzer or the grader of lab project. Accordingly, in the main task of Lab1.c, **TExaS_Init()** will be **GRADER** or **LOGICANALYZER**.

```c
int main(void) {
    ...
    // TExaS_Init(GRADER, 1571);
    TExaS_Init(LOGICANALYZER, 1571);
    ...
```

Open the TExaSdisplay, click the *Open* button on the Toolbar to connect with  LauchPad's serial port. Switching to *Text Display* or *Logic* on Toolbar depends on how you initialize TExaS in the project above.

#### Task Execution Profile

Task profile is clearly shown on the logic analyzer. Notice that software toggles the pin every time as the task runs. Therefore, a logic analzyer frequency is half of the real task frequency, i.e. a 500 Hz squarewave means the task executes at 1000 Hz rate.

![Task Execution Rates][image1]

#### Lab 1 Grade

The time unit of Grader report is microsecond (usec). **min** is the minimum time and **max** is the maximum time between two consecutive executions of a task. **jitter** equals that **max** minus **min**. **ave** is the average period of a task. **error** is a deviation of **ave** from **Expected** in percentage.

![Lab Grades][image2]

## Demostration

On the LCD display, ***Time*** counts every second. Accelerometer measures the rotation of the device and adds to ***Step***. Microphone performs the environmental ***Sound*** measuring. Tilting light sensor towards the light source or shading the sensor by a finger changes the ***Light*** intensity measured. Switching between different mode by pushing the button.

![Lab 1 Demo Video][gif1]



[//]: # (References)
[link0]: https://www.edx.org/course/real-time-bluetooth-networks-shape-world-utaustinx-ut-rtbn-12-01x-0 "Course Homepage"
[link1]: http://edx-org-utaustinx.s3.amazonaws.com/UT601x/RTOSdownload.html "SW Installation Instruction"
[link2]: http://edx-org-utaustinx.s3.amazonaws.com/UT601x/RTOSKeilInstall.htm "Keil 5.2 Installation"
[link3]: https://www.keil.com/demo/eval/arm.htm "Register Keil"
[link4]: http://edx-org-utaustinx.s3.amazonaws.com/UT601x/RTBN_Install.exe "TExaS Download Part 1"
[link5]: http://edx-org-utaustinx.s3.amazonaws.com/UT601x/RTBN_Installpart2.exe "TExaS Download Part 2"
[link6]: http://edx-org-utaustinx.s3.amazonaws.com/UT601x/InstallDrivers7.htm "LaunchPad Drivers Installation"
[image1]: examples/tasks-execution-logic-analyzer-view.JPG "Task Execution Rates"
[image2]: examples/tasks-execution-grader-view.JPG "Lab Grades"
[gif1]: examples/lab-1-demo.gif "Lab 1 Demo Video"
