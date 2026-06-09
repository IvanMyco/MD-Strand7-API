---
title: "Beam Attributes – Set"
source: "Strand7 R246 API Manual"
pages: 241–271
---

# Beam Attributes – Set

Nodal Attributes – Get
Input Parameters

uID
Strand7 model file ID number.

NodeNum
The node number.

CaseNum
The load case number.
Output Parameters

ResponseType
Type of response variable, either reNodeDisplacement or reNodeReaction.

UCSId
The ID number for the specified UCS.

Status[0..5]
A 6 element array describing the active DoFs for the response variable in the
UCS axis system. Each element may be set to btTrue or btFalse to enable or
disable the corresponding DoF.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidBeamEnd,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_InvalidResponseType,
ERR7_NoError, ERR7_ResultFileIsOpen


---

### `St7SetBeamID`

Sets the ID number of the specified beam.

**Syntax**

```c
long St7SetBeamID(long uID, long BeamNum, long BeamID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `BeamID` — The beam ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetBeamReferenceAngle1`

Sets the reference angle for the specified beam. This angle controls the local
rotation of the beam cross-section from the default orientation, about the beam
length. See Beam Local Coordinates for further information.

**Syntax**

```c
long St7SetBeamReferenceAngle1(long uID, long BeamNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `Doubles[0]` — The reference angle used to align the beam principal axis system, see Beam Local Coordinates.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetBeamConnectionUCS`

Sets the UCS used in the connection element formulation at the specified beam
end. The translational and rotational stiffness components are distributed
according to the 123 axis convention in the specified UCS. This attribute is only
applicable to beams of connection element type.

**Syntax**

```c
long St7SetBeamConnectionUCS(long uID, long BeamNum, long
BeamEnd, long UCSId)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `BeamEnd` — Beam end identifier, either 1 or 2.
- `UCSId` — The UCS ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetBeamTaper2`

Sets the taper properties for the specified beam.

**Syntax**

```c
long St7SetBeamTaper2(long uID, long BeamNum, long
TaperAxis, long TaperType, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `TaperAxis` — The local beam axis to be tapered: axLocalX or axLocalY. See Beam Local Coordinates for further information.
- `TaperType` — The type of beam taper; one of btTop, btSymm or btBottom.
- `Doubles[0..1]` — A 2 element array that specifies the taper ratios at either beam end. The dimension of the beam section is scaled by this value to calculate the tapered shape.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,


ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetBeamOffset2`

Sets the offsets for the specified beam.

**Syntax**

```c
long St7SetBeamOffset2(long uID, long BeamNum, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `Doubles[0..1]` — A 2 element array describing the beam offsets. Doubles[i-1] describes the offset in the ith principal axis direction, see Beam Local Coordinates.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidTaperAxis,
ERR7_InvalidTaperRatio, ERR7_InvalidTaperType,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetBeamSupport2F`

Sets the elastic support value assigned to the specified beam.

**Syntax**

```c
long St7SetBeamSupport2F(long uID, long BeamNum, long
CaseNum, long Status, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `CaseNum` — The freedom case number.
- `Status` — Compression-only flag, either btTrue or btFalse.
- `Doubles[0..1]` — A 2 element array describing the elastic support conditions for the specified beam. Doubles[i-1] describes the elastic support in the ith principal axis direction, see Beam Local Coordinates.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetBeamSectionFactor7`

Sets the beam section factors for the specified beam. These factors are used to
scale the beam section data contained in the associated beam property.

**Syntax**

```c
long St7SetBeamSectionFactor7(long uID, long BeamNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `Doubles[0..6]` — [0] - 1-axis shear stiffness factor. [1] - 2-axis shear stiffness factor. [2] - Axial stiffness factor. [3] - 1-axis bending stiffness factor. [4] - 2-axis bending stiffness factor. [5] - Torsional stiffness factor. [6] - Mass factor.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetBeamTRelease3`

Sets the translational end release conditions at the specified beam.

**Syntax**

```c
long St7SetBeamTRelease3(long uID, long BeamNum, long
BeamEnd, long* Status, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `BeamEnd` — Beam end identifier, either 1 or 2.
- `Status[0..2]` — Status[i-1] - describes the release conditions of the specified beam end for the ith principal axis direction, see Beam Local Coordinates – one of kBeamEndRelReleased, kBeamEndRelFixed or kBeamEndRelPartial.
- `Doubles[0..2]` — A 3 element array containing the partial stiffnesses to be used in the case of partial end release conditions.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidBeamEnd,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetBeamRRelease3`

Sets the rotational end release conditions at the specified beam.

**Syntax**

```c
long St7SetBeamRRelease3(long uID, long BeamNum, long
BeamEnd, long* Status, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `BeamEnd` — Beam end identifier, either 1 or 2.
- `Status[0..2]` — Status[i-1] describes the release conditions of the specified beam end for the ith principal axis direction, see Beam Local Coordinates – one of kBeamEndRelReleased, kBeamEndRelFixed or kBeamEndRelPartial.
- `Doubles[0..2]` — A 3 element array containing the partial stiffnesses to be used in the case of partial end release conditions.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidBeamEnd,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetBeamCableFreeLength1`

Sets the free cable length for the specified beam. This is the unstressed cable
length and is only active for beam of type cable.

**Syntax**

```c
long St7SetBeamCableFreeLength1(long uID, long BeamNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `Doubles[0]` — The free cable length.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetBeamRadius1`

Sets the bend radius of the specified beam. This attribute is only active for beams
of type pipe.

**Syntax**

```c
long St7SetBeamRadius1(long uID, long BeamNum, long BeamDir,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `BeamDir` — The axis of the bend: axPrincipal1 or axPrincipal2. The beam will be bent in the axis direction specified, not about the axis, see Beam Local Coordinates.
- `Doubles[0]` — The radius of curvature of the bend.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidBeamDir,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetPipePressure2AF`

Sets the internal and external pipe pressure for the specified beam. This attribute
is only active for beam of type pipe.

**Syntax**

```c
long St7SetPipePressure2AF(long uID, long BeamNum, long
CaseNum, long Status, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `CaseNum` — The load case number.
- `Status` — Model a pipe with closed ends: btTrue or btFalse. An additional force component is assigned at the beam ends to account for the pressure acting on a close-ended pipe.
- `Doubles[0..1]` — A 2 element array describing the inner and outer radial pressures acting on the element surface respectively.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetPipeTemperature2OT`

Sets the internal and external pipe temperatures for the specified beam. This
attribute is only active for beams of type pipe.

**Syntax**

```c
long St7SetPipeTemperature2OT(long uID, long BeamNum, long
CaseNum, long Status, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `CaseNum` — The load case number.
- `Status` — Set the external temperature equal to the nodal temperatures at each end: btTrue or btFalse. In the case of unequal end temperatures the average temperature is used.
- `Doubles[0..1]` — A 2 element array describing the inner and outer surface temperatures respectively.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetBeamStringGroup1`

Assigns the specified beam to a string group. The string group attribute is only
active for truss elements and will ensure that the axial force in all members is
equal.

**Syntax**

```c
long St7SetBeamStringGroup1(long uID, long BeamNum, long
StringID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `StringID` — The ID number of the string group.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidStringID,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetBeamPreLoad1`

Sets the pre-load conditions for the specified beam.

**Syntax**

```c
long St7SetBeamPreLoad1(long uID, long BeamNum, long
CaseNum, long LoadType, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `CaseNum` — The load case number.
- `LoadType` — The type of pre-load, plBeamPreTension or plBeamPreStrain.
- `Doubles[0]` — The pre-load value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidPreLoadType,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetBeamTempGradient2`

Sets the temperature gradient for the specified beam.

**Syntax**

```c
long St7SetBeamTempGradient2(long uID, long BeamNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `CaseNum` — The load case number.
- `Doubles[0..1]` — A 2 element array describing the temperature gradient in the 1-axis and 2axis directions in the beam principal axis system, see Beam Local Coordinates.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetBeamCFL4ID`

Assigns point force data for the specified beam element. The force is applied
according to the beam principal axis system.

**Syntax**

```c
long St7SetBeamCFL4ID(long uID, long BeamNum, long CaseNum,
long ID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — Beam number.
- `CaseNum` — Load case number.
- `ID` — Point force ID number.
- `Doubles[0..3]` — [0..2] - The force components in the beam principal axis system. [3] - The relative length position at which the force is applied, see Beam Local Coordinates.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidBeamPosition,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetBeamCFG4ID`

Assigns point force data for the specified beam element. The force is applied
according to the Global Cartesian Coordinate system.

**Syntax**

```c
long St7SetBeamCFG4ID(long uID, long BeamNum, long CaseNum,
long ID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — Beam number.
- `CaseNum` — Load case number.
- `ID` — Point force ID number.
- `Doubles[0..3]` — [0..2] - The force components in the Global Cartesian Coordinate system. [3] - The relative length position at which the force is applied, see Beam Local Coordinates.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidBeamPosition,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetBeamCML4ID`

Assigns point moment data for the specified beam element. The moment is
applied according to the beam principal axis system.

**Syntax**

```c
long St7SetBeamCML4ID(long uID, long BeamNum, long CaseNum,
long ID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — Beam number.
- `CaseNum` — Load case number.
- `ID` — Point moment ID number.
- `Doubles[0..3]` — [0..2] - The moment components in the beam principal axis system. [3] - The relative length position at which the moment is applied, see Beam Local Coordinates.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidBeamPosition,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetBeamCMG4ID`

Assigns point moment data for the specified beam element. The moment is
applied according to the Global Cartesian Coordinate system.

**Syntax**

```c
long St7SetBeamCMG4ID(long uID, long BeamNum, long CaseNum,
long ID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — Beam number.
- `CaseNum` — Load case number.
- `ID` — Point moment ID number.
- `Doubles[0..3]` — [0..2] - The moment components in the Global Cartesian Coordinate system. [3] - The relative length position at which the moment is applied, see Beam Local Coordinates.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidBeamPosition,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetBeamDLL6ID`

Assigns distributed load data for the specified beam element. The force is
applied according to the beam principal axis system.

**Syntax**

```c
long St7SetBeamDLL6ID(long uID, long BeamNum, long BeamDir,
long CaseNum, long DLType, long ID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — Beam number.
- `BeamDir` — Principal axis direction, either 1, 2 or 3, see Beam Local Coordinates.
- `CaseNum` — Load case number.
- `DLType` — Distributed load type, one of kConstantDL, kLinearDL, kTriangularDL, kThreePoint0DL, kThreePoint1DL or kTrapezoidalDL.
- `ID` — Distributed load ID number.
- `Doubles[0..5]` — A 6 element array describing the distributed load. See Beam Distribution Types for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidBeamDir,
ERR7_InvalidBeamLoadType, ERR7_InvalidBeamPosition,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetBeamDML6ID`

Assigns distributed moment data for the specified beam element. The moment is
applied according to the beam principal axis system.

**Syntax**

```c
long St7SetBeamDML6ID(long uID, long BeamNum, long BeamDir,
long CaseNum, long DLType, long ID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — Beam number.
- `BeamDir` — Principal axis direction, one of 1,2 or 3, see Beam Local Coordinates.
- `CaseNum` — Load case number.
- `DLType` — Distributed load type, one of kConstantDL, kLinearDL, kTriangularDL, kThreePoint0DL, kThreePoint1DL or kTrapezoidalDL.
- `ID` — Distributed moment ID number.
- `Doubles[0..5]` — A 6 element array describing the distributed moment. See Beam Distribution Types for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidBeamDir,
ERR7_InvalidBeamLoadType, ERR7_InvalidBeamPosition,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetBeamDLG6ID`

Assigns distributed load data for the specified beam element. The force is
applied according to the Global Cartesian Coordinate system.

**Syntax**

```c
long St7SetBeamDLG6ID(long uID, long BeamNum, long BeamDir,
long ProjectFlag, long CaseNum, long DLType, long ID,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — Beam number.
- `BeamDir` — Global axis direction, one of 1, 2 or 3, see Beam Local Coordinates.
- `ProjectFlag` — btTrue or btFalse.
- `CaseNum` — Load case number.
- `DLType` — Distributed load type, one of kConstantDL, kLinearDL, kTriangularDL, kThreePoint0DL, kThreePoint1DL or kTrapezoidalDL.
- `ID` — Distributed load ID number.
- `Doubles[0..5]` — A 6 element array describing the distributed load. See Beam Distribution Types for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidBeamDir,
ERR7_InvalidBeamLoadType, ERR7_InvalidBeamPosition,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetBeamNSMass10ID`

Assigns non-structural mass properties for the specified beam.

**Syntax**

```c
long St7SetBeamNSMass10ID(long uID, long BeamNum, long
CaseNum, long DLType, long ID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `CaseNum` — The load case number.
- `DLType` — Distributed mass type, one of kConstantDL, kLinearDL, kTriangularDL, kThreePoint0DL, kThreePoint1DL or kTrapezoidalDL.
- `ID` — The mass distribution ID number.
- `Doubles[0..9]` — [0..6] - The distributed mass parameters. See Beam Distribution Types for additional information. [7..9] - Offset vectors according to the UCS axis system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidBeamLoadType,
ERR7_InvalidBeamPosition, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidLoadID, ERR7_InvalidUCSID,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetBeamConvection2`

Sets the thermal convection coefficient and ambient temperature for the
specified beam. The convection is assumed to occur uniformly over the beam
cross-section.

**Syntax**

```c
long St7SetBeamConvection2(long uID, long BeamNum, long
BeamEnd, long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `BeamEnd` — The beam end number, see Beam Local Coordinates.
- `CaseNum` — The load case number.
- `Doubles[0..1]` — [0] - Convection coefficient. [1] - Ambient temperature.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidBeamEnd,
ERR7_InvalidEntity, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidLoadID, ERR7_InvalidUCSID,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetBeamConvectionTables`

Specifies the tables to be associated with thermal convection properties for the
specified beam. A Factor vs Temperature table may apply to the convection
coefficient and Factor vs Time tables may apply to both the convection
coefficient and ambient temperature.

**Syntax**

```c
long St7SetBeamConvectionTables(long uID, long BeamNum,
long BeamEnd, long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `BeamEnd` — The beam end number, see Beam Local Coordinates.
- `CaseNum` — The load case number.
- `Tables[0..2]` — [0] - Factor vs Time table ID associated with the ambient temperature, use zero for none. [1] - Factor vs Temperature table ID associated with the convection coefficient, use zero for none. [2] - Factor vs Time table ID associated with the convection coefficient, use zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidTableType,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_TableDoesNotExist
```


---

### `St7SetBeamRadiation2`

Sets the thermal radiation coefficient and ambient temperature for the specified
beam.

**Syntax**

```c
long St7SetBeamRadiation2(long uID, long BeamNum, long
BeamEnd, long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `BeamEnd` — The beam end number, see Beam Local Coordinates.
- `CaseNum` — The load case number.
- `Doubles[0..1]` — [0] - Radiation coefficient. [1] - Ambient temperature.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidBeamEnd,
ERR7_InvalidEntity, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidLoadID, ERR7_InvalidUCSID,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetBeamRadiationTables`

Specifies the tables associated with the thermal radiation properties of the
specified beam. A Factor vs Temperature table may apply to the radiation
coefficient and Factor vs Time tables may apply to both the radiation coefficient
and ambient temperature.

**Syntax**

```c
long St7SetBeamRadiationTables(long uID, long BeamNum, long
BeamEnd, long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `BeamEnd` — The beam end number, see Beam Local Coordinates.
- `CaseNum` — The load case number.
- `Tables[0..2]` — [0] - Factor vs Time table ID associated with the ambient temperature, use zero for none. [1] - Factor vs Temperature table ID associated with the radiation coefficient, use zero for none. [2] - Factor vs Time table ID associated with the radiation coefficient, use zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidBeamEnd,
ERR7_InvalidEntity, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidLoadID,
ERR7_InvalidTableType, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7SetBeamFlux1`

Sets the heat flux for the specified beam.

**Syntax**

```c
long St7SetBeamFlux1(long uID, long BeamNum, long BeamEnd,
long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `BeamEnd` — The beam end number, see Beam Local Coordinates.
- `CaseNum` — The load case number.
- `Doubles[0]` — The heat flux through the beam.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidBeamEnd,
ERR7_InvalidEntity, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidLoadID, ERR7_InvalidUCSID,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetBeamFluxTables`

Specifies the tables to be associated with the heat flux for the specified beam.
Both a Factor vs Time and Factor vs Temperature table can be assigned.

**Syntax**

```c
long St7SetBeamFluxTables(long uID, long BeamNum, long
BeamEnd, long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `BeamEnd` — The beam end number, see Beam Local Coordinates.
- `CaseNum` — The load case number.
- `Tables[0..1]` — [0] - Factor vs Time table ID associated with the heat flux, use zero for none. [1] - Factor vs Temperature table ID associated with the heat flux, use zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidBeamEnd,
ERR7_InvalidEntity, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidLoadID,
ERR7_InvalidTableType, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7SetBeamHeatSource1`

Sets the thermal heat source value for the specified beam.

**Syntax**

```c
long St7SetBeamHeatSource1(long uID, long BeamNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `CaseNum` — The load case number.
- `Doubles[0]` — The thermal heat source value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetBeamHeatSourceTables`

Specifies the tables to be associated with the thermal heat source for the
specified beam. Both a Factor vs Time and Factor vs Temperature table can be
assigned.

**Syntax**

```c
long St7SetBeamHeatSourceTables(long uID, long BeamNum,
long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `CaseNum` — The load case number.
- `Tables[0..1]` — [0] - Factor vs Time table ID associated with the beam heat source, use zero for none. [1] - Factor vs Temperature table ID associated with the beam heat source, use zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,


ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidTableType,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_TableDoesNotExist
```


---

### `St7SetBeamResponse`

Assigns a response variable to the specified beam. Response variables are only
used by the Load Influence Solver.

**Syntax**

```c
long St7SetBeamResponse(long uID, long BeamNum, long
BeamEnd, long CaseNum, long* Status)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `BeamEnd` — The beam end number.
- `CaseNum` — The load case number.
- `Status[0..5]` — [ipBeamResponseSF1] - Shear force in the principal 1-axis direction, either btTrue or btFalse. [ipBeamResponseSF2] - Shear force in the principal 2-axis direction, either btTrue or btFalse. [ipBeamResponseAxial] - Axial force, either btTrue or btFalse. [ipBeamResponseBM1] - Bending moment in the principal 1-axis direction, either btTrue or btFalse. [ipBeamResponseBM2] - Bending moment in the principal 2-axis direction, either btTrue or btFalse. [ipBeamResponseTorque] Torque, either btTrue or btFalse.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidBeamEnd,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_InvalidResponseType,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetBeamCreepLoadingAge1`

Sets the creep loading age for the specified beam. This attribute is only used
when performing a creep analysis using the Quasi-Static Solver.

**Syntax**

```c
long St7SetBeamCreepLoadingAge1(long uID, long BeamNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `Doubles[0]` — The creep loading age in seconds.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```
