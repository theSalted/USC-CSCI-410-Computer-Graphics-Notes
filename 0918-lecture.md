# Shaders

## Homework
- Next Monday is dedicated to HW
- Should be able do after this class
- Try to install and compile

## Shading Languague

- The major advance in real time graphics has been the programmable pipeline:
- First introduced by NVIDIA GeForce 3 (in 2001)
- Supported by all modern high-end commodity cards
    - Nvidia, AMD, Intel 
- Software Support
    - Direct2D
    - OpenGL

This lecture: programmable pipeline and shaders

## GLSL
### OpenGL Extensions
Initial OpenGL version was 1.0
Current OpenGL version is 4.6

As graphics hardware improved, new capabilities was added to OpenGL
- Multitexturing
- Multisampling
- Non-power-of-two textures
- Shaders
- And many more


## Verrex Array Objects
Shaders are customized programs that replace a part of the OpenGL pipeline

They enable many effects not possible by the fixed OpenGL pipeline

Motivated by Pixar's Renderman (offline shader)

Shaders Enable Many New Effects:
- Complex materials
- Shadows
- Lighting environments
- Advanced mapping

## Vertex Shader
User must tessellate into triangles (in the VBO)
4x4x2 = 32 trainagles


## Fragment Shader
- It's like pixel (but not really) beacause fragment(pixel) don't always align with physical pixel


GPU - (verticeies) -> Vertex Shader - (vertices) -> Tessellation Shader - (triangles) -> Geometry Shader - (triangles) -> Clipping - (triangles) -> Rasterizer - (fragments) -> Fragments Shader - (pixels) -> Frame Buffer

- Compatibility profile: Default shaders are provided by OpenGL
- Core profile: no default vertex or fragment shader; must be provided by the programmer
- Tessleation shaders, geometry shaders and compute shaders are optional

## How to actually write a shader program
- A very small set of C++

*Atrribute*
s- Information specific to each vertex.pixel passed to vertex/fragment shader
- e.g. Vertex Color
*Uniform*
- Constant information passed to vertex/fragment shader
- Cannot be written to in a shader
- e.g. Light position, eye position
*Out/in*
- Info passed from vertex shader to fragment shader
- INterpolated from vertices to pixels
- Write in vertex shader,  but only read in fragment shader
- e.g. vertex color, texture coords
*Const*
- To declare non-writable, constant variables
- e.g. pi, e, 0.480

**Early shaders**: assembly languague
**Since ~2004:** high-level shading language
- OpenGL Shading Language (GLSL)
- Cg (NVIDIA and Microsoft), very similar to GLSL
- HLSL (Microsoft), the shading languague of Direct 3D
- All of these are simpliefied version of C/C++
- Different driver implement GLSL differently

- The shading langugae of OpenGL
- Managed by OpenGL Architecture Review Board
- Introduced in OpenGL 2.0
- We use shader version 1.50:
- Current version: 4.60

## Vertex Shader
- Input: vertices, in object coordinates and pre-vertex attributes
    - Color
    - Normal
    - Texture/UV coordinates
    - Many more
- Output:
    - Vertex location in clip coordinates
    - Vertex color
    - Vertex normal
    - Many more possible

## Fragment Shader
- Input: fragments （tentative pixels), and per pixel attributes
    - Color
    - Normal
    - Texture coordinates
    - Manay more are possible
- Inputs are outputs from the vertex shader, interpolated (by the GPU) to pixel location!
- Output:
    - pixel color
    - depth value
    - can discard the fragment using the discard keyword
## Perspective projection
- Where do we handle the final perpective divede?
- Is it even possible in a shader? Or should OpenGL handle it for us?
- Expercise!

### Pipeline Program
- Container of all the saders
- Vertext, fragment, geometry, tessellation, compute
- Can have several programs
- Must have at least one
- At any moment of time, exactly one pipeline program is bound

#### Installing Pipeline Programs
1. Create Shaders
2. Specify Shaders
3. Compiling Shaders
    - Shader are almost never (pre)compiled because even each version of graphics card are different architecture
4. Creating Program Objects
5. Attach Shaders to Programs
6. Link Shaders to Programs
7. Enable Shaders

*GLSL: Swizzling*
- Swiziling is a convenient way to acces vector components, e.g. `myVector.rgba`, `myVector.xy`

*GLSL: Flow Control*
Loops
- C++ style if-else
- C++ style for, while, and do
Best not using them

Jumps
- continue
- break
- return
- discard (in fragment shader, not draw in this frame)

*GLSL: Functions*
- Much like C++
- entry point into a shader is `void main()`
- No support for recursion
- Call by value return calling convention can add a parameter qy
- c++ like overloading exists
- args can be const
- You can add a parameter qualifier

