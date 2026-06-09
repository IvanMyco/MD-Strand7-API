---
title: "Solver – Harmonic Response"
source: "Strand7 R246 API Manual"
pages: 775–780
---

# Solver – Harmonic Response

Solver – Natural Frequency

Doubles[0..2]
A 3 element array describing the direction vector in the Global Cartesian
Coordinate system. The orientation of this vector is used when calculating
mass participation factors.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen


---

### `St7GetNFAModeParticipationVectors`

Returns the direction vector assigned for Natural Frequency analysis used when
calculating mass participation factors.

**Syntax**

```c
long St7GetNFAModeParticipationVectors(long uID, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `Doubles[0..2]` — A 3 element array describing the direction vector in the Global Cartesian Coordinate system. The orientation of this vector is used when calculating mass participation factors.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetHRARange`

Assigns the frequency range used when performing Harmonic Response analysis.

**Syntax**

```c
long St7SetHRARange(long uID, long NumSteps, double F1,
double F2, bool AutoInsert)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `NumSteps` — Number of steps in the range.
- `F1` — Starting frequency (Hz).
- `F2` — Finishing frequency (Hz).
- `AutoInsert` — btTrue to automatically insert additional steps within the range. This feature is used to ensure that peaks in the frequency response are adequately captured.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetHRARange`

Returns the frequency range assigned for Harmonic Response analysis.

**Syntax**

```c
long St7GetHRARange(long uID, long* NumSteps, double* F1,
double* F2, bool* AutoInsert)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumSteps` — Number of steps in the range.
- `F1` — Starting frequency (Hz).
- `F2` — Finishing frequency (Hz).
- `AutoInsert` — btTrue to automatically insert additional steps within the range. This feature is used to ensure that peaks in the frequency response are adequately captured.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetHRAResultType`

Assigns the result type generated when performing Harmonic Response analysis.
This option is only used when the load type is set to Applied load.

**Syntax**

```c
long St7SetHRAResultType(long uID, long lType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `lType` — Result type, either htVsTime or htVsFrequency.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidHarmonicLoadType, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetHRAResultType`

Returns the result type assigned for Harmonic Response analysis. This option is only
used when the load type is set to Applied load.

**Syntax**

```c
long St7GetHRAResultType(long uID, long* lType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `lType` — Result type, either htVsTime or htVsFrequency.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetHRABaseVector`

Assigns the base excitation vector used when performing Harmonic Response
analysis.

**Syntax**

```c
long St7SetHRABaseVector(long uID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Doubles[0..2]` — A 3 element array containing the base excitation vector.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetHRABaseVector`

Returns the base excitation vector used when performing Harmonic Response
analysis.

**Syntax**

```c
long St7GetHRABaseVector(long uID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `Doubles[0..2]` — A 3 element array containing the base excitation vector.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetHRALoadCase`

Assigns a harmonic load case factor, phase angle and frequency to a given
load case. This option is only used when the load type is set to Applied load.

**Syntax**

```c
long St7SetHRALoadCase(long uID, long CaseNum, long TableID,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Load case number.
- `TableID` — Factor vs Frequency table ID, zero for none.
- `Doubles[0..2]` — A 3 element array containing the load factor, the phase angle in degrees, and the frequency in Hz, for load case CaseNum. Note that the frequency is only used in vs Time analyses.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_InvalidTableType, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist
```


---

### `St7GetHRALoadCase`

Returns the harmonic load case factor, phase angle and frequency assigned to
a given load case. This option is only used when the load type is set to Applied
load.

**Syntax**

```c
long St7GetHRALoadCase(long uID, long CaseNum, long*
TableID, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
