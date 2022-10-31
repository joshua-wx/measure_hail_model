## Hail Measurement Library 🧊📏

### Overview

This repo is for a new method to simulate the manual measurements of hailstones using 3D models.
This includes the measurement of Dmax, Dint and Dmin following the standard procedure.
The implementation is heavily optimised to use the trimesh library and convexhulls.

### Method

1. Shift model centre of mass to 0,0,0
2. calculate convex hull of model
3. calculate which pair of vertices have the greatest separation
4. Calculate normal vector of plane normal to the Dmax (Dint-Dmin plane), and the mid point
5. Slice the convex hull at this mid point using the Dint-Dmin plane
6. Fit a minimum bounded box to the slice to find Dint and Dmin.

TODO: Proper output for analysis of errors