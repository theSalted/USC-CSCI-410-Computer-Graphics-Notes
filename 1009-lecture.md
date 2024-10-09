# Homework 1
- Use HW1 engine

# Lighting and Shading
- Global and Local illumination 
- Normal Vectors
- Light Sources
- Phong illumnination Model

## Global Illumination

- Ray tracing
- Radiosity
    - (diffuse lighting)
- Photon Mapping
    - (rendering equation)
- Follow light rays through a scene
    - Light can be bounce hundres of times
- Accurate, but expenseive (off-line)
    - All light comes from a physical light source.
    - (remeber how OpenGL works in contrast)

Local Illumination
- Apporximate model
- Local interaction between light surface, viewer
- Phong model
- fast, supported in OpenGL
- GPU shaders
- Real-time graphics
    - (there are exceptions)
- Approximate model
- Local interaction between, light, surface, viewer
- Color determined only based on surface normal , relative camera position and relative light position
- Wnat effect does this ignore?

- No shadow
- No scattering
- No refraction
- No reflection
- No subsurface scattering

### Refelected Vector
- Perfect reflection: angleof incident equals angle of reflection
- Also: i, n and r lie in the same plane

