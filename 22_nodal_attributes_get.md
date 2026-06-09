---
title: "Nodal Attributes – Get"
source: "Strand7 R246 API Manual"
pages: 225–240
---

# Nodal Attributes – Get

Nodal Attributes – Set
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidBeamEnd,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_InvalidResponseType,
ERR7_NoError, ERR7_ResultFileIsOpen


---

### `St7GetNodeID`

Returns the ID number assigned to the specified node.

**Syntax**

```c
long St7GetNodeID(long uID, long NodeNum, long* NodeID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.

**Output Parameters**

- `NodeID` — The ID number for the specified node.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetNodeRestraint6`

Returns the restraint conditions assigned to the specified node. The UCS in which
these restraints were applied is also returned.

**Syntax**

```c
long St7GetNodeRestraint6(long uID, long NodeNum, long
CaseNum, long* UCSId, long* Status, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — Node number.
- `CaseNum` — Freedom case number.

**Output Parameters**

- `UCSId` — UCS ID number.
- `Status[0..5]` — A 6 element array describing the restraint conditions for the six DoF at the specified node. Status[i-1] = btTrue indicates that the ith DoF is restrained. The DoF are restrained according to the 123456 axis convention in the specified UCS.
- `Doubles[0..5]` — A 6 element array describing the enforced displacement conditions for the six DoF at the specified node. Doubles[i-1] describes the displacement of the ith DoF according to the 123456 axis convention in the specified UCS.

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

### `St7GetNodeForce3`

Returns the point force applied to the specified node in the Global Cartesian
Coordinate system.

**Syntax**

```c
long St7GetNodeForce3(long uID, long NodeNum, long CaseNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `CaseNum` — The specified load case number.

**Output Parameters**

- `Doubles[0..2]` — A 3 element array describing the nodal force in the XYZ Cartesian coordinate system for the specified node.

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

### `St7GetNodeMoment3`

Returns the point moment applied at the specified node in the Global Cartesian
Coordinate system.

**Syntax**

```c
long St7GetNodeMoment3(long uID, long NodeNum, long CaseNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `CaseNum` — The specified load case number.

**Output Parameters**

- `Doubles[0..2]` — A 3 element array describing the nodal moments about the XYZ Cartesian coordinate system for the specified node.

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

### `St7GetNodeTemperature1`

Returns the temperature value applied at the specified node.

**Syntax**

```c
long St7GetNodeTemperature1(long uID, long NodeNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `CaseNum` — The specified load case number.

**Output Parameters**

- `Doubles[0]` — The nodal temperature value at the specified node.

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

### `St7GetNodeTemperatureType1`

Returns the temperature type assigned at the specified node.

**Syntax**

```c
long St7GetNodeTemperatureType1(long uID, long NodeNum,
long CaseNum, long* tType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `CaseNum` — The specified load case number.

**Output Parameters**

- `tType` — The type of temperature attribute applied at the specified node, one of tReferenceTemperature, tFixedTemperature, tInitialTemperature or tTableTemperature. Use St7GetNodeTemperatureTable to return the table.

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

### `St7GetNodeTemperatureTable`

Returns the table associated with the temperature at the specified node.

**Syntax**

```c
long St7GetNodeTemperatureTable(long uID, long NodeNum,
long CaseNum, long* TableID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `CaseNum` — The specified load case number.

**Output Parameters**

- `TableID` — The ID number of the table associated with the temperature attribute for the specified node, zero for none.

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

### `St7GetNodeKTranslation3F`

Returns the translational stiffness components assigned to the specified node.

**Syntax**

```c
long St7GetNodeKTranslation3F(long uID, long NodeNum, long
CaseNum, long* UCSId, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `CaseNum` — The specified freedom case number.

**Output Parameters**

- `UCSId` — The ID number of the specified UCS.
- `Doubles[0..2]` — A 3 element array describing the translational stiffnesses for the specified node. Doubles[i-1] describes the stiffness for the ith translational DoF according to the 123 axis definition in the specified UCS.

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

### `St7GetNodeKRotation3F`

Returns the rotational stiffness components assigned to the specified node.

**Syntax**

```c
long St7GetNodeKRotation3F(long uID, long NodeNum, long
CaseNum, long* UCSId, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `CaseNum` — The specified freedom case number.

**Output Parameters**

- `UCSId` — The ID number of the specified UCS.
- `Doubles[0..2]` — A 3 element array describing the rotational stiffnesses for the specified node. Doubles[i-1] describes the stiffness for the ith rotational DoF according to the 456 axis definition in the specified UCS.

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

### `St7GetNodeTMass3`

Returns the translational mass components assigned to the specified node.
Translational masses are active for all load and freedom cases.

**Syntax**

```c
long St7GetNodeTMass3(long uID, long NodeNum, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.

**Output Parameters**

- `Doubles[0..2]` — A 3 element array describing the translational mass for the specified node. Doubles[i-1] describes the translational mass for the ith translational DoF according to the XYZ Cartesian axis convention.

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

### `St7GetNodeRMass3`

Returns the rotational mass components assigned to the specified node.
Rotational masses are active for all load and freedom cases.

**Syntax**

```c
long St7GetNodeRMass3(long uID, long NodeNum, long* UCSId,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.

**Output Parameters**

- `UCSId` — The ID number of the specified UCS.
- `Doubles[0..2]` — A 3 element array describing the rotational mass for the specified node. Doubles[i-1] describes the rotational mass for the ith rotational DoF according to the 456 axis convention in the specified UCS.

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

### `St7GetNodeNSMass5`

Returns the non-structural mass components assigned to the specified node.
Unlike translational and rotational masses, non-structural mass can include an
offset in addition to a dynamic scaling factor that controls the contribution when
performing transient or frequency based dynamic analysis. Non-structural masses
are active for all freedom cases.

**Syntax**

```c
long St7GetNodeNSMass5(long uID, long NodeNum, long CaseNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The specified node number.
- `CaseNum` — The specified load case number.

**Output Parameters**

- `Doubles[0..4]` — [0] - The non-structural mass at the specified node. [1] - The dynamic factor at the specified node. This factor is used to scale the non-structural mass when performing dynamic analysis. [2..4] - A 3 element array describing the offset in the XYZ Cartesian coordinate system.

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

### `St7GetNodeKDamping3F`

Returns the translational damping coefficients assigned at the specified node.

**Syntax**

```c
long St7GetNodeKDamping3F(long uID, long NodeNum, long
CaseNum, long* UCSId, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The node number.
- `CaseNum` — The load case number.

**Output Parameters**

- `UCSId` — The UCS ID number.
- `Doubles[0..2]` — A 3 element array describing the damping factors for the specified node. Doubles[i-1] describes the damping factor for the ith translational DoF according to the 123 axis definition in the specified UCS.

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

### `St7GetNodeHeatSource1`

Returns the heat source assigned at the specified node.

**Syntax**

```c
long St7GetNodeHeatSource1(long uID, long NodeNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The node number.
- `CaseNum` — The load case number.

**Output Parameters**

- `Doubles[0]` — The heat source value for the specified node.

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

### `St7GetNodeHeatSourceTables`

Returns the tables associated with the heat source at the specified node. Both
Factor vs Time and Factor vs Temperature tables can be defined.

**Syntax**

```c
long St7GetNodeHeatSourceTables(long uID, long NodeNum,
long CaseNum, long* Tables)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The node number.
- `CaseNum` — The load case number.

**Output Parameters**

- `Tables[0..1]` — [0] - Factor vs Time table ID associated with the heat source for the specified node, use zero for none. [1] - Factor vs Temperature table ID associated with the heat source for the specified node, use zero for none.

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

### `St7GetNodeInitialVelocity3`

Returns the initial velocity components assigned at the specified node. These
initial conditions are used when performing transient dynamic analysis.

**Syntax**

```c
long St7GetNodeInitialVelocity3(long uID, long NodeNum,
long CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The node number.
- `CaseNum` — The load case number.

**Output Parameters**

- `Doubles[0..2]` — A 3 element array describing the initial velocity components for the specified node. Doubles[i-1] describes the initial velocity for the ith translational DoF according to the XYZ Cartesian axis convention.

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

### `St7GetNodeAcceleration3`

Returns the acceleration components assigned at the specified node. These
acceleration values are not used as initial conditions when performing transient
analysis, they are used to generate body forces when acting on masses.

**Syntax**

```c
long St7GetNodeAcceleration3(long uID, long NodeNum, long
CaseNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — The node number.
- `CaseNum` — The load case number.

**Output Parameters**

- `Doubles[0..2]` — A 3 element array describing the acceleration components of the specified node. Doubles[i-1] describes the acceleration for the ith translational DoF according to the XYZ Cartesian axis convention.

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

### `St7GetNodeResponse`

Returns the response variable assigned at the specified node. . Response
variables are only used by the Load Influence Solver.

**Syntax**

```c
long St7GetNodeResponse(long uID, long NodeNum, long
CaseNum, long* ResponseType, long* UCSId, long*
Status)
```
