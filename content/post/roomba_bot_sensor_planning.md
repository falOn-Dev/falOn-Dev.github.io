+++
title = "Roomba Bot: Planning for sensor interactions"
date = 2024-06-25T17:12:58-04:00
draft = false
pin = false
summary = "Planning for how to interact with the sensors in the roomba wheel modules"
tags = ["robotics"]
categories = ["projects", "roomba_bot"]
+++

Alright! So, now we know the pinout of these wheel modules, incredibly handy for interacting with them. I don't want to just jump into it with motors and automated driving and all that, I just want to start off easy with sensors. Unfortunately, starting off easy does not equal starting off cheap. The BOM for this project is rapidly increasing the more I look into it, and that only somewhat scares me.

The first step in actually making this move, is interacting with the sensors. as I said in the last post, they use that annoying little edge card connector, which means it's difficult to find and purchase a COTS breakout board for this. Luckily, a previous project (my keyboard PCB) is swooping in to save the day, or more accurately the skills I learned during it. I very quickly whipped up a breakout board in Fusion360, and it's not even that expensive to make them! About 10 dollars a board. Unfortunately the minimum order is 5, this also doesn't include shipping or tax.

Once I have these, I will be able to start setting up ROS2 nodes to interact with the roombas sensors, this will be a massive step towards turning the roomba into a modular robotics platform.

# Bill Of Materials

| Item                      | Quantity | Unit Price | Total Price |
|---------------------------|----------|------------|-------------|
| Screw Terminals           | 15       | $1.33      | $19.91      |
| Edge Card Connectors      | 5        | $2.84      | $14.20      |
| Digikey Shipping and Tax  | -        | -          | $8.42       |
| Breakout Board PCB        | 5        | $1.00      | $5.00       |
| PCBWay Shipping and Fees  | -        | -          | $22.03      |
| Raspberry Pi 4            | 1        | $45.00     | $45.00      |
| Adafruit Shipping and Tax | -        | -          | $8.30       |
| **Total**                 |          |            | **$122.86** |
