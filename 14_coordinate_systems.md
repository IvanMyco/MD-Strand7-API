---
title: "Coordinate Systems"
source: "Strand7 R246 API Manual"
pages: 138–142
---

# Coordinate Systems

---

### `St7DeleteFreedomCase`

Deletes the specified freedom case in the Strand7 model.

**Syntax**

```c
long St7DeleteFreedomCase(long uID, long CaseNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — The ID number of the freedom case to be deleted.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidFreedomCase, ERR7_NoError,
ERR7_OnlyOneFreedomCase, ERR7_ResultFileIsOpen
```


---

### `St7SetUCS`

Sets the data for a specified UCS in a Strand7 model.

**Syntax**

```c
long St7SetUCS(long uID, long UCSId, long UCSType, double*
UCSDoubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `UCSId` — The ID number for the specified UCS.
- `UCSType` — The type of the UCS, one of UCSCartesian, UCSCylindrical, UCSSpherical or UCSToroidal.
- `UCSDoubles[0..kMaxUCSDoubles-1]` — An array defining the UCS axis system. See Coordinate System Conventions.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_InvalidUCSID,
ERR7_InvalidUCSType, ERR7_NoError
```


---

### `St7GetUCS`

Returns the data for a specified UCS in a Strand7 model.

**Syntax**

```c
long St7GetUCS(long uID, long UCSId, long* UCSType, double*
UCSDoubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `UCSId` — The ID number for the specified UCS.

**Output Parameters**

- `UCSType` — The type of the UCS, one of UCSCartesian, UCSCylindrical, UCSSpherical or UCSToroidal.
- `UCSDoubles[0..kMaxUCSDoubles-1]` — An array defining the UCS axis system. See Coordinate System Conventions.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_UnknownUCS
```


---

### `St7SetUCSName`

Sets the name of a specified UCS in a Strand7 model.

**Syntax**

```c
long St7SetUCSName(long uID, long UCSId, char* UCSName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `UCSId` — The ID number of the specified UCS.
- `UCSName` — String containing the new name of the UCS.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_InvalidUCSID,
ERR7_NoError, ERR7_UCSIDAlreadyExists
```


---

### `St7GetUCSName`

Returns the name of a specified UCS in a Strand7 model.

**Syntax**

```c
long St7GetUCSName(long uID, long UCSId, char* UCSName,
long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `UCSId` — The ID number of the specified UCS.
- `MaxStringLen` — The maximum number of characters allocated for UCSName.

**Output Parameters**

- `UCSName` — String containing the name of the UCS.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_UnknownUCS
```


---

### `St7GetUCSID`

Returns the ID number corresponding to a specified UCS index in a Strand7
model.

**Syntax**

```c
long St7GetUCSID(long uID, long Index, long* UCSId)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Index` — The UCS index number. The list of available UCSs in the model is always contiguous.

**Output Parameters**

- `UCSId` — The UCS ID number corresponding to Index. UCS ID numbers are not required to be contiguous.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_InvalidIndex,
ERR7_NoError
```


---

### `St7GetNumUCS`

Returns the number of UCSs in a Strand7 model.

**Syntax**

```c
long St7GetNumUCS(long uID, long* NumUCS)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumUCS` — The number of UCSs in the model.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```
