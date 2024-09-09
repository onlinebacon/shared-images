# Derivation of Formulas for Celestial Navigation

## Computed Altitude (Hc)

The Hc, simply put, is the predicted observed altitude (Ho), given an assumed position (AP) and the geographical position (GP) of a celestial body.

Instead of using the longitude of the AP and the longitude of the GP, we'll be using the local hour angle (LHA) from the AP to the GP. The latitude of the AP will be referred to as *LAT*, while the latitude of the GP will be referred to as *DEC*.

Let's first think of the earth as a sphere of radius 1 with its center at the origin of a 3-dimensional cartesian system. The **X** axis aims at the point where the AP's meridian meets the equator, the **Y** axis also points at the equator, but 90° west of the AP's meridian and the **Z** axis aims at the north pole.

Let's define the vector $A = (A_x, A_y, A_z)$ for the position of the observer in this coordinate system. We can then calculate:

$A_x = cos(LAT)$

$A_y = 0$

$A_z = sin(LAT)$

Let's define the vector $B = (B_a, B_b, B_c)$. Being $A$ and $B$ unit vectors, the dot product between them gives us the cosine of the angle between them. Let's call this angle $\theta$.

$cos(\theta) = A \cdot B = A_x \times B_x + A_y \times B_y + A_z \times B_z$

Given that $A_y = 0$ we can reduce it to:

$cos(\theta) = A_x \times B_x + A_z \times B_z$

We can now calculate the $x$ and $z$ values of the vector $B$

$B_x = cos(DEC) * cos(LHA)$

$B_z = sin(DEC)$

Solving for $\theta$ we get:

$\theta = cos^{-1} [cos(LAT) \times cos(DEC) \times cos(LHA) + sin(LAT) \times sin(DEC)]$

The angle theta is proportional to the distance over the Earth's surface between the AP and the GP. That means this angle will be the predicted zenith distance to that celestial body from the AP making the compliment of this angle the predicted Ho. So in order to solve for the Hc instead, we can replace the *arccosine* function by the *arcsine*:

$Hc = sin^{-1}[cos(LAT) \times cos(DEC) \times cos(LHA) + sin(lat) \times sin(DEC)]$
