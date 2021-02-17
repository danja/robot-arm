# Robot Arm

The aim is to build a simple, small, inexpensive robot arm using an Arduino to drive stepper motors.

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

## Tools & Materials

I'm reasonable well equipped for working with wood and have quite a bit of 4mm aluminium sheeting. I have some bearings and ordered some [https://www.amazon.it/gp/product/B07QH94G71](toothed wheels and timing belt) that should work well with the motors.

## Design

