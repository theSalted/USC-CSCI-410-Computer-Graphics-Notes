
# Polygon Meshes and Implict Surfaces

- Polygon Meshes
- Implicit Surfaces
- Construtive Solid Geometry

## What is a surface?
Mathmatics: Differential geometry
Artist: Something I can edit with a tool
Computer programmer: Data structure

## Mathmatics of surfaces

A surface is an object that is locally a plane
- Meaning: you can picak a small part of a surface and squish so it looks like the plane
- A surface can have a boundary that looks like a half-plane
- Globally, a surface does not have to look like a plane


## Programmer's view of surfaces
A surface is some sort of the representation of a shape as data

quad mesh and point cloud are two examples

## Modeling complex shapes
- A equation for a sphere is possible, but how about an equation for a telephone or a face?
- Complexity is achieved using simple pieces
    - Polygons, parametric surfaces, or implicit surfaces
- Goals
    - Model anything with arbitrary precision (in principle)
    - Eadsy to build and modify
    - Efficent computations (for rendering, collisions, etc.)
    - Easy to implement (a minor consideration...)


### What do we need from shapes in CG
- Local control of shape for modeling
- Ability to model what we need
- Smoothness and continuity
- Ability to evaluate derivatives
- Ability to do collision detection
- Ease of rendering 
No single technique solves all problems

### Polygon meshes
- Any shape can modeled out of polygons
    - if you use enought of them..
- Polygon with how many sides
    - Can use triangles, quadrilaterals, pentagons, ... n-gons
    - Triangles are most common
    - When > 3 sides are used, ambiguity about what to do when polygon nonplanar, or concave, or self-intersecting
- Polygon meshes are built out of
    - verices (points)
    - edges (line segments between vertices)
    - faces (polygons bounded by edges)
## What sets polygon (for now this mean triangles) meshes a part?
- Eplicit surface representation
    - No need to solve an equation before drawing
- Solid 
    - Not just samples on the smooth object, but solid approximation
- Have geometrice quantites

## Boundary of a surface
- Intuitively: when you walk, you walk of thesurfac
- Mathmatically maps to the upper half-plane of R^2
- On triangles meshes

An interior edges have two two neighbor edges. Boundary edge only have one.

## Normals
Triangles defines uniquew plane and can be easily compute using cross product

## per-vertex normal
- It's apporxinate by taking an averging normal of neighbor polygon

# Data Structures for Polygon Meshes
- Simplest (but dumb)
- float triangle[n][3][3]; (each triangle stores 3 (x, y, z) points)
- redundant: each vertex stored multiple tunes
- Vertex List, Face List
    - List of vertices, each vertex consists of (x, y, z) geometric (shape) info only
    - List of triangles, each a triple of vertex id's (or pointers) topological (connectivivity, adjacency) info only
    - Example [v0, v1, v3, v3][[0, 2, 3][2, 1, 4]]
    - List of triangles, each a triple of vertex id's (or pointers) topological (connectivity, adjacency) info only
    - Fine for many purposes, but finding the faces adjacent to a vertex talkes O(F) time for a model with F faces. Such queries are important fir toplogical editiing
## Level of details
- Different models for near and far objects
- Different models for rendering ands collision detection
- Compression of data recorded from the real world

Whe need automatica algorithms for reducing the polygon count without
- losing key features
- getting artifacts in the silhouette
- popping

## Subdivsion

- There is only so much information in a simple shaple.
- To dispaly a smooth shape we need lots of polygons 
- Why should we have to store lots of polygons
    - Only store necessary informtion
    - Simple mathmatical formulat to get from samll number of stored information to detailed high-resolution surface.
- It's not enough to simple reolace wach triangle  with more triangles.
- After each upsamplingstep we neeed to move te vertices to make the surface smooth
- Subdivision rules tell us where to place new vertices and where to move the old vertic


