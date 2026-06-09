---
title: "Coordinate System Conventions"
source: "Strand7 R246 API Manual"
pages: 1020–1022
---

# Coordinate System Conventions

Energy

euJOULE

Joule (J)

euBTU

British thermal units (Btu)

euFTLBF

Kelvin (K)






All coordinate systems in Strand7 define a right-hand set of locally orthogonal axes; i1, i2
and i3, with reference to the rectangular Global Cartesian axis directions. These axes are
generically referred to as the 123 axis directions for translational degrees of freedom,
and are always listed in this order.
When there are rotational degrees of freedom defined by the right-hand rule about the
i1, i2 and i3 axes, they are listed after the 123 components in the same order. Collectively
this is referred to as the 123456 axis convention.

UCS Types
Strand7 supports a number of UCS (User Coordinate System) types including Cartesian,
cylindrical, spherical and toroidal. The integer values and types (as defined in the
include and header files) are shown below.

UCSCartesian
Cartesian system:






UCSCylindrical

Cylindrical system:


Z

T

R

UCSpherical
Spherical system:



R
P
T





