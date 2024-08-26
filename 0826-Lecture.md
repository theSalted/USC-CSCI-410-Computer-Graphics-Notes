
# CSCI 420 - August 26, 2026 Lecture

## Administrative

Professor: Oded Stein (ostein@usc.edu)

[Course Information](odedstein.com/teaching/hs-2024-csci-420)

[Submit Assignment at Brightspace](https://brightspace.usc.edu)

Teaching Assistant: Jiahao Wen
16:00-17:00 Monday
15:00-16:00 Wednesday
SAL 322

C/C++ programming


### Grading
- 51% Assignments (3x17%)
- 19% Midterm Exam
- 30% Final Exam

### Textbooks
- Interactive Computer Graphics, Sixth Edition
- OpenGL Programming Guide ("Red Book")
- learnopengl.com

### Assignment Policies
- Programming assignments
    - Hand in via Brightspace by end of due date
    - Functionalit and features
    - Style and documentation
    - Artisitic impression
- No question asked 3 late days, usable any time during semester, inform TA or Prof
- All assignments must be completed before the final exam to pass the course
- Academic intergirity policy applied rigorously
- Have extra credits

## Overview

Theory: Computer graphics disciplines:
 - Modeling: how to represent objects
 - Animation: how to control and represent motion
 - Rendering: how to create images of objects
 - Image Processing: how to edit images

Practice: OpenGL graphics library

**Not** in this course:
- HCI
- Graphic Design
- UI libraries


### OpenGL Graphics Library

- Main focus: Core OpenGL Profile ("Modern OpenGL")
- OpenGL 3.2 and higher
- Shaders
- Homeworks and use the Core Profile
- We will also study: Compatibility Profile ("Classic OpenGL")


### CG Disciplines
- Rendering
- Geometry (Modeling)
- Animation
- Image Processing

### CG Goal I
- Syntetic images indistinguishable from reality
- Practical, scentifically sound, in real time
- Likely come from world of cinema (VFX)
- Modern videogames
- e.g. Papers: Barbic James, SIGGRAPH 2010 (elicisity simulation); Thurey, Wojtan, Gross, Turk, SIGGRAPH 2010 (fluid simulation); Yue et al. SIGGRAPH 2015 (foam simulation).
- e.g. Radiosity (Wikipedia)

### CG Goal II
- Crating a new reality (not necessarily scientific)
- Practical, aesthetically pleasing, in real time
- e.g. Papers: A. Hertzmann, D. Zorin SIGGRAPH 2000 (Hand-drawn shader) (Non-photorealistic rendering) (NPR); J. Hays, A. Efros, SIGGRAPH 2007 (scene completion).

### SIGGRAPH
- Main computer science (computer graphics) event in the world
- Once per year
- 30,000 attendees
- Academia, industry
- 2024 maybe in vancouver, professor happy to recommend

## Course Ourline
- Week 2: OpenGL Baiscs
- Week 3: Input and Interaction
    - Clients and servers
    - *event driven programming*
    - hidden-surface removeal
    - [Angel, Ch.2]
- Week 4: GPU Shaders
    - Vetext program
    - Fragment program
    - Pipeline program
    - Shading languagues
    - GLSL shading languague
    - Interaction with OpenGL
- Week 5:
    - Linear algebra review
    - Coordinate systems and frames
    - Rotation, translation, scaling
    - Homogeneous coordinates
    - OpenGL transformation matrices
    - [Angel, Ch. 3]
- Week 6:
    - Viewing and Projewcrtion
    - Orthographic projection
    - Perspective projection
    - Camera postioning
    - Projections in OpenGL
    - [Angel, Ch. 4]
- Week 7: Hierachical Models
    - Re-using objects
    - Animations
    - OpenGL rountines
    - Parameters and transformation
    - [Angel, Ch. 8]
- Week 8: Light and Shading
    - Light souces
    - Ambient, diffuse, and specular reflection
    - Normal vectors
    - Material properties in OpenGL
    - Radiosity
    - [Angel, Ch. 5]
- Week 9: Curves and Surfaces
    - Review of 3D-calulus
    - Explicit represntations
    - Implicit represnetations 
    - Parametic curves
    - ...
- Week 10: Rendering
    - Clipping
    - Bounding boxes
    - Hidden-surface removal
    - Line drawing
    - Scan conversion
    - Antialiasing
    - OpenGL basic bucket sort for pixels
    - [Angel, Ch. 6]
- Week 11: Textures and Pixels
    - Texture mapping
    - OpenGL texture primitives
    - Bump Map
    - ...
- Week 12: Ray Tracing
    - Basic ray tracing [Angel, Ch. 11]
    - Spatial data structures [Angel, Ch. 8[
    - Motion blur
- Week 13: Radiosity
    - Local vs global illumination model
    - ..
- Week 14: Physically base models
    - Particle systems
    - Spring forces
    - Cloth
    - Collisions
    - Constraints
    - Fractals
    - [Angel, Ch. 9]
- Week 15. Scientific Visualization
    - Height fields and contours
    - Isosurfaces
    - Volume rendering
    - Texture mapping of volumes
    - [Angel Ch. 11]
- Two catchup weeks or guest lecture: Graphics hardware and more

### Hot Research Topics
- Modeling
    - getting models from the real world
    - multi-resolution
- Animation
    - physically based simulation
    - motion capture
- Rendering
- Macine Learning

