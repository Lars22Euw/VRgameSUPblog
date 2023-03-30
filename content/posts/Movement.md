---
title: Movement
date: 2022-11-21T20:16:33+01:00
author: "Lars Heublein"
description: "Implementing locomotion"
draft: false
---
As detailed in my last post, the idea of locomotion with a paddle is as follows:  
A stroke on one side of the board pushes it forward and gives it a slight turn to the other side.

To know when a player is paddling, I record the trail of his paddle while a button is pressed.
I then compare this line against some pre-recorded strokes for each side.
This concept is based on a YouTube tutorial by Valem and uses the library P$ Gesture Recognition.
{{< image src="/img/Row_trail.png" alt="row trail" position="center" style="border-radius: 8px;" >}}
[Demo 1](https://youtu.be/t0MTpvbi-b4) - The video shows the movement with the trail visible. The board shows the detected row and its confidence.

When we are at least 90% confident in a stroke, we perform the movement by applying force to the boat.
We also apply some rotational force to turn the boat slightly.


[Demo 2](https://youtu.be/WKlI-As9nlE) - In this video, you can see me paddling towards the first turn.


In its first iteration this implementation has some flaws:
* Forces applied to board are static -> leading to minimal physical movement
* The board turns but keeps its old direction of momentum
* When colliding with terrain, chance of tipping over the board without chance of reset for player


After seeing the kayaking implementation of my classmate, I was inspired to rework my locomotion.