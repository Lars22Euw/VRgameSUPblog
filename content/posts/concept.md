---
title: Motivation and Concept
date: 2022-11-19T18:45:57+01:00
author: "Lars Heublein"
description: "Comming up with a locomotion technique"
draft: false
---

While brainstorming locomotion techniques, my first thoughts went towards the classics like flying and teleporting.
I then concidered movement using a board, maybe surfing or skating. Those techniques however would likely be hard to get right,
as the board has to tilt below the player and cannot be performed easily whiel standing still.
So I was left with a close relative of surfing, **"Stand Up Paddling"**.
{{< image src="/img/SUP-silhouette.png" alt="silhouette of a person doing SUP" position="center" style="border-radius: 8px;" >}}

For this sport, the player stands on a large surfboard and uses a long paddle to control the movement.
The goal with Stand Up Paddling in VR is to have an immersive experience that allows for intuitive locomotion. 
One potential downside may be cybersickness as a high velocity without moving physically could increase its risk.
As I would later find out, a classmate also implemented a watersport - kayaking.

Here are some sketches detailing how forward and backward strokes of the paddle should move the player:
{{< image src="/img/paddling.png" alt="paddling forward SUP" position="center" style="border-radius: 8px;" >}}
And backwards:
{{< image src="/img/paddling_slow.png" alt="paddling backwards SUP" position="center" style="border-radius: 8px;" >}}

The next blog entry will detail my progress on implementing this feature.