---
title: "Face Attributes – Get"
source: "Strand7 R246 API Manual"
pages: 482–495
---

# Face Attributes – Get

Syntax

long St7SetGeometryFaceAttachment1(long uID, long FaceNum,
long Surface, long AttachType, long ConnectType, long
PropNum, double* Doubles)
Input Parameters

uID
Strand7 model file ID number.

FaceNum
Face number.

Surface
Local plate surface, either psPlateZMinus or psPlateZPlus.

AttachType
Attachment type, one of alDirect, alRigid or alFlexible.

ConnectType
Attachment sub-type, either alMoment or alPinned.

PropNum
Beam property number used for flexible attachment types.

Doubles[0]
The maximum distance within which the face can be connected to another
element using the attachment link.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidAttachmentType,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidPlateSurface, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen


---

### `St7GetGeometryFaceProperty`

Returns the property assigned to the specified geometry face.

**Syntax**

```c
long St7GetGeometryFaceProperty(long uID, long FaceNum,
long* PropNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.

**Output Parameters**

- `PropNum` — Face property number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetGeometryFaceID`

Returns the ID number assigned to the specified geometry face.

**Syntax**

```c
long St7GetGeometryFaceID(long uID, long FaceNum, long*
FaceID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.

**Output Parameters**

- `FaceID` — Face ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetGeometryFaceOffset1`

Returns the offset assigned to the specified geometry face.

**Syntax**

```c
long St7GetGeometryFaceOffset1(long uID, long FaceNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.

**Output Parameters**

- `Doubles[0]` — Offset value.

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

### `St7GetGeometryFaceSupport1F`

Returns the elastic support condition assigned to the specified geometry face.

**Syntax**

```c
long St7GetGeometryFaceSupport1F(long uID, long FaceNum,
long CaseNum, long* Status, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
- `CaseNum` — Freedom case number.

**Output Parameters**

- `Status` — Compression-only flag, either btTrue or btFalse.
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

### `St7GetGeometryFaceTempGradient1`

Returns the temperature gradient assigned to the specified geometry face. This
attribute is only used when performing structural analysis.

**Syntax**

```c
long St7GetGeometryFaceTempGradient1(long uID, long FaceNum,
long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
- `CaseNum` — Load case number.

**Output Parameters**

- `Doubles[0]` — Temperature gradient.

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

### `St7GetGeometryFaceNormalPressure1`

Returns the normal pressure assigned to the specified geometry face.

**Syntax**

```c
long St7GetGeometryFaceNormalPressure1(long uID, long
FaceNum, long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
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

### `St7GetGeometryFaceGlobalPressure3`

Returns the XYZ pressure components assigned to the specified face in the
Global Cartesian Coordinate system.

**Syntax**

```c
long St7GetGeometryFaceGlobalPressure3(long uID, long
FaceNum, long CaseNum, long* ProjectFlag, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
- `CaseNum` — Load case number.

**Output Parameters**

- `ProjectFlag` — btTrue or btFalse.
- `Doubles[0..2]` — A 3 element array describing the XYZ pressure components in the Global Cartesian Coordinate system.

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

### `St7GetGeometryFaceNSMass5`

Returns the non-structural mass assigned to the specified geometry face.

**Syntax**

```c
long St7GetGeometryFaceNSMass5(long uID, long FaceNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
- `CaseNum` — Load case number.

**Output Parameters**

- `Doubles[0..4]` — [0] - Non-structural mass for the specified face. [1] - Dynamic factor for the specified face. This factor is used to scale the non-structural mass when performing dynamic analysis. [2..4] - A 3 element array describing the offset in the XYZ Cartesian coordinate system.

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

### `St7GetGeometryFaceConvection2`

Returns the thermal convection coefficient and ambient temperature assigned
to the specified geometry face. This attribute is only used when performing heat
transfer analysis.

**Syntax**

```c
long St7GetGeometryFaceConvection2(long uID, long FaceNum,
long CaseNum, long Surface, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
- `CaseNum` — Load case number.
- `Surface` — Local plate surface, either psPlateZMinus or psPlateZPlus.

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

### `St7GetGeometryFaceConvectionTables`

Returns the tables associated with the thermal convection properties assigned to
a specified geometry face. A Factor vs Temperature table may apply to the
convection coefficient and Factor vs Time tables may apply to both the
convection coefficient and ambient temperature.

**Syntax**

```c
long St7GetGeometryFaceConvectionTables(long uID, long
FaceNum, long CaseNum, long Surface, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
- `CaseNum` — Load case number.
- `Surface` — Local plate surface, either psPlateZMinus or psPlateZPlus.

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

### `St7GetGeometryFaceRadiation2`

Returns the thermal radiation coefficient and ambient temperature assigned to
the specified geometry face.

**Syntax**

```c
long St7GetGeometryFaceRadiation2(long uID, long FaceNum,
long CaseNum, long Surface, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
- `CaseNum` — Load case number.
- `Surface` — Local plate surface, psPlateZMinus or psPlateZPlus.

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

### `St7GetGeometryFaceRadiationTables`

Returns the tables associated with the thermal radiation properties assigned to a
specified geometry face. A Factor vs Temperature table may apply to the
radiation coefficient and Factor vs Time tables may apply to both the radiation
coefficient and ambient temperature.

**Syntax**

```c
long St7GetGeometryFaceRadiationTables(long uID, long
FaceNum, long CaseNum, long Surface, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
- `CaseNum` — Load case number.
- `Surface` — Local plate surface, psPlateZMinus or psPlateZPlus.

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

### `St7GetGeometryFaceHeatSource1`

Returns the thermal heat source assigned to the specified geometry face.

**Syntax**

```c
long St7GetGeometryFaceHeatSource1(long uID, long FaceNum,
long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
- `CaseNum` — Load case number.

**Output Parameters**

- `Doubles[0]` — Heat source value.

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

### `St7GetGeometryFaceHeatSourceTables`

Returns the tables associated with the thermal heat source assigned to the
specified geometry face. Both Factor vs Time and Factor vs Temperature tables
may be assigned. This attribute is only used when performing heat transfer
analysis.

**Syntax**

```c
long St7GetGeometryFaceHeatSourceTables(long uID, long
FaceNum, long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
- `CaseNum` — Load case number.

**Output Parameters**

- `Tables[0..1]` — [0] - Factor vs Time table ID associated with the thermal heat source, use zero for none. [1] - Factor vs Temperature table ID associated with the thermal heat source, use zero for none.

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

### `St7GetGeometryFaceAttachment1`

Returns the attachment conditions assigned to the specified geometry face.
Attachment attributes can be used to generate attachment links using the
St7ToolAttachParts function.

**Syntax**

```c
long St7GetGeometryFaceAttachment1(long uID, long FaceNum,
long Surface, long* AttachType, long* ConnectType,
long* PropNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
- `Surface` — Local plate surface, either psPlateZMinus or psPlateZPlus.

**Output Parameters**

- `AttachType` — Attachment type, one of alDirect, alRigid or alFlexible.
- `ConnectType` — Attachment sub-type, either alMoment or alPinned.
- `PropNum` — Beam property number used for flexible attachment types.
- `Doubles[0]` — The maximum distance within which the face can be connected to another element using the attachment link.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
```
