---
title: Evaluation and Conclusion
date: 2023-02-25T23:43:01+01:00
author: "Lars Heublein"
description: " "
draft: false
---
This post marks the end of the project.

To evaluate the project, I had both my roommates join me in playing the game.
You can find the video of me playing [here](https://youtu.be/jFmV8KGidQk).

The evaluation procedure is the following:
1. Welcome the participant and explain him the technique of locomotion
2. Let the user 2 minutes to practice
3. Expose the user to the parkour during 10 minutes, with the instruction to be as fast and accurate as possible. If we exposed the user for less than 10 minutes, we would not be able to measure simulator sickness, as it takes some exposure time to feel the effects.
4. Give the user a questionnaire
5. Ask them for open comments.

To compare the results of my implementation with my classmates, each of us collected the following metrics:
* time per round
* \# of collected coins
* Interaction scores
* Simulator Sickness using: “On a scale from 1 to 10, how much motion sickness do you perceive right now?”
* Presence using: “On a scale from 1 to 10, how present did you feel in the virtual world?”
* Enjoyment using: “On a scale from 1 to 10, how much fun did you have during the task?”

Here are the metrics collected while playing:
| Users: | Lars | User2 | User3 | Average |
| ------------- |:-------------:|:-----:|:---:|:---:|
| Time | 389.1 | dnf| 426.7 | 407.9 |
| Coins (total)| 9 | 13 | 27 | 16 |
| Interaction | 1.4, 0.13 | 2.5, 0.03 | 1.7, 0.2 | 1.8, 0.36 |

Questions:
| Users:| Lars | User2 | User3 | Average |
| ------------------------|:---:|:---:|:---:|:---:|
| Sickness: (less is better)| 7  | 2  | 1  | 3  |
| Presence: (more is better)| 9  | 6  | 9  | 8  |
| Fun:	    (more is better)| 10 | 3  | 8  | 7  |


# Conclusion

In my motivation I described the goal of SUP to allow for an immersive movement accross the water.
The results show clearly that this locomotion technique does not reduce the chance of cybersickness
and even increases it for some users. As for immersion, all participants agreed that the implementation of SUP
lead to a high amount of presence in the virtual world.
One downside that was pointed out in comments by the users was the surprisingly high amount of effort that
was required to push oneself forward. It was also pointed out that we can only move on the water surface,
whereas most games require you to reach places in 3 dimensions.

Therefore we can conclude that this technique is not quite at a point where it should be used by everbody but may
find use in some applications that strive for a high degree of immersion.
