+++
title = "Kotlin For FRC - Browser Extension"
date = 2024-09-25T00:27:27-04:00
draft = false
pin = false
summary = "The process leading up to creating a browser extension to enhance documentation"
tags = ["programming", "robotics"]
categories = ["project"]
+++

So, I've been up to some things. For those of you who don't know, I'm a member of FRC 2537, and we use Kotlin to program our robots. This is somewhat abnormal as Kotlin is not an officially supported language, however, Kotlin is based off of the JVM. Kotlin being a JVM language means it interops (almost) perfectly with Java, which is a supported language. This means the barrier of entry in terms of functionality is incredibly low.

However, the barrier of entry in terms of knowledge is much higher than it would be to use Java, namely because of the lack of teams using Kotlin! Out of the couple thousand FRC teams, well over 80% use java, and well under 1% use Kotlin, this works out to less than twenty teams that use Kotlin for their FRC robots. So here is the problem, there is no official FRC documentation that includes kotlin code blocks, so I set out to change that, and here is the general process of how that went.

## PR Into the WPILib Documentation

The ideal starting point was simple, there is a website in existence for documenting Java, C++, and Python, the official languages. Why not try and simply get some Kotlin code blocks pulled into that! Unfortunately, this causes some problems, the big one being that it implies that Kotlin is official (which I will remind you it is not), and being official implies that volunteers at events, and a majority of people will be able to help you with your code, neither of those are reasonable when Kotlin in FRC is so new.

However, something good did come out of this, I was given an idea by one of the developers of WPILib (the library used for FRC robot code), he suggested I create a browser extension to inject Kotlin code blocks into the WPILib wiki, so all the information is still in one place, but people have to install it themselves, and therefor it won't be so easy to assume that it's official.

## FRC-Kotlin-Blocks Browser Extension

The way I saw it, the first step was determining a way to detect where the code blocks were in the HTML. The WPILib wiki is generated from markdown files (like this blog!), which meant that the way it formatted code blocks could be pretty strange, luckily it turns out all of the HTML elements that contain these code examples, have the same class name, and JavaScript (the language of choice for browser extensions) provides functions to get an array of all elements with a class name!

Once we get an array of all the code block elements, the extension will pull from its github repository to get YAML files that contain the code blocks. I used YAML because unlike JSON you can use newlines and whitespace, which makes manually typing the code out easier. It then will take this code and parse it into the right HTML to append to the end of the code block element, to add in a new tab to the top for Kotlin, as you can see below.

![Screenshot of the WPILib documentation to show the injected Kotlin code block](kt_codeblock.png)