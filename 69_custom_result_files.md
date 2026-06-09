---
title: "Custom Result Files"
source: "Strand7 R246 API Manual"
pages: 948–969
---

# Custom Result Files

Harmonic Time History


---

### `St7GenerateHRATimeHistory`

Generates the time history response for a specified model based on a Harmonic
Response analysis. An associated Harmonic Response result file must currently be
open.

**Syntax**

```c
long St7GenerateHRATimeHistory(long uID, double StartTime,
double EndTime, long NumSteps)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `StartTime` — Start time for the time history integration.
- `EndTime` — End time for the time history integration.
- `NumSteps` — Number of steps used for the time history integration.

**Errors**

```
ERR7_ExceededResultCase, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_InvalidNumSteps,
ERR7_InvalidResultFile, ERR7_InvalidStartEndTimes,
ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7NewResFile`

Creates a new custom result file.

**Syntax**

```c
long St7NewResFile(long uID, char* FileName, long
ResultType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the new result file.
- `ResultType` — Result file type, one of stLinearStaticSolver, stLinearBucklingSolver, stNonlinearStaticSolver, stNaturalFrequencySolver, stLinearTransientDynamicSolver, stNonlinearTransientDynamicSolver, stSteadyHeatSolver, stTransientHeatSolver or stQuasiStaticSolver.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResFileAlreadyOpen, ERR7_ResFileContainsNoElements,
ERR7_ResFileContainsNoNodes, ERR7_ResFileUnsupportedType,
ERR7_UnknownError
```


---

### `St7OpenResFile`

Opens a specified custom result file.

**Syntax**

```c
long St7OpenResFile(long uID, char* FileName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the result file.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotEditSolverFiles, ERR7_CannotOpenResultFile,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidResultFile, ERR7_NoError,
ERR7_ResFileAlreadyOpen, ERR7_UnknownError
```


---

### `St7CloseResFile`

Closes the open custom result file.

**Syntax**

```c
long St7CloseResFile(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResFileCantSave, ERR7_ResFileNotOpen,
ERR7_UnknownError
```


---

### `St7SetResFileDescription`

Sets the description for a specified result file.

**Syntax**

```c
long St7SetResFileDescription(long uID, char* Name)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Name` — Result file description.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResFileNotOpen
```


---

### `St7GetResFileDescription`

Returns the description of a specified result file.

**Syntax**

```c
long St7GetResFileDescription(long uID, char* Name, long
MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `MaxStringLen` — Maximum number of characters allocated for Name.

**Output Parameters**

- `Name` — Result file description.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResFileNotOpen
```


---

### `St7SetResFileNumCases`

Sets the number of result cases in the open result file.

**Syntax**

```c
long St7SetResFileNumCases(long uID, long NumCases)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NumCases` — Number of result cases in the file.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResFileInvalidNumCases, ERR7_ResFileNotOpen
```


---

### `St7SetResFileCaseName`

Sets the name of a specified result case.

**Syntax**

```c
long St7SetResFileCaseName(long uID, long CaseNum, char*
CaseName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Result case number.
- `CaseName` — Result case name.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResFileInvalidCase, ERR7_ResFileInvalidName,
ERR7_ResFileNotOpen
```


---

### `St7AssociateResFileCase`

Associate load and freedom cases with a specified result case.

**Syntax**

```c
long St7AssociateResFileCase(long uID, long CaseNum, long
LoadCase, long FreedomCase)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Result case number.
- `LoadCase` — Load case number.
- `FreedomCase` — Freedom case number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResFileAssociationNotAllowed, ERR7_ResFileInvalidCase,
ERR7_ResFileNotOpen
```


---

### `St7AssociateResFileStage`

Associate a stage with a specified result case.

**Syntax**

```c
long St7AssociateResFileStage(long uID, long CaseNum, long
StageNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Result case number.
- `StageNum` — Stage number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_StageDoesNotExist, ERR7_ResFileInvalidCase,
ERR7_ResFileNotOpen
```


---

### `St7SetResFileMode`

Sets the modal frequency for the specified result case.

**Syntax**

```c
long St7SetResFileMode(long uID, long CaseNum, double Mode)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Result case number.
- `Mode` — Modal frequency (Hz) for natural frequency results, or linear buckling factor for linear buckling results.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResFileIncompatibleQuantity, ERR7_ResFileInvalidCase,
ERR7_ResFileNotOpen
```


---

### `St7GetResFileMode`

Returns the modal frequency assigned to the specified result case.

**Syntax**

```c
long St7GetResFileMode(long uID, long CaseNum, double*
Mode)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Result case number.

**Output Parameters**

- `Mode` — Modal frequency (Hz) for natural frequency results, or linear buckling factor for linear buckling results.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResFileIncompatibleQuantity, ERR7_ResFileInvalidCase,
ERR7_ResFileNotOpen
```


---

### `St7SetResFileTime`

Sets the integration time for a specified result case, in seconds.

**Syntax**

```c
long St7SetResFileTime(long uID, long CaseNum, double Time)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Result case number.
- `Time` — Integration time in seconds.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResFileIncompatibleQuantity, ERR7_ResFileInvalidCase,
ERR7_ResFileNotOpen
```


---

### `St7GetResFileTime`

Returns the integration time assigned to a specified result case, in seconds.

**Syntax**

```c
long St7GetResFileTime(long uID, long CaseNum, double*
Time)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Result case number.

**Output Parameters**

- `Time` — Integration time in seconds.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResFileIncompatibleQuantity, ERR7_ResFileInvalidCase,
ERR7_ResFileNotOpen
```


---

### `St7SetResFileTimeUnit`

Sets the time units displayed in the specified result file. Note that this setting does
not affect the time input to St7SetResFileTime which is always in seconds.

**Syntax**

```c
long St7SetResFileTimeUnit(long uID, long TimeUnit)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `TimeUnit` — Integration time unit, one of tuMilliSec, tuSec, tuMin, tuHour or tuDay.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidTimeUnit, ERR7_NoError,
ERR7_ResFileIncompatibleQuantity, ERR7_ResFileNotOpen
```


---

### `St7GetResFileTimeUnit`

Returns the time units displayed in the specified result file. Note that this setting
does not affect the time output by St7GetResFileTime which is always in seconds.

**Syntax**

```c
long St7GetResFileTimeUnit(long uID, long* TimeUnit)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `TimeUnit` — Integration time unit, one of tuMilliSec, tuSec, tuMin, tuHour or tuDay.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResFileIncompatibleQuantity, ERR7_ResFileNotOpen
```


---

### `St7SetResFileQuantity`

Includes a specified result quantity in a given result case.

**Syntax**

```c
long St7SetResFileQuantity(long uID, long CaseNum, long
Entity, long Quantity)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Result case number.
- `Entity` — Entity type, one of tyNODE, tyBEAM, tyPLATE or tyBRICK.
- `Quantity` — Result quantity, see Custom Results for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResFileDoesNotHaveEntity,
ERR7_ResFileIncompatibleQuantity, ERR7_ResFileInvalidCase,
ERR7_ResFileInvalidQuantity, ERR7_ResFileNotOpen
```


---

### `St7GetResFileQuantity`

Returns the status of an element result quantity in a given result case.

**Syntax**

```c
long St7GetResFileQuantity(long uID, long CaseNum, long
Entity, long Quantity, bool* State)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Result case number.
- `Entity` — Entity type, one of tyNODE, tyBEAM, tyPLATE or tyBRICK.
- `Quantity` — Result quantity, see Custom Results for additional information.

**Output Parameters**

- `State` — btTrue if the specified entity result quantity is included in the given result case.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResFileDoesNotHaveEntity,
ERR7_ResFileIncompatibleQuantity, ERR7_ResFileInvalidCase,
ERR7_ResFileInvalidQuantity, ERR7_ResFileNotOpen
```


---

### `St7ClearResFileQuantity`

Removes a specified result quantity from a given result case.

**Syntax**

```c
long St7ClearResFileQuantity(long uID, long CaseNum, long
Entity, long Quantity)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Result case number.
- `Entity` — Entity type, one of tyNODE, tyBEAM, tyPLATE or tyBRICK.
- `Quantity` — Result quantity, see Custom Results for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResFileCantClearQuantity,
ERR7_ResFileDoesNotHaveEntity,
ERR7_ResFileIncompatibleQuantity, ERR7_ResFileInvalidCase,
ERR7_ResFileInvalidQuantity, ERR7_ResFileNotOpen
```


---

### `St7SetResFileNodeResult`

Sets the specified nodal result quantities for a given node and result case.

**Syntax**

```c
long St7SetResFileNodeResult(long uID, long CaseNum, long
Node, long Quantity, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Result case number.
- `Node` — Node number.
- `Quantity` — Result quantity; one of rtNodeDisp, rtNodeVel, rtNodeAcc, rtNodeReact, rtNodeTemp or rtNodeFlux.
- `Doubles[0..5]` — An array defining the specified nodal result quantity. See Custom Results for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResFileInvalidCase,
ERR7_ResFileInvalidQuantity, ERR7_ResFileNotOpen,
ERR7_ResFileQuantityNotExist
```


---

### `St7GetResFileNodeResult`

Returns the specified nodal result quantities for a given node and result case.

**Syntax**

```c
long St7GetResFileNodeResult(long uID, long CaseNum, long
Node, long Quantity, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Result case number.
- `Node` — Node number.
- `Quantity` — Result quantity; one of rtNodeDisp, rtNodeVel, rtNodeAcc, rtNodeReact, rtNodeTemp or rtNodeFlux.

**Output Parameters**

- `Doubles[0..5]` — An array defining the specified nodal result quantity. See Custom Results for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResFileInvalidCase,
ERR7_ResFileInvalidQuantity, ERR7_ResFileNotOpen,
ERR7_ResFileQuantityNotExist
```


---

### `St7SetResFileBeamStations`

Sets the number of result stations used to store beam results for a specified result
case.

**Syntax**

```c
long St7SetResFileBeamStations(long uID, long CaseNum, long
Stations)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Result case number.
- `Stations` — Number of result stations along the length of beam elements in the specified result case. Note that only two stations (corresponding to the beam ends) are permitted for heat transfer results.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidNumBeamStations, ERR7_NoError,
ERR7_ResFileInvalidCase, ERR7_ResFileNotOpen
```


---

### `St7GetResFileBeamStations`

Returns the number of result stations used to store beam results for a specified
result case.

**Syntax**

```c
long St7GetResFileBeamStations(long uID, long CaseNum,
long* Stations)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Result case number.

**Output Parameters**

- `Stations` — Number of result stations along the length of beam elements in the specified result case.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResFileInvalidCase, ERR7_ResFileNotOpen
```


---

### `St7SetResFileBeamResult`

Sets the specified beam result quantities for a given beam element and result
case.

**Syntax**

```c
long St7SetResFileBeamResult(long uID, long CaseNum, long
Beam, long Quantity, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Result case number.
- `Beam` — Beam number.
- `Quantity` — Result quantity; one of rtBeamForce, rtBeamStrain, rtBeamNodeReact or rtBeamFlux.
- `Doubles[..]` — An array defining the specified beam result quantity at each station along the beam. The quantities for the ith station are stored in a block starting at: Doubles[(i-1)*kBeamResFileForceSize] - for rtBeamForce Doubles[(i-1)*kBeamResFileStrainSize] - for rtBeamStrain Doubles[(i-1)*kBeamResFileReactSize] - for rtBeamNodeReact Doubles[(i-1)*kBeamResFileFluxSize] - for rtBeamFlux. See Custom Results for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResFileInvalidCase,
ERR7_ResFileInvalidQuantity, ERR7_ResFileNotOpen,
ERR7_ResFileQuantityNotExist
```


---

### `St7GetResFileBeamResult`

Returns the specified beam result quantities for a given beam element and result
case.

**Syntax**

```c
long St7GetResFileBeamResult(long uID, long CaseNum, long
Beam, long Quantity, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Result case number.
- `Beam` — Beam number.
- `Quantity` — Result quantity; one of rtBeamForce, rtBeamStrain, rtBeamNodeReact or rtBeamFlux.

**Output Parameters**

- `Doubles[..]` — An array defining the specified beam result quantity at each station along the beam. The quantities for the ith station are stored in a block starting at: Doubles[(i-1)*kBeamResFileForceSize] - for rtBeamForce Doubles[(i-1)*kBeamResFileStrainSize] - for rtBeamStrain Doubles[(i-1)*kBeamResFileReactSize] - for rtBeamNodeReact Doubles[(i-1)*kBeamResFileFluxSize] - for rtBeamFlux. See Custom Results for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResFileInvalidCase,
ERR7_ResFileInvalidQuantity, ERR7_ResFileNotOpen,
ERR7_ResFileQuantityNotExist
```


---

### `St7SetResFilePlateResult`

Sets the specified plate result quantities for a given plate element and result case.

**Syntax**

```c
long St7SetResFilePlateResult(long uID, long CaseNum, long
Plate, long Quantity, bool NonlinearMaterial, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Result case number.
- `Plate` — Plate number.
- `Quantity` — Result quantity; one of rtPlateStress, rtPlateStrain, rtPlateNodeReact or rtPlateFlux.
- `NonlinearMaterial` — btTrue if the results correspond to a material nonlinear analysis.
- `Doubles[..]` — An array defining the specified plate result quantity at each Gauss point on the plate. The results at the ith Gauss point are stored in a block starting at: Doubles[(i-1)*kPlateShellResFileStressSize] - for rtPlateStress Doubles[(i-1)*kPlateShellResFileStrainSize] - for rtPlateStrain. Doubles[(i-1)*kPlateResFileReactSize] - for rtPlateNodeReact. Doubles[(i-1)*kPlateResFileFluxSize] - for rtPlateFlux. Exceptionally for two-dimensional plates, the results at the ith Gauss point are stored in a block starting at: Doubles[(i-1)*kPlate2DResFileStressSize] - for rtPlateStress Doubles[(i-1)*kPlate2DResFileStrainSize] - for rtPlateStrain. See Custom Results for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResFileInvalidCase,
ERR7_ResFileInvalidQuantity, ERR7_ResFileNotOpen,
ERR7_ResFileQuantityNotExist
```


---

### `St7GetResFilePlateResult`

Returns the specified plate result quantities for a given plate element and result
case.

**Syntax**

```c
long St7GetResFilePlateResult(long uID, long CaseNum, long
Plate, long Quantity, bool* NonlinearMaterial, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Result case number.
- `Plate` — Plate number.
- `Quantity` — Result quantity; one of rtPlateStress, rtPlateStrain, rtPlateNodeReact or rtPlateFlux.

**Output Parameters**

- `NonlinearMaterial` — btTrue if the results correspond to a material nonlinear analysis.
- `Doubles[..]` — An array defining the specified plate result quantity at each Gauss point on the plate. The results at the ith Gauss point are stored in a block starting at: Doubles[(i-1)*kPlateShellResFileStressSize] - for rtPlateStress Doubles[(i-1)*kPlateShellResFileStrainSize] - for rtPlateStrain. Doubles[(i-1)*kPlateResFileReactSize] - for rtPlateNodeReact. Doubles[(i-1)*kPlateResFileFluxSize] - for rtPlateFlux. Exceptionally for two-dimensional plates, the results at the ith Gauss point are stored in a block starting at: Doubles[(i-1)*kPlate2DResFileStressSize] - for rtPlateStress Doubles[(i-1)*kPlate2DResFileStrainSize] - for rtPlateStrain. See Custom Results for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResFileInvalidCase,
ERR7_ResFileInvalidQuantity, ERR7_ResFileNotOpen,
ERR7_ResFileQuantityNotExist
```


---

### `St7SetResFileBrickResult`

Sets the specified brick result quantities for a given brick element and result case.

**Syntax**

```c
long St7SetResFileBrickResult(long uID, long CaseNum, long
Brick, long Quantity, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Result case number.
- `Brick` — Brick number.
- `Quantity` — Result quantity; one of rtBrickStress, rtBrickStrain, rtBrickNodeReact or rtBrickFlux.
- `Doubles[..]` — An array defining the specified brick result quantity at each Gauss point on the brick. The results at the ith Gauss point are stored in a block starting at: Doubles[(i-1)*kBrickResFileStressSize] - for rtBrickStress Doubles[(i-1)*kBrickResFileStrainSize] - for rtBrickStrain. Doubles[(i-1)*kBrickResFileReactSize] - for rtBrickNodeReact. Doubles[(i-1)*kBrickResFileFluxSize] - for rtBrickFlux. See Custom Results for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResFileInvalidCase,
ERR7_ResFileInvalidQuantity, ERR7_ResFileNotOpen,
ERR7_ResFileQuantityNotExist
```


---

### `St7GetResFileBrickResult`

Returns the specified brick result quantities for a given brick element and result
case.

**Syntax**

```c
long St7GetResFileBrickResult(long uID, long CaseNum, long
Brick, long Quantity, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
