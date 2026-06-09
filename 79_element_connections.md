---
title: "Element Connections"
source: "Strand7 R246 API Manual"
pages: 1026–1026
---

# Element Connections

Entity Types
There are five entity types in Strand7. These are nodes, beams, plates, bricks and links.
Each of these entity types is referred to by a constant (as defined in the include and
header files) and are listed below.

- `tyNODE`

Nodes

- `tyBEAM`

Beams

- `tyPLATE`

Plates

- `tyBRICK`

Bricks

- `tyLINK`

Links

The total number of properties can be obtained for each element type by using the
St7GetTotalProperties function call. Positions within the output parameters NumProperties
and LastProperty can be accessed using the following constants:

- `ipBeamPropTotal`

Beams

- `ipPlatePropTotal`

Plates

- `ipBrickPropTotal`

Bricks

- `ipPlyPropTotal`

Plies

When referring to property types, such as in functions like St7GetPropertyName,
St7DeleteProperty, etc., use the following constants:

- `ptBEAMPROP`

Beams

- `ptPLATEPROP`

Plates

- `ptBRICKPROP`

Bricks

- `ptPLYPROP`

Plies





