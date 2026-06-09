---
title: "Brick Local Coordinates"
source: "Strand7 R246 API Manual"
pages: 1031–1035
---

# Brick Local Coordinates

Plate Local Coordinates


For quadrilateral elements:
x

x

The local x-y axes may be rotated about the local z axis using St7SetPlateXAngle1. The
local z axis is invariant, and completes the right-hand coordinate system.





Intrinsic Coordinate System
Each brick element in Strand7 possesses a node and face numbering scheme, and a set
of intrinsic coordinates UVW that parameterise its extent in XYZ space. The intrinsic
coordinates are defined by the node numbering scheme, summarised in the table
below. They may be queried using St7GetBrickUVW.
Element Type

Nodal Intrinsic Coordinates

Faces

Numbering

Node

U

V

W

Face

Nodal definition






1-2-3






4-1-3






4-2-1






4-3-2


-1

-1



1-2-3-4



-1



5-1-4






5-2-1


-1




5-3-2






5-4-3




-1


1-2-3




-1


5-2-1-4




-1


4-6-5






4-1-3-6






6-3-2-5





Tet4

Pyra5

Wedge6






Hex8

Tet10

Pyra13



-1

-1

-1


1-2-3-4



-1

-1


7-3-2-6




-1


6-5-8-7


-1


-1


5-1-4-8


-1

-1



8-4-3-7



-1



6-2-1-5






-1








1-5-2-6-3-7






4-8-1-7-3-10






4-9-2-5-1-8






4-10-3-6-2-9


0.5




0.5

0.5




0.5





0.5


0.5


0.5



0.5

0.5


-1

-1



1-6-2-7-3-8-4-9



-1



5-10-1-9-4-13






5-11-2-6-1-10


-1




5-12-3-7-2-11






5-13-4-8-3-12



-1













Wedge15



-1




-0.5

-0.5

0.5


0.5

-0.5

0.5


0.5

0.5

0.5


-0.5

0.5

0.5




-1


1-7-2-8-3-9




-1


5-11-2-7-1-10-4-13




-1


4-15-6-14-5-13






4-10-1-9-3-12-6-15






6-12-3-8-2-11-5-14






0.5


-1


0.5

0.5

-1



0.5

-1














0.5




0.5

0.5




0.5



-1

-1

-1


1-9-2-10-3-11-4-12



-1

-1


7-3-10-2-6-14




-1


6-13-5-16-8-15-7-14


-1


-1


5-1-12-4-8-16


-1

-1



8-4-11-3-7-15



-1



6-2-9-1-5-13





Hex16

Hex20







-1





-1

-1




-1




-1


-1


-1



-1











-1




-1

-1

-1


1-9-2-10-3-11-4-12



-1

-1


7-15-3-10-2-14-6-18




-1


6-17-5-20-8-19-7-18


-1


-1


5-13-1-12-4-16-8-20


-1

-1



8-16-4-11-3-15-7-19



-1



6-14-2-9-1-13-5-17






-1





-1

-1




-1




-1


-1


-1


-1

-1




-1







-1






