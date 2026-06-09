---
title: "Edge Attributes – Set"
source: "Strand7 R246 API Manual"
pages: 445–456
---

# Edge Attributes – Set

Vertex Attributes – Get

ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_NoError, ERR7_ResultFileIsOpen


---

### `St7GetVertexHeatSourceTables`

Returns the tables associated with the heat source assigned to the specified
vertex. Both Factor vs Time and Factor vs Temperature tables may be assigned.
This attribute is only used when performing heat transfer analysis.

**Syntax**

```c
long St7GetVertexHeatSourceTables(long uID, long VertexNum,
long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.
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

### `St7SetGeometryEdgeType`

Sets the type for the specified geometry edge.

**Syntax**

```c
long St7SetGeometryEdgeType(long uID, long EdgeNum, long
EdgeType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.
- `EdgeType` — Edge type, either etInterpolated or etNonInterpolated.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_InvalidGeometryEdgeType
```


---

### `St7SetGeometryEdgeRelease1`

Sets the edge release condition on the specified geometry edge.

**Syntax**

```c
long St7SetGeometryEdgeRelease1(long uID, long EdgeNum,
long* Status)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.
- `Status` — btTrue or btFalse.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetGeometryEdgeSupport1F`

Assigns an elastic edge support to the specified geometry edge.

**Syntax**

```c
long St7SetGeometryEdgeSupport1F(long uID, long EdgeNum,
long CaseNum, long Status, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.
- `CaseNum` — Freedom case number.
- `Status` — Compression-only flag, either btTrue or btFalse.
- `Doubles[0]` — Elastic support value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetGeometryEdgePressure1`

Assigns a pressure to the specified geometry edge.

**Syntax**

```c
long St7SetGeometryEdgePressure1(long uID, long EdgeNum,
long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.
- `CaseNum` — Load case number.
- `Doubles[0]` — Edge pressure value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetGeometryEdgeShear1`

Assigns a shear stress to the specified geometry edge.

**Syntax**

```c
long St7SetGeometryEdgeShear1(long uID, long EdgeNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.
- `CaseNum` — Load case number.
- `Doubles[0]` — Shear stress value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetGeometryEdgeNormalShear1`

Assigns a normal shear stress to the specified geometry edge.

**Syntax**

```c
long St7SetGeometryEdgeNormalShear1(long uID, long EdgeNum,
long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.
- `CaseNum` — Load case number.
- `Doubles[0]` — Normal shear stress value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetGeometryEdgeConvection2`

Assigns thermal convection coefficient and ambient temperature to the
specified geometry edge. This attribute is only used when performing heat
transfer analysis.

**Syntax**

```c
long St7SetGeometryEdgeConvection2(long uID, long EdgeNum,
long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.
- `CaseNum` — Load case number.
- `Doubles[0..1]` — [0] - Convection coefficient. [1] - Ambient temperature.

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

### `St7SetGeometryEdgeConvectionTables`

Specifies the tables associated with the thermal convection properties assigned
to a specified geometry edge. A Factor vs Temperature table may apply to the
convection coefficient and Factor vs Time tables may apply to both the
convection coefficient and ambient temperature.

**Syntax**

```c
long St7SetGeometryEdgeConvectionTables(long uID, long
EdgeNum, long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.
- `CaseNum` — Load case number.
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

### `St7SetGeometryEdgeRadiation2`

Assigns the thermal radiation coefficient and ambient temperature for the
specified geometry edge.

**Syntax**

```c
long St7SetGeometryEdgeRadiation2(long uID, long EdgeNum,
long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.
- `CaseNum` — Load case number.
- `Doubles[0..1]` — [0] - Radiation coefficient. [1] - Ambient temperature.

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

### `St7SetGeometryEdgeRadiationTables`

Specifies the tables associated with the thermal radiation properties assigned to
a specified geometry edge. A Factor vs Temperature table may apply to the
radiation coefficient and Factor vs Time tables may apply to both the radiation
coefficient and ambient temperature.

**Syntax**

```c
long St7SetGeometryEdgeRadiationTables(long uID, long
EdgeNum, long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.
- `CaseNum` — Load case number.
- `Tables[0..2]` — [0] - Factor vs Time table ID associated with the ambient temperature, use zero for none. [1] - Factor vs Temperature table ID associated with the radiation coefficient, use zero for none. [2] - Factor vs Time table ID associated with the radiation coefficient, use zero for none.

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

### `St7SetGeometryEdgeFlux1`

Assigns a heat flux to the specified geometry edge.

**Syntax**

```c
long St7SetGeometryEdgeFlux1(long uID, long EdgeNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.
- `CaseNum` — Load case number.
- `Doubles[0]` — The heat flux through the edge.

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

### `St7SetGeometryEdgeFluxTables`

Specifies the tables associated with the heat flux assigned to the specified
geometry edge. Both Factor vs Time and Factor vs Temperature tables may be
assigned. This attribute is only used when performing heat transfer analysis.

**Syntax**

```c
long St7SetGeometryEdgeFluxTables(long uID, long EdgeNum,
long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.
- `CaseNum` — Load case number.
- `Tables[0..1]` — [0] - Factor vs Time table ID associated with the edge heat flux, use zero for none. [1] - Factor vs Temperature table ID associated with the edge heat flux, use zero for none.

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

### `St7SetGeometryEdgeAttachment1`

Assigns an attachment condition to the specified geometry edge. Attachment
attributes can be used to generate attachment links using the St7ToolAttachParts
function.

**Syntax**

```c
long St7SetGeometryEdgeAttachment1(long uID, long EdgeNum,
long Direction, long AttachType, long ConnectType,
long PropNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.
- `Direction` — Direction of attachment, one of adPlanar, adPlusZ or adMinusZ.
- `AttachType` — Attachment type, one of alDirect, alRigid or alFlexible.
- `ConnectType` — Attachment sub-type, either alMoment or alPinned.
- `PropNum` — Beam property number used for flexible attachment types.
- `Doubles[0]` — The maximum distance within which the edge can be connected to another element using the attachment link.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidAttachmentDirection,
ERR7_InvalidAttachmentType, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
```
