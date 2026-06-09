---
title: "Nodal Attributes – Set"
source: "Strand7 R246 API Manual"
pages: 209–224
---

# Nodal Attributes – Set

Entities – Load Paths

[ipLoadPathTarget] - Load path target entity, one of tyBEAM, tyPLATE,
tyBRICK or tyNULL to target all entities.

[ipLoadPathDivisions] - Number of divisions along the load path.
Doubles[0..8]
[0..2] - The start XYZ point in the definition of the load path (defined in the
global coordinate system).

[3..5] - The end XYZ point in the definition of the load path.
[6..8] - The lateral XYZ point in the definition of the load path, used to
define the plane of the load path and its curvature (for circular load paths).
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError


---

### `St7DeleteLoadPath`

Deletes the specified load path.

**Syntax**

```c
long St7DeleteLoadPath(long uID, long LoadPathID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathID` — Load path ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetNodeID`

Sets the ID number of the specified node.

**Syntax**

```c
long St7SetNodeID(long uID, long NodeNum, long NodeID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `NodeID` — The ID number for the specified node,

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetNodeRestraint6`

Sets the restraint conditions at the given node in the specified UCS.

**Syntax**

```c
long St7SetNodeRestraint6(long uID, long NodeNum, long
CaseNum, long UCSId, long* Status, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — Node number.
- `CaseNum` — Freedom case number.
- `UCSId` — UCS ID number.
- `Status[0..5]` — A 6 element array describing the restraint conditions for the six DoF at the specified node. Status[i-1] = btTrue indicates that the ith DoF is restrained. The DoF are restrained according to the 123456 axis convention in the specified UCS.
- `Doubles[0..5]` — A 6 element array describing the enforced displacement conditions for the six DoF at the specified node. Doubles[i-1] describes the displacement of the ith DoF according to the 123456 axis convention in the specified UCS.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetNodeForce3`

Sets the point force acting on the specified node in the Global Cartesian
Coordinate system.

**Syntax**

```c
long St7SetNodeForce3(long uID, long NodeNum, long CaseNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `CaseNum` — The specified load case number.
- `Doubles[0..2]` — A 3 element array describing the nodal force in the XYZ Cartesian coordinate system for the specified node.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetNodeMoment3`

Sets the point moment acting on the specified node in the Global Cartesian
Coordinate system.

**Syntax**

```c
long St7SetNodeMoment3(long uID, long NodeNum, long CaseNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `CaseNum` — The specified load case number.
- `Doubles[0..2]` — A 3 element array describing the nodal moments about the XYZ Cartesian coordinate system for the specified node.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetNodeTemperature1`

Sets the temperature at the specified node.

**Syntax**

```c
long St7SetNodeTemperature1(long uID, long NodeNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `CaseNum` — The specified load case number.
- `Doubles[0]` — The nodal temperature value at the specified node.

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

### `St7SetNodeTemperatureType1`

Sets the type of temperature at the specified node.

**Syntax**

```c
long St7SetNodeTemperatureType1(long uID, long NodeNum,
long CaseNum, long tType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `CaseNum` — The specified load case number.
- `tType` — The type of temperature attribute applied at the specified node: tReferenceTemperature, tFixedTemperature, tInitialTemperature or tTableTemperature. If required, use St7SetNodeTemperatureTable to set the table.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidAttributeType, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidLoadCase,
ERR7_InvalidLoadID, ERR7_InvalidTemperatureType,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetNodeTemperatureTable`

Specifies the table to be associated with the temperature at the given node. A
table can only be assigned for nodes with the appropriate table temperature
type, as set using the St7SetNodeTemperatureType1 function.

**Syntax**

```c
long St7SetNodeTemperatureTable(long uID, long NodeNum,
long CaseNum, long TableID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `CaseNum` — The specified load case number.
- `TableID` — The ID number of the Temperature vs Time table to be associated with the temperature attribute for the specified node.

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

### `St7SetNodeKTranslation3F`

Sets the translational stiffness acting at the specified node.

**Syntax**

```c
long St7SetNodeKTranslation3F(long uID, long NodeNum, long
CaseNum, long UCSId, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `CaseNum` — The specified freedom case number.
- `UCSId` — The ID number for the specified UCS.
- `Doubles[0..2]` — A 3 element array describing the translational stiffnesses for the specified node. Doubles[i-1] describes the stiffness for the ith translational DoF according to the 123 axis definition in the specified UCS.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetNodeKRotation3F`

Sets the rotational stiffness acting at the specified node.

**Syntax**

```c
long St7SetNodeKRotation3F(long uID, long NodeNum, long
CaseNum, long UCSId, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `CaseNum` — The specified freedom case number.
- `UCSId` — The ID number for the specified UCS.
- `Doubles[0..2]` — A 3 element array describing the rotational stiffnesses for the specified node. Doubles[i-1] describes the stiffness for the ith rotational DoF according to the 456 axis definition in the specified UCS.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetNodeTMass3`

Sets the translational mass assigned to the specified node. Translational masses
are active in all load and freedom cases in the model.

**Syntax**

```c
long St7SetNodeTMass3(long uID, long NodeNum, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `Doubles[0..2]` — A 3 element array describing the translational mass for the specified node. Doubles[i-1] describes the translational mass for the ith translational DoF according to the XYZ Cartesian axis convention.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,


ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetNodeRMass3`

Sets the rotational mass assigned to the specified node. Rotational masses are
active in all load and freedom cases in the model

**Syntax**

```c
long St7SetNodeRMass3(long uID, long NodeNum, long UCSId,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `UCSId` — The ID number for the specified UCS.
- `Doubles[0..2]` — A 3 element array describing the rotational mass for the specified node. Doubles[i-1] describes the rotational mass for the ith rotational DoF according to the 456 axis convention in the specified UCS.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetNodeNSMass5`

Sets the non-structural mass at the specified node. Unlike translational and
rotational masses, non-structural mass can include an offset in addition to a
dynamic scaling factor that controls the contribution when performing transient
or frequency based dynamic analysis. Non-structural masses are active for all
freedom cases.

**Syntax**

```c
long St7SetNodeNSMass5(long uID, long NodeNum, long CaseNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `CaseNum` — The specified load case number.
- `Doubles[0..4]` — [0] - The non-structural mass at the specified node. [1] - The dynamic factor at the specified node. This factor is used to scale the non-structural mass when performing dynamic analysis. [2..4] - A 3 element array describing the offset in the XYZ Cartesian coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetNodeKDamping3F`

Sets the translational damping coefficients at the specified node.

**Syntax**

```c
long St7SetNodeKDamping3F(long uID, long NodeNum, long
CaseNum, long UCSId, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `CaseNum` — The specified load case number.
- `UCSId` — The ID number for the specified UCS.
- `Doubles[0..2]` — A 3 element array describing the damping factors for the specified node. Doubles[i-1] describes the damping factor for the ith translational DoF according to the 123 axis definition in the specified UCS.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetNodeHeatSource1`

Sets the heat source at the specified node.

**Syntax**

```c
long St7SetNodeHeatSource1(long uID, long NodeNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `CaseNum` — The specified load case number.
- `Doubles[0]` — The heat source value for the specified node.

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

### `St7SetNodeHeatSourceTables`

Specifies the tables to be associated with the specified nodal heat source. Both
Factor vs Time and Factor vs Temperature tables can be assigned.

**Syntax**

```c
long St7SetNodeHeatSourceTables(long uID, long NodeNum,
long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `CaseNum` — The specified load case number.
- `Tables[0..1]` — [0] - Factor vs Time table ID associated with the heat source for the specified node, use zero for none. [1] - Factor vs Temperature table ID associated with the heat source for the specified node, use zero for none.

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

### `St7SetNodeInitialVelocity3`

Sets the initial Global Cartesian velocity components for the specified node.
These initial conditions are used when performing transient dynamic analysis.

**Syntax**

```c
long St7SetNodeInitialVelocity3(long uID, long NodeNum,
long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `CaseNum` — The specified load case number.
- `Doubles[0..2]` — A 3 element array describing the initial velocity components for the specified node. Doubles[i-1] describes the initial velocity for the ith translational DoF according to the XYZ Cartesian axis convention.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetNodeAcceleration3`

Sets the Global Cartesian acceleration components at the specified node. These
acceleration values are not used as initial conditions when performing transient
analysis, they are used to generate body forces when acting on masses.

**Syntax**

```c
long St7SetNodeAcceleration3(long uID, long NodeNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `CaseNum` — The specified load case number.
- `Doubles[0..2]` — A 3 element array describing the acceleration components of the specified node. Doubles[i-1] describes the acceleration for the ith translational DoF according to the XYZ Cartesian axis convention.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetNodeResponse`

Assigns a response variable to the specified node. Response variables are only
used by the Load Influence Solver.

**Syntax**

```c
long St7SetNodeResponse(long uID, long NodeNum, long
CaseNum, long ResponseType, long UCSId, long* Status)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `CaseNum` — The specified load case number.
- `ResponseType` — Type of response variable, either reNodeDisplacement or reNodeReaction.
- `UCSId` — The ID number for the specified UCS.
- `Status[0..5]` — A 6 element array describing the active DoFs for the response variable in the UCS axis system. Each element may be set to btTrue or btFalse to enable or disable the corresponding DoF.
