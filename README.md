# 3D Optical Ray Tracer

**Individual Python project - Imperial College London | Project mark: 89%**

## Overview

I developed a numerical optical ray tracer as part of my second-year Physics computing coursework at Imperial College London.

The project models the propagation of three-dimensional light rays through refracting and reflecting optical systems. I used object-oriented programming to represent rays, optical surfaces and compound lenses, and then used the completed model to investigate focal behaviour, compare geometrical spot sizes with a diffraction scale, quantify spherical aberration, optimise lens geometry and model chromatic dispersion.

## Technologies & Skills

- Python
- NumPy
- SciPy
- Matplotlib
- Object-Oriented Programming
- Numerical Modelling
- Numerical Optimisation
- Unit Testing
- GitHub
- VS Code

## Results

### 1. Launching the Rays
   
The simulation begins with individual rays or circular bundles of rays defined by their initial position, direction and wavelength.
For most of the investigations, the rays begin parallel to the optical axis and travel towards an optical surface or lens. A `RayBundle` generates many rays across different distances from the optical axis, allowing the behaviour of an entire beam to be studied rather than only a single ray. 

<img width="450" alt="Circular ray bundle propagating through the optical system" src="https://github.com/user-attachments/assets/b285d9c1-510e-499c-bd8f-66c70b39af4c" />

*Circular ray bundle propagating through a spherical refracting surface towards the focal region.*


### 2. Interaction With the Optical System

As each ray moves through the model, the program determines where it intersects the next optical surface.
Depending on the element, the ray can then:

-	refract at a spherical or planar interface using Snell's law; 
-	reflect from a spherical reflecting surface; 
-	pass through multiple surfaces forming a compound lens; 
-	fail to continue if it misses the optical element or cannot be refracted through the interface. 

The model also supports wavelength-dependent refractive indices, so rays of different wavelengths can follow different paths through the same lens. 

### 3. Reaching The Focal Region

After passing through the optical system, rays are propagated towards an output plane or focal plane.
The final ray positions can then be analysed using:
-	ray-path plots; 
-	spot diagrams; 
-	calculated focal positions; 
-	RMS spot size. 
This makes it possible to see whether the rays converge tightly to a common point or spread out because of imperfections in the optical system. 

<img width="450" alt="Spot diagram of the ray bundle at the focal plane" src="https://github.com/user-attachments/assets/cff3d0d4-d567-47fe-868d-c811cdc8d74f" />

*Final ray positions at the focal plane, visualised using a spot diagram.*

### 4. Evaluating Optical Performance

Once the rays reach the image plane, the simulation can be used to study how well different optical systems perform.

#### Spherical Aberration

Rays entering far from the optical axis do not necessarily focus at exactly the same location as paraxial rays. I quantified this using both transverse and longitudinal spherical aberration.


<img width="450" alt="Longitudinal spherical aberration showing ray focal position with beam radius" src="https://github.com/user-attachments/assets/7dd2a92a-52f7-4bc1-b020-e2c5d61da7ee" />

*Longitudinal spherical aberration: rays further from the optical axis focus at different longitudinal positions.*

<img width="450" alt="Transverse spherical aberration showing RMS spot size with beam radius" src="https://github.com/user-attachments/assets/2d345c42-ae98-482c-b12c-d0da998a8242" />

*Transverse spherical aberration quantified using RMS spot size.*


#### Lens Orientation

I compared plano-convex lenses in different orientations to investigate how orientation changes the final spot size.

<img width="450" alt="Comparison of plano-convex lens orientations using RMS spot size" src="https://github.com/user-attachments/assets/74ab1cdf-91f7-4cb9-bf5b-7db2f6ae3037" />

*Comparison of lens orientation using RMS spot size against input beam radius.*

#### Lens Optimisation

I used numerical optimisation to vary the curvatures of a bi-convex lens and minimise its RMS spot size, then compared its performance with a plano-convex design. 

<img width="450" alt="Spot diagram comparison between plano-convex and optimised bi-convex lenses" src="https://github.com/user-attachments/assets/d482fef3-97b2-41b8-97fc-18d8fd774e28" />

*Comparison between the original lens design and a bi-convex lens whose curvatures were numerically optimised to reduce RMS spot size.*

#### Chromatic Dispersion

Using the Sellmeier equation, the model calculates different refractive indices for different wavelengths. This allows the simulation to show how blue, green and red rays follow slightly different paths through BK7 glass. 

<img width="450" alt="Chromatic dispersion of different wavelengths through a BK7 bi-convex lens" src="https://github.com/user-attachments/assets/a7efc4b9-5894-47fc-9958-58ada8acb84b" />

*Different wavelengths follow different paths through BK7 glass because its refractive index varies with wavelength.*

## Why This Project Is Useful

Optical ray tracing is used to understand how light propagates through optical systems before they are physically built. By modelling refraction, reflection, focal behaviour and aberrations, a ray tracer can help compare lens designs, estimate image quality and understand how changes in geometry or material properties affect an optical system.

The same principles could be extended to model astronomical imaging systems, for example by simulating how light from a distant star propagates through a telescope and maps onto a detector.

## What I Learned

This was my first substantial project in which I translated advanced physics directly into a computational model, rather than using Python primarily to analyse experimental data.

A major lesson was the value of object-oriented programming. Representing rays, optical surfaces and lenses as separate classes made the code easier to organise and reuse. Inheritance also allowed related optical elements to share common behaviour instead of repeatedly implementing the same functionality. 

I also learned the importance of testing a numerical model incrementally. Checking ray propagation and refraction before building more complex optical systems made errors easier to isolate and prevented mistakes from becoming hidden inside later stages of the simulation. 

Using GitHub throughout the project also gave me experience maintaining a clear development history, regularly saving progress and tracking how the project changed over time.

Most importantly, the project showed me how mathematical physics can be translated into working numerical algorithms: equations describing refraction, geometry, dispersion and aberration became components of a model that could be tested and visualised.

## Applying What I Learned

In future projects, I would reuse the same approach of breaking a complex problem into small, testable components before combining them into a larger model.

I would also continue using object-oriented design where it genuinely improves reuse and organisation, while maintaining regular version control and testing throughout development.


## Academic Integrity

The full source code is not publicly available because this project formed part of my assessed university coursework. This repository provides a portfolio summary of the methods, results and skills demonstrated by the project.

