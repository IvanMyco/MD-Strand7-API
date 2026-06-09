---
title: "Entities – Nodes Elements and Links"
source: "Strand7 R246 API Manual"
pages: 162–186
---

# Entities – Nodes Elements and Links

Syntax

long St7ConvertUnits(long uID, long* Units)
Input Parameters

uID
Strand7 model file ID number.

Units[0..kLastUnit-1]
[ipLENGTHU] - luMETRE, luCENTIMETRE, luMILLIMETRE, luFOOT or luINCH.
[ipFORCEU] - fuNEWTON, fuKILONEWTON, fuMEGANEWTON, fuKILOFORCE,
fuPOUNDFORCE, fuTONNEFORCE or fuKIPFORCE.

[ipSTRESSU] - suPASCAL, suKILOPASCAL, suMEGAPASCAL, suKSCm, suPSI,
suKSI or suPSF.

[ipMASSU] - muKILOGRAM, muTONNE, muGRAM, muPOUND or muSLUG.
[ipTEMPERU] - tuCELSIUS, tuFAHRENHEIT or tuKELVIN.
[ipENERGYU] - euJOULE, euBTU, euFTLBF or euCALORIE.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_InvalidUnits,
ERR7_NoError, ERR7_ResultFileIsOpen


## Entities – Nodes, Elements and Links


Entities – Nodes, Elements and Links


---

### `St7SetNodeXYZ`

Sets the position of a specified node in the Global Cartesian coordinate system.
A new node is created if the node number does not already exist. If the new
node number is not consecutive with the existing node total a series of nodes are
created at the origin such that the node list remains contiguous.

**Syntax**

```c
long St7SetNodeXYZ(long uID, long NodeNum, double* XYZ)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `XYZ[0..2]` — The node position as a 3 element array, specifying the position according to the Global Cartesian coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_UnknownError
```


---

### `St7GetNodeXYZ`

Returns the position of a specified node in the Global Cartesian coordinate
system, when no result file is open. When a result file and model window is open,
results will depend on the draw state and Displacement Scale.

**Syntax**

```c
long St7GetNodeXYZ(long uID, long NodeNum, double* XYZ)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.

**Output Parameters**

- `XYZ[0..2]` — The node position as a 3 element array, specifying the position according to the Global Cartesian coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededTotal, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_NoError
```


---

### `St7SetNodeUCS`

Sets the position of a specified node in a given UCS. A new node is created if the
node number does not already exist. If the new node number is not consecutive
with the existing node total a series of nodes are created at the origin such that
the node list remains contiguous.

**Syntax**

```c
long St7SetNodeUCS(long uID, long NodeNum, long UCSId,
double* XYZ)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `UCSId` — The specified UCS ID number. Entities – Nodes, Elements and Links
- `XYZ[0..2]` — The node position as a 3 element array, specifying the position according to the 123 axis UCS convention.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_UnknownError, ERR7_UnknownUCS
```


---

### `St7GetNodeUCS`

Returns the position of a specified node in a given UCS, when no result file is open.
When a result file and model window is open, results will depend on the draw
state and Displacement Scale.

**Syntax**

```c
long St7GetNodeUCS(long uID, long NodeNum, long UCSId,
double* XYZ)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `UCSId` — The specified UCS ID number.

**Output Parameters**

- `XYZ[0..2]` — The node position as a 3 element array, specifying the position according to the 123 axis UCS convention.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededTotal, ERR7_FileNotOpen,


ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_UnknownUCS
```


---

### `St7SetElementConnection`

Sets the nodal connectivity and property ID for a specified element. A new entity
is created if the element number does not already exist. If the new element
number is not consecutive with the existing element total a series of null elements
are created such that the element list remains contiguous. These null elements do
not have any connectivity or property ID assigned.

**Syntax**

```c
long St7SetElementConnection(long uID, long Entity, long
EltNum, long PropNum, long* Connection)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Strand7 element type, one of tyBEAM, tyPLATE or tyBRICK.
- `EltNum` — The specified element number.
- `PropNum` — The ID number for the property or the link type to be assigned to the element.
- `Connection[0..kMaxElementNode]` — [0] - Number of nodes in the element. [1..20] - Node numbers in the element. See Element Connections for more information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity,
ERR7_InvalidEntityNodes, ERR7_InvalidEntityNumber,


Entities – Nodes, Elements and Links

ERR7_InvalidFileUnit, ERR7_InvalidLinkType, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownError
```


---

### `St7GetElementConnection`

Returns the connectivity information for a specified element.

**Syntax**

```c
long St7GetElementConnection(long uID, long Entity, long
EltNum, long* Connection)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Strand7 element type, one of tyBEAM, tyPLATE, tyBRICK or tyLINK.
- `EltNum` — Element number.

**Output Parameters**

- `Connection[0..kMaxElementNode]` — [0] - Number of nodes in the element. [1..20] - Node numbers in the element. See Element Connections for more information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededTotal, ERR7_FileNotOpen,
ERR7_InvalidEntity, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetElementData`

Return element specific geometric data for a given element.

**Syntax**

```c
long St7GetElementData(long uID, long Entity, long EltNum,
double* EltData)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Strand7 element type, one of tyBEAM, tyPLATE or tyBRICK.
- `EltNum` — The specified element number.

**Output Parameters**

- `EltData` — Geometric data for the specified element: tyBEAM - Beam length. tyPLATE - Plate area. tyBRICK - Brick volume.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededTotal, ERR7_FileNotOpen,
ERR7_InvalidEntity, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetElementCentroid`

Returns the position of the geometric centroid for a specified element, when no
result file is open. When a result file and model window is open, results will depend
on the draw state and Displacement Scale.

**Syntax**

```c
long St7GetElementCentroid(long uID, long Entity, long
EltNum, long FaceEdgeNum, double* XYZ)


Entities – Nodes, Elements and Links
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Strand7 element type, either tyPLATE or tyBRICK.
- `EltNum` — Element number.
- `FaceEdgeNum` — Local face or edge number, one of 0,1,2,3 or 4 for tyPLATE or 0,1,2,3,4,5 or 6 for tyBRICK. Enter 0 to return centroid for whole element. See Element Connections for further information.

**Output Parameters**

- `XYZ[0..2]` — The centroid position as a 3 element array, specifying the position according to the XYZ Cartesian convention.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededTotal, ERR7_FileNotOpen,
ERR7_InvalidBrickFace, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidPlateEdge, ERR7_NoError
```


---

### `St7GetLinkType`

Returns the link type for a specified link.

**Syntax**

```c
long St7GetLinkType(long uID, long LinkNum, long* LinkType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LinkNum` — The specified link number.

**Output Parameters**

- `LinkType` — The link type, one of ilMasterSlaveLink, ilSectorSymmetryLink, ilCouplingLink, ilPinnedLink, ilRigidLink, ilShrinkLink, ilTwoPointLink, ilAttachmentLink or
  ilMultiPointLink

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_DataNotFound, ERR7_ExceededTotal, ERR7_InvalidFileUnit,
ERR7_NoError
```


---

### `St7SetMasterSlaveLink`

Assigns the parameters for the specified master/slave link.

**Syntax**

```c
long St7SetMasterSlaveLink(long uID, long LinkNum, long
UCSId, long* Connection, long* Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LinkNum` — The specified link number.
- `UCSId` — The specified UCS ID number.
- `Connection[0..2]` — [0] - Number of nodes in the link (2). [1..2] - Node numbers.
- `Integers[0..5]` — Entities – Nodes, Elements and Links A 6 element array describing the relationship between each DoF in the linked nodes according to the UCS axis system. Entries for each DoF may be one of msFree, msFix or msFixNegate.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetMasterSlaveLink`

Returns the parameters assigned to the specified master/slave link.

**Syntax**

```c
long St7GetMasterSlaveLink(long uID, long LinkNum, long*
UCSId, long* Connection, long* Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LinkNum` — The specified link number.

**Output Parameters**

- `UCSId` — The specified UCS ID number.
- `Connection[0..2]` — [0] - Number of nodes in the link (2). [1..2] - Node numbers.
- `Integers[0..5]` — A 6 element array describing the relationship between each DoF in the linked nodes according to the UCS axis system. Entries for each DoF may be one of msFree, msFix or msFixNegate.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededTotal, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_LinkNotMasterSlave, ERR7_NoError
```


---

### `St7SetSectorSymmetryLink`

Assigns the parameters for the specified sector symmetry link.

**Syntax**

```c
long St7SetSectorSymmetryLink(long uID, long LinkNum, long
Axis, long* Connection)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LinkNum` — The specified link number.
- `Axis` — Axis of symmetry, one of 1,2 or 3.
- `Connection[0..2]` — [0] - Number of nodes in the link (2). [1..2] - Node numbers.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidAxisSystem, ERR7_InvalidAxis,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileIsOpen


Entities – Nodes, Elements and Links
```


---

### `St7GetSectorSymmetryLink`

Returns the parameters assigned to the specified sector symmetry link.

**Syntax**

```c
long St7GetSectorSymmetryLink(long uID, long LinkNum, long*
Axis, long* Connection)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LinkNum` — The specified link number.

**Output Parameters**

- `Axis` — Axis of symmetry, one of 1,2 or 3.
- `Connection[0..2]` — [0] - Number of nodes in the link (2). [1..2] - Node numbers.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededTotal, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_LinkNotSectorSymmetry, ERR7_NoError
```


---

### `St7SetCouplingLink`

Assigns the parameters for the specified coupling link.

**Syntax**

```c
long St7SetCouplingLink(long uID, long LinkNum, long Couple,
long* Connection)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LinkNum` — The specified link number.
- `Couple` — Coupling type, one of cpTranslational, cpRotational or cpBoth.
- `Connection[0..3]` — [0] - Number of nodes in the link (3). [1..3] - Node numbers. See Element Connections for more information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidCoupleType,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetCouplingLink`

Returns the parameters assigned to the specified coupling link.

**Syntax**

```c
long St7GetCouplingLink(long uID, long LinkNum, long*
Couple, long* Connection)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LinkNum` — The specified link number. Entities – Nodes, Elements and Links

**Output Parameters**

- `Couple` — Coupling type, one of cpTranslational, cpRotational or cpBoth.
- `Connection[0..3]` — [0] - Number of nodes in the link (3). [1..3] - Node numbers. See Element Connections for more information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededTotal, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_LinkNotCoupling, ERR7_NoError
```


---

### `St7SetPinnedLink`

Assigns the parameters for the specified pinned link.

**Syntax**

```c
long St7SetPinnedLink(long uID, long LinkNum, long*
Connection)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LinkNum` — The specified link number.
- `Connection[0..2]` — [0] - Number of nodes in the link (2). [1..2] - Node numbers.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPinnedLink`

Returns the parameters assigned to the specified pinned link.

**Syntax**

```c
long St7GetPinnedLink(long uID, long LinkNum, long*
Connection)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LinkNum` — The specified link number.

**Output Parameters**

- `Connection[0..2]` — [0] - Number of nodes in the link (2). [1..2] - Node numbers.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededTotal, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_LinkNotPinned, ERR7_NoError
```


---

### `St7SetRigidLink`

Assigns the parameters for the specified rigid link.


Entities – Nodes, Elements and Links

**Syntax**

```c
long St7SetRigidLink(long uID, long LinkNum, long UCSId,
long Plane, long* Connection)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LinkNum` — The specified link number.
- `UCSId` — The specified Cartesian UCS ID number.
- `Plane` — Rigid link type, one of rgPlaneXYZ, rgPlaneXY, rgPlaneYZ or rgPlaneZX.
- `Connection[0..2]` — [0] - Number of nodes in the link (2). [1..2] - Node numbers.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidRigidPlane,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetRigidLink`

Returns the parameters assigned to the specified rigid link.

**Syntax**

```c
long St7GetRigidLink(long uID, long LinkNum, long* UCSId,
long* Plane, long* Connection)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LinkNum` — The specified link number.

**Output Parameters**

- `UCSId` — The Cartesian UCS ID number.
- `Plane` — Rigid link type, one of rgPlaneXYZ, rgPlaneXY, rgPlaneYZ or rgPlaneZX.
- `Connection[0..2]` — [0] - Number of nodes in the link (2). [1..2] - Node numbers.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededTotal, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_LinkNotRigid, ERR7_NoError
```


---

### `St7SetShrinkLink`

Assigns the parameters for the specified shrink link.

**Syntax**

```c
long St7SetShrinkLink(long uID, long LinkNum, long*
Connection, long* Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LinkNum` — The specified link number.
- `Connection[0..2]` — [0] - Number of nodes in the link (2). Entities – Nodes, Elements and Links [1..2] - Node numbers.
- `Integers[0..2]` — A 3 element array describing the shrink directions for the link. Each entry may be either btTrue or btFalse to enable shrinkage in each of the global Cartesian co-ordinate directions.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetShrinkLink`

Returns the parameters assigned to the specified shrink link.

**Syntax**

```c
long St7GetShrinkLink(long uID, long LinkNum, long*
Connection, long* Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LinkNum` — The specified link number.

**Output Parameters**

- `Connection[0..2]` — [0] - Number of nodes in the link (2). [1..2] - Node numbers.
- `Integers[0..2]` — A 3 element array describing the shrink directions for the link. Each entry may be either btTrue or btFalse to enable shrinkage in each of the global Cartesian co-ordinate directions.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededTotal, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_LinkNotShrink, ERR7_NoError
```


---

### `St7SetTwoPointLink`

Assigns the parameters for the specified two point link.

**Syntax**

```c
long St7SetTwoPointLink(long uID, long LinkNum, long*
Connection, long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LinkNum` — The specified link number.
- `Connection[0..2]` — [0] - Number of nodes in the link (2). [1..2] - Node numbers.
- `Integers[0..3]` — [ipTwoPointDOF1] - DoF at node 1, one of 1,2,3,4,5 or 6. [ipTwoPointDOF2] - DoF at node 2, one of 1,2,3,4,5 or 6. [ipTwoPointUCS1] - UCS ID number at node 1. [ipTwoPointUCS2] - UCS ID number at node 2.
- `Doubles[0..2]` — [ipTwoPointC0] - Constant coefficient. [ipTwoPointC1] - Coefficient of node 1. Entities – Nodes, Elements and Links [ipTwoPointC2] - Coefficient of node 2.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetTwoPointLink`

Returns the parameters assigned to the specified two point link.

**Syntax**

```c
long St7GetTwoPointLink(long uID, long LinkNum, long*
Connection, long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LinkNum` — The specified link number.

**Output Parameters**

- `Connection[0..2]` — [0] - Number of nodes in the link (2). [1..2] - Node numbers.
- `Integers[0..3]` — [ipTwoPointDOF1] - DoF at node 1, one of 1,2,3,4,5 or 6. [ipTwoPointDOF2] - DoF at node 2, one of 1,2,3,4,5 or 6. [ipTwoPointUCS1] - UCS ID number at node 1. [ipTwoPointUCS2] - UCS ID number at node 2.
- `Doubles[0..2]` — [ipTwoPointC0] - Constant coefficient. [ipTwoPointC1] - Coefficient of node 1. [ipTwoPointC2] - Coefficient of node 2.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededTotal, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_LinkNotTwoPoint, ERR7_NoError
```


---

### `St7SetAttachmentLink`

Assigns the parameters for the specified attachment link.

**Syntax**

```c
long St7SetAttachmentLink(long uID, long LinkNum, long*
Connection, long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LinkNum` — The specified link number.
- `Connection[0..1]` — [0] - Number of nodes in the link (1). [1] - Node number for attached node.
- `Integers[0..3]` — [ipAttachmentElType] - Target entity type, one of tyBEAM, tyPLATE or tyBRICK. [ipAttachmentElNum] - Target element number. [ipAttachmentBrickFaceNum] - Target face number for tyBRICK, one of 1,2,3,4,5 or 6. [ipAttachmentCouple] - Connection between the degrees of freedom with target element, one of cpTranslational, cpRotational or cpBoth. Entities – Nodes, Elements and Links
- `Doubles[0..1]` — A 2 element array containing the UV coordinates for the attachment location on the target element. If the target element is a beam only the first value is used. These values must lie between -1.0 and +1.0.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidBrickFace, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetAttachmentLink`

Returns the parameters assigned to the specified attachment link.

**Syntax**

```c
long St7GetAttachmentLink(long uID, long LinkNum, long*
Connection, long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LinkNum` — The specified link number.

**Output Parameters**

- `Connection[0..1]` — [0] - Number of nodes in the link (1). [1] - Node number for attached node.
- `Integers[0..3]` — [ipAttachmentElType] - Target entity type, one of tyBEAM, tyPLATE or tyBRICK. [ipAttachmentElNum] - Target element number. [ipAttachmentBrickFaceNum] - Target face number for tyBRICK, one of 1,2,3,4,5 or 6. [ipAttachmentCouple]- Connection between the degrees of freedom with target element, one of cpTranslational, cpRotational or cpBoth.
- `Doubles[0..1]` — A 2 element array containing the UV coordinates for the attachment location on the target element. If the target element is a beam only the first value is used. These values must lie between -1.0 and +1.0.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededTotal, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_LinkNotAttachment, ERR7_NoError
```


---

### `St7SetMultiPointLink`

Assigns the parameters for the specified multi-point link.

**Syntax**

```c
long St7SetMultiPointLink(long uID, long LinkNum, long
NumNodes, long FactorsType, long Couple, long*
Connection, long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LinkNum` — The specified link number.
- `NumNodes` — The number of nodes in the link.
- `FactorsType` — Multi-point link type, either mpInterpolatedFactors or mpUserFactors.
- `Couple` — Entities – Nodes, Elements and Links Coupling type, one of cpTranslational, cpRotational or cpBoth.
- `Connection[0..NumNodes-1]` — Node numbers for linked nodes, with the slave node specified first.
- `Integers[0..NumNodes-1]` — DoF for linked nodes, with the slave DoF specified first.
- `Doubles[0..NumNodes]` — Factors for linked nodes, with the slave factor specified first. Doubles[NumNodes] is used to specify the constant factor.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidCoupleType,
ERR7_InvalidEntityNodes, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidMultiPointFactorsType,
ERR7_InvalidMultiPointLink, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetNumMultiPointLinkNodes`

Returns the number of nodes in the specified multi-point link.

**Syntax**

```c
long St7GetNumMultiPointLinkNodes(long uID, long LinkNum,
long* NumNodes)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LinkNum` — The specified link number.

**Output Parameters**

- `NumNodes` — The number of nodes in the link.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededTotal, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_LinkNotMultiPoint, ERR7_NoError
```


---

### `St7GetMultiPointLink`

Returns the parameters assigned to the specified multi-point link. Use
St7GetNumMultiPointLinkNodes to determine the number of nodes in the
specified multi-point link.

**Syntax**

```c
long St7GetMultiPointLink(long uID, long LinkNum, long*
FactorsType, long* Couple, long* Connection, long*
Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LinkNum` — The specified link number.

**Output Parameters**

- `FactorsType` — Multi-point link type, either mpInterpolatedFactors or mpUserFactors.
- `Couple` — Coupling type, one of cpTranslational, cpRotational or cpBoth.
- `Connection[0..NumNodes-1]` — Node numbers for linked nodes, with the slave node specified first.
- `Integers[0..NumNodes-1]` — DoF for linked nodes, with the slave DoF specified first.
  Doubles[0..NumNodes]
