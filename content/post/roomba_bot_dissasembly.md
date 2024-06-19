+++
title = "Roomba Bot Project: Dissasembly"
date = 2024-06-17T18:22:20-04:00
draft = false
pin = false
summary = "Discoveries while dissasembling a Roomba"
tags = ["robotics"]
categories = ["projects", "roomba_bot"]
+++

In a continuation of the Roomba project, I just recently finished dissasembling it and figuring out how it works. Within this post you can find some of the important things I discovered while working on it.

## Modularity

The biggest important thing I learned is that most of the individual parts (each wheel, the rubber dust rollers, the spinning brush on the front) are all almost completely modular! All of them except for the spinning brush even use this handy dandy little connector.

![Wheel Pinout](wheel_pinout.png)

## Wheel Control

That image specifically is the pinout of one wheel "module". This taught me two very important things about this project, one good and one less good, being:
- I was going to need a motor driver board
- The wheels have encoders
Now, I feel like it's obvious which is which, but just in case, the encoders is the good one. This means I can more accurately control (and even automate) the roomba once its completed. The annoying part is those A and B pins, those are for controlling the motor, and I'll need a motor driver board for that.

The other semi-unfortunate part about the wheel control, is I'm gonna need a breakout board to easily connect to those connectors, but I do have a solution!

![Wheel Breakout Board](wheel_breakout_board.png)

Funny enough, the solution to needing a breakout board, is a breakout board! I whipped one up in f360 really quickly, and it uses a COTS 6-pin edge card connector, theoretically this will fit right into the little slot in the chassis that the connectors sit in, and just wire them straight up to a handful of screw terminals to make prototyping easier! Maybe I'll design a real mainboard at some point, but I learned that's expensive recenly, so probably not.

## Summary

Basically, I took my new friend apart, documented his insides, and put him back together, easy. I'm starting to figure out how to actually electronically interface with the parts, and then I'll work on the software, so stay tuned for that!