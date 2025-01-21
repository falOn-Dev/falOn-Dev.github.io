+++
title = "The adventures of going out of scope; And the beginnings of CartPole"
date = 2025-01-20T20:02:44-05:00
draft = false
pin = true
summary = "Putting old projects to rest, and the start of a new one with tight requirements"
tags = ["cad", "electrical", "3d-print"]
categories = ["projects"]
+++

# Preface - Going out of scope

When you look at my blog, it's very easy to notice quite a few incomplete projects. This is due in part to my constant desire to overcomplicate everything I touch, which in turn leads to taking the idea of project scope, and microwaving it for a few minutes. Whether it be money (in the case of the keyboard), or the tools I have availiable (in the case of the roomba), or many other options, I'm very good at blowing constraints out of the water.

I don't enjoy having unfinished projects, but as of right now, many uncompleted projects need to be put on the shelf for some period of time. I have taken this, and set forth on a new journey, the journey to finish a project using the absolute minimum resources. Such began CartPole

# What is CartPole?

CartPole, Cart-Pole, or Cart Pole, are all different ways it's written as, although I do doubt that was your first question. CartPole is often used to train reinforcement algorithms, it is a pretty basic system of a cart moving on one axis, with a pendulum attached to it. Jeffery Chang has a lovely visual example [HERE](https://jeffjar.me/cartpole.html).

CartPole serves as a simple to construct, but complex to control system, useful for anything from learning PID, to practicing the creation of ML reinforcement algorithms.

# Setting constraints

As stated in the preface, I have issues staying in scope. For this project I decided to pull in my constraints as much as possible, to the point of restriction. The first step to this, was purchasing as little as possible. If I already own something similar to what I want, tough cookies, I'm using what I have. I also intended to use as much old material as I could pull from my robotics team's shop, and have to design around that. Along with any parts from my recently dissasembled Ender 3 V2.

# Designing CartPole

This project was designed in OnShape. I recently picked it up working on my robotics team, and I like it a lot more than fusion. It also has the added advantage of being availiable on linux, which I daily drive rather than windows.

I found a piece of 1" x 1" V-slot extrusion in my team's shop, and decided to use this as the basis for my project. After some deliberation the general structure I came to was the following:
    - Carriage made up of two 3D printed plates, sandwiching the V-wheels riding on the extrusion.
    - Front plate has a bearing to hold the pendulum at the top.
    - Back plate serves as an electronics "backpack", connects to an MPU6050 on the pendulum using a slip ring, powered by a USB battery pack transmitting data with a radio module.
    - Driven by a stepper motor at the end of the extrusion, similar to how bedslinger printers control their print head.
    - Use the threaded rod from the Ender 3 Z-axis as the rod for the pendulum, use steel blanks for coin making as the weight.
    - Rasperry Pi "Brain" at one end, recieving the data from an arduino on the backpack, and controlling the stepper.

As of right now, I've selected all of my parts, and I am finishing up the design! Most of the structure will be built from 3D printed parts, or pulled from the Ender, using M3, M4, and M5 bolts, nuts, and heat set inserts. Once I finish up the CAD I will need to source about 115 USD for parts, and then it's off to the races!