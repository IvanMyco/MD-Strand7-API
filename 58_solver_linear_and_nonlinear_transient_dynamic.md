---
title: "Solver – Linear and Nonlinear Transient Dynamic"
source: "Strand7 R246 API Manual"
pages: 815–828
---

# Solver – Linear and Nonlinear Transient Dynamic

Solver – Harmonic, Spectral and Linear Transient
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidModeNumber, ERR7_NoError


---

### `St7SetTransientInitialConditionsType`

Sets the type of initial conditions used for Linear and Nonlinear Transient analysis.

**Syntax**

```c
long St7SetTransientInitialConditionsType(long uID, long
InitialType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `InitialType` — Initial conditions type, one of icAppliedVectors, icNodalVelocity or icFromFile.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidInitialConditionsType, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetTransientInitialConditionsType`

Returns the type of initial conditions assigned for Linear and Nonlinear Transient
analysis.

**Syntax**

```c
long St7GetTransientInitialConditionsType(long uID, long*
InitialType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `InitialType` — Initial conditions type, one of icAppliedVectors, icNodalVelocity or icFromFile.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetTransientInitialConditionsVectors`

Sets the initial acceleration and velocity vectors used for Linear and Nonlinear
Transient analysis. A uniform acceleration and velocity is applied to all nodes in
the specified model.

**Syntax**

```c
long St7SetTransientInitialConditionsVectors(long uID,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Doubles[0..5]` — [0..2] - Initial acceleration components according to the XYZ axis system in the Global Cartesian coordinate system. [3..5] - Initial velocity components according to the XYZ axis system in the Global Cartesian coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetTransientInitialConditionsVectors`

Returns the initial acceleration and velocity vectors assigned for Linear and
Nonlinear Transient analysis. A uniform acceleration and velocity is applied to all
nodes in the model.

**Syntax**

```c
long St7GetTransientInitialConditionsVectors(long uID,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `Doubles[0..5]` — [0..2] - Initial acceleration components according to the XYZ axis system in the Global Cartesian coordinate system. [3..5] - Initial velocity components according to the XYZ axis system in the Global Cartesian coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetTransientInitialConditionsNodalVelocity`

Sets the load case used to specified the initial nodal velocity for Linear and
Nonlinear Transient analysis. The initial velocity components are determined by
the Initial Velocity nodal attribute.

**Syntax**

```c
long St7SetTransientInitialConditionsNodalVelocity(long uID,
long CaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Load case number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetTransientInitialConditionsNodalVelocity`

Returns the load case assigned to specified the initial velocity for Linear and
Nonlinear Transient analysis. The initial velocity components are determined by
the Initial Velocity nodal attribute.

**Syntax**

```c
long St7GetTransientInitialConditionsNodalVelocity(long uID,
long* CaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `CaseNum` — Load case number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetTransientBaseVector`

Sets the base acceleration vector for Linear and Nonlinear Transient analysis. The
base acceleration is applied to all restrained nodes in the specified model.

**Syntax**

```c
long St7SetTransientBaseVector(long uID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Doubles[0..2]` — Base acceleration components according to the XYZ axis system in the Global Cartesian coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetTransientBaseVector`

Returns the base acceleration vector assigned for Linear and Nonlinear Transient
analysis. The base acceleration is applied to all restrained nodes in the specified
model.

**Syntax**

```c
long St7GetTransientBaseVector(long uID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `Doubles[0..2]` — Base acceleration components according to the XYZ axis system in the Global Cartesian coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetTransientBaseVelocity`

Sets the initial base velocity for Linear and Nonlinear Transient analysis. All
restrained nodes in the specified model will initially have this velocity.

**Syntax**

```c
long St7SetTransientBaseVelocity(long uID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Doubles[0..2]` — Base velocity components according to the XYZ axis system in the Global Cartesian coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetTransientBaseVelocity`

Returns the initial base velocity assigned for Linear and Nonlinear Transient
analysis. All restrained nodes in the specified model will initially have this velocity.

**Syntax**

```c
long St7GetTransientBaseVelocity(long uID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `Doubles[0..2]` — Base velocity components according to the XYZ axis system in the Global Cartesian coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetTransientBaseTables`

Specifies the Acceleration vs Time tables to be associated with the base
acceleration components for Linear and Nonlinear Transient analysis.

**Syntax**

```c
long St7SetTransientBaseTables(long uID, long* Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Integers[0..2]` — ID numbers for the Acceleration vs Time tables to be used, zero for none. A table can be assigned to each of the XYZ acceleration components specified via the St7SetTransientBaseVector function.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7GetTransientBaseTables`

Returns the Acceleration vs Time tables associated with the base acceleration
components for Linear and Nonlinear Transient analysis.

**Syntax**

```c
long St7GetTransientBaseTables(long uID, long* Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `Integers[0..2]` — ID numbers for the Acceleration vs Time tables to be used, zero for none. A table can be assigned to each of the XYZ acceleration components specified via the St7SetTransientBaseVector function.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetTransientBaseResults`

Sets the global coordinate frame used for reporting displacement results in Linear
and Nonlinear Transient analysis.

**Syntax**

```c
long St7SetTransientBaseResults(long uID, bool* Logicals)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Logicals[0..2]` — A 3 element array specifying the coordinate frame used for reporting displacement, velocity and acceleration results respectively. Elements are either btTrue for the static global frame, or btFalse for the moving base frame.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetTransientBaseResults`

Returns the global coordinate frame used for reporting displacement results in
Linear and Nonlinear Transient analysis.

**Syntax**

```c
long St7GetTransientBaseResults(long uID, bool* Logicals)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `Logicals[0..2]` — A 3 element array specifying the coordinate frame used for reporting displacement, velocity and acceleration results respectively. Elements are either btTrue for the static global frame, or btFalse for the moving base frame.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7AddTransientNodeHistoryCase`

Adds a new node history case for Linear and Nonlinear Transient analysis.

**Syntax**

```c
long St7AddTransientNodeHistoryCase(long uID, long NodeNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — Node number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededMaxNumNodeHistory, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7InsertTransientNodeHistoryCase`

Inserts a new node history case for Linear and Nonlinear Transient analysis.

**Syntax**

```c
long St7InsertTransientNodeHistoryCase(long uID, long
NodeNum, long Pos)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NodeNum` — Node number.
- `Pos` — Node history case number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededMaxNumNodeHistory, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_NodeHistoryDoesNotExist, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7DeleteTransientNodeHistoryCase`

Deletes the specified node history case for Linear and Nonlinear Transient analysis.

**Syntax**

```c
long St7DeleteTransientNodeHistoryCase(long uID, long Pos)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Pos` — Node history case number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededMaxNumNodeHistory, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_NodeHistoryDoesNotExist,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetNumTransientNodeHistoryCases`

Returns the number of node history cases assigned for Linear and Nonlinear
Transient analysis.

**Syntax**

```c
long St7GetNumTransientNodeHistoryCases(long uID, long*
NumCases)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumCases` — Number of node history cases.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetTransientNodeHistoryCaseData`

Assigns the settings for the specified node history case for Linear and Nonlinear
Transient analysis.

**Syntax**

```c
long St7SetTransientNodeHistoryCaseData(long uID, long Pos,
bool* Logicals)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Pos` — Node history case number.
- `Logicals[0..5]` — [0..2] - btTrue to include nodal result component, according to the XYZ axis in the Global Cartesian coordinate system. [3..5] - btTrue to include displacement, velocity and acceleration results respectively.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_NodeHistoryDoesNotExist, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetTransientNodeHistoryCaseData`

Returns the settings assigned for the specified node history case for Linear and
Nonlinear Transient analysis.

**Syntax**

```c
long St7GetTransientNodeHistoryCaseData(long uID, long Pos,
bool* Logicals)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Pos` — Node history case number.

**Output Parameters**

- `Logicals[0..5]` — [0..2] - btTrue to include nodal result component, according to the XYZ axis in the Global Cartesian coordinate system. [3..5] - btTrue to include displacement, velocity and acceleration results respectively.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_NodeHistoryDoesNotExist, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7EnableAutoAssignPathDivisions`

Enables the transient solver to assign automatically the number of divisions on a
load path so that it is appropriate for the timestep under consideration.

**Syntax**

```c
long St7EnableAutoAssignPathDivisions(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7DisableAutoAssignPathDivisions`

Prevents the transient solver from automatically assigning the number of divisions
on a load path to suit the timestep.

**Syntax**

```c
long St7DisableAutoAssignPathDivisions(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
