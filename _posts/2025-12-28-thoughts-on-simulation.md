---
layout: post
title: Thoughts on Simulation
date: 2025-12-28
---

Over the past year, I've spent a lot of time thinking about agents and the environments they operate in. During this time, I've found myself increasingly entangled with a set of very fundamental questions about simulation; questions that feel more philosophical than purely technical.

My thoughts on this are still scattered. That's why I'm trying to write them all down in one place; maybe later I'll be able to return to them with more structure and clarity.

For me, simulation has never been an entirely abstract or intangible concept. Perhaps I started practicing it as early as four or five years old, when we played house as children. Even then, we were simulating. We wrote scenarios, assigned roles, and tried to make the story as "realistic" as possible. The holes in the scenario were always annoying; places where the story didn't quite align with how the real world works.

At the same time, our resources were limited. We couldn't build a house, so a house became a couch. But a handbag was an actual handbag. A shirt was a real shirt. Some details were born purely out of imagination, others were entirely real. A mix of reality and pretense. When we "traveled", we moved from one room to another. The notion of movement was preserved, but the distance was reduced to four meters. When we arrived at the destination, we knew we were supposed to be tired, even though we weren't, because in our narrative the journey had been long.

Sometimes, though, we forgot that in this new destination, the same familiar neighbor from our own house wasn't supposed to knock on the door. These were the scenario holes that revealed themselves mid-game. Back then, we didn't worry too much about them. It didn't really matter how closely the story matched reality; the game went on.

Years passed. About ten years later, in high school, I encountered the 3D soccer simulation league. This time, simulation was no longer a game, though traces of play were still there. There was software that simulated humanoid robots on a soccer field. Our job was to program the "mind" of the robot. For example, we had to tell the robot to rotate its right arm by 20 degrees in order to stand up, then move another arm in a different way. We sent these commands to the simulation software, which executed the movements, and we could observe the result.

The robot's perception of its environment was also fascinating. It had very limited sensors. A few flags in the corners of the soccer field, the goals, the ball, and the other players. There was something incomplete about this "seeing". The robot was meant to resemble a human, yet it only perceived a handful of points. Still, it worked. The simulation didn't need to be one-to-one or perfectly accurate for us to produce meaningful behavior.

I'll stop with the memories here and fast-forward to today. These days, I think a lot about simulating agentic environments. I keep asking myself:

When can we afford to give up on precise, one-to-one simulation?

How much accuracy do we really need?

Up to what point must we preserve details so that the system doesn't "break"?

The simplest idea that comes to mind is defining layers of precision; similar to how we treat decimal numbers. If our precision is 0.1, we only read the first decimal place and ignore or round the rest. If it's 0.01, we go one digit further. The layers are clear, and we know where the boundary lies.

But when we try to define a global model for an agent, this clarity disappears. We don't know what the layers of precision even are. We don't know which details can be safely discarded and which ones will come back to haunt us later. We don't know what a general rule for "ignoring details" should look like; rounding, omission, simplification. More importantly, we don't know how to tell when the simulation is still working and when it no longer is.

Another familiar example is representing decimal numbers in the binary systems of computers. Many numbers that are perfectly finite in base ten cannot be represented exactly with a finite number of bits in binary. So we approximate them. Or consider representing very large numbers with a limited number of bits: there's no room left to preserve extremely fine-grained decimals, so we discard them. At first glance, this doesn't seem like a big problem. But these seemingly harmless approximations can accumulate elsewhere and trigger numerical explosions that cause the entire algorithm to fail.

That's why concepts like numerical stability exist; a collection of tricks, corrections, and constraints designed to prevent systems from collapsing despite all these approximations. This is precisely the part I feel I haven't yet reached in my own simulations. I still don't know how to restore stability when coarse and fine approximations start to destabilize the system.

Is there a general rule for doing this?

Or do we have to identify every tricky situation and design a specific stabilizing fix for each one?

And if we keep applying patches for every instability, will we eventually end up with a stable system?

And, perhaps most importantly: will this stabilized system still be simulating the original one, or will it have quietly turned into a new system governed by different rules?
