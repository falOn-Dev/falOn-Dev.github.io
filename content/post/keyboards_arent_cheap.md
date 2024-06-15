+++
title = "Keyboards aren't cheap"
date = 2024-06-14T01:13:57-04:00
draft = false
pin = false
summary = "Why I started, and didn't finish my custom keyboard: What I learned making a keyboard PCB"
tags = ["cad", "electrical"]
categories = ["projects"]
+++

As the title suggests, I recently took up the project of designing a custom keyboard PCB, case, and firmware (using QMK). As the title *also* suggests, I didn't finish it.
Fun fact about me, for all the cool stuff I do, I can be very naive, or more accurately I can underestimate the cost of a project, both in time, and money.
In this case, what really got me was the PCB cost, I designed everything, only to drop it into PCBway, and find that the left half of the board alone (we'll get to that) would be nearly one-hundred dollars per board. Unfortunately that was slightly out of my price range, so I will be temporairily halting the progression of this project, but who knows, maybe I'll pick it up again later!

### The Idea

Like any project, it needed to start with an idea, unfortunately this was a problem for me. I knew I wanted to build a full sized keyboard, to replace the shoddy office keyboard I've been using. I also knew that I wanted a 100% or near 100% board, I didn't want to be missing keys. This causes a problem, when designing a keyboard it's usually wired and programmed in a "matrix". A keyboard matrix is comprised of rows and columns, and unfortunately every individual column or row requires a GPIO pin, and a Pi Pico (my board of choice) just ***barely*** has enough GPIO pins for a full 100% matrix. I also wanted to add some extra things like possibly some dials or extra buttons, so clearly this wasn't an option! The "solution" I decided upon was using QMK's "split keyboard" functionality. This would allow me to wire the letter and number rows to one pico, and the numpad, arrows, and navigation keys to another! This decision would provide me the freedom to add extra functionality to the right half of the keyboard, namely two encoders with built in push buttons, for volume control, and something else.

With these decisions in mind, I began work on the layout in [KLE](http://www.keyboard-layout-editor.com/), creating a sort of warped 60% keyboard for the left half, and a strange amalgamation of the numpad, navigation, and arrow keys. Once finished with that I moved on to the design process!

![Left Side Layout](keyboard_left_layout.png)

### Design First, Think Later

My first designs for the left and right PCBs were understandably mid. This was largely a project to teach myself how to use Fusion360's electronics design suite, so I wasn't expecting to get it right the first time. I decided I wanted to do all throughole as I am a very inexperienced solder-er. Being completely new to F360 ECad meant that this took significantly longer than it really should've (largely because I didn't know there was a script to snap stuff to your grid after changing it). 

Technically I had two functional PCBs at the end of this, but they really weren't done right. One of my biggest mistakes was designing the PCBs first, rather than designing the shape of their enclosure, it's much harder (for me at least) to design around an existing board, than it is to design inside an existing enclosure. With all of this in mind, I decided my best choice would be to start over, keeping what I learned in mind for the second time around.

### Rethinking Ideas

With two finished PCBs under my belt, I was now a lot more comfortable with F360's ECad suite, including creating and modifying my own part libraries, which was very nessecary considering one of the decisions I made for the second version, I was going to use surface mount. Now, I didn't really want to use surface mount components, but I did want to use what are called "hotswap sockets", these allow the keyboard's switches to be easily swapped, without needing to be desoldered, and then resoldered with new ones, and these only really come as surface mount components.

I also of course knew this time to design the case's profile first, then the PCB to reduce my headaches later in the process.

### Design Two: Electric Boogaloo

I won't be as detailed with talking about the second design as it was much less eventful, largely due to me setting my constraints earlier on, namely designing a placeholder case to derive a PCB shape from. Other tiny things streamlined this like my discovery of a script that would allow me to snap parts back onto the grid in the PCB designer after modifying it, although it does still confuse me why that isn't the default (or at least worthy of a little "would you like to snap parts to new grid" dialog box).

I decided this time I would design the entire left half first, the PCB, case, and key plate, before moving on to the right side. This would (theoretically) allow me to catch any major mistakes earlier on, and it certainly did. Once I had designed the PCB, and started on the case, I decided to get an estimate from PCBway. What I saw was unsurprising, but unfortunate, to manufacture these PCBs, it would cost around sixty dollars per PCB, leading to a nearly 300 dollar cost for the minimum order of five of them.

Knowing this I had to make a decision, do I finish the project, knowing I can't build it, or do I cut my losses and just finish the left half. I decided to call a time-out for now, leaving the right half unfinished, largely because I still accomplished most of what I set out to do with this project. I learned the basics of Fusion360 electronic design, and even some more advanced features. This is a project I would love to pick back up in a little while, if I find myself with more funding to throw at a project like this, but until then, I'm very happy with what I did.

![Left Keyboard PCB](keyboard_left_half_render.png)

### Conclusion

Alright, what did I learn?
- Fusion360's Electronics Design Suite
- QMK Firmware Creation
- The Importance of Constraints
- How expensive PCBs are!

With all of that in mind, although I didn't actually build the keyboard, I'd consider this project a success.