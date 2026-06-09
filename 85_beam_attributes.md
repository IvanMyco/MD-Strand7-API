---
title: "Beam Attributes"
source: "Strand7 R246 API Manual"
pages: 1040–1046
---

# Beam Attributes

Influence
Type
ATTRNodeInfluence
Parameters
- `CaseNum` — Load case number.
Heat Source
Type
ATTRNodeHeatSource
Parameters
- `CaseNum` — Load case number.
Initial Velocity
Type
ATTRNodeVelocity
Parameters
Case Num - Load case number.
Acceleration
Type
ATTRNodeAcceleration
Parameters
- `CaseNum` — Load case number.






Angle
Type
ATTRBeamAngle
Parameters
None.
Offset
Type
ATTRBeamOffset
Parameters
None.
Translational End Release
Type
ATTRBeamTEndRelease
Parameters
- `LocalNum` — Beam end, either 1 or 2.
Rotational End Release
Type
ATTRBeamREndRelease
Parameters
- `LocalNum` — Beam end, either 1 or 2.
Support
Type
ATTRBeamSupport
Parameters
None.




Pre-Load
Type
ATTRBeamPreTension
Parameters
- `CaseNum` — Load case number.
Cable Free-Length
Type
ATTRCableFreeLength
Parameters
None.
Local Distributed Load
Type
ATTRBeamDLL
Parameters
- `CaseNum` — Load case number.
- `LocalNum` — Local axis direction, one of 1, 2 or 3.
ID - Distribution ID number.
Global Distributed Load
Type
ATTRBeamDLG
Parameters
- `CaseNum` — Load case number.
- `LocalNum` — Global axis direction, one of 1, 2 or 3.
ID - Distribution ID number.
Local Point Force
Type





ATTRBeamCFL
Parameters
- `CaseNum` — Load case number.
ID - Force ID number.
Global Point Force
Type
ATTRBeamCFG
Parameters
- `CaseNum` — Load case number.
ID - Force ID number.
Local Point Moment
Type
ATTRBeamCML
Parameters
- `CaseNum` — Load case number.
ID - Moment ID number.
Global Point Moment
Type
ATTRBeamCMG
Parameters
- `CaseNum` — Load case number.
ID - Moment ID number.
Temperature Gradient
Type
ATTRBeamTempGradient
Parameters





- `CaseNum` — Load case number.
Convection
Type
ATTRBeamConvection
Parameters
- `CaseNum` — Load case number.
- `LocalNum` — Beam end, either 1 or 2.
Radiation
Type
ATTRBeamRadiation
Parameters
- `CaseNum` — Load case number.
- `LocalNum` — Beam end, either 1 or 2.
Heat Flux
Type
ATTRBeamFlux
Parameters
- `CaseNum` — Load case number.
- `LocalNum` — Beam end, either 1 or 2.
Heat Source
Type
ATTRBeamHeatSource
Parameters
- `CaseNum` — Load case number.
Pipe Radius
Type





ATTRBeamRadius
Parameters
None.
Pipe Pressure
Type
ATTRPipePressure
Parameters
- `CaseNum` — Load case number.
Non-Structural Mass
Type
ATTRBeamNSMass
Parameters
- `CaseNum` — Load case number.
ID - Mass distribution ID number.
Pipe Temperature
Type
ATTRPipeTemperature
Parameters
- `CaseNum` — Load case number.
Local Distributed Moment
Type
ATTRBeamDML
Parameters
- `CaseNum` — Load case number.
- `LocalNum` — Local axis direction, one of 1, 2 or 3.
ID - Distribution ID number.





String Group
Type
ATTRBeamStringGroup
Parameters
None.
Taper
Type
ATTRBeamTaper
Parameters
- `LocalNum` — Local axis direction, either 1 or 2.
Influence
Type
ATTRBeamInfluence
Parameters
- `CaseNum` — Load case number.
Cross-Section Factor
Type
ATTRBeamSectionFactor
Parameters
None.
Creep Loading Age
Type
ATTRBeamCreepLoadingAge
Parameters
None.





