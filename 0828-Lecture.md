# Introduction to OpenGL (August 28)

How do computers display things:

- Lamps
- Dot matrix printer (probably why output to console called still call print)
- CRT (roughly over 100 years old technology)
- Printers
- Sounds (this day advance text to speech)
- **Screens**

### How to draw on a screen?
- Small screens have lots of pixels
- Referesh rates are very high
- CPUs are quite slow for this
- Specific hardware born to resolves this
    - Draw simple 2D object
    - Drawing  text
    - Simple effects
    - Modern GPU come from this

### What is OpenGL
- A low-level graphicvs library (API) for 2D and 3D interactive graphics
- Descendent of GL (from SGI)
- First version in 92; now: 4.6 (released july 2017)
- Managed by Khronos Group (non-profit consortium)
- API is governed by Architecture Reiview BOARD (PART OF KHRONOS）

### Where is OpenGL used
- CAD
    - AutoCAD
- VR
- Scientific visualization
- Flight simulation
- Video games
    - StarCraft
- 3D Modeling Software
    - Blender

### Graphic library (API)
- Itermediary between applications and gaphics hardware
- Other popular APIs:
    - Direct3D
    - OpenGL ES (DEAD)
    - X3D (DEAD)
    - Vulkan
    - Metal
    - WebGL
    - WebGPU


**Before Geaphics Engines**
- Directly rendering to a file
- Directly wirting to a framebuffer

## History of OpenGL
- OpenGL i sadministered by OpenGL ARB
- The ARB defines a standard API with version that te different graphics card vendors (nvidia, AMD) implement
- OpenGL become very popular very quickly thanks to wide range device support
- Nowaday OpenGL is operate by Kronos industry group
- New modern OpenGL API is introduced (3, 4)

Old OpenGL
- you tell GPU how to draw primitives
- You tell GOPU about lights, material, params, textures, etc,
- GPU does it for you

Modern OpenGL
- Load everythijng into GPU memory
- Tell the GPU where all obeject are
- Write GOU shader that assigns colors to all your objects
- Run GPU Programs

- Note: it's very interesting that old OpenGL is more high level/apporachable and new OpenGL profile is more low level and difficult. This is opposite how a lot of technology works. 

### After OpenGL
- Future for OpenGL is uncertain.
    - But not for shader-based graphic pipelines
- Many people use higher-level engines (Unreal, Unity, etc...)
- Big engines developers like access that is more low-level than OprnGL
- Vulkan (also by Khronos)
- OS-Specific Walled Garden
- ...but OpenGL is very easy to get into

### Choice iof Programming Language
- OpenGL live close to the hardware
- OpenGL is not object oriented
- OpenGL is not a functional language (as in, ML)
- Use C to expose and explioit low-level details
- Use C++, Java, ... for toolkits
- Support for C in assignments
    - (but why do you)

### So, who actually implements OpenGL
- Graphics Card vendors
    - Graphics cards need to translate OpenGL code to microcode that can run on GPUs
    - Graphics cards need to translated OpenGL insturctuion to exlectrical signas
- OS


## OpenGL Library Organization
- GL (Gaphics library): core gaphics capabilities
- GLUT (OpenGL Utility toolkit): input and windowing <- this sucks majorly
- GLEW (extension wrangler): removes OS dependencies
- GLU (OpenGL Utility Library; compatibility profile only): utilities on top of GL

### Core vs Compatibility Profile
- Core Profile
    - Mordern OpenGL
    - Intoduced in OpenGL 3.2 (August 2009)
    - Optimized in modern graphic slibrary
- Modern


- Classic:
    - Issue CPU commands to draw graphic primitives

- Modern:
    - You directly interact with the GPU memory
    - You write a program which te GPU executes on each prinmitve (the shader)

### Mixing core and compatibility profiles
- Windows, Linux: yes
- Mac: No

### How does OpenGL work
From the programmer's point of view:
1. Spcify geometric objects
2. Describe object properties
    - color
    - how object reflect lights
3. Define how objects should be viewed
    - Where is the camera
    - What type of camera
4. Specify light sources
    - were, what kind
5. Move camera or objects around for animation

Mix of mathmatics & GPU coding to make everyting happend.

Everything resolves around "the pipeline (next class)"

### Geometric obects (vertices and triangles)
- OpenGL can draw points, lines, and triangels
- We havce to specify these objects (or primitives), and load the into GPU memeory. 
- We then need to tell the GPU where in memory which primoitive lies, and to draw each of them

### Attributes
- Set before primitive are drawn
- Remain effect until changed
- Color is an attribute
    - In OpenGL vertex hold color attribute
    - Color in between will be smoothly interpolated (but you have to set it yourself in core profile)
    - Frament shaders deal with this
    - In core profile interprolation is non trivial
    - You would have write interpolation yourself

### Flat vs Smooth Shading
- Colors are jiust used to specify the physical color of an object
- We have to mimic the effects of actual light that hits a camera 
- Reflection based on angle of object with respect to light source and camera

### Flat vs Shading
- Flat shading: The actual representation of geometry
    - this is useful where crease is important to have
    - or a specific artstyl
- Smooth shading: The average of the normal (can make fewer triangle looks good)
- A model (3D) usually combine both shading methods


### Lights
- 
