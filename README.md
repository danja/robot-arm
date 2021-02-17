# Robot Arm

The aim is to build a simple, small, inexpensive robot arm using an Arduino to control stepper motors.

#### Status 

**2021-02-17** Planning, set up this repo

This is a really low-priority project. I've ordered motors etc. but it'll be about a month before they arrive.

More detailed notes will go in [devlog.md](devlog.md).

![overview sketch](https://github.com/danja/robot-arm/blob/main/images/overview-sketch.jpeg)

## Motivation

I recently bought an [Arduino Kit](https://www.banggood.com/Geekcreit-UNOR3-Basic-Starter-Kits-No-Battery-Version-for-Arduino-Carton-Box-Packaging-p-1133595.html) which contained a servo and a stepper motor. I've used Arduino and related boards before but have never had a go at robotics. Out of curiosity I had a play with the servo and came up with the [Cat Annoyer](https://github.com/danja/cat-toy). It was astonishing how easy it was, so now I want to have a go with stepper motors.

For years I've wanted an plotter, but rather than taking the standard X-Y route I think it will be more fun to make a robot arm with a pen instead of a gripper (maybe experiment with grippers later). The ultra-cheap servos would struggle with the kind of torques the arm is likely to encounter, also they are rather jittery. Hopefully using 28BYJ-48 stepper motors will cover these issues. 

## Requirements

* Enough degrees of freedom to enable drawing
* Enough reach to cover an A4 sheet
* Wherever possible, use tools and materials I already have

## Components

To keep costs down I intend using very inexpensive parts:

* Controller : Arduino attached over USB to PC 
* Stepper motors : 28BYJ-48
* Drivers : ULN2003
* Power Supply : no sure if this will be necessary, but a 9v power pack (with whatever regulation is needed) will be an easy way of giving the drivers enough current

For the microcontroller, an Arduino Nano should be adequate, though if more IO is required a Mega2650 or whatever. A possible future angle could be using an ESP32 to enable wireless control. 

## Tools & Materials

I'm reasonable well equipped for working with wood and have quite a bit of 4mm aluminium sheeting and suitable hand tools. I have some bearings and ordered some [https://www.amazon.it/gp/product/B07QH94G71](toothed wheels and timing belt) that should work well with the motors.

![parts](https://github.com/danja/robot-arm/blob/main/images/bits.jpeg)

## Software

For code on the Arduino I'll use PlatformIO on VSCode on Ubuntu.

I *think* it'll be best to put low-level translation code on the Arduino, so the movement can be driven from the host PC over USB serial with statements of the form ```moveTo(x, y, z)```. I need to research it a little, but for the drawing application this could be simplified to things like: 
```
drawPoint(x, y)
drawLine(x1, y1, x2, y2)
```

From there is's all TBD, but I do want to play around with parametric drawing (to do things like Lissajous, & chaotic figures), drawing from vector images (SVG), raster scans & calculated/optimised human-like drawing (perhaps with a bit of machine learning). 

## Design

Only just starting to think about this. Some considerations:

* the *end effector* should be able to able to smoothly move through 3D space with a max reach of around 30cm
* ease of construction/dismantling, to allow simple modification
* accuracy and (adequate) dexterity are key requirements
* speed is a non-requirement
* materials - wooden support, aluminium spars
* sensors? - it may be desirable to add sensing elements such as rotary encoders and/or IR proximity detectors

General considerations are weight distribution and the reduction of unnecessary loads on the motors. Weight in itself is a non-issue, but the moving parts should be reasonably light to allow easy movement. The system when at rest should be as stable and rigid as possible to allow accurate movement.  

Looking at existing designs, a suitable approach would seem to be :
1. fixed base
2. horizontal rotating platform
3. first elbow joint
4. 2nd elbow joint
5. end effector joint

To reduce the static strain on the motors and increase rigidity, at least the first arm section should be doubled, ie. two spars with 2 or 3cm spacing between them.

I plan to experiment a little with joints using wooden spars to get an idea of suitable proportions, mechanisms etc. 

#### Base

A heavy piece of plywood would seem the easiest. 

#### Rotary Platform

This will need to take the whole weight of the arm, so it seems to make sense for it not to be directly driven by the motor. 

![rotary platform sketch](https://github.com/danja/robot-arm/blob/main/images/rotary-platform-sketch.jpeg)

#### 1st Elbow Joint

In the first instance, driving this directly from a motor (mounted on a bracket attached to the rotation platform) seems worth a try. An on-axis bearing can help with the load.

#### 2nd Elbow Joint

TBD. Direct drive, with the motor local to the joint is the easiest option, but for better weight distribution it might make sense to mount the motor close to the 1st Elbow Joint and use a drive belt to connect it to the joint.

#### End Effector Joint

TBD. At least for the plotting application, a passive joint that simply keeps the end section vertical will be adequate.

**Later** : a simple servo-based gripper and/or sensors might be useful.