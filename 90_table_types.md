---
title: "Table Types"
source: "Strand7 R246 API Manual"
pages: 1061–1063
---

# Table Types

Load Patch Types
the edge is selected to define the load patch: a bit value of 1 indicates that an edge is
selected. For ptAuto1, ptAuto2 and ptAuto3 only one edge bit is set. For ptAngleSplit,
two adjacent edge bits must be set. For ptManual, at least one edge bit must be set.
For example,

b’00000000 00000000 00000000 00000001’ = 1 : Edge 1
b’00000000 00000000 00000000 00000010’ = 2 : Edge 2
b’00000000 00000000 00000000 00000100’ = 4 : Edge 3
b’00000000 00000000 00000000 00001000’ = 8 : Edge 4
b’00000000 00000000 00000000 00001001’ = 9 : Edges 1 and 4





Strand7 accepts a number of table types for use in nonlinear solutions. The types for
these tables are listed below.

General Table Types

ttVsTime - Factor vs time.
ttVsTemperature - Factor vs temperature.
ttVsFrequency - Factor vs frequency.
ttStressStrain - Stress vs strain.
ttForceDisplacement - Force vs displacement.
ttMomentCurvature - Moment vs curvature.
ttMomentRotation - Moment vs rotation.
ttAccVsTime - Acceleration vs time.
ttForceVelocity - Force vs velocity.
ttVsPosition - Factor vs position.
ttStrainTime - Strain vs time.

Frequency Table Types (only applies to factor vs frequency table type)

- `tyPeriod` — vs period.
- `tyFrequency` — vs Frequency.

Beam Property Table Types

- `ptBeamStiffModVsTemp` — Stiffness modulus vs temperature.
- `ptBeamAlphaVsTemp` — Expansion coefficient vs temperature.
- `ptBeamConductVsTemp` — Conductivity vs temperature.






- `ptBeamCpVsTemp` — Specific heat vs temperature.
- `ptBeamStiffModVsTime` — Stiffness modulus vs time.
- `ptBeamConductVsTime` — Conductivity vs time.
- `ptSpringAxialVsDisp` — Spring axial force vs displacement.
- `ptSpringTorqueVsTwist` — Spring torque vs twist.
- `ptSpringAxialVsVelocity` — Spring axial force vs velocity.
- `ptTrussAxialStressVsStrain` — Truss axial stress vs strain.
- `ptBeamAxialStressVsStrain` — Beam axial stress vs strain.
- `ptBeamMomentK1` — Beam moment vs curvature on plane 1.
- `ptBeamMomentK2` — Beam moment vs curvature on plane 2.
- `ptConnectionShear1` — Connection shear table.
- `ptConnectionShear2` — Connection shear table.
- `ptConnectionAxial` — Connection axial table.
- `ptConnectionBend1` — Connection bending table.
- `ptConnectionBend2` — Connection bending table.
- `ptConnectionTorque` — Connection torque table.
- `ptBeamYieldVsTemp` — Yield vs Temperature.

Plate Property Table Types

- `ptPlateModVsTemp` — Modulus vs temperature.
- `ptPlateAlphaVsTemp` — Expansion coefficient vs temperature.
- `ptPlateConductVsTemp` — Conduction vs temperature.
- `ptPlateCpVsTemp` — Specific heat vs temperature.
- `ptPlateModVsTime` — Modulus vs time.
- `ptPlateConductVsTime` — Conductivity vs time.




