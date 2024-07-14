+++
title = "Scrying Statues"
date = 2024-07-13T22:01:19-04:00
draft = true
pin = false
summary = "New Post"
tags = ["programming", "modding"]
categories = ["projects"]
+++

I've recently reached a wall in my roomba project, namely money. So I decided while I wait to get some more funding, I'd pick up something new to mess around with. I settled on minecraft modding!

### Background

For a little bit of background, when I was in grade school, I took an online course on minecraft modding. I can't for the life of me remember who taught it, but it was for a pre 1.14 version, and it was for forge. This was also probably nearly ten years ago, so it really didn't help me, I couldn't tell you a single line of code from that class, and I'm sure most of this is obsolete. But I figured if me at around 10 could figure it out, me now could as well.

### Starting the Project

I went into this knowing I wanted to use a mod launcher called Quilt, this was namely because I get all of the functionality of another launcher called fabric (due to quilt being a fork), but I get some more updated features, as well as not needing to support the Fabric project, which has had some powerful people make some questionable choices.

Quilt provides a mod template generator, so I was very easily able to create a template project, although it was created in java. Although I'm familiar with java, I prefer using kotlin, so I did also use the `fabric-kotlin-language` api to add kotlin support, to make my development more streamlined.

### The Mod

The mod itself is intended to be a low-tech solution to base security. The main feature of the mod is the "statue" entity, which is spawned using an item of the same name, renaming the item in an anvil will change the ID of the statue. Each statue is tied to the UUID of the person who placed it, so only they can bind a mirror to it. Speaking of which, scrying mirrors allow you to see through the eyes of a statue, when you click on a statue that is tied to your UUID, it will show the ID of the statue in the item's name, and allow you to see through the eyes of said statue.

One of the main interesting things I needed to do to get this to work, was to create a few "mixins". Mixins are a way to inject your own code into minecrafts source code. This was needed as the default function I was using to change the players camera, also teleported them to the entity. I needed to inject some code into the player class to save the player's position when they start to spectate a statue, and teleport them back to it after. All of the source code is available on my GitHub.

### Conclusion

This was a great project, both for staying familiar with kotlin during my robotics team's off season, and giving me a new opportunity to put more work out there for people to see what I'm capable of. I intend to create more mods at some later date, but I need to come up with the next idea first.

If you made it to the end of this blog post, I hope you enjoyed or learned something interesting, feel free to reach out if you have any more questions!