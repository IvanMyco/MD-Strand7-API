---
title: "Beam Attributes – Get"
source: "Strand7 R246 API Manual"
pages: 272–305
---

# Beam Attributes – Get

---

### `St7SetBeamEndAttachment1`

Sets the attachment properties for the specified beam. Attachment attributes
can be used to generate attachment links using the St7ToolAttachParts function.

**Syntax**

```c
long St7SetBeamEndAttachment1(long uID, long BeamNum, long
BeamEnd, long AttachType, long ConnectType, long
PropNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — Beam number.
- `BeamEnd` — Beam end number, either 1 or 2.
- `AttachType` — Attachment type, one of alDirect, alRigid or alFlexible.
- `ConnectType` — Attachment sub-type, either alMoment or alPinned.
- `PropNum` — Beam property number to be used for flexible type connections.
- `Doubles[0]` — The maximum distance within which the beam can be attached to another element using the attachment link.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidAttachmentType,
ERR7_InvalidBeamEnd, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetBeamID`

Returns the ID number for the specified beam.

**Syntax**

```c
long St7GetBeamID(long uID, long BeamNum, long* BeamID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number

**Output Parameters**

- `BeamID` — The beam ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamReferenceAngle1`

Returns the reference angle for the specified beam. This angle controls the local
rotation of the beam cross-section about the beam length, as per the beam
local axis system definition. See Beam Local Coordinates for further information.

**Syntax**

```c
long St7GetBeamReferenceAngle1(long uID, long BeamNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.

**Output Parameters**

- `Doubles[0]` — The reference angle used to align the beam principal axis system, see Beam Local Coordinates.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamConnectionUCS`

Returns the UCS used to define the connection element formulation for the
specified beam end. The translational and rotational stiffness components are
distributed according to the 123 axis convention in the specified UCS. This
attribute is only applicable to beams of connection element type.

**Syntax**

```c
long St7GetBeamConnectionUCS(long uID, long BeamNum, long
BeamEnd, long* UCSId)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `BeamEnd` — The beam end number.

**Output Parameters**

- `UCSId` — The UCS ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamTaper2`

Returns the taper properties for the specified beam.

**Syntax**

```c
long St7GetBeamTaper2(long uID, long BeamNum, long
TaperAxis, long* TaperType, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `TaperAxis` — The local beam axis to be tapered: axLocalX or axLocalY. See Beam Local Coordinates for further information.

**Output Parameters**

- `TaperType` — The type of beam taper; one of btTop, btSymm or btBottom.
- `Doubles[0..1]` — A 2 element array that specifies the taper ratios at either beam end. The dimension of the beam section is scaled by this value to calculate the tapered shape.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidTaperAxis, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetBeamOffset2`

Returns the offsets assigned to the specified beam.

**Syntax**

```c
long St7GetBeamOffset2(long uID, long BeamNum, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.

**Output Parameters**

- `Doubles[0..1]` — A 2 element array describing the beam offsets. Doubles[i-1] describes the offset in the ith principal axis direction, see Beam Local Coordinates.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamSupport2F`

Returns the elastic support value assigned to the specified beam.

**Syntax**

```c
long St7GetBeamSupport2F(long uID, long BeamNum, long
CaseNum, long* Status, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `CaseNum` — The freedom case number.

**Output Parameters**

- `Status` — Compression-only option: btTrue or btFalse.
- `Doubles[0..1]` — A 2 element array describing the elastic support conditions for the specified beam. Doubles[i-1] describes the elastic support in the ith principal axis direction, see Beam Local Coordinates.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamSectionFactor7`

Returns the section factors for the specified beam. These factors are used to
scale the beam section data contained in the associated beam property.

**Syntax**

```c
long St7GetBeamSectionFactor7(long uID, long BeamNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.

**Output Parameters**

- `Doubles[0..6]` — [0] - 1-axis shear stiffness factor. [1] - 2-axis shear stiffness factor. [2] - Axial stiffness factor. [3] - 1-axis bending stiffness factor. [4] - 2-axis bending stiffness factor. [5] - Torsional stiffness factor. [6] - Mass factor.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamTRelease3`

Returns the translational end release conditions assigned to the specified beam.

**Syntax**

```c
long St7GetBeamTRelease3(long uID, long BeamNum, long
BeamEnd, long* Status, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `BeamEnd` — The beam end identifier, either 1 or 2.

**Output Parameters**

- `Status[0..2]` — Status[i-1] describes the release conditions of the specified beam end for the ith principal axis direction, see Beam Local Coordinates – one of kBeamEndRelReleased, kBeamEndRelFixed or kBeamEndRelPartial.
- `Doubles[0..2]` — A 3 element array containing the partial stiffnesses to be used in the case of partial end release conditions.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamRRelease3`

Returns the rotational end release conditions assigned to the specified beam.

**Syntax**

```c
long St7GetBeamRRelease3(long uID, long BeamNum, long
BeamEnd, long* Status, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `BeamEnd` — The beam end identifier, either 1 or 2.

**Output Parameters**

- `Status[0..2]` — Status[i-1] describes the release conditions of the specified beam end for the ith principal axis direction, see Beam Local Coordinates – one of kBeamEndRelReleased, kBeamEndRelFixed or kBeamEndRelPartial.
- `Doubles[0..2]` — A 3 element array containing the partial stiffnesses to be used in the case of partial end release conditions.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamCableFreeLength1`

Returns the free cable length for the specified beam. This is the unstressed cable
length and is only active for beam of type cable.

**Syntax**

```c
long St7GetBeamCableFreeLength1(long uID, long BeamNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.

**Output Parameters**

- `Doubles[0]` — The free cable length.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamRadius1`

Returns the bend radius for the specified beam. This attribute si only active for
beams of type pipe.

**Syntax**

```c
long St7GetBeamRadius1(long uID, long BeamNum, long*
BeamDir, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.

**Output Parameters**

- `BeamDir` — The axis of the bend: axPrincipal1 or axPrincipal2. The beam will be bent in the axis direction specified, not about the axis, see Beam Local Coordinates.
- `Doubles[0]` — The radius of curvature of the bend.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPipePressure2AF`

Returns the internal and external pressures applied to the specified beam. This
attribute is only active for beams of type pipe.

**Syntax**

```c
long St7GetPipePressure2AF(long uID, long BeamNum, long
CaseNum, long* Status, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `CaseNum` — The load case number.

**Output Parameters**

- `Status` — Model a pipe with closed ends: btTrue or btFalse. An additional force component is assigned at the beam ends to account for the pressure acting on a close-ended pipe.
- `Doubles[0..1]` — A 2 element array describing the inner and outer radial pressures acting on the element surface respectively.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPipeTemperature2OT`

Returns the internal and external temperatures applied to the specified beam.
This attribute of only active for beams of type pipe.

**Syntax**

```c
long St7GetPipeTemperature2OT(long uID, long BeamNum, long
CaseNum, long* Status, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `CaseNum` — The load case number.

**Output Parameters**

- `Status` — Set the external temperature equal to the nodal temperatures at each end: btTrue or btFalse. In the case of unequal end temperatures the average temperature is used.
- `Doubles[0..1]` — A 2 element array describing the inner and outer surface temperatures respectively.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamStringGroup1`

Returns the ID number of the string group the specified beam is assigned to. The
string group attribute is only active for truss elements and will ensure that the axial
force in all members is equal.

**Syntax**

```c
long St7GetBeamStringGroup1(long uID, long BeamNum, long*
StringID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.

**Output Parameters**

- `StringID` — The ID number of the string group.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamPreLoad1`

Returns the pre-load assigned to the specified beam.

**Syntax**

```c
long St7GetBeamPreLoad1(long uID, long BeamNum, long
CaseNum, long* LoadType, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `CaseNum` — The load case number.

**Output Parameters**

- `LoadType` — The type of pre-load: plBeamPreTension or plBeamPreStrain.
- `Doubles[0]` — The pre-load value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,


ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamTempGradient2`

Returns the temperature gradients assigned to the specified beam.

**Syntax**

```c
long St7GetBeamTempGradient2(long uID, long BeamNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `CaseNum` — The load case number.

**Output Parameters**

- `Doubles[0..1]` — A 2 element array describing the temperature gradient in the 1-axis and 2axis directions in the beam principal axis system, see Beam Local Coordinates.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamCFL4ID`

Returns point force data assigned to the specified beam element. The force is
applied according to the beam principal axis system.

**Syntax**

```c
long St7GetBeamCFL4ID(long uID, long BeamNum, long CaseNum,
long ID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — Beam number.
- `CaseNum` — Load case number.
- `ID` — Point force ID number.

**Output Parameters**

- `Doubles[0..3]` — [0..2] - The force components in the beam principal axis system. [3] - The relative length position at which the force is applied, see Beam Local Coordinates.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamCFG4ID`

Returns point force data assigned to the specified beam element. The force is
applied according to the Global Cartesian Coordinate axis system.

**Syntax**

```c
long St7GetBeamCFG4ID(long uID, long BeamNum, long CaseNum,
long ID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — Beam number.
- `CaseNum` — Load case number.
- `ID` — Point force ID number.

**Output Parameters**

- `Doubles[0..3]` — [0..2] - The force components in the Global Cartesian Coordinate system. [3] - The relative length position at which the force is applied, see Beam Local Coordinates.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamCML4ID`

Returns point moment data assigned to the specified beam element. The
moment is applied according to the beam principal axis system.

**Syntax**

```c
long St7GetBeamCML4ID(long uID, long BeamNum, long CaseNum,
long ID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — Beam number.
- `CaseNum` — Load case number.
- `ID` — Point moment ID number.

**Output Parameters**

- `Doubles[0..3]` — [0..2] - The moment components in the beam principal axis system. [3] - The relative length position at which the moment is applied, see Beam Local Coordinates.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamCMG4ID`

Returns point moment data assigned to the specified beam element. The
moment is applied according to the Global Cartesian Coordinate system.

**Syntax**

```c
long St7GetBeamCMG4ID(long uID, long BeamNum, long CaseNum,
long ID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — Beam number.
- `CaseNum` — Load case number.
- `ID` — Point moment ID number.

**Output Parameters**

- `Doubles[0..3]` — [0..2] - The moment components in the Global Cartesian Coordinate system. [3] - The relative length position at which the moment is applied, see Beam Local Coordinates.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamDLL6ID`

Returns distributed load data assigned to the specified beam element. The force
is applied according to the beam principal axis system.

**Syntax**

```c
long St7GetBeamDLL6ID(long uID, long BeamNum, long BeamDir,
long CaseNum, long ID, long* DLType, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — Beam number.
- `BeamDir` — Principal axis direction, one of 1, 2 or 3, see Beam Local Coordinates.
- `CaseNum` — Load case number.
- `ID` — Distributed load ID number.

**Output Parameters**

- `DLType` — Distributed load type, one of kConstantDL, kLinearDL, kTriangularDL, kThreePoint0DL, kThreePoint1DL or kTrapezoidalDL.
- `Doubles[0..5]` — A 6 element array describing the distributed load. See Beam Distribution Types for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,


ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamDML6ID`

Returns distributed moment data assigned to the specified beam element. The
moment is applied according to the beam principal axis system.

**Syntax**

```c
long St7GetBeamDML6ID(long uID, long BeamNum, long BeamDir,
long CaseNum, long ID, long* DLType, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — Beam number.
- `BeamDir` — Principal axis direction, one of 1, 2 or 3, see Beam Local Coordinates.
- `CaseNum` — Load case number.
- `ID` — Distributed moment ID number.

**Output Parameters**

- `DLType` — Distributed load type, one of kConstantDL, kLinearDL, kTriangularDL, kThreePoint0DL, kThreePoint1DL or kTrapezoidalDL.
- `Doubles[0..5]` — A 6 element array describing the distributed moment. See Beam Distribution Types for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamDLG6ID`

Returns distributed load data assigned to the specified beam element. The force
is applied according to the Global Cartesian Coordinate system.

**Syntax**

```c
long St7GetBeamDLG6ID(long uID, long BeamNum, long BeamDir,
long CaseNum, long ID, long* ProjectFlag, long* DLType,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — Beam number.
- `BeamDir` — Global axis direction, one of 1, 2 or 3, see Beam Local Coordinates.
- `CaseNum` — Load case number.
- `ID` — Distributed load ID number.

**Output Parameters**

- `ProjectFlag` — btTrue or btFalse.
- `DLType` — Distributed load type, one of kConstantDL, kLinearDL, kTriangularDL, kThreePoint0DL, kThreePoint1DL or kTrapezoidalDL.
- `Doubles[0..5]` — A 6 element array describing the distributed load. See Beam Distribution Types for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamNSMass10ID`

Returns non-structural mass properties assigned to the specified beam element.

**Syntax**

```c
long St7GetBeamNSMass10ID(long uID, long BeamNum, long
CaseNum, long ID, long* DLType, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `CaseNum` — The load case number.
- `ID` — The mass distribution ID number.

**Output Parameters**

- `DLType` — Distributed mass type, one of kConstantDL, kLinearDL, kTriangularDL, kThreePoint0DL, kThreePoint1DL or kTrapezoidalDL.
- `Doubles[0..9]` — [0..6] - The distributed mass parameters. See Beam Distribution Types for additional information. [7..9] - Offset vectors according to the UCS axis system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamConvection2`

Returns the thermal convection coefficient and ambient temperature assigned
to the specified beam. The convection is assumed to occur uniformly over the
beam cross-section.

**Syntax**

```c
long St7GetBeamConvection2(long uID, long BeamNum, long
BeamEnd, long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `BeamEnd` — The beam end number, see Beam Local Coordinates.
- `CaseNum` — The load case number.

**Output Parameters**

- `Doubles[0..1]` — [0] - Convection coefficient. [1] - Ambient temperature.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamConvectionTables`

Returns the tables associated with thermal convection properties for the
specified beam. A Factor vs Temperature table may apply to the convection
coefficient and Factor vs Time tables may apply to both the convection
coefficient and ambient temperature.

**Syntax**

```c
long St7GetBeamConvectionTables(long uID, long BeamNum,
long BeamEnd, long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `BeamEnd` — The beam end number, see Beam Local Coordinates.
- `CaseNum` — The load case number.

**Output Parameters**

- `Tables[0..2]` — [0] - Factor vs Time table ID associated with the ambient temperature, use zero for none. [1] - Factor vs Temperature table ID associated with the convection coefficient, use zero for none. [2] - Factor vs Time table ID associated with the convection coefficient, use zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamRadiation2`

Returns the thermal radiation coefficient and ambient temperature assigned to
the specified beam.

**Syntax**

```c
long St7GetBeamRadiation2(long uID, long BeamNum, long
BeamEnd, long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `BeamEnd` — The beam end number, see Beam Local Coordinates.
- `CaseNum` — The load case number.

**Output Parameters**

- `Doubles[0..1]` — [0] - Radiation coefficient. [1] - Ambient temperature.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamRadiationTables`

Returns the tables associated with the thermal radiation properties of the
specified beam. A Factor vs Temperature table may apply to the radiation
coefficient and Factor vs Time tables may apply to both the radiation coefficient
and ambient temperature.

**Syntax**

```c
long St7GetBeamRadiationTables(long uID, long BeamNum, long
BeamEnd, long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `BeamEnd` — The beam end number, see Beam Local Coordinates.
- `CaseNum` — The load case number.

**Output Parameters**

- `Tables[0..2]` — [0] - Factor vs Time table ID associated with the ambient temperature, use zero for none. [1] - Factor vs Temperature table ID associated with the radiation coefficient, use zero for none. [2] - Factor vs Time table ID associated with the radiation coefficient, use zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamFlux1`

Returns the heat flux assigned to the specified beam.

**Syntax**

```c
long St7GetBeamFlux1(long uID, long BeamNum, long BeamEnd,
long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `BeamEnd` — The beam end number, see Beam Local Coordinates.
- `CaseNum` — The load case number.

**Output Parameters**

- `Doubles[0]` — The heat flux through the beam.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamFluxTables`

Returns the tables associated with the heat flux for the specified beam. Both a
Factor vs Time and Factor vs Temperature table may be assigned.

**Syntax**

```c
long St7GetBeamFluxTables(long uID, long BeamNum, long
BeamEnd, long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `BeamEnd` — The beam end number, see Beam Local Coordinates.
- `CaseNum` — The load case number.

**Output Parameters**

- `Tables[0..1]` — [0] - Factor vs Time table ID associated with the heat flux, use zero for none. [1] - Factor vs Temperature table ID associated with the heat flux, use zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamHeatSource1`

Returns the heat source value assigned to the specified beam.

**Syntax**

```c
long St7GetBeamHeatSource1(long uID, long BeamNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `CaseNum` — The load case number.

**Output Parameters**

- `Doubles[0]` — The heat source value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamHeatSourceTables`

Returns the tables associated with the heat source for the specified beam. Both a
Factor vs Time and Factor vs Temperature table may be assigned.

**Syntax**

```c
long St7GetBeamHeatSourceTables(long uID, long BeamNum,
long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `CaseNum` — The load case number.

**Output Parameters**

- `Tables[0..1]` — [0] - Factor vs Time table ID associated with the beam heat source, use zero for none. [1] - Factor vs Temperature table ID associated with the beam heat source, use zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamResponse`

Returns the response variable assigned for the specified beam. Response
variables are only used by the Load Influence Solver.

**Syntax**

```c
long St7GetBeamResponse(long uID, long BeamNum, long
BeamEnd, long CaseNum, long* Status)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.
- `BeamEnd` — The beam end number, either 1 or 2.
- `CaseNum` — The load case number.

**Output Parameters**

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

### `St7GetBeamCreepLoadingAge1`

Returns the creep loading age for the specified beam. This attribute is only used
when performing a creep analysis using the Quasi-Static Solver.

**Syntax**

```c
long St7GetBeamCreepLoadingAge1(long uID, long BeamNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — The beam number.

**Output Parameters**

- `Doubles[0]` — The creep loading age in seconds.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBeamEndAttachment1`

Returns the attachment properties for the specified beam. This attribute can be
used to generate attachment links using the St7ToolAttachParts function.

**Syntax**

```c
long St7GetBeamEndAttachment1(long uID, long BeamNum, long
BeamEnd, long* AttachType, long* ConnectType, long*
PropNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — Beam number.
- `BeamEnd` — Beam end number.

**Output Parameters**

- `AttachType` — Attachment type, one of alDirect, alRigid or alFlexible.
- `ConnectType` — Attachment sub-type, either alMoment or alPinned.
- `PropNum` — Beam property number to be used for flexible type connections.
- `Doubles[0]` — The maximum distance within which the beam can be attached to another element using the attachment link.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
```
