---
title: "Result File Combination"
source: "Strand7 R246 API Manual"
pages: 938–946
---

# Result File Combination

---

### `St7GetFactorsEnvelopeSetData`

Returns the settings assigned to a specified set in a factors envelope.

**Syntax**

```c
long St7GetFactorsEnvelopeSetData(long uID, long Pos, long*
SetType, char* SetName, char* SetGroup, long
MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Pos` — Set position.
- `MaxStringLen` — Maximum number of characters allocated for SetName.

**Output Parameters**

- `SetType` — Type of set, either stExclusiveOR or stExclusiveAND.
- `SetName` — Name of the set.
- `SetGroup` — Group identifier for set.

**Errors**

```
ERR7_DataNotFound, ERR7_ExceededResultCase,
ERR7_FileNotOpen, ERR7_InvalidEnvelopeSet,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7SetResultFileCombTargetFileName`

Sets the name of the target file produced when forming a combined result file.

**Syntax**

```c
long St7SetResultFileCombTargetFileName(long uID, char*
FileName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the target file.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetResultFileCombTargetFileName`

Returns the name of the target file produced when forming a combined result file.

**Syntax**

```c
long St7GetResultFileCombTargetFileName(long uID, char*
FileName, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `MaxStringLen` — Maximum number of characters allocated for FileName.

**Output Parameters**

- `FileName` — Full path and name for the target file.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7AddResultFileCombFileName`

Adds a new file to the current results file combination.

**Syntax**

```c
long St7AddResultFileCombFileName(long uID, char* FileName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the new result file.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededMaxNumCombResFiles, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7DeleteResultFileCombFileName`

Deletes a specified file from the current results file combination.

**Syntax**

```c
long St7DeleteResultFileCombFileName(long uID, long
FileNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileNum` — File number in current combination.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidCombResFile,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetResultFileCombFileName`

Sets the name of a specified file in the current result file combination.

**Syntax**

```c
long St7SetResultFileCombFileName(long uID, long FileNum,
char* FileName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileNum` — File number in the current combination.
- `FileName` — Full path and name for the result file.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidCombResFile,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetResultFileCombFileName`

Returns the name of a specified file in the current results file combination.

**Syntax**

```c
long St7GetResultFileCombFileName(long uID, long FileNum,
char* FileName, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileNum` — File number in the current combination.
- `MaxStringLen` — Maximum number of characters allocated for FileName.

**Output Parameters**

- `FileName` — Full path and name for the file.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidCombResFile,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7AddResultFileCombCase`

Adds a new case to the current result file combination.

**Syntax**

```c
long St7AddResultFileCombCase(long uID, char* CaseName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseName` — New combination case name.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededMaxNumRows, ERR7_FileNotOpen,
ERR7_InvalidCombResFile, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7DeleteResultFileCombCase`

Deletes a specified case from the current result file combination.

**Syntax**

```c
long St7DeleteResultFileCombCase(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidCombResFile,
ERR7_InvalidFileUnit, ERR7_InvalidTableRow, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetResultFileCombCaseData`

Sets the combination data for a combined result case in the specified result file
combination.

**Syntax**

```c
long St7SetResultFileCombCaseData(long uID, long FileNum,
long Pos, long CaseNum, double Factor)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileNum` — Combination file number.
- `Pos` — Result case in combined file.
- `CaseNum` — Result case.
- `Factor` — Combination factor.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededResultCase, ERR7_FileNotOpen,
ERR7_InvalidCombResFile, ERR7_InvalidFileUnit,
ERR7_InvalidTableRow, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetResultFileCombCaseData`

Returns the combination data assigned to a combined result case in the
specified result file combination.

**Syntax**

```c
long St7GetResultFileCombCaseData(long uID, long FileNum,
long Pos, long* CaseNum, double* Factor)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileNum` — Combination file number.
- `Pos` — Result case in combined file.

**Output Parameters**

- `CaseNum` — Result case.
- `Factor` — Combination factor.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidCombResFile,
ERR7_InvalidFileUnit, ERR7_InvalidTableRow, ERR7_NoError
```


---

### `St7SetResultFileCombCaseName`

Sets the name of a combined result case in the specified result file combination.

**Syntax**

```c
long St7SetResultFileCombCaseName(long uID, long Pos, char*
CaseName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Pos` — Result case in combined file.
- `CaseName` — Combined result case name.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidCombResFile,
ERR7_InvalidFileUnit, ERR7_InvalidTableRow, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetResultFileCombCaseName`

Returns the name assigned to a combined result case in the specified result file
combination.

**Syntax**

```c
long St7GetResultFileCombCaseName(long uID, long Pos, char*
CaseName, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Pos` — Result case in combined file.
- `MaxStringLen` — Maximum number of characters allocated for CaseName.

**Output Parameters**

- `CaseName` — Combined result case name.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidCombResFile,
ERR7_InvalidFileUnit, ERR7_InvalidTableRow, ERR7_NoError
```


---

### `St7GenerateResultFileComb`

Generates the combined result file using the specified method.

**Syntax**

```c
long St7GenerateResultFileComb(long uID, long Method)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Method` — Combination method, either rfCombFactors or rfCombSRSS.
