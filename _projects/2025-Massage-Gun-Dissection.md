---
layout: project
title: Massage Gun Dissection  
description: Choosing design for torque wrench
technologies: [Matlab, Tektronix, Oscilloscope]
image: /assets/images/massage-gun-inside.jpg
---

Dissection project for system dynamics students(MAE 3260). Students were given the option of either researching a system of their choice and relating it to course content or receiving a physical device to dissect and analyze its system. Our group chose to dissect a massage gun because we believed that the system's dynamics for the mechanical and electrical parts of the system were interesting to characterize. 

The flow of the system is a voltage input from a beterry being applied across the terminals of a DC motor that provides the input torque to the mechanical patrt of the sytstem. The rotation of the motor shaft with a offset cam and linkage attached to the it results in linear translation of the masssage gun tip at an oscillatory frequency. TO characterize the system, we setup an experimental apprartus where an accelerometer was attached to the tip of the massage gun tip to track displacement and banana clips were attached to the teriminals of the DC motor. The data from the accelerometer and voltage across the motor terminals were visualized using an oscilloscope. 

<figure style="text-align: center;">
  <img src="/fa25-portfolio-cav85-Charles/assets/images/massage-gun-inside.jpg" width="200">
  <figcaption><b>Figure 1:</b> Inside structure of massage gun.</figcaption>
</figure>

<figure style="text-align: center;">
  <img src="/fa25-portfolio-cav85-Charles/assets/images/massage-gun-apparatus-1.jpg" width="200">
  <figcaption><b>Figure 2:</b> Experimental setup showing accelerometer connection.</figcaption>
</figure>

<figure style="text-align: center;">
  <img src="/fa25-portfolio-cav85-Charles/assets/images/massage-gun-apparatus-2.jpeg" width="200">
  <figcaption><b>Figure 3:</b> Experimental setup showing oscilloscope connections to massage gun.</figcaption>
</figure> 

We used the data on the oscilloscope to analyze two modes of the machine gun, a "fast" mode charterized by high amplitude and frequency of oscillation and a "slow" mode with a lower oscillatory frequency. The fast mode occurs while a disturbance load is being applied to the tip such as when the massage gun is pressed against a person's body. The plots on the oscilloscope gives us insight on the way the modes work. There is a clear jump in voltage for the accelerometer data when transitioning from fast to slow mode, which corresponds to the observed increase in the amplitude of oscillations. The voltage data showed us something interesting. We expected the voltage to be a step input. However, the voltage was a pulse width modulation with a duty cycle. 

<figure style="text-align: center;">
  <img src="/fa25-portfolio-cav85-Charles/assets/images/massage-transition.png" width="200">
  <figcaption><b>Figure 4:</b> Plot of accelerometer and motor voltage data. Motor voltage is in green and accelerometer data that repesnets the displacement of massage gun tip is in yellow.</figcaption>
</figure> 

<figure style="text-align: center;">
  <img src="/fa25-portfolio-cav85-Charles/assets/images/massage-pulse-duty.png" width="200">
  <figcaption><b>Figure 5:</b> Zoomed in scale of oscilloscope plots to show duty cycle on voltage.</figcaption>
</figure> 

We obeserved the response of the duty cycle as it transitioned between the two modes. The duty cycle would increaase from 44% up to 84% over an interval of time. However, the resolution on the plots for the oscilloscope were to small to get more information on how the duty cycle changes with respect to time. Thus, we needed to take more data. We set a reference time and tracked the points of time where the duty cycle changed by about 2%. This new data was plotted on a % duty cycle vs. time graph. 


<figure style="text-align: center;">
  <img src="/fa25-portfolio-cav85-Charles/assets/images/duty-cycle-plot.png" width="200">
  <figcaption><b>Figure 6:</b> Plot of data characterizing changes in duty cycle with time.</figcaption>
</figure> 

We expected the response for the duty cycle changes to be an exponential growth rate. However, the plot duty cycle seemed to increase more similarly to a step increase where there would be periods of time with linear increase followed by a jump that seemed to have a small exponential response analogous to a step input. We concluded that the response of the duty cycle is most likely the result of a more complex control law. 

The fast and slow modes were also compared by estimating the frequency of the oscillations using the data from the accelerometer. We estimated that the fast mode oscillates at around 42.5 Hz and the slow mode oscillates at 21.5 Hz which is roughly a difference by a factor of 2 between the two modes' frequencies. From a functional standpoint, we theorize that the massage gun was designed to have an additional fast mode to overcome the disturbance load and increased damping produced when the tip contacts a surface.








