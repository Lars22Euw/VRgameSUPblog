---
title: Interaction
date: 2023-02-05T20:16:33+01:00
author: "Lars Heublein"
description: "Interaction: Concepts and Implementation"
draft: false
---

This post will describe concepts I concidered and my actual implementation.
They should align with the overall paddling metaphor and fulfill both positioning and rotating an object in space.
The parkour has a preset tetris shape that needs to be moved to a random place nearby, while also changing up its rotation.

My first concept follows an old Wii game, where you have to match a pose in time. This may be fun and remains immersive
in the environment, but isn't actually a real interaction. - Incidentally my classmate with the kayak project went for an
implementation close to this.

The second idea allows the player to hit the T-shape with their paddle and box it around. While sounding fun at first,
it may not allow for precise turns and have you give up on that sweet perfect score.

Last but not least, a magnetic paddle can pick up the T-shape and move and rotate it along a stick.
There is one issue with this concept: due to the length of the paddle we cannot freely rotate the object among all axis
unless the player also moves the surfboard around.

My implementation follows the last concept by attaching the "My Grab" script to the paddle. 
When the player holds the hand trigger while the tip of the paddle is inside the object to be picked up, it is glued to
the paddle. However it is also rotated like the paddle so the pitch roation issue is not resolved.
```C#
if (isInCollider && triggerValue > 0.95f)
	selectedObj.transform.parent.transform.parent = this.transform;
```