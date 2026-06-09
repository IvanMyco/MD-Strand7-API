---
title: "Load Path Templates"
source: "Strand7 R246 API Manual"
pages: 680–714
---

# Load Path Templates

Input Parameters

uID
Strand7 model file ID number.

CreepID
Creep definition ID number.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen


---

### `St7GetTotalLoadPathTemplates`

Returns the total number and highest ID number of the load path templates in
the specified model.

**Syntax**

```c
long St7GetTotalLoadPathTemplates(long uID, long*
NumTemplates, long* LastTemplate)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumTemplates` — The total number of load path templates in the model.
- `LastTemplate` — The highest load path template ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetLoadPathTemplateNumByIndex`

Returns the load path template number associated with a specified template
index. The load path template indices are stored internally and are based on a
contiguous numbering system.

**Syntax**

```c
long St7GetLoadPathTemplateNumByIndex(long uID, long Index,
long* PathNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Index` — Load path template index.

**Output Parameters**

- `PathNum` — Load path template ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_InvalidIndex,
ERR7_NoError
```


---

### `St7NewLoadPathTemplate`

Creates a new load path template.

**Syntax**

```c
long St7NewLoadPathTemplate(long uID, long
LoadPathTemplateID, char* LoadPathTemplateName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `LoadPathTemplateName` — Name of the new template.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID,


ERR7_LoadPathTemplateIDAlreadyExists, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetLoadPathTemplateName`

Sets the name of the specified load path template.

**Syntax**

```c
long St7SetLoadPathTemplateName(long uID, long
LoadPathTemplateID, char* LoadPathTemplateName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `LoadPathTemplateName` — Name of the template.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetLoadPathTemplateName`

Returns the name assigned to the specified load path template.

**Syntax**

```c
long St7GetLoadPathTemplateName(long uID, long
LoadPathTemplateID, char* LoadPathTemplateName, long
MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `MaxStringLen` — Maximum number of characters allocated for LoadPathTemplateName.

**Output Parameters**

- `LoadPathTemplateName` — Name of the template.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_NoError
```


---

### `St7SetLoadPathTemplateParameters`

Sets the data for the specified load path template.

**Syntax**

```c
long St7SetLoadPathTemplateParameters(long uID, long
LoadPathTemplateID, long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Integers[0..2]` — [ipLPTColour] - Load path colour as a 32 bit RGB value. [ipLPTNumLanes] - Number of lanes. [ipLPTMultiLaneType] - Multi lane type, either lpAllSameFactors or lpAllDifferentFactors.
- `Doubles[0..1]` — [ipLPTTolerance] - Relative tolerance. [ipLPTMinLaneWidth] - Minimum lane width.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathLaneFactorType,
ERR7_InvalidLoadPathTemplateID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetLoadPathTemplateParameters`

Returns the data assigned to the specified load path template.

**Syntax**

```c
long St7GetLoadPathTemplateParameters(long uID, long
LoadPathTemplateID, long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.

**Output Parameters**

- `Integers[0..2]` — [ipLPTColour] - Load path colour as a 32 bit RGB value. [ipLPTNumLanes] - Number of lanes. [ipLPTMultiLaneType] - Multi lane type, either lpAllSameFactors or lpAllDifferentFactors.
- `Doubles[0..1]` — [ipLPTTolerance] - Relative tolerance. [ipLPTMinLaneWidth] - Minimum lane width.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_NoError
```


---

### `St7SetLoadPathTemplateLaneFactor`

Assigns the lane factor for the specified load path template.

**Syntax**

```c
long St7SetLoadPathTemplateLaneFactor(long uID, long
LoadPathTemplateID, long Lane, double Factor)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Lane` — Lane number.
- `Factor` — Lane factor.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathLane, ERR7_InvalidLoadPathTemplateID,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetLoadPathTemplateLaneFactor`

Returns the lane factor assigned to the specified load path template.

**Syntax**

```c
long St7GetLoadPathTemplateLaneFactor(long uID, long
LoadPathTemplateID, long Lane, double* Factor)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Lane` — Lane number.

**Output Parameters**

- `Factor` — Lane factor.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathLane, ERR7_InvalidLoadPathTemplateID,
ERR7_NoError
```


---

### `St7AddLoadPathTemplateVehicle`

Adds a vehicle to the specified load path template.

**Syntax**

```c
long St7AddLoadPathTemplateVehicle(long uID, long
LoadPathTemplateID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededMaxNumLoadPathVehicles,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetLoadPathTemplateVehicleName`

Sets the name of a vehicle in the specified load path template.

**Syntax**

```c
long St7SetLoadPathTemplateVehicleName(long uID, long
LoadPathTemplateID, long Vehicle, char*
LoadPathTemplateVehicleName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number.
- `LoadPathTemplateVehicleName` — Vehicle name.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_InvalidLoadPathVehicle,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetLoadPathTemplateVehicleName`

Returns the name assigned to a vehicle in the specified load path template.

**Syntax**

```c
long St7GetLoadPathTemplateVehicleName(long uID, long
LoadPathTemplateID, long Vehicle, char*
LoadPathTemplateVehicleName, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number.
- `MaxStringLen` — Maximum number of characters allocated for LoadPathTemplateVehicleName.

**Output Parameters**

- `LoadPathTemplateVehicleName` — Vehicle name.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_InvalidLoadPathVehicle,
ERR7_NoError
```


---

### `St7InsertLoadPathTemplateVehicle`

Inserts a new vehicle at the specified position in the specified load path template.

**Syntax**

```c
long St7InsertLoadPathTemplateVehicle(long uID, long
LoadPathTemplateID, long Vehicle)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — New vehicle number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededMaxNumLoadPathVehicles,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_InvalidLoadPathVehicle,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7CloneLoadPathTemplateVehicle`

Creates a copy of a vehicle in the specified load path template and appends it
to the vehicle list.

**Syntax**

```c
long St7CloneLoadPathTemplateVehicle(long uID, long
LoadPathTemplateID, long Vehicle)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number to be cloned.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededMaxNumLoadPathVehicles,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_InvalidLoadPathVehicle,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7DeleteLoadPathTemplateVehicle`

Deletes a vehicle within the specified load path template.

**Syntax**

```c
long St7DeleteLoadPathTemplateVehicle(long uID, long
LoadPathTemplateID, long Vehicle)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_InvalidLoadPathVehicle,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetNumLoadPathTemplateVehicles`

Returns the number of vehicles assigned to the specified load path template.

**Syntax**

```c
long St7GetNumLoadPathTemplateVehicles(long uID, long
LoadPathTemplateID, long* NumVehicles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.

**Output Parameters**

- `NumVehicles` — Number of vehicles.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_NoError
```


---

### `St7SetLoadPathTemplateVehicleData`

Sets the data for a vehicle in the specified load path template.

**Syntax**

```c
long St7SetLoadPathTemplateVehicleData(long uID, long
LoadPathTemplateID, long Vehicle, long* Integers,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number.
- `Integers` — [ipLPTVehicleInstance] - Vehicle instance type, either lpVehicleSingleLane or lpVehicleDoubleLane [ipLPTVehicleDirection] - Vehicle direction flag, either lpVehicleForward or lpVehicleBackward.
- `Doubles` — [ipLPTVehicleVelocity] - Vehicle velocity. [ipLPTVehicleStartTime] - Vehicle start time.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_InvalidLoadPathVehicle,
ERR7_InvalidLoadPathVehicleInstance, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetLoadPathTemplateVehicleData`

Returns the data assigned to a vehicle in the specified load path template.

**Syntax**

```c
long St7GetLoadPathTemplateVehicleData(long uID, long
LoadPathTemplateID, long Vehicle, long* Integers,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number.

**Output Parameters**

- `Integers[0..1]` — [ipLPTVehicleInstance] - Vehicle instance type, either lpVehicleSingleLane or lpVehicleDoubleLane [ipLPTVehicleDirection] - Vehicle direction flag, either lpVehicleForward or lpVehicleBackward.
- `Doubles[0..1]` — [ipLPTVehicleVelocity] - Vehicle velocity. [ipLPTVehicleStartTime] - Vehicle start time.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_InvalidLoadPathVehicle,
ERR7_NoError
```


---

### `St7EnableLoadPathTemplateVehicleLane`

Enables a vehicle/lane combination within the specified load path template.

**Syntax**

```c
long St7EnableLoadPathTemplateVehicleLane(long uID, long
LoadPathTemplateID, long Vehicle, long Lane)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number.
- `Lane` — Lane number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathLane, ERR7_InvalidLoadPathTemplateID,


ERR7_InvalidLoadPathVehicle, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7DisableLoadPathTemplateVehicleLane`

Disables a vehicle/lane combination within the specified load path template.

**Syntax**

```c
long St7DisableLoadPathTemplateVehicleLane(long uID, long
LoadPathTemplateID, long Vehicle, long Lane)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number.
- `Lane` — Lane number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathLane, ERR7_InvalidLoadPathTemplateID,
ERR7_InvalidLoadPathVehicle, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetLoadPathTemplateVehicleLaneState`

Returns the state of a vehicle/lane combination within the specified load path
template.

**Syntax**

```c
long St7GetLoadPathTemplateVehicleLaneState(long uID, long
LoadPathTemplateID, long Vehicle, long Lane, bool*
State)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number.
- `Lane` — Lane number.

**Output Parameters**

- `State` — btTrue if the specified vehicle/lane combination is enabled.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathLane, ERR7_InvalidLoadPathTemplateID,
ERR7_InvalidLoadPathVehicle, ERR7_NoError
```


---

### `St7AddLoadPathTemplatePointForce`

Adds a point force to the specified load path template.

**Syntax**

```c
long St7AddLoadPathTemplatePointForce(long uID, long
LoadPathTemplateID, long Vehicle)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededMaxNumRows,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_InvalidLoadPathVehicle,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7InsertLoadPathTemplatePointForce`

Inserts a point force within the specified load path template.

**Syntax**

```c
long St7InsertLoadPathTemplatePointForce(long uID, long
LoadPathTemplateID, long Vehicle, long Pos)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number.
- `Pos` — Point force number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_InvalidLoadPathVehicle,
ERR7_InvalidTableRow, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7DeleteLoadPathTemplatePointForce`

Deletes a point force from the specified load path template.

**Syntax**

```c
long St7DeleteLoadPathTemplatePointForce(long uID, long
LoadPathTemplateID, long Vehicle, long Pos)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number.
- `Pos` — Point force number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetNumLoadPathTemplatePointForces`

Returns the number of point forces assigned to the specified load path template.

**Syntax**

```c
long St7GetNumLoadPathTemplatePointForces(long uID, long
LoadPathTemplateID, long Vehicle, long*
NumPointForces)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number.

**Output Parameters**

- `NumPointForces` — Number of point forces.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_InvalidLoadPathVehicle,
ERR7_NoError
```


---

### `St7SetLoadPathTemplatePointForceData`

Sets the point force data for the specified load path template.

**Syntax**

```c
long St7SetLoadPathTemplatePointForceData(long uID, long
LoadPathTemplateID, long Vehicle, long Pos, long*
Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number.
- `Pos` — Point force number.
- `Integers[0..3]` — [ipLPTMobility] - Mobility, either lpPointForceMobilityGrouped or lpPointForceMobilityFloating. [ipLPTAxisSystem] - Axis system, either lpAxisGlobal or lpAxisLocal [ipLPTAdjacency] - Consider adjacency, either btTrue or btFalse. [ipLPTCentrifugal] - Consider centrifugal effects, either btTrue or btFalse.
- `Doubles[0..4]` — [0..1] - XY position of the point force. [2..4] - Components of the point force according to the 123 axis convention in the specified axis system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidAxisSystem,
ERR7_InvalidFileUnit, ERR7_InvalidLoadPathTemplateID,
ERR7_InvalidMobilityType, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetLoadPathTemplatePointForceData`

Returns the point force data assigned to the specified load path template.

**Syntax**

```c
long St7GetLoadPathTemplatePointForceData(long uID, long
LoadPathTemplateID, long Vehicle, long Pos, long*
Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number.
- `Pos` — Point force number.

**Output Parameters**

- `Integers[0..3]` — [ipLPTMobility] - Mobility, either lpPointForceMobilityGrouped or lpPointForceMobilityFloating. [ipLPTAxisSystem] - Axis system, either lpAxisGlobal or lpAxisLocal [ipLPTAdjacency] - Consider adjacency, either btTrue or btFalse. [ipLPTCentrifugal] - Consider centrifugal effects, either btTrue or btFalse.
- `Doubles[0..4]` — [0..1] - XY position of the point force. [2..4] - Components of the point force according to the 123 axis convention in the specified axis system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_NoError
```


---

### `St7AddLoadPathTemplateDistributedForce`

Adds a distributed force to the specified load path template.

**Syntax**

```c
long St7AddLoadPathTemplateDistributedForce(long uID, long
LoadPathTemplateID, long Vehicle)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededMaxNumRows,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_InvalidLoadPathVehicle,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7InsertLoadPathTemplateDistributedForce`

Inserts a new distributed force to the specified load path template.

**Syntax**

```c
long St7InsertLoadPathTemplateDistributedForce(long uID,
long LoadPathTemplateID, long Vehicle, long Pos)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number.
- `Pos` — Distributed force number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_InvalidLoadPathVehicle,
ERR7_InvalidTableRow, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7DeleteLoadPathTemplateDistributedForce`

Deletes a distributed force from the specified load path template.

**Syntax**

```c
long St7DeleteLoadPathTemplateDistributedForce(long uID,
long LoadPathTemplateID, long Vehicle, long Pos)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number.
- `Pos` — Distributed load number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetNumLoadPathTemplateDistributedForces`

Returns the number of distributed forces assigned to the specified load path
template.

**Syntax**

```c
long St7GetNumLoadPathTemplateDistributedForces(long uID,
long LoadPathTemplateID, long Vehicle, long*
NumDistributedForces)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number.

**Output Parameters**

- `NumDistributedForces` — Number of distributed forces.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_InvalidLoadPathVehicle,
ERR7_NoError
```


---

### `St7SetLoadPathTemplateDistributedForceData`

Sets the distributed force data for the specified load path template.

**Syntax**

```c
long St7SetLoadPathTemplateDistributedForceData(long uID,
long LoadPathTemplateID, long Vehicle, long Pos, long*
Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number,
- `Pos` — Distributed force number.
- `Integers[0..3]` — [ipLPTMobility] - Mobility, one of lpDistrForceMobilityGrouped, lpDistrForceMobilityLeading, lpDistrForceMobilityTrailing, lpDistrForceMobilityFullLength or lpDistrForceMobilityFloating. [ipLPTAxisSystem] - Axis system, either lpAxisGlobal or lpAxisLocal [ipLPTAdjacency] - Consider adjacency, either btTrue or btFalse. [ipLPTCentrifugal] - Consider centrifugal effects, either btTrue or btFalse.
- `Doubles[0..6]` — [0..3] - Position of endpoints according to the [x1, x2, y1, y2] format. [4..6] - Components of distributed force according to the 123 axis convention in the specified coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidAxisSystem,
ERR7_InvalidFileUnit, ERR7_InvalidLoadPathTemplateID,
ERR7_InvalidMobilityType, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetLoadPathTemplateDistributedForceData`

Returns the distributed force data assigned to the specified load path template.

**Syntax**

```c
long St7GetLoadPathTemplateDistributedForceData(long uID,
long LoadPathTemplateID, long Vehicle, long Pos, long*
Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number.
- `Pos` — Distributed force number.

**Output Parameters**

- `Integers[0..3]` — [ipLPTMobility] - Mobility, one of lpDistrForceMobilityGrouped, lpDistrForceMobilityLeading, lpDistrForceMobilityTrailing, lpDistrForceMobilityFullLength or lpDistrForceMobilityFloating. [ipLPTAxisSystem] - Axis system, either lpAxisGlobal or lpAxisLocal [ipLPTAdjacency] - Consider adjacency, either btTrue or btFalse. [ipLPTCentrifugal] - Consider centrifugal effects, either btTrue or btFalse.
- `Doubles[0..6]` — [0..3] - Position of endpoints according to the [x1, x2, y1, y2] format. [4..6] - Components of distributed force according to the 123 axis convention in the specified coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_NoError
```


---

### `St7AddLoadPathTemplateHeatSource`

Adds a new heat source to the specified load path template.

**Syntax**

```c
long St7AddLoadPathTemplateHeatSource(long uID, long
LoadPathTemplateID, long Vehicle)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededMaxNumRows,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_InvalidLoadPathVehicle,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7InsertLoadPathTemplateHeatSource`

Inserts a new heat source in the specified load path template.

**Syntax**

```c
long St7InsertLoadPathTemplateHeatSource(long uID, long
LoadPathTemplateID, long Vehicle, long Pos)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number.
- `Pos` — Heat source number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededMaxNumRows,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,


ERR7_InvalidLoadPathTemplateID, ERR7_InvalidLoadPathVehicle,
ERR7_InvalidTableRow, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7DeleteLoadPathTemplateHeatSource`

Deletes a heat source from the specified load path template.

**Syntax**

```c
long St7DeleteLoadPathTemplateHeatSource(long uID, long
LoadPathTemplateID, long Vehicle, long Pos)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number.
- `Pos` — Heat source number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetNumLoadPathTemplateHeatSources`

Returns the number of heat sources assigned to the specified load path template.

**Syntax**

```c
long St7GetNumLoadPathTemplateHeatSources(long uID, long
LoadPathTemplateID, long Vehicle, long*
NumHeatSources)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number.

**Output Parameters**

- `NumHeatSources` — Number of heat sources.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_InvalidLoadPathVehicle,
ERR7_NoError
```


---

### `St7SetLoadPathTemplateHeatSourceData`

Sets the heat source data for the specified load path template.

**Syntax**

```c
long St7SetLoadPathTemplateHeatSourceData(long uID, long
LoadPathTemplateID, long Vehicle, long Pos, long*
Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number.
- `Pos` — Heat source number.
- `Integers[0]` — Currently unused, a dummy integer may be passed.
- `Doubles[0..4]` — [0..1] - XY position of the heat source. [2..3] - XY dimensions of heat source. [4] - Heat source value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidAxisSystem,
ERR7_InvalidFileUnit, ERR7_InvalidLoadPathTemplateID,
ERR7_InvalidMobilityType, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetLoadPathTemplateHeatSourceData`

Returns the heat source data assigned to the specified load path template.

**Syntax**

```c
long St7GetLoadPathTemplateHeatSourceData(long uID, long
LoadPathTemplateID, long Vehicle, long Pos, long*
Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number.
- `Pos` — Heat source number.

**Output Parameters**

- `Integers[0]` — Currently unused, a dummy integer may be passed.
- `Doubles[0..4]` — [0..1] - XY position of the heat source. [2..3] - XY dimensions of heat source. [4] - Heat source value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_NoError
```


---

### `St7SetLoadPathTemplateVehicleSet`

Assigns a vehicle set to a specified vehicle in a given load path template.

**Syntax**

```c
long St7SetLoadPathTemplateVehicleSet(long uID, long
LoadPathTemplateID, long Vehicle, char*
LoadPathTemplateVehicleSet)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number.
- `LoadPathTemplateVehicleSet` — String identifying the vehicle set. A null string indicates that the specified vehicle does not belong to a set.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetLoadPathTemplateVehicleSet`

Returns the vehicle set assigned to a specified vehicle in a given load path
template.

**Syntax**

```c
long St7GetLoadPathTemplateVehicleSet(long uID, long
LoadPathTemplateID, long Vehicle, char*
LoadPathTemplateVehicleSet, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `Vehicle` — Vehicle number.
- `MaxStringLen` — Maximum number of characters allocated for LoadPathTemplateVehicleSet.

**Output Parameters**

- `LoadPathTemplateVehicleSet` — String identifying the vehicle set. A null string indicates that the specified vehicle does not belong to a set.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_NoError
```


---

### `St7DeleteLoadPathTemplate`

Deletes the specified load path template.

**Syntax**

```c
long St7DeleteLoadPathTemplate(long uID, long
LoadPathTemplateID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetLoadPathTemplateCentrifugalData`

Sets the centrifugal data for the specified load path template.

**Syntax**

```c
long St7SetLoadPathTemplateCentrifugalData(long uID, long
LoadPathTemplateID, char* K0, char* K1, long* Integers,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `K0` — Expression for the K0 term in the centrifugal force equation: Fc = K0 + K1*Fz. This formula can be a function of R, L, V and g.
- `K1` — Expression for the K1 term in the centrifugal force equation: Fc = K0 + K1*Fz. This formula can be a function of R, L, V and g.
- `Integers[0..2]` — [ipLPTLimitK1] - Impose K1 limits, either btTrue or btFalse. [ipLPTLengthUnit] - Length unit, one of luMETRE, luCENTIMETRE, luMILLIMETRE, luFOOT or luINCH. [ipLPTForceUnit] - Force unit, one of fuNEWTON, fuKILONEWTON, fuMEGANEWTON, fuKILOFORCE, fuPOUNDFORCE, fuTONNEFORCE or fuKIPFORCE.
- `Doubles[0..1]` — [ipLPTMinK1] - Minimum K1 value. [ipLPTMaxK1] - Maximum K1 value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_InvalidUnits,
ERR7_NoError, ERR7_ResultFileIsOpen, ERR7_UnknownError
```


---

### `St7GetLoadPathTemplateCentrifugalData`

Returns the centrifugal data assigned to the specified load path template.

**Syntax**

```c
long St7GetLoadPathTemplateCentrifugalData(long uID, long
LoadPathTemplateID, char* K0, char* K1, long
MaxStringLen, long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
