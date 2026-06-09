---
title: "Global Load Cases"
source: "Strand7 R246 API Manual"
pages: 1023–1023
---

# Global Load Cases

Coordinate System Conventions

UCSToroidal

Toroidal system:

T

R

P

The UCSDoublesArray vector contains the definition of the UCS, including the origin point,
and two points defining a plane. In the case of a toroidal system, an additional value
defines the major radius of the torus. The following includes the positional information for
the UCSDoublesArray vector.
UCS Doubles Array

[0..2]

Origin point in Global Cartesian coordinates.

[3..5]

1st plane point in Global Cartesian coordinates.

[6..8]

2nd plane point in Global Cartesian coordinates.

[9]

Toroidal radius.





