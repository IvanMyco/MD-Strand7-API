---
title: "Linear Load Case Combinations"
source: "Strand7 R246 API Manual"
pages: 909–915
---

# Linear Load Case Combinations

Results
Input Parameters

uID
Strand7 model file ID number.

BrickNum
Brick number.

ResultCase
Result case number.
Output Parameters

NumGauss
Number of Gauss points.

Doubles[0..80]
[0..3*NumGauss-1] - An array containing the XYZ position of the result
Gauss points in the Global Cartesian coordinate system. The positions are
returned in blocks of length 3, with the position of the ith point starting at
Doubles[(i-1)*3].
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededResultCase,
ERR7_ExceededTotal, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidResultType, ERR7_NoError,
ERR7_ResultFileNotOpen


---

### `St7GetNumLSACombinations`

Returns the number of linear load case combinations in the specified model.

**Syntax**

```c
long St7GetNumLSACombinations(long uID, long* NumCases)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumCases` — Number of linear load case combinations.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetLSACombinationName`

Sets the name of the specified linear load case combination.

**Syntax**

```c
long St7SetLSACombinationName(long uID, long CaseNum, char*
CaseName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Load case combination number.
- `CaseName` — Name of the specified load case combination.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidCombinationCaseNumber,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetLSACombinationName`

Returns the name of the specified linear load case combination.

**Syntax**

```c
long St7GetLSACombinationName(long uID, long CaseNum, char*
CaseName, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Load case combination number.
- `MaxStringLen` — Maximum number of characters allocated for CaseName.

**Output Parameters**

- `CaseName` — Name of the specified load case combination.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidCombinationCaseNumber,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetLSACombinationSpectralName`

Sets the spectral results filename to be used in linear load combination.

**Syntax**

```c
long St7SetLSACombinationSpectralName(long uID, char*
FileName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the spectral results file.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetLSACombinationSpectralName`

Returns the spectral results filename used in linear load combination.

**Syntax**

```c
long St7GetLSACombinationSpectralName(long uID, char*
FileName, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `MaxStringLen` — Maximum number of characters allocated for FileName.

**Output Parameters**

- `FileName` — Full path and name for the spectral results file.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7AddLSACombination`

Adds a new linear load case combination to the specified model.

**Syntax**

```c
long St7AddLSACombination(long uID, char* IncName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `IncName` — Name of the load case combination.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7InsertLSACombination`

Inserts a new linear load case combination at the specified position in the model.

**Syntax**

```c
long St7InsertLSACombination(long uID, long Pos, char*
IncName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Pos` — Load case combination number.
- `IncName` — Name of the load case combination.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CombinationDoesNotExist, ERR7_FileNotOpen,
ERR7_IncrementDoesNotExist, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7DeleteLSACombination`

Deletes the specified linear load case combination from the model.

**Syntax**

```c
long St7DeleteLSACombination(long uID, long Pos)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Pos` — Load case combination number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CombinationDoesNotExist, ERR7_FileNotOpen,
ERR7_IncrementDoesNotExist, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SetLSACombinationFactor`

Sets the multiplying factor for the specified case in a linear load case
combination.

**Syntax**

```c
long St7SetLSACombinationFactor(long uID, long LType, long
Pos, long LCaseNum, long FCaseNum, double Factor)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LType` — Type of load case, one of ltLoadCase, ltSeismicCase or ltSpectralCase.
- `Pos` — Load case combination number.
- `LCaseNum` — Load, Seismic or Spectral case number.
- `FCaseNum` — Freedom case number.
- `Factor` — Factor value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CombinationDoesNotExist, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetLSACombinationFactor`

Returns the multiplying factor for the specified case in a linear load case
combination.

**Syntax**

```c
long St7GetLSACombinationFactor(long uID, long LType, long
Pos, long LCaseNum, long FCaseNum, double* Factor)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LType` — Type of load case, one of ltLoadCase, ltSeismicCase or ltSpectralCase.
  Pos
