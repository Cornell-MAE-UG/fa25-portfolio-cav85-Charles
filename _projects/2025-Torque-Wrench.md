---
layout: project
title: Torque Wrench  
description: Choosing design for torque wrench
technologies: [Matlab, ANSYS, Fusion 360]
images: /assets/images/full_wrench.png
---

Torque wrench design project for mechanics of engineering materials class(MAE 3270). We were given a base design and had were tasked with modifying the design to meet the design requirements: a factor of safety against yielding or brittle failure of 4, a factor of safety against fracture of 2 with an assumed crack length of 0.04 inches, and a factor of safety against fatigue stress with cyclic loading of 1.5. Below is a overview of the design in CAD and the results from a finite element analysis of the design.

<figure style="text-align: center;">
  <img src="/fa25-portfolio-cav85-Charles/assets/images/crossSectionDimensions.png" width="200">
  <figcaption><b>Figure 1:</b> Cross section dimension for torque wrench handle. The width (h) is 0.45 inches and the height(b) is 0.5 inches.</figcaption>
</figure>

<figure style="text-align: center;">
  <img src="/fa25-portfolio-cav85-Charles/assets/images/Drive_Geometry_Dimensions.png" width="200">
  <figcaption><b>Figure 2:</b> Drive dimensions for torque wrench. Center of drive is 1 inch from the end of the handle. For the drive to be centered on the handle, the drive's edge must be 0.038 inches from the side of the handle.</figcaption>
</figure>

<figure style="text-align: center;">
  <img src="/fa25-portfolio-cav85-Charles/assets/images/handle_length.png" width="200">
  <figcaption><b>Figure 3:</b> Total length of handle is distance between tip where load is applied and center of drive(20 inches) plus distance between center of drive and end of handle(1 inch).</figcaption>
</figure> 

The material I chose for the torque wrench was "Press Hardening Steel, 22MnB5, austenized & H20 quenched, uncoated." The young's modulus of the material was 29 Msi while the poisson's ratio for the material is 0.29.The yield strength is 144 Ksi while the tensile strength of the is 218 Ksi. The fracture toughness of the material is 111 ksi*sqrt(in) and the fatigue strength of was 79 ksi. The material was more ductile than brittle so I used von mises yield criterion for calculating the factor of safety on the normal stress. I chose this material due to its high fracture toughness. On my iterations of the analysis of the base design, which used M42 steel, I noticed that the requirement that was most limiting was the fracture factor of safety. This lead me to look for materials that have both a high yield strength to young's modulus ratio and high fracture toughness to young's modulus ratio. The biggest downside of the material was its larger amount of elongation compared to more brittle matierals. 

<figure style="text-align: center;">
  <img src="/fa25-portfolio-cav85-Charles/assets/images/wrench_boundary_conditions.png" width="200">
  <figcaption><b>Figure 4:</b> Shows the loading and boundary conditions used for FEM analysis.</figcaption>
</figure> 

<figure style="text-align: center;">
  <img src="/fa25-portfolio-cav85-Charles/assets/images/strain__zoomed_out.png" width="200">
  <figcaption><b>Figure 5:</b> Strain contours of whole wrench.</figcaption>
</figure> 

<figure style="text-align: center;">
  <img src="/fa25-portfolio-cav85-Charles/assets/images/strain__drive.png" width="200">
  <figcaption><b>Figure 6:</b> Strain contours at interface between drive and handle.</figcaption>
</figure> 

<figure style="text-align: center;">
  <img src="/fa25-portfolio-cav85-Charles/assets/images/principal_stresses_full.png" width="200">
  <figcaption><b>Figure 7:</b> Maximum principal stress contours along wrench.</figcaption>
</figure> 

<figure style="text-align: center;">
  <img src="/fa25-portfolio-cav85-Charles/assets/images/principal_stresses_drive_2.png" width="200">
  <figcaption><b>Figure 8:</b> Maximum principal stress contours at interface between drive and handle.</figcaption>
</figure> 

The maximum normal stress in the torque wrench is approximately 78.3 Ksi. If we approximate that the only principal stress is 78.23 Ksi, then the von mises stress would be equal to 78.3 Ksi. This give a von mises factor against ductile yielding of 1.84 which does not make the requirement for the factor of safety. If we use the maximum von mises stress calculated through FEM, then the factor of safety would be on the order of 10^-4. The maximum deflection of the beam was recorded to be 0.79 inches, which is significant relative to the total length of the beam(deflection/Length = 3.76%). The strain gauge was a distance of 0.75 inches away from the drive center and measured a strain of 1,180.6 microstrain.

<figure style="text-align: center;">
  <img src="/fa25-portfolio-cav85-Charles/assets/images/normal_stress_contours.png" width="200">
  <figcaption><b>Figure 9:</b> Normal stress contours for torque wrench.</figcaption>
</figure> 

<figure style="text-align: center;">
  <img src="/fa25-portfolio-cav85-Charles/assets/images/wrench_deflection.png" width="200">
  <figcaption><b>Figure 10:</b> Deflection along handle given loading analysis in FEM.</figcaption>
</figure> 

<figure style="text-align: center;">
  <img src="/fa25-portfolio-cav85-Charles/assets/images/strain_gauge_reading.png" width="200">
  <figcaption><b>Figure 11:</b> Strain gauge reading for given location on handle relative to drive.</figcaption>
</figure> 

<figure style="text-align: center;">
  <img src="/fa25-portfolio-cav85-Charles/assets/images/strain_gauge_location.png" width="200">
  <figcaption><b>Figure 12:</b> Location of strain gauge along wrench handle.</figcaption>
</figure> 

Using the strain gauge reading from above, we can find the mV/V reading using Vout/Vin = 2K(strain)/4 for a half bridge design, where k is the gauge calibration factor. Usually k is approximately 2 so for this design, a reading of approximately 1.18 mV/V would be measured. 

For picking a strain gauge, we want the width of the strain gauge to be reasonably smaller than the cross-sectional height, b = 0.5 inches. I would use two SGD-3/120-LY13 linear strain gauge from DwyerOmega(link:https://www.dwyeromega.com/en-us/linear-strain-gages/SGD-LINEAR1-AXIS/p/SGD-3-120-LY13). The purpose of buying two strain gauges is to create the affect of a half bridge design where a strain gauge is placed on each side of the torque wrench. The width of the strain gauge is 3.8 mm or about 0.15 inches and the length is 7.8 mm or about 0.3 inches. The width is about 30% of the cross-sectional height and the length of the handle is much longer than the length of the strain gauge so it would fit onto our design. 





