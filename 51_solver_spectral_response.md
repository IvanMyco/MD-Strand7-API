---
title: "Solver – Spectral Response"
source: "Strand7 R246 API Manual"
pages: 781–792
---

# Solver – Spectral Response

Solver – Harmonic Response

CaseNum
Load case number.
Output Parameters

TableID
Factor vs Frequency table ID, zero for none.

Doubles[0..2]
A 3 element array containing the load factor, the phase angle in degrees,
and the frequency in Hz, for load case CaseNum. Note that the frequency is
only used in vs Time analyses.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_NoError


---

### `St7AddSRALoadCase`

Adds a new blank load case to the Spectral Response analysis load case table.
Spectral load cases are only used when the load type is set to Applied Load.

**Syntax**

```c
long St7AddSRALoadCase(long uID, char* CaseName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseName` — Spectral Response load case name.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededMaxNumSpectralCases, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7InsertSRALoadCase`

Inserts a new blank load case at the specified position within the Spectral
Response analysis load case table. Spectral load cases are only used when the
load type is set to Applied Load.

**Syntax**

```c
long St7InsertSRALoadCase(long uID, long Pos, char*
CaseName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Pos` — Spectral Response load case number.
- `CaseName` — Spectral Response load case name.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededMaxNumSpectralCases, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_InvalidSpectralCase,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7DeleteSRALoadCase`

Deletes the specified load case from the Spectral Response analysis load case
table. Spectral load cases are only used when the load type is set to Applied Load.

**Syntax**

```c
long St7DeleteSRALoadCase(long uID, long Pos)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Pos` — Spectral Response load case number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededMaxNumSpectralCases, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_InvalidSpectralCase,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetNumSRALoadCases`

Returns the number of load cases assigned for Spectral Response analysis.

**Syntax**

```c
long St7GetNumSRALoadCases(long uID, long* NumCases)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumCases` — Number of Spectral Response analysis load cases.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetSRALoadCaseTable`

Specifies the table associated with the specified Spectral Response analysis load
case. Spectral load cases are only used when the load type is set to Applied Load.

**Syntax**

```c
long St7SetSRALoadCaseTable(long uID, long Pos, long
CaseNum, long TableID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Pos` — Spectral Response load case number.
- `CaseNum` — Global load case number.
- `TableID` — Table ID number, zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_InvalidSpectralCase,


ERR7_InvalidTableType, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_TableDoesNotExist
```


---

### `St7GetSRALoadCaseTable`

Returns the table associated with the specified Spectral Response analysis load
case. Spectral load cases are only used when the load type is set to Applied Load.

**Syntax**

```c
long St7GetSRALoadCaseTable(long uID, long Pos, long
CaseNum, long* TableID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Pos` — Spectral Response analysis load case number.
- `CaseNum` — Global load case number.

**Output Parameters**

- `TableID` — Table ID number, zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_InvalidSpectralCase,
ERR7_NoError
```


---

### `St7AddSRADirectionVector`

Adds a new direction based Spectral Response analysis load case. This option is
only used if the load type is set to one of Base Acceleration, Velocity or
Displacement.

**Syntax**

```c
long St7AddSRADirectionVector(long uID, char* CaseName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseName` — Spectral Response load case name.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededMaxNumSpectralCases, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7InsertSRADirectionVector`

Inserts a new direction based Spectral Response analysis load case at the
specified position. This option is only used if the load type is set to one of Base
Acceleration, Velocity or Displacement.

**Syntax**

```c
long St7InsertSRADirectionVector(long uID, long Pos, char*
CaseName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Pos` — Spectral Response load case number.
- `CaseName` — Spectral Response load case name.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededMaxNumSpectralCases, ERR7_FileNotOpen,


ERR7_InvalidFileUnit, ERR7_InvalidSpectralCase,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7DeleteSRADirectionVector`

Deletes the specified direction based Spectral Response load case. This option is
only used if the load type is set to one of Base Acceleration, Velocity or
Displacement.

**Syntax**

```c
long St7DeleteSRADirectionVector(long uID, long Pos)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Pos` — Spectral Response load case number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidSpectralCase, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetNumSRADirectionVectors`

Returns the number of direction based load cases assigned for Spectral Response
Analysis.

**Syntax**

```c
long St7GetNumSRADirectionVectors(long uID, long* NumCases)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumCases` — Number of direction based load cases.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetSRADirectionVectorTable`

Sets the table associated with the specified Spectral Response load case. This
option is only used if the load type is set to one of Base Acceleration, Velocity or
Displacement.

**Syntax**

```c
long St7SetSRADirectionVectorTable(long uID, long Pos, long
TableID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Pos` — Spectral Response load case number.
- `TableID` — Table ID number, zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidSpectralCase, ERR7_InvalidTableType,
ERR7_NoError, ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7GetSRADirectionVectorTable`

Returns the table associated with the specified Spectral Response load case. This
option is only used if the load type is set to one of Base Acceleration, Velocity or
Displacement.

**Syntax**

```c
long St7GetSRADirectionVectorTable(long uID, long Pos,
long* TableID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Pos` — Spectral Response load case.

**Output Parameters**

- `TableID` — Table ID number, zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidSpectralCase, ERR7_NoError
```


---

### `St7SetSRADirectionVectorFactors`

Assigns the components of the direction vector for the specified Spectral
Response load case. This option is only used if the load type is set to one of Base
Acceleration, Velocity or Displacement.

**Syntax**

```c
long St7SetSRADirectionVectorFactors(long uID, long Pos,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Pos` — Spectral Response load case number.
- `Doubles[0..2]` — A 3 element array describing the XYZ components of the direction vector according to the Global Cartesian Coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidSpectralCase, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetSRADirectionVectorFactors`

Returns the components of the direction vector assigned to the specified
Spectral Response load case. This option is only used if the load type is set to one
of Base Acceleration, Velocity or Displacement.

**Syntax**

```c
long St7GetSRADirectionVectorFactors(long uID, long Pos,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Pos` — Spectral Response load case number.

**Output Parameters**

- `Doubles[0..2]` — A 3 element array describing the XYZ components of the direction vector according to the Global Cartesian Coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidSpectralCase, ERR7_NoError
```


---

### `St7SetSRAResultModal`

Sets the state of the Modal result option for the Spectral Response Solver.

**Syntax**

```c
long St7SetSRAResultModal(long uID, bool Modal)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Modal` — btTrue to generate Modal results.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetSRAResultSRSS`

Sets the state of the SRSS result option for the Spectral Response solver.

**Syntax**

```c
long St7SetSRAResultSRSS(long uID, bool SRSS)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `SRSS` — btTrue to generate SRSS results.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetSRAResultCQC`

Sets the state of the CQC result option for the Spectral Response solver.

**Syntax**

```c
long St7SetSRAResultCQC(long uID, bool CQC)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CQC` — btTrue to generate CQC results.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetSRAType`

Assigns the spectrum type used for Spectral Response analysis.

**Syntax**

```c
long St7SetSRAType(long uID, long SpectrumType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `SpectrumType` — Type of spectrum supplied, either stResponse or stPSD
