---
title: "Solver – General"
source: "Strand7 R246 API Manual"
pages: 844–880
---

# Solver – General

Solver – Steady-State and Transient Heat


---

### `St7SetSolverHeatNonlinear`

Sets the state of the nonlinear analysis option for the Heat solvers. Models
containing radiative boundary conditions or temperature dependent material
conditions should use the nonlinear analysis option.

**Syntax**

```c
long St7SetSolverHeatNonlinear(long uID, bool Nonlinear)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Nonlinear` — btTrue to perform nonlinear heat analyses. The nonlinear flag must be active to solve problems incorporating radiative boundary conditions or temperature dependent material properties.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetSolverScheme`

Sets the scheme used for the solution of the linear system arising from the Finite
Element model.

**Syntax**

```c
long St7SetSolverScheme(long uID, long Solver)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Solver` — Solver scheme, one of stSkyline, stSparse or stIterativePCG.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidSolverScheme, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_SparseSolverNotLicenced
```


---

### `St7GetSolverScheme`

Returns the scheme assigned for the solution of the linear system arising from the
Finite Element model.

**Syntax**

```c
long St7GetSolverScheme(long uID, long* Solver)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `Solver` — Solver scheme, one of stSkyline, stSparse or stIterativePCG.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetSolverSort`

Sets the node number re-ordering strategy used by the solver.

**Syntax**

```c
long St7SetSolverSort(long uID, long Sort)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Sort` — Re-ordering method, one of rnNone, rnTree, rnGeometry or rnAMD.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidSortOption, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetSolverSort`

Returns the node number re-ordering strategy assigned to the solver.

**Syntax**

```c
long St7GetSolverSort(long uID, long* Sort)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `Sort` — Re-ordering method, one of rnNone, rnTree, rnGeometry or rnAMD.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetSolverTreeStartNumber`

Sets the starting node number for the Tree type re-ordering strategy.

**Syntax**

```c
long St7SetSolverTreeStartNumber(long uID, long Start)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Start` — Starting node number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetSolverTreeStartNumber`

Returns the starting node number assigned for the Tree type re-ordering strategy.

**Syntax**

```c
long St7GetSolverTreeStartNumber(long uID, long* Start)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `Start` — Starting node number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetSolverActiveStage`

Sets the active stage for the analysis.

**Syntax**

```c
long St7SetSolverActiveStage(long uID, long Stage)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Stage` — Stage number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_StageDoesNotExist
```


---

### `St7GetSolverActiveStage`

Returns the active stage assigned for the analysis.

**Syntax**

```c
long St7GetSolverActiveStage(long uID, long* Stage)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `Stage` — Stage number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetSolverTemperatureDependence`

Specifies the type of temperature dependence used for Quasi-Static, Nonlinear
Static and Nonlinear Transient analysis.

**Syntax**

```c
long St7SetSolverTemperatureDependence(long uID, long
TempType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `TempType` — Temperature dependence type, either tdNone or tdCombined.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidTempDependenceType, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetSolverTemperatureDependence`

Returns the type of temperature dependence used for Quasi-Static, Nonlinear
Static and Nonlinear Transient analysis.

**Syntax**

```c
long St7GetSolverTemperatureDependence(long uID, long*
TempType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `TempType` — Temperature dependence type, either tdNone or tdCombined.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetSolverLoadCaseTemperatureDependence`

Sets the load case used to specify the temperature dependence for Linear Static,
Load Influence, Natural Frequency and Linear Transient analysis.

**Syntax**

```c
long St7SetSolverLoadCaseTemperatureDependence(long uID,
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

### `St7GetSolverLoadCaseTemperatureDependence`

Returns the load case assigned to specify the temperature dependence for
Linear Static, Load Influence, Natural Frequency and Linear Transient analysis.

**Syntax**

```c
long St7GetSolverLoadCaseTemperatureDependence(long uID,
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

### `St7SetSolverFreedomCase`

Sets the freedom case used for the analysis. Multiple freedom cases may be
specified for Linear Static analysis using the St7EnableLSALoadCase function.

**Syntax**

```c
long St7SetSolverFreedomCase(long uID, long CaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Freedom case number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetSolverFreedomCase`

Returns the freedom case assigned for the analysis. Multiple freedom cases may
be specified for Linear Static analysis using the St7EnableLSALoadCase function.

**Syntax**

```c
long St7GetSolverFreedomCase(long uID, long* CaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `CaseNum` — Freedom case number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetDampingType`

Sets the type of damping used for the analysis.

**Syntax**

```c
long St7SetDampingType(long uID, long DampType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `DampType` — Damping type, one of dtNoDamping, dtRayleighDamping, dtModalDamping or dtViscousDamping.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidDampingType,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetDampingType`

Returns the type of damping assigned for the analysis.

**Syntax**

```c
long St7GetDampingType(long uID, long* DampType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `DampType` — Damping type, one of dtNoDamping, dtRayleighDamping, dtModalDamping or dtViscousDamping.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetRayleighFactors`

Sets the Rayleigh damping factors used for the analysis.

**Syntax**

```c
long St7SetRayleighFactors(long uID, long RayleighMode,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `RayleighMode` — Type of Rayleigh factors specified, either rmSetFrequencies or rmSetAlphaBeta.
- `Doubles[0..5]` — rmSetAlphaBeta: [0..1] - Alpha, Beta values respectively. rmSetFrequencies: [0..1] - Frequency 1 and 2 respectively (Hz). [2..3] - Ratio 1 and 2 respectively. [4..5] - Minimum and maximum frequency respectively.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidRayleighMode, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetRayleighFactors`

Returns the Rayleigh damping factors assigned for the analysis.

**Syntax**

```c
long St7GetRayleighFactors(long uID, long* RayleighMode,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `RayleighMode` — Type of Rayleigh factors specified, either rmSetFrequencies or rmSetAlphaBeta.
- `Doubles[0..5]` — rmSetAlphaBeta: [0..1] - Alpha, Beta values respectively. rmSetFrequencies: [0..1] - Frequency 1 and 2 respectively. [2..3] - Ratio 1 and 2 respectively. [4..5] - Minimum and maximum frequency respectively.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetSoilFluidOptions`

Sets the soil/fluid options for the analysis. These parameters are only used for
models containing soil or fluid properties.

**Syntax**

```c
long St7SetSoilFluidOptions(long uID, long CaseNum, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Gravitational load case number.
- `Doubles[0..2]` — A 3 element array describing the default fluid level, fluid mass density and fluid bulk modulus respectively.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetSoilFluidOptions`

Returns the soil/fluid parameters assigned for the analysis. These parameters are
only used for models containing soil or fluid properties.

**Syntax**

```c
long St7GetSoilFluidOptions(long uID, long* CaseNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `CaseNum` — Gravitational load case number.
- `Doubles[0..2]` — A 3 element array describing the default fluid level, fluid mass density and fluid bulk modulus respectively.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetSturmCheck`

Assigns the state of the Sturm Check option, for eigenvalue analyses.

**Syntax**

```c
long St7SetSturmCheck(long uID, bool DoSturm)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `DoSturm` — btTrue to enable the Sturm Check.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetSturmCheck`

Returns the state of the Sturm Check option, for eigenvalue analyses.

**Syntax**

```c
long St7GetSturmCheck(long uID, bool* DoSturm)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `DoSturm` — btTrue to enable the Sturm Check.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetSolverNonlinearGeometry`

Sets the state of the Nonlinear geometry option for Nonlinear analyses.

**Syntax**

```c
long St7SetSolverNonlinearGeometry(long uID, bool
NonlinearGeometry)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NonlinearGeometry` — btTrue to enable the Nonlinear geometry option.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetSolverNonlinearGeometry`

Returns the state assigned for the Nonlinear Geometry option for Nonlinear
analyses.

**Syntax**

```c
long St7GetSolverNonlinearGeometry(long uID, bool*
NonlinearGeometry)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NonlinearGeometry` — btTrue to enable the Nonlinear geometry option.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetSolverNonlinearMaterial`

Sets the state of the Nonlinear material option for Nonlinear analyses.

**Syntax**

```c
long St7SetSolverNonlinearMaterial(long uID, bool
NonlinearMaterial)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NonlinearMaterial` — btTrue to enable the Nonlinear material option.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetSolverNonlinearMaterial`

Returns the state assigned for the Nonlinear Material option for Nonlinear analyses.

**Syntax**

```c
long St7GetSolverNonlinearMaterial(long uID, bool*
NonlinearMaterial)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NonlinearMaterial` — btTrue to enable the Nonlinear material option.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetSolverCreep`

Sets the state of the Creep option for creep analyses.

**Syntax**

```c
long St7SetSolverCreep(long uID, bool Creep)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Creep` — btTrue to enable the Creep option.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetSolverCreep`

Returns the state assigned for the Creep option for creep analyses.

**Syntax**

```c
long St7GetSolverCreep(long uID, bool* Creep)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `Creep` — btTrue to enable the Creep option.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetSolverIncludeKG`

Sets the state of the KG parameter for Nonlinear analyses. This option controls the
use of the Geometric Stiffness matrix (KG).

**Syntax**

```c
long St7SetSolverIncludeKG(long uID, bool IncludeKG)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `IncludeKG` — btTrue to include the KG matrix.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetSolverIncludeKG`

Returns the state assigned for the KG option for nonlinear analyses. This option
controls the use of the Geometric Stiffness matrix (KG).

**Syntax**

```c
long St7GetSolverIncludeKG(long uID, bool* IncludeKG)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `IncludeKG` — btTrue to include the KG matrix.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetSolverStressStiffening`

Sets the state of the stress stiffening option for Linear Transient analyses.

**Syntax**

```c
long St7SetSolverStressStiffening(long uID, bool
AddStressStiffening)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `AddStressStiffening` — btTrue to include the stress stiffening effects.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetSolverStressStiffening`

Returns the state assigned for the stress stiffening option for Linear Transient
analyses.

**Syntax**

```c
long St7GetSolverStressStiffening(long uID, bool*
AddStressStiffening)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `AddStressStiffening` — btTrue to include the stress stiffening effects.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetEntityResult`

Sets the state for the specified entity result. Only enabled entity results are written
to the result file.

**Syntax**

```c
long St7SetEntityResult(long uID, long Result, long State)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Result` — See Solver Options for additional information.
- `State` — btTrue to enable the specified result.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidResultType, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetEntityResult`

Returns the state for the specified entity result. Only enabled entity results are
written to the result file.

**Syntax**

```c
long St7GetEntityResult(long uID, long Result, long* State)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Result` — See Solver Options for additional information.

**Output Parameters**

- `State` — btTrue to enable the specified result.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidResultType, ERR7_NoError
```


---

### `St7SetResultSurfaceBricksOnly`

Sets the state of the Surface bricks only option for the analysis.

**Syntax**

```c
long St7SetResultSurfaceBricksOnly(long uID, long State)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `State` — btTrue to calculate the results for Surface bricks only.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetResultSurfaceBricksOnly`

Returns the state of the Surface bricks only option assigned for the analysis.

**Syntax**

```c
long St7GetResultSurfaceBricksOnly(long uID, long* State)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `State` — btTrue to calculate the results for Surface bricks only.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetResultLimit`

Assigns a limit for the calculated entity stress results.

**Syntax**

```c
long St7SetResultLimit(long uID, long Entity, long State,
double Limit)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Entity type, either tyPLATE or tyBRICK.
- `State` — btTrue to enforce limits when calculating results.
- `Limit` — Stress result limit value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetResultLimit`

Returns the limit assigned for the specified entity stress results.

**Syntax**

```c
long St7GetResultLimit(long uID, long Entity, long* State,
double* Limit)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Entity type, either tyPLATE or tyBRICK.

**Output Parameters**

- `State` — btTrue to enforce limits when calculating results.
- `Limit` — Stress result limit value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError
```


---

### `St7EnableResultGroup`

Enables the specified group results for the analysis. Only element results
corresponding to enabled groups are written to the result file.

**Syntax**

```c
long St7EnableResultGroup(long uID, long GroupID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `GroupID` — Group ID number to enable.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_GroupIdDoesNotExist,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7DisableResultGroup`

Disables the specified group results for the analysis. Only element results
corresponding to enabled groups are written to the result file.

**Syntax**

```c
long St7DisableResultGroup(long uID, long GroupID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `GroupID` — Group ID number to disable.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_GroupIdDoesNotExist,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetResultGroupState`

Returns the state of the group results for the analysis. Only element results
corresponding to enabled groups are written to the result file.

**Syntax**

```c
long St7GetResultGroupState(long uID, long GroupID, bool*
State)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `GroupID` — Group ID number.

**Output Parameters**

- `State` — btTrue if the specified group is enabled.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_GroupIdDoesNotExist,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7EnableResultProperty`

Enables the specified property results for the analysis. Only element results
corresponding to enabled properties are written to the result file.

**Syntax**

```c
long St7EnableResultProperty(long uID, long Entity, long
PropNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Property type, one of ptBEAMPROP, ptPLATEPROP or ptBRICKPROP.
- `PropNum` — Property number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7DisableResultProperty`

Disables the specified property results for the analysis. Only element results
corresponding to enabled properties are written to the result file.

**Syntax**

```c
long St7DisableResultProperty(long uID, long Entity, long
PropNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Property type, one of ptBEAMPROP, ptPLATEPROP or ptBRICKPROP.
- `PropNum` — Property number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7GetResultPropertyState`

Returns the state of the specified property results for the analysis. Only element
results corresponding to enabled properties are written to the result file.

**Syntax**

```c
long St7GetResultPropertyState(long uID, long Entity, long
PropNum, bool* State)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Property type, one of ptBEAMPROP, ptPLATEPROP or ptBRICKPROP.
- `PropNum` — Property number.

**Output Parameters**

- `State` — btTrue if the specified property results are enabled.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_UnknownProperty
```


---

### `St7SetResultFileName`

Sets the name of the results file for the analysis.

**Syntax**

```c
long St7SetResultFileName(long uID, char* FileName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the results file.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetResultLogFileName`

Sets the name of the solver log-file for the analysis.

**Syntax**

```c
long St7SetResultLogFileName(long uID, char* LogName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LogName` — Full path and name of the log-file.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetStaticRestartFile`

Sets the name of the static restart file for the analysis.

**Syntax**

```c
long St7SetStaticRestartFile(long uID, char* FileName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the static restart file.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetStaticRestartFile`

Returns the name of the static restart file assigned for the analysis.

**Syntax**

```c
long St7GetStaticRestartFile(long uID, char* FileName, long
MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `MaxStringLen` — Maximum number of characters allocated for FileName.

**Output Parameters**

- `FileName` — Full path and name for the static restart file.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetDynamicRestartFile`

Sets the name of the dynamic restart file for the analysis.

**Syntax**

```c
long St7SetDynamicRestartFile(long uID, char* FileName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the dynamic restart file.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetDynamicRestartFile`

Returns the name of the dynamic restart file assigned to the analysis.

**Syntax**

```c
long St7GetDynamicRestartFile(long uID, char* FileName,
long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `MaxStringLen` — Maximum number of characters allocated for FileName.

**Output Parameters**

- `FileName` — Full path and name for the dynamic restart file.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetQuasiStaticRestartFile`

Sets the name of the quasi-static restart file for the analysis.

**Syntax**

```c
long St7SetQuasiStaticRestartFile(long uID, char* FileName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the quasi-static restart file.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetQuasiStaticRestartFile`

Gets the name of the quasi-static restart file for the analysis.

**Syntax**

```c
long St7GetQuasiStaticRestartFile(long uID, char* FileName,
long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `MaxStringLen` — Maximum number of characters allocated for FileName.

**Output Parameters**

- `FileName` — Full path and name for the quasi-static restart file.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetNodeHistoryFile`

Sets the name of the node history file for the analysis.

**Syntax**

```c
long St7SetNodeHistoryFile(long uID, char* FileName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the node history file.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetNodeHistoryFile`

Gets the name of the node history file for the analysis.

**Syntax**

```c
long St7GetNodeHistoryFile(long uID, char* FileName, long
MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `MaxStringLen` — Maximum number of characters allocated for FileName.

**Output Parameters**

- `FileName` — Full path and name for the node history file.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7EnableSaveRestart`

Enables the Save Restart option for the analysis.

**Syntax**

```c
long St7EnableSaveRestart(long uID)
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

### `St7DisableSaveRestart`

Disables the Save Restart option for the analysis.

**Syntax**

```c
long St7DisableSaveRestart(long uID)
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

### `St7EnableSaveLastRestartStep`

Enables the Save Last Restart Step option for the analysis.

**Syntax**

```c
long St7EnableSaveLastRestartStep(long uID)
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

### `St7DisableSaveLastRestartStep`

Disables the Save Last Restart Step option for the analysis.

**Syntax**

```c
long St7DisableSaveLastRestartStep(long uID)
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

### `St7SetSolverDefaultsLogical`

Sets a series of Boolean parameters for the analysis.

**Syntax**

```c
long St7SetSolverDefaultsLogical(long uID, long Parameter,
bool pValue)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Parameter` — Solver logical parameter, see Solver Options for additional information.
- `pValue` — Boolean value, either btTrue or btFalse.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidSolverParameter, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetSolverDefaultsLogical`

Returns the state assigned for a set of Boolean parameters for the analysis.

**Syntax**

```c
long St7GetSolverDefaultsLogical(long uID, long Parameter,
bool* pValue)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Parameter` — Solver logical parameter, see Solver Options for additional information.

**Output Parameters**

- `pValue` — Boolean value, either btTrue or btFalse.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidSolverParameter, ERR7_NoError
```


---

### `St7SetSolverDefaultsInteger`

Sets the integer solver default values.

**Syntax**

```c
long St7SetSolverDefaultsInteger(long uID, long Parameter,
long pValue)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Parameter` — Solver integer parameter, see Solver Options for additional information.
- `pValue` — Integer value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidSolverParameter, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetSolverDefaultsInteger`

Returns the value assigned to the integer solver defaults.

**Syntax**

```c
long St7GetSolverDefaultsInteger(long uID, long Parameter,
long* pValue)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Parameter` — Solver integer parameter, see Solver Options for additional information.

**Output Parameters**

- `pValue` — Integer value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidSolverParameter, ERR7_NoError
```


---

### `St7SetSolverDefaultsDouble`

Sets the double solver default values.

**Syntax**

```c
long St7SetSolverDefaultsDouble(long uID, long Parameter,
double pValue)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Parameter` — Solver double parameter, see Solver Options for additional information.
- `pValue` — Double value.
