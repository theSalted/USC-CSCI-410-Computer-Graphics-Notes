# High-level overview of OpenGL

## Graphics Pipeline
Vertices                        -> Transformers          -> Clipper              -> Projector -> Rasterizer       -> Pixels
Primitives+ material properties | Translate Rotate Scale | Is it visible on screen | 3D to 2D | Convert to pixels | Shown on the screen

Not shown here:
- colors
- attributes 
- effects
- shader programs

## The Framebuffer
- Special memory on the graphics card
- Stores the current pixels to be displayed on the monitor
- Monitor has no storage capabilities
- The framebuffer is copied to the monitor at each refresh cycle

## Rendering with OpenGL
- Application generates the geometric primitives (polygons, lines)
- System draws each one into buffer
- Entire scene redrawn anew every frame
- Compare to: off-line rendering
(e.g., Pixar Renderman, Ray tracers)

## Rendering with OpenGL
- Application generates the geometric primitives (polygons, lines)
    - Video game
    - Interactive application (CAD, etc.)
    - High-performance computing
- Written in any language on the CPU

OpenGL programmer does not need to implement the pipeline.

However, pipeline is reconfigurable
    -> "Shaders"

## Graphics Pipleine
- Efficently implementable in hardware
(but not in software)
- Each stage can employ mulitiple specialized processors, working in parallel, buses between stages
- #processors per stage, bus bandwidths are fully tuned for typical grahics use
- Latency vs throughput

## Vertices
- What is a vertex
- A vertex is a point （kind of)
- Vertices in world coordinates
- Use GL_type for portability and consistency

- glVertex{234}{sfid}[v](TYPE coords)

## Coordinate systems
- World coordinates
- Camera coodintaes
- Scene/window coordinates

## Vertices (core profile)
- Vertices in world coordinates
- Store vertices into a Vertex Buffer Object (VBO)
- Upload VBO to GPU

## Transformer
- The OpenGL camera is in one place only
    - Looks at the xy plane
- If you would like to look at the world from any other direction, you must rotate your world to fit.

### Compatibility profile
- Transformer in world coordinates
- Must be set before object is drawn!
    - glRotate(45.0, 0.0, 0.0, -1.0);
    - glVertex2(1.0, 0.0);
- Compare [Angel Ch. 3]

### Core profile
- Transformer in world coordinates
- 4x4 matrix
- Created manually by the user
- Transmited to the shader program before rendering
- You write your on transformation

- 4x4 matrix
    - We uses 4x4 to handle translations
    - Homogeneous coordinates
    - We can write p = (x, y, z), but then a matrix can only rotate. 

## Clipper
- Mostly automatic (must set viewing volume)
- You do not fully control the clipper - OpenGL has a standard clipping setting. 

## Projector
- In modern OpenGL, you have to do this yourself.
- This isn't ard and thre are good reasons to not hardcoding this.

### Orthographic Projection 
- .. flatenning
- just kill the z coordinate
- Think like look things very far away and zoom in

### Perspective lenses
- inmitate how lenses works

## Rasterizer
- Interesting algorithms [Angel Ch. 6]
- To window coordinate 
- Antialiasing
- Rasterizer is very difficult to implement
- This is really, really difficult
- More difficult than you think

## Geomertic primitives
- Suppose we have 8 vertices: p0...p8
- We would have multiple ways to interpreter/connect them
- GLPOINTS, GL_LINES, GL_TRIANGLES are examoles of primitive type

## Triangles 
- Can be any shape or size
- Well-shaped triangles have advantages for numerical simulation
- Shpe quality makes little difference for basic OpenGL rendering
- Triangles are our main primitive
- Why would you use any other primitive?
- Many OpenGL implementations only reluctangtly let yu draw lines and points 
    - On Mac, you can't set line thicknesses at all.
- If you want to draw a line, or a point: fake it with triangles
- If you want to draw polygon fake with triangles

## Geometry Primitives (compatility profile)
- Specified via vertices
- General schema


## Example: Draw Two Square Edges (compatibility profile)
- you use glBegin(type) and glEnd();

## Geometric Primitives (Core profile)
- Specificed via vertices
- Stored in a Vertex Buffer Object (VBO)

## Clunky interface
- You have to be careful
- Raw arrray
- No data structures
- You directly interact with memory

## Render Points and Line Segments (core profile)
- you use glDrawArrays

## Polygon
- Core profile don't support
- Three points define a plane, but if you add the fourth points there are lots ambiguity

## Triangles Strips
- Efficency in space and time
- Reuces visual effects 
- Probabilty don't use this
- Draw based on index order

## Triangle Mesh
- You need to explicitly define indices
- Makes certain shading technqiues impossible
- This saves memory

- Note: OpenGL have a very comprehensive documentation


