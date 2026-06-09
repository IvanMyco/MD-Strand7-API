---
title: "Results"
source: "Strand7 R246 API Manual"
pages: 884–908
---

# Results

ERR7_InvalidSolverMode, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_UnknownError, ERR7_UnknownSolver


---

### `St7CheckSolverRunning`

Returns the execution state for the specified solver process.

**Syntax**

```c
long St7CheckSolverRunning(long ProcessID, bool* IsRunning)
```

**Input Parameters**

- `ProcessID` — Solver process ID number.

**Output Parameters**

- `IsRunning` — btTrue if the solver process is currently executing.

**Errors**

```
ERR7_NoError
```


---

### `St7GetResultCaseName`

Returns the name of the specified result case in the result file currently open.

**Syntax**

```c
long St7GetResultCaseName(long uID, long CaseNum, char*
CaseName, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Result case number.
- `MaxStringLen` — Maximum number of characters allocated for CaseName.

**Output Parameters**

- `CaseName` — Result case name.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededResultCase, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7GetResultFreedomCaseName`

Returns the name of the freedom case in the result file currently open.

**Syntax**

```c
long St7GetResultFreedomCaseName(long uID, char* CaseName,
long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `MaxStringLen` — Maximum number of characters allocated for CaseName.

**Output Parameters**

- `CaseName` — Result freedom case name.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileNotOpen
```


---

### `St7GetResultCaseConvergence`

Returns the convergence of the specified result case in the result file currently
open.

**Syntax**

```c
long St7GetResultCaseConvergence(long uID, long CaseNum,
bool* Converged)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Result case number.

**Output Parameters**

- `Converged` — btTrue if the specified result case is converged.

**Errors**

```
ERR7_ExceededResultCase, ERR7_FileNotOpen,
ERR7_IncompatibleResultFile, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7GetResultCaseTime`

Returns the integration time for the specified result case in the result file currently
open.

**Syntax**

```c
long St7GetResultCaseTime(long uID, long CaseNum, double*
Time)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Result case number.

**Output Parameters**

- `Time` — Integration time.

**Errors**

```
ERR7_ExceededResultCase, ERR7_FileNotOpen,
ERR7_IncompatibleResultFile, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7GetResultCaseFactor`

Returns a context dependent factor relevant to the opened result file.

**Syntax**

```c
long St7GetResultCaseFactor(long uID, long CaseNum, double*
Factor)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Result case number.

**Output Parameters**

- `Factor` — The value of this output depends on the analysis that produced the results file. Linear Static Analysis - undefined. Linear Buckling Analysis - buckling factor for mode CaseNum. Load Influence Analysis - undefined. Nonlinear Static Analysis - the fractional substep when CaseNum is a substep, otherwise zero for complete steps. Linear Transient Dynamic Analysis - integration time at CaseNum. Quasi-Static Analysis - integration time at CaseNum. Nonlinear Transient Dynamic Analysis - integration time at CaseNum. Natural Frequency Analysis - undefined. Harmonic Response Analysis - frequency (Hz) of applied load for CaseNum, when CaseNum is a harmonic result case. When a harmonic time history is generated, it is the time at CaseNum. Spectral Response Analysis - returns the natural frequency (Hz) of the mode from which the Spectral response arises when CaseNum is not combined; -1.0 when CaseNum is an SRSS combination; -2.0 when CaseNum is a CQC combination; -3.0 when CaseNum has been generated as any other combination. Steady State Heat Analysis - undefined. Transient Heat Analysis - integration time at CaseNum.

**Errors**

```
ERR7_ExceededResultCase, ERR7_FileNotOpen,
ERR7_IncompatibleResultFile, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7GetFrequency`

Returns the frequency for the specified results case.

**Syntax**

```c
long St7GetFrequency(long uID, long Mode, double* Freq)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Mode` — Result case/mode number.

**Output Parameters**

- `Freq` — Mode frequency (Hz).

**Errors**

```
ERR7_ExceededResultCase, ERR7_FileNotOpen,
ERR7_IncompatibleResultFile, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7GetInertiaReliefResults`

Returns the inertial results for the specified result case in inertial relief.

**Syntax**

```c
long St7GetInertiaReliefResults(long uID, long CaseNum,
double* InertiaRes)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Result case number.

**Output Parameters**

- `InertiaRes[0..11]` — [ipMassXIRA] - Mass component in the global X direction. [ipMassYIRA] - Mass component in the global Y direction. [ipMassZIRA] - Mass component in the global Z direction. [ipXcIRA] - Global X ordinate of the centre of mass. [ipYcIRA] - Global Y ordinate of the centre of mass. [ipZcIRA] - Global Z ordinate of the centre of mass. [ipAccXIRA] - Translational acceleration of the centre of mass in the global X direction. [ipAccYIRA] - Translational acceleration of the centre of mass in the global Y direction. [ipAccZIRA] - Translational acceleration of the centre of mass in the global Z direction. [ipAngAccXIRA] - Rotational acceleration about the global X axis in degrees/(time2). [ipAngAccYIRA] - Rotational acceleration about the global Y axis in degrees/(time2). [ipAngAccZIRA] - Rotational acceleration about the global Z axis in degrees/(time2).

**Errors**

```
ERR7_ExceededResultCase, ERR7_ResultCaseNotInertiaRelief,
ERR7_FileNotOpen, ERR7_IncompatibleResultFile,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7GetModalResultsNFA`

Returns the modal results from a natural frequency analysis for the specified
mode.

**Syntax**

```c
long St7GetModalResultsNFA(long uID, long Mode, double*
ModalRes)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Mode` — Result case/mode number.

**Output Parameters**

- `ModalRes[0..9]` — [ipFrequencyNFA] - Mode frequency (Hz). [ipModalMassNFA] - Modal mass. [ipModalStiffNFA] - Modal stiffness. [ipModalDampNFA] - Modal damping. [ipModalTMassP1] - Translational Mass Participation - first direction or total participation when not Global. [ipModalTMassP2] - Translational Mass Participation - second direction or zero when not Global. [ipModalTMassP3] - Translational Mass Participation - third direction or zero when not Global. [ipModalRMassP1] - Rotational Mass Participation - first direction or zero when not Global. [ipModalRMassP2] - Rotational Mass Participation - second direction or zero when not Global. [ipModalRMassP3] - Rotational Mass Participation - third direction or zero when not Global.

**Errors**

```
ERR7_ExceededResultCase, ERR7_FileNotOpen,
ERR7_IncompatibleResultFile, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7GetBuckFactor`

Returns the buckling factor for the specified result case.

**Syntax**

```c
long St7GetBuckFactor(long uID, long Mode, double* Fact)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Mode` — Result case/mode number.

**Output Parameters**

- `Fact` — Buckling factor.

**Errors**

```
ERR7_ExceededResultCase, ERR7_FileNotOpen,
ERR7_IncompatibleResultFile, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7GetNodeResult`

Returns the specified nodal result quantity in the Global Cartesian coordinate
system.

**Syntax**

```c
long St7GetNodeResult(long uID, long ResultType, long
NodeNum, long ResultCase, double* NodeRes)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `ResultType` — Nodal result quantity, see Node Results for additional information.
- `NodeNum` — Node number.
- `ResultCase` — Result case number.

**Output Parameters**

- `NodeRes[0..5]` — A 6 element array containing the nodal results. See Node Results for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededResultCase, ERR7_ExceededTotal,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileNotOpen,
ERR7_ResultQuantityNotAvailable, ERR7_UnknownResultType,
ERR7_UnknownUCS
```


---

### `St7GetNodeResultUCS`

Returns the specified nodal result in a UCS.

**Syntax**

```c
long St7GetNodeResultUCS(long uID, long ResultType, long
UCSId, long NodeNum, long ResultCase, double* NodeRes)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `ResultType` — Nodal result quantity, see Node Results for additional information.
- `UCSId` — UCS ID number.
- `NodeNum` — Node number.
- `ResultCase` — Result case number.

**Output Parameters**

- `NodeRes[0..5]` — A 6 element array containing the nodal results. See Node Results for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededResultCase, ERR7_ExceededTotal,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileNotOpen,
ERR7_ResultQuantityNotAvailable, ERR7_UnknownResultType,
ERR7_UnknownUCS
```


---

### `St7GetBeamResultArray`

Returns the specified beam result quantity at several stations along the length of
the beam. Additional stations are inserted to ensure that the maximum/minimum
results are captured.

**Syntax**

```c
long St7GetBeamResultArray(long uID, long ResultType, long
ResultSubType, long BeamNum, long MinStations, long


ResultCase, long* NumStations, long* NumColumns,
double* BeamPos, double* BeamRes)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `ResultType` — Beam result quantity, see Beam Results for additional information.
- `ResultSubType` — Beam result sub-type, see Beam Results for additional information.
- `BeamNum` — Beam number.
- `MinStations` — Minimum number of stations required.
- `ResultCase` — Result case number.

**Output Parameters**

- `NumStations` — Number of stations used.
- `NumColumns` — Number of result quantities returned at each station.
- `BeamPos[0..kMaxBeamResult-1]` — [0..NumStations-1] - an array of positions of the beam stations measured along the element from End1. Positions vary between zero and the length of the element.
- `BeamRes[0..kMaxBeamResult-1]` — [0..NumStations*NumColumns-1] - an array containing the beam results at each station. The results are returned in blocks of length NumColumns with the start of the ith block for the ith station at BeamRes[(i-1)*NumColumns]. See Beam Results for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededResultCase, ERR7_ExceededTotal,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidResultType, ERR7_NoError,
ERR7_ResultFileNotOpen, ERR7_ResultQuantityNotAvailable,
ERR7_TooManyBeamStations, ERR7_UnknownResultType
```


---

### `St7GetBeamResultArrayPos`

Returns the specified beam results at a series of positions along the length of the
beam.

**Syntax**

```c
long St7GetBeamResultArrayPos(long uID, long ResultType,
long ResultSubType, long BeamNum, long ResultCase,
long NumStations, double* BeamPos, long* NumColumns,
double* BeamRes)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `ResultType` — Beam result quantity, see Beam Results for additional information.
- `ResultSubType` — Beam result sub-type, see Beam Results for additional information.
- `BeamNum` — Beam number.
- `ResultCase` — Result case number.
- `NumStations` — Number of stations specified.
- `BeamPos[0..kMaxBeamResult-1]` — [0..NumStations-1] - an array of positions of the beam stations measured along the element from End1. Positions vary between zero and the length of the element.

**Output Parameters**

- `NumColumns` — Number of result quantities returned at each station.
- `BeamRes[0..kMaxBeamResult-1]` — [0..NumStations*NumColumns-1] - an array containing the beam results at each station. The results are returned in blocks of length NumColumns with the start of the ith block for the ith station at BeamRes[(i-1)*NumColumns]. See Beam Results for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededResultCase, ERR7_ExceededTotal,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidResultType, ERR7_NoError,
ERR7_ResultFileNotOpen, ERR7_ResultQuantityNotAvailable,
ERR7_TooManyBeamStations, ERR7_UnknownResultType
```


---

### `St7GetBeamResultEndPos`

Returns the specified beam result at the beam endpoints.

**Syntax**

```c
long St7GetBeamResultEndPos(long uID, long ResultType, long
ResultSubType, long BeamNum, long ResultCase, long*
NumColumns, double* BeamRes)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `ResultType` — Beam result quantity, see Beam Results for additional information.
- `ResultSubType` — Beam result sub-type, see Beam Results for additional information.
- `BeamNum` — Beam number.
- `ResultCase` — Result case number.

**Output Parameters**

- `NumColumns` — Number of result quantities returned at each endpoint.
- `BeamRes[0..kMaxBeamResult-1]` — [0..NumColumns-1] - a block of results for End1. [NumColumns..2*NumColumns-1] - a block of results for End2. See Beam Results for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededResultCase,
ERR7_ExceededTotal, ERR7_FileNotOpen, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileNotOpen,
ERR7_ResultQuantityNotAvailable, ERR7_TooManyBeamStations,
ERR7_UnknownResultType
```


---

### `St7GetBeamResultSinglePos`

Returns the specified beam result at a single position along the length of the
beam.

**Syntax**

```c
long St7GetBeamResultSinglePos(long uID, long ResultType,
long ResultSubType, long BeamNum, long ResultCase,
double Position, long* NumColumns, double* BeamRes)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `ResultType` — Beam result quantity, see Beam Results for additional information.
- `ResultSubType` — Beam result sub-type, see Beam Results for additional information.
- `BeamNum` — Beam number.
- `ResultCase` — Result case number.
- `Position` — The position of the beam station measured along the element from End1. Positions vary between zero and the length of the element.

**Output Parameters**

- `NumColumns` — Number of result quantities returned at the specified Position.
- `BeamRes[0..kMaxBeamResult-1]` — [0..NumColumns-1] - a block of results at the specified Position. See Beam Results for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededResultCase, ERR7_ExceededTotal,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidResultType, ERR7_NoError,
ERR7_ResultFileNotOpen, ERR7_ResultQuantityNotAvailable,
ERR7_TooManyBeamStations, ERR7_UnknownResultType
```


---

### `St7GetBeamReleaseResult`

Returns the release results for the specified beam.

**Syntax**

```c
long St7GetBeamReleaseResult(long uID, long BeamNum, long
ResultCase, bool* BeamReleased, double* ReleaseValue)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — Beam number.
- `ResultCase` — Result case number.

**Output Parameters**

- `BeamReleased[0..kMaxBeamRelease-1]` — An array containing the release status for the beam ends according to the local 123456 axis system for translational and rotational DoF. Values set to btTrue indicate a release for the corresponding DoF. [0..5] - release conditions for End1. [6..11] - release conditions for End2.
- `ReleaseValue[0..kMaxBeamRelease-1]` — An array containing the displacement results for the released beam end DoF. The same format as the BeamReleased array is used.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededResultCase, ERR7_ExceededTotal,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7GetPlateResultArray`

Returns the specified plate results at a series of sample locations on the element.

**Syntax**

```c
long St7GetPlateResultArray(long uID, long ResultType, long
ResultSubType, long PlateNum, long ResultCase, long
SampleLocation, long Surface, long Layer, long*
NumPoints, long* NumColumns, double* PlateResult)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `ResultType` — Plate result quantity, see Plate Results for additional information.
- `ResultSubType` — Plate result sub-type, see Plate Results for additional information.
- `PlateNum` — Plate number.
- `ResultCase` — Result case number.
- `SampleLocation` — Result sampling location, one of AtCentroid, AtGaussPoints, AtNodesAverageNever, AtNodesAverageAll or AtNodesAverageSame.
- `Surface` — Plate surface, one of psPlateMidPlane, psPlateZPlus or psPlateZMinus.
- `Layer` — Layer number for elements that reference a composite property or a plate reinforcement property, unused for other property types.

**Output Parameters**

- `NumPoints` — Number of sample locations used.
- `NumColumns` — Number of result quantities returned at each sample location.
- `PlateResult[0..kMaxPlateResult-1]` — [0..NumPoints*NumColumns-1] - An array containing the plate results at each sample location. The results are returned in blocks of length NumColumns, with the start of the ith block for the ith location at PlateResult[(i-1)*NumColumns]. See Plate Results for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededResultCase,
ERR7_ExceededTotal, ERR7_FileNotOpen, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_PlyDoesNotExist, ERR7_ResultFileNotOpen,
ERR7_ResultQuantityNotAvailable, ERR7_UnknownProperty,
ERR7_UnknownResultLocation, ERR7_UnknownResultType,
ERR7_UnknownSubType, ERR7_UnknownSurfaceLocation,
ERR7_UnknownUCS
```


---

### `St7SetPlateResultMaxJunctionAngle`

Sets the maximum junction angle used when calculating averaged plate results.

**Syntax**

```c
long St7SetPlateResultMaxJunctionAngle(long uID, double
MaxJunctionAngle)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `MaxJunctionAngle` — Maximum allowable angle between adjacent plate surfaces.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetPlateResultMaxJunctionAngle`

Returns the maximum junction angle used when calculating averaged plate
results.

**Syntax**

```c
long St7GetPlateResultMaxJunctionAngle(long uID, double*
MaxJunctionAngle)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `MaxJunctionAngle` — Maximum allowable angle between adjacent plate surfaces.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetPlateResultUserEquation`

Assigns a user defined equation for plate results. The calculated results can be
accessed using the St7GetPlateResultArray function.

**Syntax**

```c
long St7SetPlateResultUserEquation(long uID, char* Equation,
long TrigType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Equation` — User defined equation as a character array. See User Defined Results for additional information.
- `TrigType` — Type of angle arguments, either ipRadian or ipDegree.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidTrigType, ERR7_InvalidUserEquation,
ERR7_NoError
```


---

### `St7GetPlateResultUserEquation`

Returns the user defined equation assigned for plate results. The calculated results
can be accessed using the St7GetPlateResultArray function.

**Syntax**

```c
long St7GetPlateResultUserEquation(long uID, char* Equation,
long MaxStringLen, long* TrigType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `MaxStringLen` — Maximum number of characters allocated for Equation.

**Output Parameters**

- `Equation` — User defined equation as a character array. See User Defined Results for additional information.
- `TrigType` — Type of angle arguments, either ipRadian or ipDegree.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetPlateResultGaussPoints`

Returns the position of the result Gauss points for the specified plate.

**Syntax**

```c
long St7GetPlateResultGaussPoints(long uID, long PlateNum,
long ResultCase, long* NumGauss, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `ResultCase` — Result case number.

**Output Parameters**

- `NumGauss` — Number of Gauss points.
- `Doubles[0..26]` — [0..3*NumGauss-1] - An array containing the XYZ position of the result Gauss points in the Global Cartesian coordinate system. The positions are returned in blocks of length 3, with the position of the ith point starting at Doubles[(i-1)*3].

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededResultCase,
ERR7_ExceededTotal, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidResultType, ERR7_NoError,
ERR7_ResultFileNotOpen
```


---

### `St7GetBrickResultArray`

Returns the specified brick results at series of sample locations in the element.

**Syntax**

```c
long St7GetBrickResultArray(long uID, long ResultType, long
ResultSubType, long BrickNum, long ResultCase, long
SampleLocation, long* NumPoints, long* NumColumns,
double* BrickRes)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `ResultType` — Brick result quantity, see Brick Results for additional information.
- `ResultSubType` — Brick result sub-type, see Brick Results for additional information.
- `BrickNum` — Brick number.
- `ResultCase` — Result case number.
- `SampleLocation` — Result sampling location, one of AtCentroid, AtGaussPoints, AtNodesAverageNever, AtNodesAverageAll or AtNodesAverageSame.

**Output Parameters**

- `NumPoints` — Number of sampling points used.
- `NumColumns` — Number of result quantities returned at each sample location.
- `BrickRes[0..kMaxBrickResult-1]` — [0..NumPoints*NumColumns-1] - An array containing the brick results at each sample location. The results are returned in blocks of length NumColumns, with the start of the ith block for the ith location at BrickResult[(i-1)*NumColumns]. See Brick Results for additional information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededResultCase, ERR7_ExceededTotal,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileNotOpen,
ERR7_ResultQuantityNotAvailable, ERR7_UnknownResultLocation,
ERR7_UnknownResultType, ERR7_UnknownSubType,
ERR7_UnknownUCS
```


---

### `St7SetBrickResultUserEquation`

Assigns a user defined equation for brick results. The calculated results can be
accessed using the St7GetBrickResultArray function.

**Syntax**

```c
long St7SetBrickResultUserEquation(long uID, char* Equation,
long TrigType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Equation` — User defined equation as a character array. See User Defined Results for additional information.
- `TrigType` — Type of angle arguments, either ipRadian or ipDegree.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,


ERR7_InvalidTrigType, ERR7_InvalidUserEquation,
ERR7_NoError
```


---

### `St7GetBrickResultUserEquation`

Returns the user defined equation assigned for brick results. The calculated results
can be accessed using the St7GetBrickResultArray function.

**Syntax**

```c
long St7GetBrickResultUserEquation(long uID, char* Equation,
long MaxStringLen, long* TrigType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `MaxStringLen` — Maximum number of characters allocated for Equation.

**Output Parameters**

- `Equation` — User defined equation as a character array. See User Defined Results for additional information.
- `TrigType` — Type of angle arguments, either ipRadian or ipDegree.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetBrickResultGaussPoints`

Returns the position of the result Gauss points for the specified brick.

**Syntax**

```c
long St7GetBrickResultGaussPoints(long uID, long BrickNum,
long ResultCase, long* NumGauss, double* Doubles)
```
