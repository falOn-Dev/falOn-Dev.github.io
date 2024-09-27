+++
title = 'Early Experienced w/ Rust'
date = 2024-06-10T16:43:59-04:00
draft = true 
pin = false
summary = "Thoughts and opinions about Rust from a first look"
tags = ["research", "programming"]
categories = []
+++

I've spent the last few weeks reading through the rust book and I figured it might be worth putting some of my thoughts down on paper, so here it is.

## Rust Object Oriented
The bulk of my interest in rust has come from its semi-unique approach to OOP where it removes classes and replaces them with just structs with methods. This isn't particularly ground breaking but it provides and interesting perspective, after all (as I had someone pointed out to me), what is a class if not a form of **Struct**ured data.

I also for the msot part enjoy the `impl` block system. I do wish that there was a way to shorthand define the struct and your first `impl` together, but thats a me problem.
The traits system is super nice, especially since it allows you to add traits to other people's structs to add your own methods, very similar to kotlin's extension functions.

## Rust's Borrow Checker
I'm very much not the right person to speak on this, as I have very minimal experience with C-like languages where memory management is up to the user. But from my very minimal experience with C, C++, and more recently Rust, Rust's borrow checker makes it a lot harder to shoot yourself in the foot.

## Rust Closures
Rust's "Closures" (similar to lambdas in other languages) are very interesting, namely for their ability to "Capture" their environment, where they gain access to variables at the same scope as where the closure itself is declared. This has a very interesting ramification in the different traits that closures can derive, based on what they do with the captured variables, like mutating them, taking ownership and not returning them (consuming them), etc. Very interesting feature that I need to do more with (although that applies to most of my feelings about rust)