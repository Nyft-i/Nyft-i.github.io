--- 
layout: post
title: "Amateur Pulsar Astronomy (If you happen to own a 42ft telescope)"
---

This document (and my interpretation of pulsar astronomy as a whole) is heavily influenced by the layout and workings of the following two books:
- A. Lyne , F. Graham-Smith F. _Pulsar Astronomy_. 4th ed. Cambridge University Press; 2012.
- D. R. Lorimer, M. Kramer. _Handbook of Pulsar Astronomy_. Cambridge: Cambridge University Press, 2005.
I highly recommend the both of them. The former, *Pulsar Astronomy*, is my personal favourite of the two, and delves better into the theory aspect of neutron stars. The latter, *Handbook of Pulsar Astronomy*, talks a lot more about instrumentation and methodology, which is very useful for the experiment. Both are "available" in the library, though your mileage may vary.

So you've been selected for the Crab Pulsar lab. I've decided to write my own pseudo-lab-script, which can be read alongside the real lab script, providing some personal insight on what I found useful on a rather involved but very interesting experiment. 
# Neutron Stars and Pulsars

A neutron star is of the most extreme object in the universe. They are the penultimate stage of life for the most massive stars following a type II (core collapse) supernovae. Their gravity is so immense that it overcomes all but the pressure provided by the nuclei of what once was their many different constituent atoms. It becomes energetically favourable under the pressure for nearly all protons to undergo electron capture and become neutrons (you can see where this is going). At this density, the gravity is too strong for any of the neutrons to form bound states with one another, resulting in the main component of a these stars to be fluid neutrons. Hence, the neutron star is born. Should a neutron star be too massive (more specifically, if it exceeds the TOV mass limit), the power of gravity wins out over even the neutron pressure; the star collapses further, into a singularity, giving us our black holes.

Stars, prior to collapse, have some amount of angular momentum. Like every demonstration of angular momentum you've seen: if you get smaller, you spin faster. The same holds true for a neutron star. Stars with huge radii of order millions of kilometres are compacted to the size of a city ($\sim20\text{km}$) in a supernova. So it's safe to say they speed up a considerable amount.

Pulsars are highly magnetised, rapidly spinning neutron stars. We've discussed why they spin so fast, but their magnetic field is a little more complicated and beyond the scope of this blog post and lab experiment (we don't really know). The Crab pulsar is one such star, named due to its location: in the middle of the crab nebulae. It's one of the most luminous and interesting pulsars we know about, and as a result is observed as often as twice per day. I imagine one of the reasons (if not the main reason) the undergraduates at UoM are allowed to use the 42ft telescope for the Crab Lab is because that's what the big expensive piece of equipment would be looking at anyway.

![[Pasted image 20250114210912.png]]
Radio Astronomy

They emit lighthouse-like pulses in the radio spectrum as a result of the poles in their magnetic field being misaligned with their rotational axis. These beams alone are very weak, and so there is some amount of finesse required to retrieve information good enough to draw conclusions about a pulsar. Timing pulsars, and understanding why they emit light in the way that they do is important for us to understand the corresponding mechanisms. Due to the extreme conditions within and around a pulsar, understanding the mechanisms can then help us to develop new areas of physics at these extremities where our current model breaks down.

# The Lab Script

Let's take a step back for a second and look back towards the lab script. For us, this experiment could be broken down into three main components:
1. Dispersion measures of known pulsars (1-2 weeks).
2. Periodicity of unknown pulsars (1-2 weeks).
3. Precise timing of The Crab pulsar (2-3 weeks).
The times I've put in brackets are rough estimates of how long it took myself and my lab partner to perform this, but it is in no way a solid guideline. As you have done a 3rd year lab report by now, you are familiar with the reduced page limit. As such, it makes the most sense to pick only one of these three parts of the experiment to write your lab report on, and I recommend the last. 

# Radio Astronomy

## Basic Radiometer System

There's some important concepts in radio astronomy. The first we will tackle is as follows: "Why do we need a dish". The answer is obviously to collect more light. We can put this into numbers using "Gain". We must first understand directivity, a measure of how much of the sky you are looking at:
$$D = \frac{4\pi}{\Omega_A}.$$
Where $\Omega_A$ is the solid angle of the sky which your beam covers. It can be seen that this is simply the inverse of the fraction of sky which the telescope beam covers. 

Gain, different from the value given in the exam script, and denoted as such here as $G'$ to reduce confusion, is given by the equation $G'=D\eta$.
$$G' = \eta D = \eta \frac{4\pi}{\Omega_A}$$
Its easiest to think of this in terms of an emitter, rather than a receiver. A system emitting isotropically will follow the inverse square law, reducing with distance from the source, such as a star. Now, if you emitted the same amount of energy using an antenna, the flux at the same distance would be multiplied by the gain.

We still need more tools to derive the equation provided in the lab script, another is the Antenna Theorem. Suppose we put an antenna in a blackbody cavity: an isolated box which no light can escape.
![[Pasted image 20250114230720.png]]After some time, this whole system will be in thermodynamic equilibrium. The part of the cavity which the beam can see (i.e. subtends solid angle $\Omega_A$), radiates at its blackbody temperature,
$$B_\nu=\frac{2k_BT}{\lambda^2} \; \text{Wm}^{-2}\text{Hz}^{-1}\text{sr}^{-1},$$
where we have taken the Rayleigh-Jeans limit (citaion needed). The power then collected by the receiver is given by,
$$P_{\text{rec}}=\frac{k_BT}{\lambda^2} A_e \Omega_A \; \text{W}\text{Hz}^{-1}.$$
We have multiplied by the effective area of the antenna, $A_e=\eta A$, and the solid angle of the beam, $\Omega_A$. Additionally, we have lost a factor of two as the antenna can only collect power from a single polarisation. In thermodynamic equilibrium, the receiver has matched the load resistor, shown on the right at temperature $T$, which produces transferrable power $k_BT$ (per unit bandwidth). We can set this equal to our previous expression to obtain the "Antenna Theorem":
$$P_\text{rec}=\frac{k_BT}{\lambda^2}A_e\Omega_A=k_BT$$
$$A_e\Omega_A= \lambda^2$$




Interestingly, the lab script defines gain differently to how it is 
... given by the Radiometer equation:
$$\Delta T_\text{rms} = \frac{T_\text{sys}}{\sqrt{\Delta\nu \:\tau}}$$
You'll notice this is very similar to the equation given in the lab script. It describes how observation bandwidth, observation time and system temperature all influence the random statistics on *measurable* readings. The "temperature" of the source needs to exceed this value, $\Delta T_\text{rms}$. Intuitively, this makes sense. Your receiver system needs to see have the signal appear more significantly than the average size of the fluctuations.
## Heterodyne Receiver System (42ft Telescope)