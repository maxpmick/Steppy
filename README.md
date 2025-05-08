# 🚗 Steppy

![8cacbb82-e8cf-46d6-8a27-ba90b54e280e](https://github.com/user-attachments/assets/33447f47-9df4-46fd-89c5-9a1c604a0bae)

A 100% recycled mobile robotics platform, built (almost) entirely from an Ender 3 and some printed parts.

## 📝 Overview

I was sitting around thinking about how I could get started in robotics, and how to do it as cheaply as possible. My poor old Ender 3 V2 in the corner stared at me longingly, looking for a purpose in life since I had bought a Creality K1C.

Thus, Steppy was born.

I'm not the best at writing readme files, especially when the project is still at its inception, but I'll share my progress here as I develop it, and hopefully other makers will build their own, re-using the obligatory Ender 3 in a closet that all makers end up with eventually.

## 🎯 Project Goals

* Reuse as many components as possible from the Ender 3 V2—like, seriously everything.
* Create a functional robot car platform that can be used for other projects, not something that gets in the way of its actual purpose.
* Demonstrate creative hardware repurposing.

## 🔧 Components Used

* **Printed Parts** (you either have a working Ender 3, or another 3D printer)
* **X, Y, Z, and E** stepper motors for 4 wheel drive
* **GT2 Pulleys and Belts** (TBD if I’ll stick with belt drive, cutting and splicing these things is a nightmare…)
* **All** included M5 fasteners, bearings, and bushings
* **WIP:** Re-using the control board. Boards with STM32 work great; mine is a GD32F303 on the V4.2.2 and I haven't figured out how to replace it's bootloader. If you have tips, please reach out!

## ⚙️ Mechanical Details (WIP)

The current MVP for the drivetrain is pictured below—a 3:1 gear reduction from the motor to the wheels ensures we have enough torque to avoid stalling under load.

<img width="670" alt="Screenshot 2025-05-08 at 3 56 04 PM" src="https://github.com/user-attachments/assets/0f7226f4-e4be-4ee8-9f90-18b4d5ad1ab9" />

A concern with this design is the strength of spliced belts. While it would be super neat (and further the goals of this project) to re-use the GT2 belts from the X and Y axes, I'm not sure how well a glued splice would hold up over the long-term. I currently use the printable [GT2 belt-splice tool](https://www.thingiverse.com/thing:1814419) from Thingiverse to cut up the X and Y belts to proper lengths.

Another concern is the ~7mm of axle that is actually supported in the frame, while the internal bearing design is solid, I think I'll end up reworking it some to give it more support while still re-using the M5 x 45mm included bolts.

## 🔋 Electrical Details (TBD)

Since I'm still working on the mechanical aspect of this, the electrical design is somewhat up in the air.

I intend to re-use the main Creality control board, connected via serial to an ESP32, Pico 2W, or similar for wi-fi, since having a 4 channel stepper motor driver already included for free is a great win. I'll also re-use the provided fan for ventilation.

The current prototype (what I'm testing with) is just a perf board with 4 A4899 Stepper Motor Driver breakout boards connected to a Pico 2W, but as soon as I finish either modifying a build of Marlin to add custom Gcode commands, or find a way to properly target the GD32F303 board when compiling in Arduino IDE, I'll switch to the Creality board and update this repo.

## 🤝 Contributing

This project is very much in alpha, if you:

* Figure out how to reprogram the GD32F303 on the V4.2.2 WITHOUT needing to glue together custom bootloaders and solder debug headers to the board.

please open a PR or drop me an issue!

## 📄 License

This project is open source under the MIT License. Seriously, do whatever you want—just don’t forget to give credit. Happy recycling!
