---
title: "Beam Local Coordinates"
source: "Strand7 R246 API Manual"
pages: 1027–1027
---

# Beam Local Coordinates

Element Connections

Element Connections
The ConnectionArray vector is used to determine the nodal connections of an
element. It is used for all element types ranging from Beam2 to Brick20 elements.
The first position in the ConnectionArray vector, ConnectionArray[0], holds the
number of nodes in the element. Positions thereafter hold the ordered nodal
connections. For a Beam2 element, ConnectionArray[0..2] is filled, with
ConnectionArray[0] = 2, ConnectionArray[1] = Node1 and
ConnectionArray[2] = Node2 respectively. A Brick20 element will use the entire
vector in a similar fashion.
Refer to Beam Local Coordinates, Plate Local Coordinates and Brick Local Coordinates
for element node connection sequences for all element types.





