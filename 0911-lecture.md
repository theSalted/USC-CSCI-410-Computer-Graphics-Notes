
# Transformations

- Model view matrix (4x4 matrix)
- Projection matrix (4x4 matrix）

Vertices in 3D -> Model View -> Vertices in the camera coordinate system -> Projection -> Vertices in 2D

## Model-view matrix
- Philosophically think model and view matrix as two different model
- Model: Translate, rotat, scale obnjects in world space
- Model: The user rotated the object, but we don't want reload the obejct
- View matrix: account for coordinates of the camera
- These two do more or less the same thing (mathmatically)
- Rigids maps in 3D that postion things
- Difference betwen "model" (moving around object) and "view" (moving around the camera) is purely a convention
- In the OpenGL model, they are often not distinguished at all.

## OpenGL Transformation Matrices
- Manipulated separately in OpenGL
Core profile: set them directly 
- YOU WILL LOAD THE MATRICES into memory and apply them yourself in a shader
Compatibility profile: 
- must be set matrix model

Note in template code:
``
pipelineProgram->SetUniformVariableMatrix4fv("modelViewMatrix", isRowMajor, m);
``
`isRowMajor` is how computer interpreter matrix (if coulumn are major (like mathmatical) or row are major (more natural to computers)

- You can multiply with any matrix here.
    - Do more than just boring old...


## The renderng coordinate system
- World rendering coordinate system = rendering coordinate system

Say we have a matrix M and Matrix A. We want to apply transform matrix T so A = dot(M, T).
You shouldn't solve for T. Instead, transofrm M to world origin and then transofrm to A.

# Math behind Computer Graphics
## Scalars
- Scalars from a scalar field
- Operations a + b, dot(a, b), 0, 1, -a, ()^-1
- "Expected" law apply'
- Examples: rational or real s with addition and multiplication
- Scalars are number: double and float (int are not numbers)
 a = 3

## Vectors
- Vectors u, v, w from a vector space
- Vector addition u + v, subtactionb u - v
- Scalar multification does not exit

- We only deal with RealNumber^n where n = 3 and n = 4
- Vector space over real numbers
- On CPU:
    - Float[3], double[3]...
- On GPU:
    - vec3f, vec3d

When you add two vectors you just add all of their contents

## Euclidean Space
- Vector space over real numbers
- 3D in computer graphics
- Dot product a = dot(u, v) = u_1 * v_1 + u_2 * v_2 + U_3 + v_3
- dot(0, 0) = 0
- u,v are othogonal if dot(u, v) = 0
- |v|^2 = dot(v, v) defines |v|, the length of v
- if |v| = 1, the vector is normal

## Two Interpretations of vectors
- Just a point in space (a vector can mean a coordinate)
- (it can also be interpreate as) An arrow pointing in direction of a certain lenght (physicist love to think this)
- In CS, we don't care

## Lines and line segaments
- Parametric form of line P(alpha) = p_0 + alpha d
- Line segments between Q and R:
P(a) = (1-a) Q + a R for 0 <= a <= 1, where a is alpha

## Convex Hull
- Convex hull defined by...
- And is relevant to CG

## Projection
- Dot product projects one vector onto another vector
- Orthogonal projection is because the dot product behind it is equal to zero??? (why?)

## Cross product
- |a * b| = |a||b||sin(theta)|
- Cross product is perpendicalr to both a and b
- Right hand rule
- In practice avoid cross product because floating point percision because subtracton sucks

## Plane
- Plane is defined by point P0 and

## Frames
Frame should always be othonormal

## Change of coordinate system
- Bases {u_1, u_2, u_3) and { v_1, v_2, v_3 }
- Exprss basis vectors u_i in terms of v_j

## Matrices
- matrices represent linear transformations *a = MB*
- On CPU: float[3][3], double[3][3]
- On GPU: mat3f, ...
- matrices can be added and multiplied by a scalar like a vector
- matrices can be multiplied woith each other
- Can represent rotation, scaling, and reflection
    - Rotation: SO(3) = {3x3 matrices with determaint 1}
    - Scaling: diagnoal matricies with positive on diagnoal only
    - Reflection: identity matricies where one value is -1
    - Rotation
The forth component in matrix allow translation and the extra 1 scalar is used to define coordinate ssytem

## Rotation in 2D
x' = x...

