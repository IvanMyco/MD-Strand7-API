---
title: "Attribute Types"
source: "Strand7 R246 API Manual"
pages: 1036–1036
---

# Attribute Types



-1











-1



Local Coordinate System
The intrinsic coordinate system is generally curvilinear and non-orthogonal. An
orthogonal local coordinate system is also defined for bricks for the purpose of applying
directional attributes and material properties.
By default the local coordinate system is aligned with the Global Cartesian coordinates,
but may be realigned to any other UCS using St7SetBrickLocalAxes1.
Face Axis System
Some attributes are defined with reference to a coordinate system defined on a given
face of a brick. The face axis system is oriented with respect to the nodes in the face’s
definition (listed above) such that it coincides with the default local axis system of a
plate element with the same nodal definition.
The face axis system for a face on a particular brick element can be interrogated using
St7GetBrickFaceAxisSystem.





