---
title: "Plate Local Coordinates"
source: "Strand7 R246 API Manual"
pages: 1028–1030
---

# Plate Local Coordinates

Beam Local Coordinates
Each beam element in Strand7 possesses a node numbering scheme that defines the
default orientation of the principal coordinate system of the beam, denoted 1-2-3. The
principal coordinate system is a right-handed coordinate system defined by the beam’s
properties such that over the cross-section S in the 1-2 plane

I12   x1 x2 dA  0 .
S

Note that this is generally a rotation away from the native x-y directions in which the
beam cross-section is defined. These x-y directions with the z-direction that completes
the right-hand coordinate system, is termed the local beam axis system.
The default orientation for Beam2 elements is defined by:


i3 – is the unit vector directed from Node 1 to Node 2.



i2 – is the unit vector arising from i2 = Z × i3 where Z is the unit vector in the global Zdirection



i1 – completes the right handed system such that i1 × i2 = i3

The default orientation for Beam3 elements is defined by:


i3 – is the unit vector directed from Node 1 to Node 2.



i2 – is the unit vector perpendicular to i3, lying in the plane defined by Nodes 1, 2 and
3, directed towards Node 3.



i1 – completes the right handed system such that i1 × i2 = i3

The principal axes (hence the beam itself) may be rotated about the 3-axis from the
default orientation using St7SetBeamReferenceAngle1.
The principal axes can be interrogated using St7GetBeamAxisSystem.
Beam End Numbering
Attributes may also be applied to a particular end of a beam element. End 1 is defined
as the end occurring at Node 1, and End 2 is defined as the end occurring at Node 2.
Where l is the distance in the 3-direction from Node 1 along the beam, and L is the
length of the beam, the relative length position is defined as l / L.






Intrinsic Coordinate System
Each plate element in Strand7 possesses a node and edge numbering scheme, and a
set of intrinsic coordinates UV that parameterise its extent in Global Cartesian space. The
intrinsic coordinates are defined by the node numbering scheme, summarised in the
table below. They may be queried using St7GetPlateUV.
Element Type

Nodal Intrinsic Coordinates

Edges

Numbering

Node

U

V

Edge

Nodal definition





1-2





2-3





3-1


-1

-1


1-2



-1


2-3





3-4


-1



4-1





1-4-2





2-5-3





3-6-1


0.5



0.5

0.5



0.5

Tri3

Quad4

Tri6





Quad8

Quad9


-1

-1


1-5-2



-1


2-6-3





3-7-4


-1



4-8-1



-1








-1



-1

-1


1-5-2



-1


2-6-3





3-7-4


-1



4-8- 1



-1








-1





Local Coordinate System
The intrinsic coordinate system is generally curvilinear and non-orthogonal. An
orthogonal local coordinate system is also defined for plates for the purpose of applying
directional attributes and material properties.
The local coordinate system is a right-handed coordinate system defined such that the xy plane lies in the median plane of the plate. The median plane of the plate is that plane
which minimizes the sum of squared perpendicular distances to it (calculated by a
principal components analysis).
By default the local coordinate system is aligned relative to the plate nodes such that for
triangular elements:





