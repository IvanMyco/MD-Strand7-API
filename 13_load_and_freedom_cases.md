---
title: "Load and Freedom Cases"
source: "Strand7 R246 API Manual"
pages: 116–137
---

# Load and Freedom Cases

[ipBXSSxx] - Plastic modulus about the local X axis.
[ipBXSSyy] - Plastic modulus about the local Y axis.
[ipBXSrx] - Radius of gyration in the local X axis direction.
[ipBXSry] - Radius of gyration in the local Y axis direction.
[ipBXSJ] - Torsion constant.
[ipBXSIw] - Warping constant.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotCalculateBXSData, ERR7_CannotMakeBXS,
ERR7_CannotSaveFile, ERR7_FileNotOpen, ERR7_InvalidFileName,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_ZeroPlateElements


---

### `St7NewLoadCase`

Creates a new load case within a Strand7 model.

**Syntax**

```c
long St7NewLoadCase(long uID, char* CaseName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseName` — String containing the name of the new load case.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CaseNameAlreadyExists, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7NewSeismicCase`

Creates a new seismic load case within a Strand7 model.

**Syntax**

```c
long St7NewSeismicCase(long uID, char* CaseName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseName` — String containing the name of the new seismic case.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CaseNameAlreadyExists, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7NewFreedomCase`

Creates a new freedom case within a Strand7 model.

**Syntax**

```c
long St7NewFreedomCase(long uID, char* CaseName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseName` — String containing the name of the new freedom case.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CaseNameAlreadyExists, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetNumLoadCase`

Returns the number of load cases in a Strand7 model.

**Syntax**

```c
long St7GetNumLoadCase(long uID, long* NumCases)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumCases` — The number of load cases in the model.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetNumSeismicCase`

Returns the number of seismic cases in a Strand7 model.

**Syntax**

```c
long St7GetNumSeismicCase(long uID, long* NumCases)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumCases` — The number of seismic cases in the model.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetNumFreedomCase`

Returns the number of freedom cases in a Strand7 model.

**Syntax**

```c
long St7GetNumFreedomCase(long uID, long* NumCases)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumCases` — The number of freedom cases in the model.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetLoadCaseName`

Sets the name of a specified load case in a Strand7 model.

**Syntax**

```c
long St7SetLoadCaseName(long uID, long CaseNum, char*
CaseName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — The load case ID number.
- `CaseName` — String containing the new name of the load case.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CaseNameAlreadyExists, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidSeismicCase, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetLoadCaseName`

Returns the name of a specified load case within a Strand7 model.

**Syntax**

```c
long St7GetLoadCaseName(long uID, long CaseNum, char*
CaseName, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — The load case ID number.
- `MaxStringLen` — The maximum number of characters allocated for CaseName.

**Output Parameters**

- `CaseName` — String containing the name of the specified load case.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_NoError
```


---

### `St7SetSeismicCaseName`

Sets the name of a specified seismic case in a Strand7 model.

**Syntax**

```c
long St7SetSeismicCaseName(long uID, long CaseNum, char*
CaseName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — The seismic case ID number.
- `CaseName` — String containing the new name of the seismic case.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CaseNameAlreadyExists, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidSeismicCase, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetSeismicCaseName`

Returns the name of a specified seismic case with a Strand7 model.

**Syntax**

```c
long St7GetSeismicCaseName(long uID, long CaseNum, char*
CaseName, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — The seismic case ID number.
- `MaxStringLen` — The maximum number of characters allocated for CaseName.

**Output Parameters**

- `CaseName` — String containing the name of the specified seismic case.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidSeismicCase, ERR7_NoError
```


---

### `St7SetFreedomCaseName`

Sets the name of a specified freedom case within a Strand7 model.

**Syntax**

```c
long St7SetFreedomCaseName(long uID, long CaseNum, char*
CaseName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — The freedom case ID number.
- `CaseName` — String containing the new name for the freedom case.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CaseNameAlreadyExists, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_InvalidSeismicCase, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetFreedomCaseName`

Returns the name of a specified freedom case in a Strand7 model.

**Syntax**

```c
long St7GetFreedomCaseName(long uID, long CaseNum, char*
CaseName, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — The freedom case ID number.
- `MaxStringLen` — The maximum number of characters allocated for CaseName.

**Output Parameters**

- `CaseName` — String containing the name of the specified freedom case.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_NoError
```


---

### `St7SetLoadCaseDefaults`

Sets the defaults for the specified load case in a Strand7 model.

**Syntax**

```c
long St7SetLoadCaseDefaults(long uID, long CaseNum, double*
Defaults)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — The load case ID number.
- `Defaults[0..12]` — [0] - Reference temperature. [1..3] - Origin for angular velocity and acceleration. [4..6] - Linear acceleration components. [7..9] - Angular velocity components. [10..12] - Angular acceleration components.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetLoadCaseDefaults`

Returns the default values for a specified load case within a Strand7 model.

**Syntax**

```c
long St7GetLoadCaseDefaults(long uID, long CaseNum, double*
Defaults)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — The load case ID number.

**Output Parameters**

- `Defaults[0..12]` — [0] - Reference temperature. [1..3] - Origin for angular velocity and acceleration. [4..6] - Linear acceleration components. [7..9] - Angular velocity components. [10..12] - Angular acceleration components.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_NoError
```


---

### `St7SetSeismicCaseDefaults`

Sets the defaults for a specified seismic case within a Strand7 model.

**Syntax**

```c
long St7SetSeismicCaseDefaults(long uID, long CaseNum,
double* Defaults)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — The seismic case ID number.
- `Defaults[0..8]` — [ipSeismicCaseDefAlpha] - Seismic case α parameter. [ipSeismicCaseDefPhi] - Seismic case ϕ parameter. [ipSeismicCaseDefBeta] - Seismic case β parameter. [ipSeismicCaseDefK] - Seismic case k parameter. [ipSeismicCaseDefh0] - Seismic base height parameter h0. [ipSeismicCaseDefDir] - Seismic acceleration direction, one of 1,2 or 3 to denote the Global Cartesian XYZ directions respectively. [ipSeismicCaseDefLinAcc] - Seismic acceleration value. [ipSeismicCaseDefV1] - Global X component of base excitation direction . [ipSeismicCaseDefV2] - Global Y component of base excitation direction.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidSeismicCase, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetSeismicCaseDefaults`

Returns the defaults for a specified seismic case within a Strand7 model.

**Syntax**

```c
long St7GetSeismicCaseDefaults(long uID, long CaseNum,
double* Defaults)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — The seismic case ID number.

**Output Parameters**

- `Defaults[0..8]` — [ipSeismicCaseDefAlpha] - Seismic case α parameter. [ipSeismicCaseDefPhi] - Seismic case ϕ parameter. [ipSeismicCaseDefBeta] - Seismic case β parameter. [ipSeismicCaseDefK] - Seismic case k parameter. [ipSeismicCaseDefh0] - Seismic base height parameter h0. [ipSeismicCaseDefDir] - Seismic acceleration direction, one of 1,2 or 3 to denote the Global Cartesian XYZ directions respectively. [ipSeismicCaseDefLinAcc] - Seismic acceleration value. [ipSeismicCaseDefV1] - Global X component of base excitation direction . [ipSeismicCaseDefV2] - Global Y component of base excitation direction.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidSeismicCase, ERR7_NoError
```


---

### `St7SetFreedomCaseDefaults`

Sets the defaults for a specified freedom case within a Strand7 model.

**Syntax**

```c
long St7SetFreedomCaseDefaults(long uID, long CaseNum,
long* Defaults)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — The freedom case ID number.
- `Defaults[0..5]` — An array describing the global restraint conditions for each DoF in the Global Cartesian coordinate system. Defaults[i] = btTrue indicates that DoF i is restrained.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetFreedomCaseDefaults`

Returns the defaults for a specified freedom case in a Strand7 model.

**Syntax**

```c
long St7GetFreedomCaseDefaults(long uID, long CaseNum,
long* Defaults)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — The freedom case ID number.

**Output Parameters**

- `Defaults[0..5]` — An array describing the global restraint conditions for each DoF in the Global Cartesian coordinate system. Defaults[i] = btTrue indicates that DoF i is restrained.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_NoError
```


---

### `St7SetLoadCaseType`

Sets the type for a specified load case in a Strand7 model.

**Syntax**

```c
long St7SetLoadCaseType(long uID, long CaseNum, long
CaseType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — The load case ID number.
- `CaseType` — The load case type (kNoInertia, kGravity or kAccelerations).

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_InvalidLoadCaseType,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetLoadCaseType`

Returns the type for a specified load case in a Strand7 model.

**Syntax**

```c
long St7GetLoadCaseType(long uID, long CaseNum, long*
CaseType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — The load case ID number.

**Output Parameters**

- `CaseType` — The load case type (kNoInertia, kGravity or kAccelerations).

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_NoError
```


---

### `St7SetLoadCaseGravityDir`

Sets the direction of the gravity vector for the specified load case.

**Syntax**

```c
long St7SetLoadCaseGravityDir(long uID, long CaseNum, long
GravDir)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Load case number.
- `GravDir` — Gravity direction as an axis index for the Global Cartesian Coordinate system, one of 1, 2 or 3.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidGravityDirection, ERR7_InvalidLoadCase,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetLoadCaseGravityDir`

Returns the direction of the gravity vector assigned to the specified load case.

**Syntax**

```c
long St7GetLoadCaseGravityDir(long uID, long CaseNum, long*
GravDir)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Load case number.

**Output Parameters**

- `GravDir` — Gravity direction as an axis index for the Global Cartesian Coordinate system, one of 1, 2 or 3.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_NoError
```


---

### `St7SetFreedomCaseType`

Sets the type for a specified freedom case in a Strand7 model.

**Syntax**

```c
long St7SetFreedomCaseType(long uID, long CaseNum, long
CaseType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — The freedom case ID number.
- `CaseType` — The freedom case type, one of kNormalFreedom, kFreeBodyInertiaRelief, kSingleSymmetryInertiaXY, kSingleSymmetryInertiaYZ, kSingleSymmetryInertiaZX, kDoubleSymmetryInertiaX, kDoubleSymmetryInertiaY or kDoubleSymmetryInertiaZ.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_InvalidFreedomCaseType,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetFreedomCaseType`

Returns the type of a specified freedom case with a Strand7 model.

**Syntax**

```c
long St7GetFreedomCaseType(long uID, long CaseNum, long*
CaseType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — The freedom case ID number.

**Output Parameters**

- `CaseType` — The freedom case type, one of kNormalFreedom, kFreeBodyInertiaRelief, kSingleSymmetryInertiaXY, kSingleSymmetryInertiaYZ, kSingleSymmetryInertiaZX, kDoubleSymmetryInertiaX, kDoubleSymmetryInertiaY or kDoubleSymmetryInertiaZ.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_NoError
```


---

### `St7SetLoadCaseMassOption`

Sets the mass options for a specified load case in a Strand7 model.

**Syntax**

```c
long St7SetLoadCaseMassOption(long uID, long CaseNum, bool
SMass, bool NSMass)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — The load case ID number.
- `SMass` — btTrue indicates that global accelerations are applied to structural mass in the model.
- `NSMass` — btTrue indicates that global accelerations are applied to non-structural mass in the model.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetLoadCaseMassOption`

Returns the mass options for a specified load case in a Strand7 model.

**Syntax**

```c
long St7GetLoadCaseMassOption(long uID, long CaseNum, bool*
SMass, bool* NSMass)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — The load case ID number.

**Output Parameters**

- `SMass` — btTrue indicates that global accelerations are applied to structural mass in the model.
- `NSMass` — btTrue indicates that global accelerations are applied to non-structural mass in the model.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_NoError
```


---

### `St7EnableSeismicNSMassCase`

Includes the non-structural mass from a specified load case in a seismic case.

**Syntax**

```c
long St7EnableSeismicNSMassCase(long uID, long
SeismicCaseNum, long LoadCaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `SeismicCaseNum` — The seismic case ID number.
- `LoadCaseNum` — The load case ID number for the case to be included in the specified seismic case.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidSeismicCase, ERR7_InvalidLoadCase, ERR7_NoError
```


---

### `St7DisableSeismicNSMassCase`

Excludes the non-structural mass from a specified load case in a seismic case.

**Syntax**

```c
long St7DisableSeismicNSMassCase(long uID, long
SeismicCaseNum, long LoadCaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `SeismicCaseNum` — The seismic case ID number.
- `LoadCaseNum` — The load case ID number for the case to be excluded from the specified seismic case.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidSeismicCase, ERR7_InvalidLoadCase, ERR7_NoError
```


---

### `St7GetSeismicNSMassCaseState`

Returns whether the non-structural mass from a specified load case is included in
a given seismic case in the Strand7 model.

**Syntax**

```c
long St7GetSeismicNSMassCaseState(long uID, long
SeismicCaseNum, long LoadCaseNum, bool* State)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `SeismicCaseNum` — The seismic case ID number.
- `LoadCaseNum` — The load case ID number.

**Output Parameters**

- `State` — btTrue indicates that the non-structural mass from the specified load case is included in the given seismic case.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidSeismicCase, ERR7_InvalidLoadCase, ERR7_NoError
```


---

### `St7DeleteLoadCase`

Deletes the specified load case from the Strand7 model.

**Syntax**

```c
long St7DeleteLoadCase(long uID, long CaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — The ID number for the load case to be deleted.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_NoError, ERR7_OnlyOneLoadCase,
ERR7_ResultFileIsOpen
```


---

### `St7DeleteSeismicCase`

Deletes the specified seismic case from the Strand7 model.

**Syntax**

```c
long St7DeleteSeismicCase(long uID, long CaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — The ID number for the seismic case to be deleted.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidSeismicCase, ERR7_NoError,
ERR7_ResultFileIsOpen
```
