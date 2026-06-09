---
title: "Envelopes"
source: "Strand7 R246 API Manual"
pages: 916–937
---

# Envelopes

Load case combination number.

LCaseNum
Load, Seismic or Spectral case number.

FCaseNum
Freedom case number.
Output Parameters

Factor
Factor value.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CombinationDoesNotExist, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidLoadCase, ERR7_NoError


---

### `St7GetNumEnvelopes`

Returns the number of envelopes in the specified model.

**Syntax**

```c
long St7GetNumEnvelopes(long uID, long* NumLimitEnvelopes,
long* NumCombinationEnvelopes, long*
NumFactorsEnvelopes)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumLimitEnvelopes` — Number of limit envelopes.
- `NumCombinationEnvelopes` — Number of combination envelopes.
- `NumFactorsEnvelopes` — Number of factors envelopes.

**Errors**

```
ERR7_ExceededResultCase, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7AddLimitEnvelope`

Adds a new limit envelope to the specified model.

**Syntax**

```c
long St7AddLimitEnvelope(long uID, long EnvType, char*
EnvName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EnvType` — Limit envelope type, one of etLimitEnvelopeAbs, etLimitEnvelopeMin or etLimitEnvelopeMax.
- `EnvName` — Name of the envelope.

**Errors**

```
ERR7_ExceededMaxNumLimitEnvelopes, ERR7_ExceededResultCase,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLimitEnvelopeType, ERR7_NoError,
ERR7_ResultFileNotOpen
```


---

### `St7InsertLimitEnvelope`

Inserts a new limit envelope at the specified position.

**Syntax**

```c
long St7InsertLimitEnvelope(long uID, long Envelope, long
EnvType, char* EnvName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Envelope` — Limit envelope number.
- `EnvType` — Limit envelope type, one of etLimitEnvelopeAbs, etLimitEnvelopeMin or etLimitEnvelopeMax.
- `EnvName` — Name of the envelope.

**Errors**

```
ERR7_ExceededResultCase, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_InvalidLimitEnvelope,
ERR7_InvalidLimitEnvelopeType, ERR7_NoError,
ERR7_ResultFileNotOpen
```


---

### `St7DeleteLimitEnvelope`

Deletes the specified limit envelope.

**Syntax**

```c
long St7DeleteLimitEnvelope(long uID, long Envelope)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Envelope` — Limit envelope number.

**Errors**

```
ERR7_ExceededResultCase, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_InvalidLimitEnvelope,
ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7EnableLimitEnvelopeCase`

Enables the specified result case in a limit envelope. Only results from enabled
result cases are included in the envelope.

**Syntax**

```c
long St7EnableLimitEnvelopeCase(long uID, long Envelope,
long CaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Envelope` — Limit envelope number.
- `CaseNum` — Result case number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededResultCase,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLimitEnvelope, ERR7_NoError,
ERR7_ResultFileNotOpen
```


---

### `St7DisableLimitEnvelopeCase`

Disables the specified result case in a limit envelope. Only results from enabled
result cases are included in the envelope.

**Syntax**

```c
long St7DisableLimitEnvelopeCase(long uID, long Envelope,
long CaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Envelope` — Limit envelope number.
- `CaseNum` — Result case number to disable.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededResultCase,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLimitEnvelope, ERR7_NoError,
ERR7_ResultFileNotOpen
```


---

### `St7GetLimitEnvelopeCaseState`

Returns the state of a specified result case in a limit envelope. Only results from
enabled result cases are included in the envelope.

**Syntax**

```c
long St7GetLimitEnvelopeCaseState(long uID, long Envelope,
long CaseNum, bool* State)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Envelope` — Limit envelope number.
- `CaseNum` — Result case number.

**Output Parameters**

- `State` — btTrue if the specified result case is enabled.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededResultCase,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLimitEnvelope, ERR7_NoError,
ERR7_ResultFileNotOpen
```


---

### `St7SetLimitEnvelopeData`

Assigns the settings for a specified limit envelope.

**Syntax**

```c
long St7SetLimitEnvelopeData(long uID, long Envelope, long
EnvType, char* EnvName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Envelope` — Limit envelope number.
- `EnvType` — Limit envelope type, one of etLimitEnvelopeAbs, etLimitEnvelopeMin or etLimitEnvelopeMax.
- `EnvName` — Name of the envelope.

**Errors**

```
ERR7_DataNotFound, ERR7_ExceededResultCase,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLimitEnvelope, ERR7_InvalidLimitEnvelopeType,
ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7GetLimitEnvelopeData`

Returns the settings assigned to a specified limit envelope.

**Syntax**

```c
long St7GetLimitEnvelopeData(long uID, long Envelope, long*
EnvType, char* EnvName, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Envelope` — Limit envelope number.
- `MaxStringLen` — Maximum number of characters allocated for EnvName.

**Output Parameters**

- `EnvType` — Limit envelope type, one of etLimitEnvelopeAbs, etLimitEnvelopeMin or etLimitEnvelopeMax.
- `EnvName` — Name of the specified envelope.

**Errors**

```
ERR7_DataNotFound, ERR7_ExceededResultCase,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLimitEnvelope, ERR7_NoError,
ERR7_ResultFileNotOpen
```


---

### `St7AddCombinationEnvelope`

Adds a new combination envelope to the specified model.

**Syntax**

```c
long St7AddCombinationEnvelope(long uID, long EnvType,
char* EnvName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EnvType` — Combination envelope type, either etCombEnvelopeMin or etCombEnvelopeMax.
- `EnvName` — Name of the envelope.

**Errors**

```
ERR7_ExceededMaxNumCombEnvelopes, ERR7_ExceededResultCase,
ERR7_FileNotOpen, ERR7_InvalidCombEnvelopeType,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7InsertCombinationEnvelope`

Inserts a new combination envelope at a specified position.

**Syntax**

```c
long St7InsertCombinationEnvelope(long uID, long Envelope,
long EnvType, char* EnvName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Envelope` — Combination envelope number.
- `EnvType` — Combination envelope type, either etCombEnvelopeMin or etCombEnvelopeMax.
- `EnvName` — Name of the envelope.

**Errors**

```
ERR7_ExceededResultCase, ERR7_FileNotOpen,
ERR7_InvalidCombEnvelope, ERR7_InvalidCombEnvelopeType,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7DeleteCombinationEnvelope`

Deletes the specified combination envelope.

**Syntax**

```c
long St7DeleteCombinationEnvelope(long uID, long Envelope)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Envelope` — Combination envelope number.

**Errors**

```
ERR7_ExceededResultCase, ERR7_FileNotOpen,
ERR7_InvalidCombEnvelope, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7SetCombinationEnvelopeCase`

Sets the state of a specified results case in a combination envelope.

**Syntax**

```c
long St7SetCombinationEnvelopeCase(long uID, long Envelope,
long CaseNum, long State)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Envelope` — Combination envelope number.
- `CaseNum` — Result case number.
- `State` — State of the result case, one of esCombEnvelopeOn, esCombEnvelopeOff or esCombEnvelopeCheck.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededResultCase,
ERR7_FileNotOpen, ERR7_InvalidCombEnvelope,
ERR7_InvalidCombEnvelopeAccType, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7GetCombinationEnvelopeCase`

Returns the state of a specified result case in a combination envelope.

**Syntax**

```c
long St7GetCombinationEnvelopeCase(long uID, long Envelope,
long CaseNum, long* State)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Envelope` — Combination envelope number.
- `CaseNum` — Result case number.

**Output Parameters**

- `State` — State of the result case, one of esCombEnvelopeOn, esCombEnvelopeOff or esCombEnvelopeCheck.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededResultCase,
ERR7_FileNotOpen, ERR7_InvalidCombEnvelope,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7SetCombinationEnvelopeData`

Assigns the settings for a specified combination envelope.

**Syntax**

```c
long St7SetCombinationEnvelopeData(long uID, long Envelope,
long EnvType, char* EnvName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Envelope` — Combination envelope number.
- `EnvType` — Combination envelope type, either etCombEnvelopeMin or etCombEnvelopeMax.
- `EnvName` — Name of the envelope.

**Errors**

```
ERR7_DataNotFound, ERR7_ExceededResultCase,
ERR7_FileNotOpen, ERR7_InvalidCombEnvelope,
ERR7_InvalidCombEnvelopeType, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7GetCombinationEnvelopeData`

Returns the settings assigned to a specified combination envelope.

**Syntax**

```c
long St7GetCombinationEnvelopeData(long uID, long Envelope,
long* EnvType, char* EnvName, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Envelope` — Combination envelope number.
- `MaxStringLen` — Maximum number of characters allocated for EnvName.

**Output Parameters**

- `EnvType` — Combination envelope type, either etCombEnvelopeMin or etCombEnvelopeMax.
- `EnvName` — Name of the envelope.

**Errors**

```
ERR7_DataNotFound, ERR7_ExceededResultCase,
ERR7_FileNotOpen, ERR7_InvalidCombEnvelope,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7AddFactorsEnvelope`

Adds a new factors envelope to a specified model.

**Syntax**

```c
long St7AddFactorsEnvelope(long uID, long EnvType, char*
EnvName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EnvType` — Factors envelope type, either etFactEnvelopeMin or etFactEnvelopeMax.
- `EnvName` — Name of the envelope.

**Errors**

```
ERR7_ExceededMaxNumFactorsEnvelopes,
ERR7_ExceededResultCase, ERR7_FileNotOpen,
ERR7_InvalidFactorsEnvelopeType, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7InsertFactorsEnvelope`

Inserts a new factors envelope at the specified position.

**Syntax**

```c
long St7InsertFactorsEnvelope(long uID, long Envelope, long
EnvType, char* EnvName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Envelope` — Factors envelope number.
- `EnvType` — Factors envelope type, either etFactEnvelopeMin or etFactEnvelopeMax.
- `EnvName` — Name of the envelope.

**Errors**

```
ERR7_ExceededResultCase, ERR7_FileNotOpen,
ERR7_InvalidFactorsEnvelope,
ERR7_InvalidFactorsEnvelopeType, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7DeleteFactorsEnvelope`

Deletes the specified factors envelope.

**Syntax**

```c
long St7DeleteFactorsEnvelope(long uID, long Envelope)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Envelope` — Factors envelope number.

**Errors**

```
ERR7_ExceededResultCase, ERR7_FileNotOpen,
ERR7_InvalidFactorsEnvelope, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7SetFactorsEnvelopeData`

Assigns the settings for a specified factors envelope.

**Syntax**

```c
long St7SetFactorsEnvelopeData(long uID, long Envelope,
long EnvType, char* EnvName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Envelope` — Factors envelope number.
- `EnvType` — Factors envelope type, either etFactEnvelopeMin or etFactEnvelopeMax.
- `EnvName` — Name of the envelope.

**Errors**

```
ERR7_DataNotFound, ERR7_ExceededResultCase,
ERR7_FileNotOpen, ERR7_InvalidFactorsEnvelope,
ERR7_InvalidFactorsEnvelopeType, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7GetFactorsEnvelopeData`

Returns the settings assigned to a specified factors envelope.

**Syntax**

```c
long St7GetFactorsEnvelopeData(long uID, long Envelope,
long* EnvType, char* EnvName, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Envelope` — Factors envelope number.
- `MaxStringLen` — Maximum number of characters allocated for EnvName.

**Output Parameters**

- `EnvType` — Factors envelope type, either etFactEnvelopeMin or etFactEnvelopeMax.
- `EnvName` — Name of the envelope.

**Errors**

```
ERR7_DataNotFound, ERR7_ExceededResultCase,
ERR7_FileNotOpen, ERR7_InvalidFactorsEnvelope,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7AddFactorsEnvelopeCase`

Adds a new result case dependency to a specified factors envelope.

**Syntax**

```c
long St7AddFactorsEnvelopeCase(long uID, long Envelope)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Envelope` — Factors envelope number.

**Errors**

```
ERR7_DataNotFound, ERR7_ExceededResultCase,
ERR7_FileNotOpen, ERR7_InvalidFactorsEnvelope,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7InsertFactorsEnvelopeCase`

Inserts a new result case dependency at a specified position in a factors
envelope.

**Syntax**

```c
long St7InsertFactorsEnvelopeCase(long uID, long Envelope,
long Pos)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Envelope` — Factors envelope number.
- `Pos` — New factors envelope case number.

**Errors**

```
ERR7_DataNotFound, ERR7_ExceededResultCase,
ERR7_FileNotOpen, ERR7_InvalidFactorsEnvelope,
ERR7_InvalidFileUnit, ERR7_InvalidTableRow, ERR7_NoError,
ERR7_ResultFileNotOpen
```


---

### `St7DeleteFactorsEnvelopeCase`

Deletes the specified result case dependency for a factors envelope.

**Syntax**

```c
long St7DeleteFactorsEnvelopeCase(long uID, long Envelope,
long Pos)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Envelope` — Factors envelope number.
- `Pos` — Factors envelope case number.

**Errors**

```
ERR7_DataNotFound, ERR7_ExceededResultCase,
ERR7_FileNotOpen, ERR7_InvalidFactorsEnvelope,
ERR7_InvalidFileUnit, ERR7_InvalidTableRow, ERR7_NoError,
ERR7_ResultFileNotOpen
```


---

### `St7SetFactorsEnvelopeCaseData`

Assigns the settings for the specified factors envelope case.

**Syntax**

```c
long St7SetFactorsEnvelopeCaseData(long uID, long Envelope,
long Pos, long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Envelope` — Factors envelope number.
- `Pos` — Factors envelope case number.
- `Integers[0..1]` — A 2 element array containing the result case number and set number for the factors envelope case respectively.
- `Doubles[0..1]` — A 2 element array containing the Factor1 and Factor2 values for the factors envelope case.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededResultCase,
ERR7_FileNotOpen, ERR7_InvalidEnvelopeSet,
ERR7_InvalidFactorsEnvelope, ERR7_InvalidFileUnit,
ERR7_InvalidTableRow, ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7GetFactorsEnvelopeCaseData`

Returns the settings assigned to a specified factors envelope case.

**Syntax**

```c
long St7GetFactorsEnvelopeCaseData(long uID, long Envelope,
long Pos, long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Envelope` — Factors envelope number.
- `Pos` — Factors envelope case number.

**Output Parameters**

- `Integers[0..1]` — A 2 element array containing the result case number and set number for the factors envelope case respectively.
- `Doubles[0..1]` — A 2 element array containing the Factor1 and Factor2 values for the factors envelope case.

**Errors**

```
ERR7_DataNotFound, ERR7_ExceededResultCase,
ERR7_FileNotOpen, ERR7_InvalidFactorsEnvelope,
ERR7_InvalidFileUnit, ERR7_InvalidTableRow, ERR7_NoError,
ERR7_ResultFileNotOpen
```


---

### `St7AddFactorsEnvelopeSet`

Adds a new set to the specified factors envelope.

**Syntax**

```c
long St7AddFactorsEnvelopeSet(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_ExceededMaxNumEnvelopeSets, ERR7_ExceededResultCase,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileNotOpen
```


---

### `St7InsertFactorsEnvelopeSet`

Inserts a new set at the specified position for a factors envelope.

**Syntax**

```c
long St7InsertFactorsEnvelopeSet(long uID, long Pos)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Pos` — New set position.

**Errors**

```
ERR7_ExceededResultCase, ERR7_FileNotOpen,
ERR7_InvalidEnvelopeSet, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileNotOpen
```


---

### `St7DeleteFactorsEnvelopeSet`

Deletes the specified set from a factors envelope.

**Syntax**

```c
long St7DeleteFactorsEnvelopeSet(long uID, long Pos)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Pos` — Set position.

**Errors**

```
ERR7_ExceededResultCase, ERR7_FileNotOpen,
ERR7_InvalidEnvelopeSet, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileNotOpen
```


---

### `St7GetNumFactorsEnvelopeSets`

Returns the number of sets assigned to a specified factors envelope.

**Syntax**

```c
long St7GetNumFactorsEnvelopeSets(long uID, long* NumSets)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumSets` — Number of sets in the envelope.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetFactorsEnvelopeSetData`

Assigns the settings for a specified set in a factors envelope.

**Syntax**

```c
long St7SetFactorsEnvelopeSetData(long uID, long Pos, long
SetType, char* SetName, char* SetGroup)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Pos` — Set position.
- `SetType` — Type of set, either stExclusiveOR or stExclusiveAND.
- `SetName` — Name of the set.
- `SetGroup` — Group identifier for set.

**Errors**

```
ERR7_DataNotFound, ERR7_ExceededResultCase,
ERR7_FileNotOpen, ERR7_InvalidEnvelopeSet,
ERR7_InvalidEnvelopeSetType, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileNotOpen
```
