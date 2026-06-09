---
title: "Edge Attributes – Get"
source: "Strand7 R246 API Manual"
pages: 457–468
---

# Edge Attributes – Get

Edge Attributes – Set

ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen


---

### `St7GetGeometryEdgeType`

Returns the type assigned to the specified geometry edge.

**Syntax**

```c
long St7GetGeometryEdgeType(long uID, long EdgeNum, long*
EdgeType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.

**Output Parameters**

- `EdgeType` — Edge type, either etInterpolated or etNonInterpolated.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetGeometryEdgeRelease1`

Returns the edge release conditions assigned to the specified geometry edge.

**Syntax**

```c
long St7GetGeometryEdgeRelease1(long uID, long EdgeNum,
long* Status)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.

**Output Parameters**

- `Status` — btTrue or btFalse.

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

### `St7GetGeometryEdgeSupport1F`

Returns the elastic support assigned to the specified geometry edge.

**Syntax**

```c
long St7GetGeometryEdgeSupport1F(long uID, long EdgeNum,
long CaseNum, long* Status, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.
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

### `St7GetGeometryEdgePressure1`

Returns the edge pressure assigned to the specified geometry edge.

**Syntax**

```c
long St7GetGeometryEdgePressure1(long uID, long EdgeNum,
long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.
- `CaseNum` — Load case number.

**Output Parameters**

- `Doubles[0]` — Edge pressure value.

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

### `St7GetGeometryEdgeShear1`

Returns the shear stress assigned to the specified geometry edge.

**Syntax**

```c
long St7GetGeometryEdgeShear1(long uID, long EdgeNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.
- `CaseNum` — Load case number.

**Output Parameters**

- `Doubles[0]` — Shear stress value.

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

### `St7GetGeometryEdgeNormalShear1`

Returns the normal shear stress assigned to the specified geometry edge.

**Syntax**

```c
long St7GetGeometryEdgeNormalShear1(long uID, long EdgeNum,
long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.
- `CaseNum` — Load case number.

**Output Parameters**

- `Doubles[0]` — Normal shear stress value.

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

### `St7GetGeometryEdgeConvection2`

Returns the thermal convection coefficient and ambient temperature assigned
to the specified geometry edge. This attribute is only used when performing heat
transfer analysis.

**Syntax**

```c
long St7GetGeometryEdgeConvection2(long uID, long EdgeNum,
long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.
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

### `St7GetGeometryEdgeConvectionTables`

Returns the tables associated with the thermal convection properties assigned to
a specified geometry edge. A Factor vs Temperature table may apply to the
convection coefficient and Factor vs Time tables may apply to both the
convection coefficient and ambient temperature.

**Syntax**

```c
long St7GetGeometryEdgeConvectionTables(long uID, long
EdgeNum, long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.
- `CaseNum` — Load case number.

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

### `St7GetGeometryEdgeRadiation2`

Returns the thermal radiation coefficient and ambient temperature assigned to
the specified geometry edge.

**Syntax**

```c
long St7GetGeometryEdgeRadiation2(long uID, long EdgeNum,
long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.
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

### `St7GetGeometryEdgeRadiationTables`

Returns the tables associated with the thermal radiation properties assigned to a
specified geometry edge. A Factor vs Temperature table may apply to the
radiation coefficient and Factor vs Time tables may apply to both the radiation
coefficient and ambient temperature.

**Syntax**

```c
long St7GetGeometryEdgeRadiationTables(long uID, long
EdgeNum, long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.
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

### `St7GetGeometryEdgeFlux1`

Returns the heat flux assigned to the specified geometry edge.

**Syntax**

```c
long St7GetGeometryEdgeFlux1(long uID, long EdgeNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.
- `CaseNum` — Load case number.

**Output Parameters**

- `Doubles[0]` — The heat flux through the edge.

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

### `St7GetGeometryEdgeFluxTables`

Returns the tables associated with the heat flux assigned to the specified
geometry edge. Both Factor vs Time and Factor vs Temperature tables may be
assigned. This attribute is only used when performing heat transfer analysis.

**Syntax**

```c
long St7GetGeometryEdgeFluxTables(long uID, long EdgeNum,
long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.
- `CaseNum` — Load case number.

**Output Parameters**

- `Tables[0..1]` — [0] - Factor vs Time table ID associated with the edge heat flux, use zero for none. [1] - Factor vs Temperature table ID associated with the edge heat flux, use zero for none.

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

### `St7GetGeometryEdgeAttachment1`

Returns the edge attachment conditions assigned to the specified geometry
edge. Attachment attributes can be used to generate the attachment attribute
using the St7ToolAttachParts function.

**Syntax**

```c
long St7GetGeometryEdgeAttachment1(long uID, long EdgeNum,
long* Direction, long* AttachType, long* ConnectType,
long* PropNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.

**Output Parameters**

- `Direction` — Direction of attachment, one of adPlanar, adPlusZ or adMinusZ.
- `AttachType` — Attachment type, one of alDirect, alRigid or alFlexible.
- `ConnectType` — Attachment sub-type, either alMoment or alPinned.
- `PropNum` — Beam property number used for flexible attachment types.
- `Doubles[0]` — The maximum distance within which the brick face can be connected to another element using the attachment link.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
```
