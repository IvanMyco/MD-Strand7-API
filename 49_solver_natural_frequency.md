---
title: "Solver – Natural Frequency"
source: "Strand7 R246 API Manual"
pages: 767–774
---

# Solver – Natural Frequency

Solver – Quasi-Static

MaxStringLen
Maximum number of characters allocated for FileName.
Output Parameters

FileName
Full path and name for the initial conditions file.

CaseNum
Result case number within FileName to be used as the initial conditions.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError


---

### `St7SetNFAInitialFile`

Assigns the initial conditions file used for Natural Frequency analysis. If an initial
conditions file is specified stress stiffening/softening effects will be included in the
analysis.

**Syntax**

```c
long St7SetNFAInitialFile(long uID, char* FileName, long
CaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the initial conditions file.
- `CaseNum` — Result case number within FileName to be used as the initial conditions.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidInitialCaseNumber, ERR7_InvalidInitialFile,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetNFAInitialFile`

Returns the initial conditions file assigned for Natural Frequency analysis. If an
initial conditions file is specified stress stiffening/softening effects will be included
in the analysis.

**Syntax**

```c
long St7GetNFAInitialFile(long uID, char* FileName, long*
CaseNum, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `MaxStringLen` — Maximum number of characters allocated for FileName

**Output Parameters**

- `FileName` — Full path and name for the initial conditions file.
- `CaseNum` — Result case number within FileName to be used as the initial conditions.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7EnableNFANonStructuralMassCase`

Activates the non-structural mass for the specified load case such that it is
included in Natural Frequency analysis.

**Syntax**

```c
long St7EnableNFANonStructuralMassCase(long uID, long
CaseNum)
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

### `St7DisableNFANonStructuralMassCase`

Deactivates the non-structural mass for the specified load case such that it is not
included in Natural Frequency analysis.

**Syntax**

```c
long St7DisableNFANonStructuralMassCase(long uID, long
CaseNum)
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

### `St7GetNFANonStructuralMassCaseState`

Returns the state assigned to the non-structural mass in the specified load case
for Natural Frequency analysis.

**Syntax**

```c
long St7GetNFANonStructuralMassCaseState(long uID, long
CaseNum, bool* State)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Load case number.

**Output Parameters**

- `State` — btTrue if the non-structural mass is enabled for the specified load case.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_NoError
```


---

### `St7SetNFANumModes`

Sets the number of modes to be solved for when performing Natural Frequency
analysis.

**Syntax**

```c
long St7SetNFANumModes(long uID, long NumModes)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NumModes` — Number of modes.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidNumModes, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetNFANumModes`

Returns the number of modes to be found when performing Natural Frequency
analysis.

**Syntax**

```c
long St7GetNFANumModes(long uID, long* NumModes)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumModes` — Number of modes.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetNFAShift`

Sets the frequency shift used by the Natural Frequency solver. The first modes
found both above and below the shift value will be found when running the
solver.

**Syntax**

```c
long St7SetNFAShift(long uID, double Shift)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Shift` — Frequency shift (Hz).

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetNFAShift`

Returns the shift value assigned to the Natural Frequency solver. The first modes
found both above and below the shift value will be found when running the
solver.

**Syntax**

```c
long St7GetNFAShift(long uID, double* Shift)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `Shift` — Frequency shift (Hz).

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetNFAModeParticipationCalculate`

Sets the state of the mass participation option for the Natural Frequency solver.

**Syntax**

```c
long St7SetNFAModeParticipationCalculate(long uID, bool
Calculate)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Calculate` — btTrue to calculate the mass participation for each mode in the analysis.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetNFAModeParticipationCalculate`

Returns the state of the mass participation option for the Natural Frequency solver.

**Syntax**

```c
long St7GetNFAModeParticipationCalculate(long uID, bool*
Calculate)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `Calculate` — btTrue to calculate the mass participation for each mode in the analysis.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetNFAModeParticipationVectors`

Assigns the direction vector used when calculating mass participation factors for
Natural Frequency analysis.

**Syntax**

```c
long St7SetNFAModeParticipationVectors(long uID, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
