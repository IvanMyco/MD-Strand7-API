---
title: "Load Patch Types"
source: "Strand7 R246 API Manual"
pages: 1059–1060
---

# Load Patch Types

Beam Distribution Types

Beam Distribution Types
There are six beam distribution types in Strand7, used by the API functions
St7SetBeamDLL6ID, St7SetBeamDML6ID, St7SetBeamDLG6ID, St7SetBeamNSMass10ID,
St7GetBeamDLL6ID, St7GetBeamDML6ID, St7GetBeamDLG6ID and
St7GetBeamNSMass10ID. The beam distribution types are referred to by the constants
listed below. The data required for each type are specified in the Doubles input
parameter.
DLType

Distribution

Definition

kConstantDL

kLinearDL

Doubles[0] = PA
Doubles[1] = PB
kTriangularDL

Doubles[2] = P1
Doubles[3] = P2

kThreePoint0DL

Doubles[4] = a
Doubles[5] = b

kThreePoint1DL

kTrapezoidalDL





There are six load patch types in Strand7, used by the API functions
St7SetPlateLoadPatch4 and St7GetPlateLoadPatch4. The load patch types are referred
to by the constants listed below. The weights required by ptManual type are specified in
the Doubles input parameter.
Type

Patch Distribution

Factor

- `ptAuto4`

N/A

- `ptAuto3`

N/A

- `ptAuto2`

N/A

- `ptAuto1`

N/A

- `ptAngleSplit`

N/A

Doubles[0] = Edge 1 weight
- `ptManual`

Doubles[1] = Edge 2 weight
Doubles[2] = Edge 3 weight
Doubles[3] = Edge 4 weight

The four least significant bits in the four byte integer EdgeBits correspond to the four
(possible) edges of the load patch. The least significant bit corresponds to Edge 1, the
second least significant bit corresponds to Edge 2, and so on. Each bit specifies whether




