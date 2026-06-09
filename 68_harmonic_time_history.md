---
title: "Harmonic Time History"
source: "Strand7 R246 API Manual"
pages: 947–947
---

# Harmonic Time History

Result File Combination
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotCombResFiles, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_InvalidResultFile, ERR7_NoError,
ERR7_ResultFileIsOpen


---

### `St7UpdateResultFileComb`

Updates the specified result file combination.

**Syntax**

```c
long St7UpdateResultFileComb(long uID, char* FileName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the result file.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidResultFile, ERR7_NoError, ERR7_ResultFileIsOpen
```
