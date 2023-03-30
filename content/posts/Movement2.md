---
title: Movement revised - Implementation
date: 2023-01-17T20:16:33+01:00
author: "Lars Heublein"
description: "Implementing movement (again)"
draft: false
---

The updated concept throws away almost all of the previous work.
We attach two colliders to the board named left and right as shown bellow.
{{< image src="/img/Board_Triggers.png" alt="Board with triggers" position="center" style="border-radius: 8px;" >}}

The paddle gets a new script called "Row Detection". Whenever its tip enters one of the triggerboxes we store its current location.
While the paddle moves within the box, each frame the difference between the old and the current position is computed.
It is important to note that we only care about the z-(forward) Direction in the local space of the board.
```C#
// calc change in forward position
var posLocal = gameObject.transform.InverseTransformPoint(pos);
var forward = -(posLocal.z - lastPosLocal.z);
```

This forward force is added to the corresbonding leftForce or rightForce variable.
So a row movement on the left side will build up a lot of leftForce and vice versa.

Next I will explain how the drag of the water is simulated:  
Since the board is streamlined, sideways drag differs from forward drag.
We therefore update both indepently.
```C#
var localVelocity = transform.InverseTransformDirection(rigidbody.velocity);
var newLocalVelocity = new Vector3(localVelocity.x*0.8f, 0, localVelocity.z*0.99f);
rigidbody.velocity = transform.TransformDirection(newLocalVelocity);
rigidbody.AddTorque(-rigidbody.angularVelocity * rotationalDrag);   // rotates board
```

Now that we are done with our bookkeeping we can add force to the board:  
To compute the turn, we get the difference in left and right force.
```C#
float forwardForceToApply = Mathf.Min((leftForce + rightForce), forwardClamp);
float rotationForceToApply = ((leftForce - rightForce) * rotationDampening);
rigidbody.AddRelativeForce(new Vector3(0, 0, forwardForceToApply));
rigidbody.AddRelativeTorque(new Vector3(0, rotationForceToApply, 0));
```

Lastly we have to decrease left and right force or otherwise we would keep our momentum from the first stroke forever. [Video demo](https://youtu.be/jFmV8KGidQk)