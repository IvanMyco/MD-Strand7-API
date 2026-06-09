---
title: "Node Attributes"
source: "Strand7 R246 API Manual"
pages: 1037–1039
---

# Node Attributes

Attribute Types

Attribute Types
Attribute types are identified by an integer constant as defined in the header files.
Individual functions are provided to set and get attribute data, and the
St7DeleteAttribute function can be used to delete attributes.
Attribute instances are uniquely identified by the arguments Entity, EltNum, AttributeType,
CaseNum, LocalID and ID. The entity type, element number and attribute type
arguments are required for all attributes. The case number, local ID and ID arguments
are dependent on the attribute type. When these arguments are not required they are
ignored.





Restraint
Type
ATTRFreedom
Parameters
- `CaseNum` — Freedom case number.
Force
Type
ATTRForce
Parameters
- `CaseNum` — Load case number.
Moment
Type
ATTRMoment
Parameters
- `CaseNum` — Load case number.
Temperature
Type
ATTRTemperature
Parameters
- `CaseNum` — Load case number.
Translational Mass
Type
ATTRMTranslation
Parameters
None.




Rotational Mass
Type
ATTRMRotation
Parameters
None.
Translational Stiffness
Type
ATTRKTranslation
Parameters
- `CaseNum` — Freedom case number.
Rotational Stiffness
Type
ATTRKRotation
Parameters
- `CaseNum` — Freedom case number.
Damping
Type
ATTRDamping
Parameters
- `CaseNum` — Freedom case number.
Non-Structural Mass
Type
ATTRNSMass
Parameters
- `CaseNum` — Load case number.





