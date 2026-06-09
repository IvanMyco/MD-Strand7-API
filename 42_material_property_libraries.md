---
title: "Material Property Libraries"
source: "Strand7 R246 API Manual"
pages: 715–724
---

# Material Property Libraries

Load Path Templates

LoadPathTemplateID
Load path template ID number.

MaxStringLen
Maximum number of characters allocated for K0, K1.
Output Parameters

K0
Expression for the K0 term in the centrifugal force equation: Fc = K0 + K1*Fz.
This formula can be a function of R, L, V and g.

K1
Expression for the K1 term in the centrifugal force equation: Fc = K0 + K1*Fz.
This formula can be a function of R, L, V and g.

Integers[0..2]
[ipLPTLimitK1] - Impose K1 limits, either btTrue or btFalse.
[ipLPTLengthUnit] - Length unit, one of luMETRE, luCENTIMETRE,
luMILLIMETRE, luFOOT or luINCH.

[ipLPTForceUnit] - Force unit, one of fuNEWTON, fuKILONEWTON,
fuMEGANEWTON, fuKILOFORCE, fuPOUNDFORCE, fuTONNEFORCE or
fuKIPFORCE.

Doubles[0..1]
[ipLPTMinK1] - Minimum K1 value.
[ipLPTMaxK1] - Maximum K1 value.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPathTemplateID, ERR7_NoError,
ERR7_UnknownError


---

### `St7GetNumLibraries`

Returns the number of material libraries currently available.

**Syntax**

```c
long St7GetNumLibraries(long uID, long LibraryType, long*
NumLibraries)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LibraryType` — Library type, one of lbMaterial, lbBeamSection, lbComposite, lbReinforcementLayout, lbCreepDefinition or lbLoadPathTemplate.

**Output Parameters**

- `NumLibraries` — Number of libraries.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLibraryType, ERR7_NoError
```


---

### `St7GetLibraryName`

Returns the name assigned to the specified library.

**Syntax**

```c
long St7GetLibraryName(long uID, long LibraryType, long
LibraryID, char* LibraryName, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LibraryType` — Library type, one of lbMaterial, lbBeamSection, lbComposite, lbReinforcementLayout, lbCreepDefinition or lbLoadPathTemplate.
- `LibraryID` — Library ID number.
- `MaxStringLen` — Maximum number of characters allocated for LibraryName.

**Output Parameters**

- `LibraryName` — Library name.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLibraryID, ERR7_InvalidLibraryType,
ERR7_NoError
```


---

### `St7GetLibraryID`

Returns the ID number assigned to a specified library.

**Syntax**

```c
long St7GetLibraryID(long uID, long LibraryType, char*
LibraryName, long* LibraryID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LibraryType` — Library type, one of lbMaterial, lbBeamSection, lbComposite, lbReinforcementLayout, lbCreepDefinition or lbLoadPathTemplate.
- `LibraryName` — Library name.

**Output Parameters**

- `LibraryID` — Library ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLibraryName, ERR7_InvalidLibraryType,
ERR7_NoError
```


---

### `St7GetNumLibraryItems`

Returns the number of items assigned to a specified library.

**Syntax**

```c
long St7GetNumLibraryItems(long uID, long LibraryType, long
LibraryID, long* NumItems)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LibraryType` — Library type, one of lbMaterial, lbBeamSection, lbComposite, lbReinforcementLayout, lbCreepDefinition or lbLoadPathTemplate.
- `LibraryID` — Library ID number.

**Output Parameters**

- `NumItems` — Number of library items.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,


ERR7_InvalidLibraryID, ERR7_InvalidLibraryType,
ERR7_NoError
```


---

### `St7GetLibraryItemName`

Returns the name assigned to a specified library item.

**Syntax**

```c
long St7GetLibraryItemName(long uID, long LibraryType, long
LibraryID, long ItemID, char* ItemName, long
MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LibraryType` — Library type, one of lbMaterial, lbBeamSection, lbComposite, lbReinforcementLayout, lbCreepDefinition or lbLoadPathTemplate.
- `LibraryID` — Library ID number.
- `ItemID` — Item ID number.
- `MaxStringLen` — Maximum number of characters allocated for ItemName.

**Output Parameters**

- `ItemName` — Name of the item.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLibraryID, ERR7_InvalidLibraryItemID,
ERR7_InvalidLibraryType, ERR7_NoError
```


---

### `St7GetLibraryItemID`

Returns the ID number assigned to a specified library item.

**Syntax**

```c
long St7GetLibraryItemID(long uID, long LibraryType, long
LibraryID, char* ItemName, long* ItemID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LibraryType` — Library type, one of lbMaterial, lbBeamSection, lbComposite, lbReinforcementLayout, lbCreepDefinition or lbLoadPathTemplate.
- `LibraryID` — Library ID number.
- `ItemName` — Name of the item.

**Output Parameters**

- `ItemID` — Item ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLibraryID, ERR7_InvalidLibraryItemName,
ERR7_InvalidLibraryType, ERR7_NoError
```


---

### `St7AssignLibraryMaterial`

Assigns the specified material library item to an element property. The material is
stored at the specified item ID position.

**Syntax**

```c
long St7AssignLibraryMaterial(long uID, long Entity, long
PropNum, long LibraryID, long ItemID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Property type, one of ptBEAMPROP, ptPLATEPROP or ptBRICKPROP.
- `PropNum` — Element property number.
- `LibraryID` — Library ID number.
- `ItemID` — Item ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidEntity,
ERR7_InvalidFileUnit, ERR7_InvalidLibraryID,
ERR7_InvalidLibraryItemID, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7AssignLibraryComposite`

Assigns the specified composite library item to a ply property. The ply material is
stored at the specified item ID position.

**Syntax**

```c
long St7AssignLibraryComposite(long uID, long PropNum, long
LibraryID, long ItemID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Composite property number.
- `LibraryID` — Library ID number.
- `ItemID` — Item ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidEntity,
ERR7_InvalidFileUnit, ERR7_InvalidLibraryID,
ERR7_InvalidLibraryItemID, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7AssignLibraryBeamSection`

Assigns the specified beam section library item to a beam property. The beam
section is stored at the specified item ID position.

**Syntax**

```c
long St7AssignLibraryBeamSection(long uID, long PropNum,
long LibraryID, long ItemID, long* Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.
- `LibraryID` — Library ID number.
- `ItemID` — Item ID number.
- `Integers[0..1]` — [0] - btTrue to import beam material data. [1] - btTrue to calculate null values.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidEntity,
ERR7_InvalidFileUnit, ERR7_InvalidLibraryID, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7AssignLibraryCreepDefinition`

Assigns the specified creep law library item to a creep law definition. The creep
law definition is stored at the specified item ID position.

**Syntax**

```c
long St7AssignLibraryCreepDefinition(long uID, long CreepID,
long LibraryID, long ItemID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CreepID` — Creep law definition ID number.
- `LibraryID` — Library ID number.
- `ItemID` — Item ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidCreepID,
ERR7_InvalidFileUnit, ERR7_InvalidLibraryID,
ERR7_InvalidLibraryItemID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7AssignLibraryLoadPathTemplate`

Assigns the specified load path library item to a load path template. The load
path template is stored at the specified item ID position.

**Syntax**

```c
long St7AssignLibraryLoadPathTemplate(long uID, long
LoadPathTemplateID, long LibraryID, long ItemID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathTemplateID` — Load path template ID number.
- `LibraryID` — Library ID number.
- `ItemID` — Item ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLibraryID, ERR7_InvalidLoadPathTemplateID,
ERR7_InvalidLibraryItemID, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7AssignLibraryReinforcementLayout`

Assigns the specified concrete reinforcement library item to a concrete
reinforcement template. The concrete reinforcement layout is stored at the
specified item ID position.

**Syntax**

```c
long St7AssignLibraryReinforcementLayout(long uID, long
LayoutID, long LibraryID, long ItemID)
```
