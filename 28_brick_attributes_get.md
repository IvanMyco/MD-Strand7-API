---
title: "Brick Attributes – Get"
source: "Strand7 R246 API Manual"
pages: 396–416
---

# Brick Attributes – Get

Syntax

long St7SetBrickFaceAttachment1(long uID, long BrickNum,
long FaceNum, long AttachType, long ConnectType, long
PropNum, double* Doubles)
Input Parameters

uID
Strand7 model file ID number.

BrickNum
Brick number.

FaceNum
Local face number. See Brick Local Coordinates for additional information.

AttachType
Attachment type, one of alDirect, alRigid or alFlexible.

ConnectType
Attachment sub-type, either alMoment or alPinned.

PropNum
Beam property number used for flexible attachment types.

Doubles[0]
The maximum distance within which the brick face can be connected to
another element using the attachment link.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen


---

### `St7GetBrickID`

Returns the ID number assigned to the specified brick.

**Syntax**

```c
long St7GetBrickID(long uID, long BrickNum, long* BrickID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.

**Output Parameters**

- `BrickID` — ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBrickLocalAxes1`

Returns the UCS used as the local axis system for the specified brick.

**Syntax**

```c
long St7GetBrickLocalAxes1(long uID, long BrickNum, long*
UCSId)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.

**Output Parameters**

- `UCSId` — UCS ID number.

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

### `St7GetBrickSupport1F`

Returns the elastic support assigned to the specified brick face. The support acts
normal to the plane of the face and is constant over the surface.

**Syntax**

```c
long St7GetBrickSupport1F(long uID, long BrickNum, long
FaceNum, long CaseNum, long* Status, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `FaceNum` — Local face number. See Brick Local Coordinates for additional information.
- `CaseNum` — Load case number.

**Output Parameters**

- `Status` — Compression-only support, either btTrue or btFalse.
- `Doubles[0]` — Elastic support value.

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

### `St7GetBrickPreLoad3`

Returns the pre-load conditions assigned to the specified brick. The pre-loads are
applied according to the orientation of the brick local axis system.

**Syntax**

```c
long St7GetBrickPreLoad3(long uID, long BrickNum, long
CaseNum, long* LoadType, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `CaseNum` — Load case number.

**Output Parameters**

- `LoadType` — plBrickPreStress or plBrickPreStrain.
- `Doubles[0..2]` — A 3 element array describing the pre-load magnitudes according to the orientation of the local brick axis system.

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

### `St7GetBrickPointForce6`

Returns the point force assigned to the specified brick face.

**Syntax**

```c
long St7GetBrickPointForce6(long uID, long BrickNum, long
FaceNum, long CaseNum, long Position, long ID, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `FaceNum` — Local face number. See Brick Local Coordinates for additional information.
- `CaseNum` — Load case number.
- `Position` — Position identifier, either axUCS or axLocal.
- `ID` — Point force ID number.

**Output Parameters**

- `Doubles[0..5]` — [0..2] - Components of applied force in the Global Cartesian coordinate system. axUCS: [3..5] - XYZ position of applied force in the Global Cartesian coordinate system. axLocal: [3..4] - UV position of applied force in the local element coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidBrickFace,
ERR7_InvalidEntity, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidLoadID,
ERR7_InvalidPositionType, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetBrickNormalPressure1`

Returns the pressure assigned to the specified brick face. The pressure acts into
the element, normal to the plane of the face and is constant over the surface.

**Syntax**

```c
long St7GetBrickNormalPressure1(long uID, long BrickNum,
long FaceNum, long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `FaceNum` — Local face number. See Brick Local Coordinates for additional information.
- `CaseNum` — Load case number.

**Output Parameters**

- `Doubles[0]` — Normal pressure value.

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

### `St7GetBrickGlobalPressure3`

Returns the pressure assigned to the specified brick face in the Global Cartesian
Coordinate system. The pressure is constant over the face surface.

**Syntax**

```c
long St7GetBrickGlobalPressure3(long uID, long BrickNum,
long FaceNum, long CaseNum, long* ProjectFlag, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `FaceNum` — Local face number. See Brick Local Coordinates for additional information.
- `CaseNum` — Load case number.

**Output Parameters**

- `ProjectFlag` — Either btTrue or btFalse to project the global pressure components.
- `Doubles[0..2]` — A 3 element array describing the XYZ components of the applied pressure in the Global Cartesian Coordinate system.

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

### `St7GetBrickShear2`

Returns the shear stress assigned to the specified brick face. The shear stress acts
in the plane of the face and is constant over the surface.

**Syntax**

```c
long St7GetBrickShear2(long uID, long BrickNum, long
FaceNum, long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `FaceNum` — Local face number. See Brick Local Coordinates for additional information.
- `CaseNum` — Load case number.

**Output Parameters**

- `Doubles[0..1]` — A 2 element array describing the shear stress components in the local face XY axis system.

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

### `St7GetBrickNSMass5`

Returns the non-structural mass assigned to the specified brick.

**Syntax**

```c
long St7GetBrickNSMass5(long uID, long BrickNum, long
FaceNum, long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `FaceNum` — Local face number. See Brick Local Coordinates for additional information.
- `CaseNum` — Load case number.

**Output Parameters**

- `Doubles[0..5]` — [0] - Non-structural mass for the specified plate. [1] - Dynamic factor for the specified plate. This factor is used to scale the non-structural mass when performing dynamic analyses. [2..5] - A 3 element array describing the offset in the XYZ Global Cartesian coordinate system.

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

### `St7GetBrickConvection2`

Returns the thermal convection coefficient and ambient temperature assigned
to the specified brick face. This attribute is only used when performing heat
transfer analysis.

**Syntax**

```c
long St7GetBrickConvection2(long uID, long BrickNum, long
FaceNum, long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `FaceNum` — Local face number. See Brick Local Coordinates for additional information.
- `CaseNum` — Load case number.

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

### `St7GetBrickConvectionTables`

Returns the tables associated with thermal convection properties assigned to the
specified brick face. A Factor vs Temperature table may apply to the convection
coefficient and Factor vs Time tables may apply to both the convection
coefficient and ambient temperature.

**Syntax**

```c
long St7GetBrickConvectionTables(long uID, long BrickNum,
long FaceNum, long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `FaceNum` — Local face number. See Brick Local Coordinates for additional information.
- `CaseNum` — Load case number.

**Output Parameters**

- `Tables[0..2]` — [0] - Factor vs Time table ID associated with the ambient temperature, zero for none. [1] - Factor vs Temperature table ID associated with the convection coefficient, zero for none. [2] - Factor vs Time table ID associated with the convection coefficient, zero for none.

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

### `St7GetBrickRadiation2`

Returns the thermal radiation coefficient and ambient temperature assigned to
the specified brick face.

**Syntax**

```c
long St7GetBrickRadiation2(long uID, long BrickNum, long
FaceNum, long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `FaceNum` — Local face number. See Brick Local Coordinates for additional information.
- `CaseNum` — Load case number.

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

### `St7GetBrickRadiationTables`

Returns the tables associated with the thermal radiation properties assigned to a
specified brick face. A Factor vs Temperature table may apply to the radiation
coefficient and Factor vs Time tables may apply to both the radiation coefficient
and ambient temperature.

**Syntax**

```c
long St7GetBrickRadiationTables(long uID, long BrickNum,
long FaceNum, long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `FaceNum` — Local face number. See Brick Local Coordinates for additional information.
- `CaseNum` — Load case number.

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

### `St7GetBrickFlux1`

Returns the heat flux assigned to the specified brick face.

**Syntax**

```c
long St7GetBrickFlux1(long uID, long BrickNum, long FaceNum,
long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `FaceNum` — Local face number. See Brick Local Coordinates for additional information.
- `CaseNum` — Load case number.

**Output Parameters**

- `Doubles[0]` — The heat flux through the brick face.

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

### `St7GetBrickFluxTables`

Returns the tables associated with the heat flux assigned to the specified brick
face. Both Factor vs Time and Factor vs Temperature tables may be assigned. This
attribute is only used when performing heat transfer analysis.

**Syntax**

```c
long St7GetBrickFluxTables(long uID, long BrickNum, long
FaceNum, long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `FaceNum` — Local face number. See Brick Local Coordinates for additional information.
- `CaseNum` — Load case number.

**Output Parameters**

- `Tables[0..1]` — [0] - Factor vs Time table ID associated with the heat flux, zero for none. [1] - Factor vs Temperature table ID associated with the heat flux, zero for none.

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

### `St7GetBrickHeatSource1`

Returns the thermal heat source assigned to the specified brick. This attribute is
only used when performing heat transfer analysis.

**Syntax**

```c
long St7GetBrickHeatSource1(long uID, long BrickNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `CaseNum` — Load case number.

**Output Parameters**

- `Doubles[0]` — Thermal heat source value.

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

### `St7GetBrickHeatSourceTables`

Returns the tables associated with the thermal heat source assigned to the
specified brick. This attribute is only used when performing heat transfer analysis.

**Syntax**

```c
long St7GetBrickHeatSourceTables(long uID, long BrickNum,
long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `CaseNum` — Load case number.

**Output Parameters**

- `Tables[0..1]` — [0] - Factor vs Time table ID associated with the heat source, use zero for none. [1] - Factor vs Temperature table ID associated with the heat source, use zero for none.

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

### `St7GetBrickSoilStress2`

Returns the in-situ soil stress assigned to the specified brick. This attribute is only
active for bricks of property type soil.

**Syntax**

```c
long St7GetBrickSoilStress2(long uID, long BrickNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `CaseNum` — Load case number.

**Output Parameters**

- `Doubles[0..1]` — A 2 element array containing the initial vertical stress and the horizontal stress ratio.

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

### `St7GetBrickSoilRatio2`

Returns the in-situ soil ratios for the specified brick. This attribute is only active for
bricks of property type soil.

**Syntax**

```c
long St7GetBrickSoilRatio2(long uID, long BrickNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `CaseNum` — Load case number.

**Output Parameters**

- `Doubles[0..1]` — A 2 element array containing the overconsolidation ratio and the initial void ratio.

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

### `St7GetBrickResponse`

Returns the response variable assigned to the specified brick. Response variables
are only used by the Load Influence solver.

**Syntax**

```c
long St7GetBrickResponse(long uID, long BrickNum, long
CaseNum, long* UCSId, long* Status)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `CaseNum` — Load case number.

**Output Parameters**

- `UCSId` — UCS ID number.
- `Status[0..5]` — A 6 element array describing which stress components are flagged as response variables – lists the 11, 22, 33, 12, 23, 31 components in the 123 axis convention in the specified UCS.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidBeamEnd,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_InvalidResponseType,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetBrickCreepLoadingAge1`

Returns the creep loading age assigned to the specified brick. This attribute is
only used when performing creep analysis using the Quasi-Static solver.

**Syntax**

```c
long St7GetBrickCreepLoadingAge1(long uID, long BrickNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.

**Output Parameters**

- `Doubles[0]` — Creep loading age in seconds.

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

### `St7GetBrickFaceAttachment1`

Returns the attachment conditions assigned to the specified brick face.
Attachment attributes can be used to generate attachment links using the
St7ToolAttachParts function.

**Syntax**

```c
long St7GetBrickFaceAttachment1(long uID, long BrickNum,
long FaceNum, long* AttachType, long* ConnectType,
long* PropNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `FaceNum` — Local face number. See Brick Local Coordinates for additional information.

**Output Parameters**

- `AttachType` — Attachment type, one of alDirect, alRigid or alFlexible.
  ConnectType
