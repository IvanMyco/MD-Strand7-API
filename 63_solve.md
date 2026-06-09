---
title: "Solve"
source: "Strand7 R246 API Manual"
pages: 881–883
---

# Solve

Solver – General
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidSolverParameter, ERR7_NoError,
ERR7_ResultFileIsOpen


---

### `St7GetSolverDefaultsDouble`

Returns the value assigned to the double solver defaults.

**Syntax**

```c
long St7GetSolverDefaultsDouble(long uID, long Parameter,
double* pValue)
```

**Input Parameters**

- `uID` — Strand7 model file D number.
- `Parameter` — Solver double parameter, see Solver Options for additional information.

**Output Parameters**

- `pValue` — Double value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidSolverParameter, ERR7_NoError
```


---

### `St7RunSolver`

Launches the specified Strand7 solver. All Strand7 solvers run as a separate
process to the calling application.

**Syntax**

```c
long St7RunSolver(long uID, long Solver, long Mode, long
Wait)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Solver` — Solver type, one of stLinearStaticSolver, stLinearBucklingSolver, stNonlinearStaticSolver, stNaturalFrequencySolver, stHarmonicResponseSolver, stSpectralResponseSolver, stLinearTransientDynamicSolver, stNonlinearTransientDynamicSolver, stSteadyHeatSolver, stTransientHeatSolver, stLoadInfluenceSolver, stQuasiStaticSolver.
- `Mode` — Solver progress mode, one of smNormalRun, smNormalCloseRun, smProgressRun or smBackgroundRun. See Solver Options for more information.
- `Wait` — Solver execution mode. If this option is set to btTrue execution of the caller will be halted until the solve is complete. If this option is set to btFalse execution of the caller will continue and the solver will run independently.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidSolverMode, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_UnknownError, ERR7_UnknownSolver
```


---

### `St7RunSolverProcess`

Launches the specified Strand7 solver and returns the ID number for the new
process created. All Strand7 solvers run as a separate process to the calling
application.

**Syntax**

```c
long St7RunSolverProcess(long uID, long Solver, long Mode,
long Wait, long* ProcessID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Solver` — Solver type, one of stLinearStaticSolver, stLinearBucklingSolver, stNonlinearStaticSolver, stNaturalFrequencySolver, stHarmonicResponseSolver, stSpectralResponseSolver, stLinearTransientDynamicSolver, stNonlinearTransientDynamicSolver, stSteadyHeatSolver, stTransientHeatSolver, stLoadInfluenceSolver, stQuasiStaticSolver.
- `Mode` — Solver progress mode, one of smNormalRun, smNormalCloseRun, smProgressRun or smBackgroundRun. See Solver Options for more information.
- `Wait` — Solver execution mode. If this option is set to btTrue execution of the caller will be halted until the solve is complete. If this option is set to btFalse execution of the calling code will continue and the solver will run independently.

**Output Parameters**

- `ProcessID` — ID number for the solver process.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
```
