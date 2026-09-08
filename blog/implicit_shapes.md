# Implicit Shapes

Do you remember this formula from pre-calculus: $x^2 + y^2 + z^2 = 4$ ? This represents all 3D points that are at exactly 2 units distance from the origin, in other words, a sphere.

If we slightly rearrange the equation we get: $x^2 + y^2 + z^2 - 4 = 0$.

One of the most basic examples of an implicit surface, an abstract way of representing a shape. We KNOW that ALL points in that sphere are represented by this equation, even without computing any of them — in fact, that formula IS the sphere.

In general, an implicit surface is defined by a function of the form:

$F(x,y,z) = 0$

Okay, it's obvious for a sphere but what about more complex shapes? Like "spot", "armadillo" or the "happy buddha". Can we represent them implicitly? How?

## Simple Algorithm for SDFs

- Given a target shape, shoot a lot of rays through it.
- Pick many uniformly distributed random points along each ray.
- For each point, measure the distance from the point to the surface of the shape.

This distance becomes the value assigned to the point in the function we are constructing: positive outside the shape, negative inside (zero on the surface).

As the number of rays and sampled points tends to infinity, the zeros of our function converge to a representation of the surface. The function we have built is called a Signed Distance Function (SDF).

But now, assume you have a big enough set of zeros of your SDF, how do you reconstruct the target mesh?

Marching Tetrahedra!