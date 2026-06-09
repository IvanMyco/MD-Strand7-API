---
title: "Node Results"
source: "Strand7 R246 API Manual"
pages: 1071–1072
---

# Node Results

Solver Options

- `spZeroFrequency` — Zero frequency factor.
- `spZeroBucklingEigen` — Zero buckling factor.
- `spCurveFitTime` — Creep curve fit time parameter.
- `spSpacingBias` — Creep curve fit spacing bias.
- `spTimeStepParam` — Time step parameter.
- `spSlidingFrictionFactor` — Sliding friction factor.
- `spMNLTangentRatio` — Nonlinear material tangent ratio.
- `spStickingFrictionFactor` — Sticking friction factor.
- `spMinArcLengthFactor` — Minimum arc length reduction factor.
- `spMaxFibreStrainInc` — Maximum MNL beam fibre strain in an increment.

Modal Load Types

mtBaseAcc - Base acceleration.
mtBaseVel - Base velocity.
mtBaseDisp - Base displacement.
mtAppliedLoad - Base applied load.





Node results include displacement, velocity, acceleration, phase, reaction, temperature,
heat flux and influence. The St7GetNodeResult and St7GetNodeResultUCS functions can
be used to access these result quantities.
Result types can be selected by the following input:

ResultType
The result quantity to be returned, one of rtNodeDisp, rtNodeVel, rtNodeAcc,
rtNodePhase, rtNodeReact, rtNodeTemp, rtNodeFlux or rtNodeInfluence.
Results are returned as a 6 element array of data. Depending on the result type
requested this array is formatted as follows:

Displacement

[0..2] - Translations in the 123 axis directions for the specified UCS.
[3..5] - Rotations about the 123 axis directions for the specified UCS.

Velocity

[0..2] - Translational velocities in the 123 axis directions for the specified UCS.
[3..5] - Angular velocities about the 123 axis directions for the specified UCS.

Acceleration

[0..2] - Translational accelerations in the 123 axis directions for the specified UCS.
[3..5] - Angular accelerations about the 123 axis directions for the specified UCS.

Phase

[0..2] - Translational components in the 123 axis directions for the specified UCS.
[3..5] - Angular components about the 123 axis directions for the specified UCS.





