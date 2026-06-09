---
title: "Properties – Beams Plates and Bricks"
source: "Strand7 R246 API Manual"
pages: 502–619
---

# Properties – Beams Plates and Bricks

---

### `St7GetEntityGroup`

Returns the group number assigned to the specified entity.

**Syntax**

```c
long St7GetEntityGroup(long uID, long Entity, long
EntityNum, long* GroupID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Strand7 entity type, one of tyBEAM, tyPLATE, tyBRICK, tyLINK, tyGEOMETRYFACE or tyLOADPATH.
- `EntityNum` — Entity number.

**Output Parameters**

- `GroupID` — Group ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededTotal, ERR7_FileNotOpen,
ERR7_InvalidEntity, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError


Properties – Beams, Plates and Bricks

Properties – Beams, Plates and Bricks
```


---

### `St7GetTotalProperties`

Returns the total number and highest property index for each of the Strand7
element types in the specified model.

**Syntax**

```c
long St7GetTotalProperties(long uID, long* NumProperties,
long* LastProperty)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumProperties[0..kMaxEntityTotals-1]` — [ipBeamPropTotal] - the total number of beam property types. [ipPlatePropTotal] - the total number of plate property types. [ipBrickPropTotal] - the total number of brick property types. [ipPlyPropTotal] - the total number of ply property types.
- `LastProperty[0..kMaxEntityTotals-1]` — [ipBeamPropTotal] - the highest beam property number. [ipPlatePropTotal] - the highest plate property number. [ipBrickPropTotal] - the highest brick property number. [ipPlyPropTotal] - the highest ply property number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetPropertyNumByIndex`

Returns the property number associated with a specified property index. The
property indices are stored internally and are based on a contiguous numbering
system.

**Syntax**

```c
long St7GetPropertyNumByIndex(long uID, long Entity, long
PropIndex, long* PropNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Property type, one of ptBEAMPROP, ptPLATEPROP, ptBRICKPROP or ptPLYPROP.
- `PropIndex` — Property index position.

**Output Parameters**

- `PropNum` — Property number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_InvalidIndex,
ERR7_NoError
```


---

### `St7SetPropertyName`

Sets the name of the specified property.

**Syntax**

```c
long St7SetPropertyName(long uID, long Entity, long PropNum,
char* PropName)


Properties – Beams, Plates and Bricks
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Property type, one of ptBEAMPROP, ptPLATEPROP, ptBRICKPROP or ptPLYPROP.
- `PropNum` — Property number.
- `PropName` — Name of the property.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7GetPropertyName`

Returns the name of the specified property.

**Syntax**

```c
long St7GetPropertyName(long uID, long Entity, long PropNum,
char* PropName, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Property type, one of ptBEAMPROP, ptPLATEPROP, ptBRICKPROP or ptPLYPROP.
- `PropNum` — Property number.
- `MaxStringLen` — Maximum number of characters allocated for PropName.

**Output Parameters**

- `PropName` — Name of the property.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError
```


---

### `St7SetPropertyColour`

Sets the colour of the specified property.

**Syntax**

```c
long St7SetPropertyColour(long uID, long Entity, long
PropNum, long PropCol)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Property type, one of ptBEAMPROP, ptPLATEPROP, ptBRICKPROP or ptPLYPROP.
- `PropNum` — Property number.
- `PropCol` — Property colour as a 32 bit RGB value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileIsOpen, ERR7_UnknownProperty


Properties – Beams, Plates and Bricks
```


---

### `St7GetPropertyColour`

Returns the colour assigned to the specified property.

**Syntax**

```c
long St7GetPropertyColour(long uID, long Entity, long
PropNum, long* PropCol)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Property type, one of ptBEAMPROP, ptPLATEPROP, ptBRICKPROP or ptPLYPROP.
- `PropNum` — Property number.

**Output Parameters**

- `PropCol` — Property colour as a 32 bit RGB value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_UnknownProperty
```


---

### `St7SetPropertyTable`

Assigns a table to the specified material property value.

**Syntax**

```c
long St7SetPropertyTable(long uID, long ptType, long
PropNum, long TableID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `ptType` — Property table type, see Table Types for additional information.
- `PropNum` — Property number.
- `TableID` — Table ID number, zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_IncompatibleTableType,
ERR7_InvalidFileUnit, ERR7_InvalidTableSetting,
ERR7_NoError, ERR7_ResultFileIsOpen, ERR7_TableDoesNotExist,
ERR7_UnknownProperty
```


---

### `St7GetPropertyTable`

Returns the table assigned to the specified material property value.

**Syntax**

```c
long St7GetPropertyTable(long uID, long ptType, long
PropNum, long* TableID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `ptType` — Property table type, see Table Types for additional information.
- `PropNum` — Property number.

**Output Parameters**

- `TableID` — Table ID number, zero for none. Properties – Beams, Plates and Bricks

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_IncompatibleTableType,
ERR7_InvalidFileUnit, ERR7_InvalidTableSetting,
ERR7_NoError, ERR7_UnknownProperty, ERR7_TableDoesNotExist
```


---

### `St7SetPropertyCreepID`

Assigns the creep definition to the specified property.

**Syntax**

```c
long St7SetPropertyCreepID(long uID, long Entity, long
PropNum, long CreepID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Property type, one of ptBEAMPROP, ptPLATEPROP or ptBRICKPROP.
- `PropNum` — Property number.
- `CreepID` — ID of creep property, zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidCreepID, ERR7_InvalidEntity,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_UnknownProperty
```


---

### `St7GetPropertyCreepID`

Returns the creep definition of the specified property.

**Syntax**

```c
long St7GetPropertyCreepID(long uID, long Entity, long
PropNum, long* CreepID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Property type, one of ptBEAMPROP, ptPLATEPROP or ptBRICKPROP.
- `PropNum` — Property number.

**Output Parameters**

- `CreepID` — ID of creep property, zero for none.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_UnknownProperty
```


---

### `St7SetMaterialName`

Sets the name of the material referenced by the specified property.

**Syntax**

```c
long St7SetMaterialName(long uID, long Entity, long PropNum,
char* MaterialName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Property type, one of ptBEAMPROP, ptPLATEPROP, ptBRICKPROP or ptPLYPROP. Properties – Beams, Plates and Bricks
- `PropNum` — Property number.
- `MaterialName` — Name of the material.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7GetMaterialName`

Returns the name of the material referenced by the specified property.

**Syntax**

```c
long St7GetMaterialName(long uID, long Entity, long PropNum,
char* MaterialName, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Property type, one of ptBEAMPROP, ptPLATEPROP, ptBRICKPROP or ptPLYPROP.
- `PropNum` — Property number.
- `MaxStringLen` — Maximum number of characters allocated for MaterialName.

**Output Parameters**

- `MaterialName` — Name of the material.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_UnknownProperty
```


---

### `St7SetHardeningType`

Sets the hardening model used for the specified property. This option is only used
when a Stress vs Strain table is assigned to the specified property.

**Syntax**

```c
long St7SetHardeningType(long uID, long Entity, long
PropNum, long HardType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Property type, use ptBEAMPROP.
- `PropNum` — Property number.
- `HardType` — Type of hardening, one of htIsotropic, htKinematic or htTakeda.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_InvalidHardeningType, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7GetHardeningType`

Returns the hardening model used for the specified property. This option is only
used when a Stress vs Strain table is assigned to the specified property.


Properties – Beams, Plates and Bricks

**Syntax**

```c
long St7GetHardeningType(long uID, long Entity, long
PropNum, long* HardType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Property type, use ptBEAMPROP.
- `PropNum` — Property number.

**Output Parameters**

- `HardType` — Type of hardening, one of htIsotropic, htKinematic or htTakeda.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_UnknownProperty
```


---

### `St7SetTimeDependentModType`

Sets the type of temperature/time dependence for the specified property. This
setting controls the scaling used to update the material modulus values. This
option is only used when an associated Factor vs Temperature/Time table is
assigned to the specified property.

**Syntax**

```c
long St7SetTimeDependentModType(long uID, long Entity, long
PropNum, long ModType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Property type, one of ptBEAMPROP, ptPLATEPROP or ptBRICKPROP.
- `PropNum` — Property number.
- `ModType` — Type of temperature/time dependence, either mtElastic or mtPlastic.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_InvalidModType, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_UnknownProperty
```


---

### `St7GetTimeDependentModType`

Returns the type of temperature/time dependence assigned to the specified
property. This setting controls the scaling used to update the material modulus
values. This option is only used when an associated Factor vs Temperature/Time
table is assigned to the specified property.

**Syntax**

```c
long St7GetTimeDependentModType(long uID, long Entity, long
PropNum, long* ModType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Property type, one of ptBEAMPROP, ptPLATEPROP or ptBRICKPROP.
- `PropNum` — Property number.

**Output Parameters**

- `ModType` — Type of temperature/time dependence, either mtElastic or mtPlastic. Properties – Beams, Plates and Bricks

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_UnknownProperty
```


---

### `St7SetAlphaTempType`

Sets the thermal expansion table type for the specified property.

**Syntax**

```c
long St7SetAlphaTempType(long uID, long Entity, long
PropNum, long AlphaTempType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Property type, one of ptBEAMPROP, ptPLATEPROP or ptBRICKPROP.
- `PropNum` — Property number.
- `AlphaTempType` — Table type, either kIntegratedAlpha or kInstantAlpha.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidAlphaTempType,
ERR7_InvalidEntity, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7GetAlphaTempType`

Returns the type of thermal expansion table assigned to the specified property.

**Syntax**

```c
long St7GetAlphaTempType(long uID, long Entity, long
PropNum, long* AlphaTempType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Property type, one of ptBEAMPROP, ptPLATEPROP or ptBRICKPROP.
- `PropNum` — Property number.

**Output Parameters**

- `AlphaTempType` — Table type, either kIntegratedAlpha or kInstantAlpha.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_UnknownProperty
```


---

### `St7NewBeamProperty`

Creates a new beam property.

**Syntax**

```c
long St7NewBeamProperty(long uID, long PropNum, long
BeamType, char* PropName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Property number.
- `BeamType` — Properties – Beams, Plates and Bricks Type of beam element, one of kBeamTypeNull, kBeamTypeSpring, kBeamTypeCable, kBeamTypeTruss, kBeamTypeCutoff , kBeamTypeContact, kBeamTypeBeam, kBeamTypeUser, kBeamTypePipe, kBeamTypeConnection.
- `PropName` — Name of the property.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidBeamType,
ERR7_InvalidFileUnit, ERR7_InvalidPropertyNumber,
ERR7_NoError, ERR7_PropertyAlreadyExists,
ERR7_ResultFileIsOpen
```


---

### `St7GetBeamPropertyData`

Returns the specified beam property.

**Syntax**

```c
long St7GetBeamPropertyData(long uID, long PropNum, long*
Integers, double* SectionData, double* BeamMaterial)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Property number.

**Output Parameters**

- `Integers[0..3]` — [0] - Type of beam element, one of kBeamTypeNull, kBeamTypeSpring, kBeamTypeCable, kBeamTypeTruss, kBeamTypeCutoff , kBeamTypeContact, kBeamTypeBeam, kBeamTypeUser, kBeamTypePipe, kBeamTypeConnection. [1] - Type of beam section, one of kNullSection, kCircularSolid, kCircularHollow, kSquareSolid, kSquareHollow, kLipChannel, kTopHatChannel, kISection, kTSection, kLSection, kZSection, kUserSection, kTrapezoidSolid, kTrapezoidHollow, kTriangleSolid, kTriangleHollow or kCruciform. [2] - Section mirror type, one of kMirrorNone, kMirrorTop, kMirrorBot, kMirrorLeft, kMirrorRight, kMirrorLeftAndTop, kMirrorLeftAndBot, kMirrorRightAndTop, kMirrorRightAndBot, kMirrorLeftTopOnly, kMirrorLeftBotOnly, kMirrorRightTopOnly or kMirrorRightBotOnly. [3] - Compatible twist option for mirrored sections, either btTrue or btFalse.
- `SectionData[0..kNumBeamSectionData-1]` — [ipAREA] - Section area. [ipI11] - Second moment of area about the principal 1 axis. [ipI22] - Second moment of area about the principal 2 axis. [ipJ] - Torsion constant. [ipSL1] - Shear centre offset in the principal 1 axis direction. [ipSL2] - Shear centre offset in the principal 2 axis direction. [ipSA1] - Shear area in the principal 1 axis direction. [ipSA2] - Shear area in the principal 2 axis direction. [ipXBAR] - Centroid offset in the principal 1 axis direction. [ipYBAR] - Centroid offset in the principal 2 axis direction. [ipANGLE] - Principal axis 1 angle w.r.t. the local section coordinates. [ipD1] - Section geometry D1 parameter. [ipD2] - Section geometry D2 parameter. [ipD3] - Section geometry D3 parameter. [ipT1] - Section geometry T1 parameter. [ipT2] - Section geometry T2 parameter. [ipT3] - Section geometry T3 parameter. [ipGapA] - Mirrored section gap parameter A. [ipGapB] - Mirrored section gap parameter B. Properties – Beams, Plates and Bricks
- `BeamMaterial[0..kNumMaterialData-1]` — [ipModulus] - Material modulus. [ipPoisson] - Material Poisson’s ratio. [ipDensity] - Material density.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_UnknownProperty
```


---

### `St7SetBeamSectionName`

Sets the section name referenced by the specified beam property.

**Syntax**

```c
long St7SetBeamSectionName(long uID, long PropNum, char*
SectionName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Property number.
- `SectionName` — Name of the section.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7GetBeamSectionName`

Returns the name of the section referenced by the specified beam property.

**Syntax**

```c
long St7GetBeamSectionName(long uID, long PropNum, char*
SectionName, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Property number.
- `MaxStringLen` — Maximum number of characters allocated for SectionName.

**Output Parameters**

- `SectionName` — Name of the section.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_UnknownProperty
```


---

### `St7SetBeamPropertyType`

Sets the beam type for the specified beam property.

**Syntax**

```c
long St7SetBeamPropertyType(long uID, long PropNum, long
BeamType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Property number.
- `BeamType` — Properties – Beams, Plates and Bricks Type of beam element, one of kBeamTypeNull, kBeamTypeSpring, kBeamTypeCable, kBeamTypeTruss, kBeamTypeCutoff , kBeamTypeContact, kBeamTypeBeam, kBeamTypeUser, kBeamTypePipe, kBeamTypeConnection.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidBeamType,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_UnknownProperty
```


---

### `St7SetBeamMirrorOption`

Sets the section mirror type for the specified beam property.

**Syntax**

```c
long St7SetBeamMirrorOption(long uID, long PropNum, long
MirrorType, long CompatibleTwist, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.
- `MirrorType` — Section mirror type, one of kMirrorNone, kMirrorTop, kMirrorBot, kMirrorLeft, kMirrorRight, kMirrorLeftAndTop, kMirrorLeftAndBot, kMirrorRightAndTop, kMirrorRightAndBot, kMirrorLeftTopOnly, kMirrorLeftBotOnly, kMirrorRightTopOnly or kMirrorRightBotOnly.
- `CompatibleTwist` — Compatible twist option for mirrored sections, either btTrue or btFalse.
- `Doubles[0..1]` — A 2 element array containing the mirror gap parameters A and B respectively.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidMirrorOption, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_SectionCannotBeMirrored,
ERR7_UnknownProperty
```


---

### `St7SetBeamNonlinearType`

Sets the nonlinear material type for the specified beam property.

**Syntax**

```c
long St7SetBeamNonlinearType(long uID, long PropNum, long
NonlinType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.
- `NonlinType` — Nonlinear material type, either ntNonlinElastic or ntElastoPlastic.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_IncompatibleCriterionCombination,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_UnknownProperty
```


---

### `St7GetBeamNonlinearType`

Returns the nonlinear material type assigned to the specified beam property.

**Syntax**

```c
long St7GetBeamNonlinearType(long uID, long PropNum, long*
NonlinType)


Properties – Beams, Plates and Bricks
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.

**Output Parameters**

- `NonlinType` — Nonlinear material type, either ntNonlinElastic or ntElastoPlastic.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_IncompatibleCriterionCombination,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_UnknownProperty
```


---

### `St7SetBeamSectionPropertyData`

Sets the beam section property data for the specified beam property.

**Syntax**

```c
long St7SetBeamSectionPropertyData(long uID, long PropNum,
long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.
- `Integers[0]` — Number of length-wise integration slices.
- `Doubles[0..10]` — [ipAREA] - Section area. [ipI11] - Second moment of area about the principal 1 axis. [ipI22] - Second moment of area about the principal 2 axis. [ipJ] - Torsion constant. [ipSL1] - Shear centre offset in the principal 1 axis direction. [ipSL2] - Shear centre offset in the principal 2 axis direction. [ipSA1] - Shear area in the principal 1 axis direction. [ipSA2] - Shear area in the principal 2 axis direction. [ipXBAR] - Centroid offset in the principal 1 axis direction. [ipYBAR] - Centroid offset in the principal 2 axis direction. [ipANGLE] - Principal axis 1 angle w.r.t. the local section coordinates.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidSectionProperties, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7GetBeamSectionPropertyData`

Returns the beam section property data assigned to the specified beam
property.

**Syntax**

```c
long St7GetBeamSectionPropertyData(long uID, long PropNum,
long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.

**Output Parameters**

- `Integers[0]` — Properties – Beams, Plates and Bricks Number of length-wise integration slices.
- `Doubles[0..10]` — [ipAREA] - Section area. [ipI11] - Second moment of area about the principal 1 axis. [ipI22] - Second moment of area about the principal 2 axis. [ipJ] - Torsion constant. [ipSL1] - Shear centre offset in the principal 1 axis direction. [ipSL2] - Shear centre offset in the principal 2 axis direction. [ipSA1] - Shear area in the principal 1 axis direction. [ipSA2] - Shear area in the principal 2 axis direction. [ipXBAR] - Centroid offset in the principal 1 axis direction. [ipYBAR] - Centroid offset in the principal 2 axis direction. [ipANGLE] - Principal axis 1 angle w.r.t. the local section coordinates.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_UnknownProperty
```


---

### `St7SetBeamSectionGeometry`

Sets the beam cross section geometry data for the specified beam property.

**Syntax**

```c
long St7SetBeamSectionGeometry(long uID, long PropNum, long
SectionType, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.
- `SectionType` — Type of beam section, one of kNullSection, kCircularSolid, kCircularHollow, kSquareSolid, kSquareHollow, kLipChannel, kTopHatChannel, kISection, kTSection, kLSection, kZSection, kUserSection, kTrapezoidSolid, kTrapezoidHollow, kTriangleSolid, kTriangleHollow or kCruciform.
- `Doubles[0..5]` — A 6 element array containing the beam cross section D1, D2, D3, T1, T2 and T3 parameters respectively.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidBeamSectionType,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_UnknownProperty
```


---

### `St7GetBeamSectionGeometry`

Returns the beam cross section data assigned to the specified beam property.

**Syntax**

```c
long St7GetBeamSectionGeometry(long uID, long PropNum,
long* SectionType, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.

**Output Parameters**

- `SectionType` — Type of beam section, one of kNullSection, kCircularSolid, kCircularHollow, kSquareSolid, kSquareHollow, kLipChannel, kTopHatChannel, kISection, kTSection, kLSection, kZSection, kUserSection, kTrapezoidSolid, kTrapezoidHollow, kTriangleSolid, kTriangleHollow or kCruciform. Properties – Beams, Plates and Bricks
- `Doubles[0..5]` — A 6 element array containing the beam cross section D1, D2, D3, T1, T2 and T3 parameters respectively.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_UnknownProperty
```


---

### `St7SetBeamSectionNominalDiscretisation`

Sets the discretisation values used when discretising the cross-section for
nonlinear beam types.

**Syntax**

```c
long St7SetBeamSectionNominalDiscretisation(long uID, long
PropNum, long* Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.
- `Integers[0..2]` — [0] - nominal divisions used to discretise the beam (along the longest ordinate), or divisions in the x-ordinate when divisions are specified. [1] - divisions in the y-ordinate used to discretise the beam when divisions are specified. [2] - btTrue to use nominal divisions, btFalse to specify the divisions in each ordinate explicitly.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7GetBeamSectionNominalDiscretisation`

Returns the discretisation values used when discretising the cross-section for
nonlinear beam types.

**Syntax**

```c
long St7GetBeamSectionNominalDiscretisation(long uID, long
PropNum, long* Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.

**Output Parameters**

- `Integers[0..2]` — [0] - nominal divisions used to discretise the beam (along the longest ordinate), or divisions in the x-ordinate when divisions are specified. [1] - divisions in the y-ordinate used to discretise the beam when divisions are specified. [2] - btTrue to use nominal divisions, btFalse to specify the divisions in each ordinate explicitly.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_UnknownProperty
```


---

### `St7SetBeamSectionCircularDiscretisation`

Sets the number of circumferential divisions used when discretising circular crosssections for nonlinear beam types.


Properties – Beams, Plates and Bricks

**Syntax**

```c
long St7SetBeamSectionCircularDiscretisation(long uID, long
PropNum, long* Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.
- `Integers[0]` — Number of circumferential divisions used to discretise the circular beam crosssection, one of; 0 - for Auto divisions 1 - for 8 divisions 2 - for 16 divisions 3 - for 32 divisions 4 - for 64 divisions.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7GetBeamSectionCircularDiscretisation`

Returns the number of circumferential divisions used when discretising circular
cross-sections for nonlinear beam types.

**Syntax**

```c
long St7GetBeamSectionCircularDiscretisation(long uID, long
PropNum, long* Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.

**Output Parameters**

- `Integers[0]` — Number of circumferential divisions used to discretise the circular beam crosssection, one of; 0 - for Auto divisions 1 - for 8 divisions 2 - for 16 divisions 3 - for 32 divisions 4 - for 64 divisions.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_UnknownProperty
```


---

### `St7CalculateBeamSectionProperties`

Calculates the section properties based on the section geometry assigned for
the specified beam property.

**Syntax**

```c
long St7CalculateBeamSectionProperties(long uID, long
PropNum, bool DoShear, bool ExactJ)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number. Properties – Beams, Plates and Bricks
- `DoShear` — Include the shear area values, either btTrue or btFalse. If the shear areas are included the “thick” beam formulation is used.
- `ExactJ` — Perform an accurate calculation for the torsional constant, either btTrue or btFalse. If this flag is set to btFalse a fast but approximate calculation is performed.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidSectionParameters, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7AssignBXS`

Assigns a BXS to the specified beam property.

**Syntax**

```c
long St7AssignBXS(long uID, long PropNum, char* BXSName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.
- `BXSName` — Name of the BXS.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileName,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_UnknownProperty
```


---

### `St7SetSpringDamperData`

Sets the spring-damper element parameters for the specified beam property.

**Syntax**

```c
long St7SetSpringDamperData(long uID, long PropNum, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.
- `Doubles[0..6]` — [ipSpringAxialStiff] - Axial stiffness. [ipSpringLateralStiff] - Lateral stiffness. [ipSpringTorsionStiff] - Torsional stiffness. [ipSpringAxialDamp] - Axial damping. [ipSpringLateralDamp] - Lateral damping. [ipSpringTorsionDamp] - Torsional damping. [ipSpringMass] - Element mass.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_PropertyNotSpring, ERR7_ResultFileIsOpen,
ERR7_UnknownProperty
```


---

### `St7GetSpringDamperData`

Returns the spring-damper element parameters assigned to the specified beam
property.


Properties – Beams, Plates and Bricks

**Syntax**

```c
long St7GetSpringDamperData(long uID, long PropNum, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.

**Output Parameters**

- `Doubles[0..6]` — [ipSpringAxialStiff] - Axial stiffness. [ipSpringLateralStiff] - Lateral stiffness. [ipSpringTorsionStiff] - Torsional stiffness. [ipSpringAxialDamp] - Axial damping. [ipSpringLateralDamp] - Lateral damping. [ipSpringTorsionDamp] - Torsional damping. [ipSpringMass] - Element mass.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_PropertyNotSpring, ERR7_UnknownProperty
```


---

### `St7SetCableData`

Sets the cable element parameters for the specified beam property.

**Syntax**

```c
long St7SetCableData(long uID, long PropNum, long*
Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.
- `Integers[0..0]` — [ipCableSegments] - Number of segments used internally to discretise cable.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_PropertyNotCable, ERR7_ResultFileIsOpen,
ERR7_UnknownProperty
```


---

### `St7GetCableData`

Returns the cable element parameters assigned to the specified beam property.

**Syntax**

```c
long St7GetCableData(long uID, long PropNum, long*
Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.

**Output Parameters**

- `Integers[0..0]` — [ipCableSegments] - Number of segments used internally to discretise cable. Properties – Beams, Plates and Bricks

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_UnknownProperty
```


---

### `St7SetTrussData`

Sets the truss element parameters for the specified beam property.

**Syntax**

```c
long St7SetTrussData(long uID, long PropNum, long*
Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.
- `Integers[0..0]` — [ipTrussIncludeTorsion] - Include torsion, either btTrue or btFalse.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_PropertyNotTruss, ERR7_ResultFileIsOpen,
ERR7_UnknownProperty
```


---

### `St7GetTrussData`

Returns the truss element parameters for the specified beam property.

**Syntax**

```c
long St7GetTrussData(long uID, long PropNum, long*
Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.

**Output Parameters**

- `Integers[0..0]` — [ipTrussIncludeTorsion] - Include torsion, either btTrue or btFalse.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_PropertyNotTruss, ERR7_UnknownProperty
```


---

### `St7SetCutoffBarData`

Sets the cut-off bar parameters for the specified beam property.

**Syntax**

```c
long St7SetCutoffBarData(long uID, long PropNum, long*
Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.
- `Integers[0..1]` — [ipCutoffType] - Type of cut-off bar, either kBrittleGap or kDuctileGap. [ipKeepMass] - Use element mass, either btTrue or btFalse.
- `Doubles[0..1]` — [ipCutoffTension] - Tensile force limit. Properties – Beams, Plates and Bricks [ipCutoffCompression] - Compressive force limit.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidCutoffType,
ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_PropertyNotCutOffBar, ERR7_ResultFileIsOpen,
ERR7_UnknownProperty
```


---

### `St7GetCutoffBarData`

Returns the cut-off bar parameters assigned to the specified beam property.

**Syntax**

```c
long St7GetCutoffBarData(long uID, long PropNum, long*
Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.

**Output Parameters**

- `Integers[0..1]` — [ipCutoffType] - Type of cut-off bar, either kBrittleGap or kDuctileGap. [ipKeepMass] - Use element mass, either btTrue or btFalse.
- `Doubles[0..1]` — [ipCutoffTension] - Tensile force limit. [ipCutoffCompression] - Compressive force limit.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_PropertyNotCutOffBar, ERR7_UnknownProperty
```


---

### `St7SetPointContactData`

Sets the point contact element parameters for the specified beam property.

**Syntax**

```c
long St7SetPointContactData(long uID, long PropNum, long*
Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.
- `Integers[0..7]` — [ipContactType] - Type of contact element, one of kZeroGapContact, kNormalContact, kTensionContact or kTakeupContact. [ipContactSubType] - Type of Takeup contact, either kTensionTakeup or kCompressionTakeup. [ipDynamicStiffness] - Update the stiffness of the contact element, either btTrue or btFalse. [ipUseInFirstIteration] - Use contact in the first iteration of a nonlinear solution, either btTrue or btFalse. [ipUpdateDirection] - Update the direction of the contact throughout solution, either btTrue or btFalse. [ipFrictionModel] - Type of friction model used, either cfElastic or cfPlastic. [ipFrictionYieldType] - Type of yield, either cyRectangular or cyElliptical. [ipTensionLateralStiffness] - Use lateral stiffness with kTensionContact elements, either btTrue or btFalse.
- `Doubles[0..3]` — Properties – Beams, Plates and Bricks [ipContactStiffness] - Penalty stiffness value. This value is updated dynamically based on the Update Direction settings. [ipFrictionC1] - Lateral friction coefficient in the 1 axis direction. [ipFrictionC2] - Lateral friction coefficient in the 2 axis direction. [ipContactMaxTension] - Maximum tensile force value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidContactSubType,
ERR7_InvalidContactType, ERR7_InvalidContactYieldType,
ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_PropertyNotPointContact, ERR7_ResultFileIsOpen,
ERR7_UnknownProperty
```


---

### `St7GetPointContactData`

Returns the point contact element parameters assigned to the specified beam
property.

**Syntax**

```c
long St7GetPointContactData(long uID, long PropNum, long*
Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.

**Output Parameters**

- `Integers[0..7]` — [ipContactType] - Type of contact element, one of kZeroGapContact, kNormalContact, kTensionContact or kTakeupContact. [ipContactSubType] - Type of Takeup contact, either kTensionTakeup or kCompressionTakeup. [ipDynamicStiffness] - Update the stiffness of the contact element, either btTrue or btFalse. [ipUseInFirstIteration] - Use contact in the first iteration of a nonlinear solution, either btTrue or btFalse. [ipUpdateDirection] - Update the direction of the contact throughout solution, either btTrue or btFalse. [ipFrictionModel] - Type of friction model used, either cfElastic or cfPlastic. [ipFrictionYieldType] - Type of yield, either cyRectangular or cyElliptical. [ipTensionLateralStiffness] - Use lateral stiffness with kTensionContact elements, either btTrue or btFalse.
- `Doubles[0..3]` — [ipContactStiffness] - Penalty stiffness value. This value is updated dynamically based on the Update Direction settings. [ipFrictionC1] - Lateral friction coefficient in the 1 axis direction. [ipFrictionC2] - Lateral friction coefficient in the 2 axis direction. [ipContactMaxTension] - Maximum tensile force value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_PropertyNotPointContact, ERR7_UnknownProperty
```


---

### `St7SetPipeData`

Sets the pipe element parameters for the specified beam property.

**Syntax**

```c
long St7SetPipeData(long uID, long PropNum, double*
Doubles)
```

**Input Parameters**

- `uID` — Properties – Beams, Plates and Bricks Strand7 model file ID number.
- `PropNum` — Beam property number.
- `Doubles[0..3]` — [ipPipeFlexibility] - Flexibility factor. [ipPipeFluidDensity] - Density of contained fluid. [ipPipeOuterDiameter] - Outer diameter. [ipPipeThickness] - Wall thickness.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_PropertyNotPipe, ERR7_ResultFileIsOpen,
ERR7_UnknownProperty
```


---

### `St7GetPipeData`

Returns the pipe element parameters for the specified beam property.

**Syntax**

```c
long St7GetPipeData(long uID, long PropNum, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.

**Output Parameters**

- `Doubles[0..3]` — [ipPipeFlexibility] - Flexibility factor. [ipPipeFluidDensity] - Density of contained fluid. [ipPipeOuterDiameter] - Outer diameter. [ipPipeThickness] - Wall thickness.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_PropertyNotPipe, ERR7_UnknownProperty
```


---

### `St7SetConnectionData`

Sets the connection element parameters for the specified beam property.

**Syntax**

```c
long St7SetConnectionData(long uID, long PropNum, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.
- `Doubles[0..5]` — A 6 element array describing the element translational and rotational stiffness values according to the 123456 axis convention in the beam’s local principal axis system. A UCS may be assigned to the element ends to override the local principal axis system using St7SetBeamConnectionUCS.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty


Properties – Beams, Plates and Bricks
```


---

### `St7GetConnectionData`

Returns the connection element parameters for the specified beam property.

**Syntax**

```c
long St7GetConnectionData(long uID, long PropNum, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.

**Output Parameters**

- `Doubles[0..5]` — A 6 element array describing the element translational and rotational stiffness values according to the 123456 axis convention in the UCS assigned to the element. A UCS may be assigned to the element ends to override the local principal axis system using St7SetBeamConnectionUCS.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_UnknownProperty
```


---

### `St7SetUserBeamData`

Sets the user defined element parameters for the specified beam property.

**Syntax**

```c
long St7SetUserBeamData(long uID, long PropNum, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.
- `Doubles[0..21]` — [0..20] - User defined material matrix K defined by the upper triangular matrix of coefficients Kij where i < j and i varies quickest; K11, K12,… K22, K23,… K66, respectively. [21] - Spring mass.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_PropertyNotUserDefinedBeam, ERR7_ResultFileIsOpen,
ERR7_UnknownProperty
```


---

### `St7GetUserBeamData`

Returns the user defined element property for the specified beam property.

**Syntax**

```c
long St7GetUserBeamData(long uID, long PropNum, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.

**Output Parameters**

- `Doubles[0..21]` — [0..20] - User defined material matrix K defined by the upper triangular matrix of coefficients Kij where i < j and i varies quickest; K11, K12,… K22, K23,… K66, respectively. [21] - Spring mass. Properties – Beams, Plates and Bricks

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_PropertyNotUserDefinedBeam, ERR7_UnknownProperty
```


---

### `St7SetBeamMaterialData`

Sets the material properties for the specified beam property.

**Syntax**

```c
long St7SetBeamMaterialData(long uID, long PropNum, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.
- `Doubles[0..8]` — [ipBeamModulus] - Modulus. [ipBeamShear] - Shear modulus. [ipBeamPoisson] - Poisson’s ratio. [ipBeamDensity] - Density. [ipBeamAlpha] - Thermal expansion coefficient. [ipBeamViscosity] - Viscous damping coefficient. [ipBeamDampingRatio] - Damping ratio. [ipBeamConductivity] - Thermal conductivity coefficient. [ipBeamSpecificHeat] - Specific heat coefficient.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,


ERR7_MaterialIsUserDefined, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7GetBeamMaterialData`

Returns the material properties assigned to the specified beam property.

**Syntax**

```c
long St7GetBeamMaterialData(long uID, long PropNum, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.

**Output Parameters**

- `Doubles[0..8]` — [ipBeamModulus] - Modulus. [ipBeamShear] - Shear modulus. [ipBeamPoisson] - Poisson’s ratio. [ipBeamDensity] - Density. [ipBeamAlpha] - Thermal expansion coefficient. [ipBeamViscosity] - Viscous damping coefficient. [ipBeamDampingRatio] - Damping ratio. [ipBeamConductivity] - Thermal conductivity coefficient. [ipBeamSpecificHeat] - Specific heat coefficient.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,


Properties – Beams, Plates and Bricks

ERR7_MaterialIsUserDefined, ERR7_NoError,
ERR7_UnknownProperty
```


---

### `St7SetBeamUsePoisson`

Sets the specified beam property to use the Poisson’s ratio rather than the Shear
modulus values supplied.

**Syntax**

```c
long St7SetBeamUsePoisson(long uID, long PropNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialIsUserDefined, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7SetBeamUseShearMod`

Sets the specified beam property to use the Shear modulus rather than the
Poisson’s ratio values supplied.

**Syntax**

```c
long St7SetBeamUseShearMod(long uID, long PropNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialIsUserDefined, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7SetBeamUseMomCurv`

Sets the state of the Moment-Curvature option for the specified beam property.
A coupled nonlinear beam formulation is available as an alternative to the
decoupled Moment-Curvature approach.

**Syntax**

```c
long St7SetBeamUseMomCurv(long uID, long PropNum, bool
UseMomCurv)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.
- `UseMomCurv` — btTrue to use the Moment-Curvature tables assigned.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7GetBeamUseMomCurv`

Returns the state of the Moment-Curvature option for the specified beam
property. A coupled nonlinear beam formulation is available as an alternative to
the decoupled Moment-Curvature approach.


Properties – Beams, Plates and Bricks

**Syntax**

```c
long St7GetBeamUseMomCurv(long uID, long PropNum, bool*
UseMomCurv)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Beam property number.

**Output Parameters**

- `UseMomCurv` — btTrue to use the Moment-Curvature tables assigned.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_UnknownProperty
```


---

### `St7NewPlateProperty`

Creates a new plate property.

**Syntax**

```c
long St7NewPlateProperty(long uID, long PropNum, long
PlateType, long MaterialType, char* PropName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.
- `PlateType` — Type of plate element, one of kPlateTypeNull, kPlateTypePlaneStress, kPlateTypePlaneStrain, kPlateTypeAxisymmetric, kPlateTypePlateShell, kPlateTypeShearPanel, kPlateTypeMembrane or kPlateTypeLoadPatch.
- `MaterialType` — Type of material, one of kMaterialTypeNull, kMaterialTypeIsotropic, kMaterialTypeOrthotropic, kMaterialTypeAnisotropic, kMaterialTypeRubber, kMaterialTypeSoil, kMaterialTypeLaminate, kMaterialTypeUserDefined, kMaterialTypePly or kMaterialTypeFluid.
- `PropName` — Name of the plate property.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_IncompatibleMaterialCombination,
ERR7_InvalidFileUnit, ERR7_InvalidMaterialType,
ERR7_InvalidPlateType, ERR7_InvalidPropertyNumber,
ERR7_NoError, ERR7_PropertyAlreadyExists,
ERR7_ResultFileIsOpen
```


---

### `St7GetPlatePropertyData`

Returns the specified plate property data.

**Syntax**

```c
long St7GetPlatePropertyData(long uID, long PropNum, long*
Integers, double* SectionData, double* PlateMaterial)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.

**Output Parameters**

- `Integers` — This is a dummy variable to allow for future expansion of this function. Any integer variable may be passed and will be returned unchanged.
- `SectionData[0..1]` — Properties – Beams, Plates and Bricks A 2 element array describing the membrane and bending thicknesses respectively.
- `PlateMaterial[0..kNumMaterialData-1]` — [ipModulus] - Modulus. [ipPoisson] - Poisson’s ratio. [ipDensity] - Density.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotIsotropic, ERR7_NoError,
ERR7_UnknownProperty
```


---

### `St7SetPlatePropertyType`

Sets the property type for the specified plate property.

**Syntax**

```c
long St7SetPlatePropertyType(long uID, long PropNum, long
PlateType, long MaterialType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.
- `PlateType` — Type of plate element, one of kPlateTypeNull, kPlateTypePlaneStress, kPlateTypePlaneStrain, kPlateTypeAxisymmetric, kPlateTypePlateShell, kPlateTypeShearPanel, kPlateTypeMembrane or kPlateTypeLoadPatch.
- `MaterialType` — Type of material, one of kMaterialTypeNull, kMaterialTypeIsotropic, kMaterialTypeOrthotropic, kMaterialTypeAnisotropic, kMaterialTypeRubber, kMaterialTypeSoil, kMaterialTypeLaminate, kMaterialTypeUserDefined, kMaterialTypePly or kMaterialTypeFluid.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_IncompatibleMaterialCombination,
ERR7_InvalidFileUnit, ERR7_InvalidMaterialType,
ERR7_InvalidPlateType, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_UnknownProperty
```


---

### `St7GetPlatePropertyType`

Returns the property type for the specified plate property.

**Syntax**

```c
long St7GetPlatePropertyType(long uID, long PropNum, long*
PlateType, long* MaterialType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.

**Output Parameters**

- `PlateType` — Type of plate element, one of kPlateTypeNull, kPlateTypePlaneStress, kPlateTypePlaneStrain, kPlateTypeAxisymmetric, kPlateTypePlateShell, kPlateTypeShearPanel, kPlateTypeMembrane or kPlateTypeLoadPatch.
- `MaterialType` — Type of material, one of kMaterialTypeNull, kMaterialTypeIsotropic, kMaterialTypeOrthotropic, kMaterialTypeAnisotropic, kMaterialTypeRubber, kMaterialTypeSoil, kMaterialTypeLaminate, kMaterialTypeUserDefined, kMaterialTypePly or kMaterialTypeFluid. Properties – Beams, Plates and Bricks

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_UnknownProperty
```


---

### `St7SetPlateNonlinearType`

Sets the nonlinear material type for the specified plate property.

**Syntax**

```c
long St7SetPlateNonlinearType(long uID, long PropNum, long
NonlinType, long YieldType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.
- `NonlinType` — Nonlinear material type, either ntNonlinElastic or ntElastoPlastic.
- `YieldType` — Yield criterion, one of ycTresca, ycVonMises, ycMaxStress, ycMohrCoulomb or ycDruckerPrager.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_IncompatibleCriterionCombination,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_UnknownProperty
```


---

### `St7GetPlateNonlinearType`

Returns the nonlinear material type assigned to the specified plate property.

**Syntax**

```c
long St7GetPlateNonlinearType(long uID, long PropNum, long*
NonlinType, long* YieldType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.

**Output Parameters**

- `NonlinType` — Nonlinear material type, either ntNonlinElastic or ntElastoPlastic.
- `YieldType` — Yield criterion, one of ycTresca, ycVonMises, ycMaxStress, ycMohrCoulomb or ycDruckerPrager.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_IncompatibleCriterionCombination,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_UnknownProperty
```


---

### `St7SetPlateThickness`

Sets the thickness for the specified plate property.

**Syntax**

```c
long St7SetPlateThickness(long uID, long PropNum, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number. Properties – Beams, Plates and Bricks
- `Doubles[0..1]` — A 2 element array containing the membrane and bending thickness values respectively.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_PlateDoesNotHaveThickness, ERR7_ResultFileIsOpen,
ERR7_UnknownProperty
```


---

### `St7GetPlateThickness`

Returns the thickness assigned to the specified plate property.

**Syntax**

```c
long St7GetPlateThickness(long uID, long PropNum, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.

**Output Parameters**

- `Doubles[0..1]` — A 2 element array containing the membrane and bending thickness values respectively.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_PlateDoesNotHaveThickness, ERR7_UnknownProperty
```


---

### `St7SetPlateIsotropicMaterial`

Sets the isotropic material parameters for the specified plate property.

**Syntax**

```c
long St7SetPlateIsotropicMaterial(long uID, long PropNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.
- `Doubles[0..7]` — [ipPlateIsoModulus] - Modulus. [ipPlateIsoPoisson] - Poisson’s ratio. [ipPlateIsoDensity] - Density. [ipPlateIsoAlpha] - Thermal expansion coefficient. [ipPlateIsoViscosity] - Viscous damping coefficient. [ipPlateIsoDampingRatio] - Damping ratio. [ipPlateIsoConductivity] - Conductivity coefficient. [ipPlateIsoSpecificHeat] - Specific heat coefficient.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotIsotropic, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty


Properties – Beams, Plates and Bricks
```


---

### `St7GetPlateIsotropicMaterial`

Returns the isotropic material properties for the specified plate property.

**Syntax**

```c
long St7GetPlateIsotropicMaterial(long uID, long PropNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.

**Output Parameters**

- `Doubles[0..7]` — [ipPlateIsoModulus] - Modulus. [ipPlateIsoPoisson] - Poisson’s ratio. [ipPlateIsoDensity] - Density. [ipPlateIsoAlpha] - Thermal expansion coefficient. [ipPlateIsoViscosity] - Viscous damping coefficient. [ipPlateIsoDampingRatio] - Damping ratio. [ipPlateIsoConductivity] - Conductivity coefficient. [ipPlateIsoSpecificHeat] - Specific heat coefficient.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotIsotropic, ERR7_NoError,
ERR7_UnknownProperty
```


---

### `St7SetPlateOrthotropicMaterial`

Sets the orthotropic material properties for the specified plate property.

**Syntax**

```c
long St7SetPlateOrthotropicMaterial(long uID, long PropNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.
- `Doubles[0..17]` — [ipPlateOrthoModulus1] - Modulus in the 1 axis direction. [ipPlateOrthoModulus2] - Modulus in the 2 axis direction. [ipPlateOrthoModulus3] - Modulus in the 3 axis direction. [ipPlateOrthoShear12] - Shear modulus in the 12 axis direction. [ipPlateOrthoShear23] - Shear modulus in the 23 axis direction. [ipPlateOrthoShear31] - Shear modulus in the 31 axis direction. [ipPlateOrthoPoisson12] - Poisson’s ratio in the 12 axis direction. [ipPlateOrthoPoisson23] - Poisson’s ratio in the 23 axis direction. [ipPlateOrthoPoisson31] - Poisson’s ratio in 31 axis direction. [ipPlateOrthoDensity] - Density. [ipPlateOrthoAlpha1] - Thermal expansion coefficient in the 12 axis direction. [ipPlateOrthoAlpha2] - Thermal expansion coefficient in the 23 axis direction. Properties – Beams, Plates and Bricks [ipPlateOrthoAlpha3] - Thermal expansion coefficient in the 31 axis direction. [ipPlateOrthoViscosity] - Viscous damping coefficient. [ipPlateOrthoDampingRatio] - Damping ratio. [ipPlateOrthoConductivity1] - Thermal conductivity in the 1 axis direction. [ipPlateOrthoConductivity2] - Thermal conductivity in the 2 axis direction. [ipPlateOrthoSpecificHeat] - Specific heat coefficient.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotOrthotropic, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7GetPlateOrthotropicMaterial`

Returns the orthotropic material properties assigned to the specified plate
property.

**Syntax**

```c
long St7GetPlateOrthotropicMaterial(long uID, long PropNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.

**Output Parameters**

- `Doubles[0..17]` — [ipPlateOrthoModulus1] - Modulus in the 1 axis direction. [ipPlateOrthoModulus2] - Modulus in the 2 axis direction. [ipPlateOrthoModulus3] - Modulus in the 3 axis direction. [ipPlateOrthoShear12] - Shear modulus in the 12 axis direction. [ipPlateOrthoShear23] - Shear modulus in the 23 axis direction. [ipPlateOrthoShear31] - Shear modulus in the 31 axis direction. [ipPlateOrthoPoisson12] - Poisson’s ratio in the 12 axis direction. [ipPlateOrthoPoisson23] - Poisson’s ratio in the 23 axis direction. [ipPlateOrthoPoisson31] - Poisson’s ratio in 31 axis direction. [ipPlateOrthoDensity] - Density. [ipPlateOrthoAlpha1] - Thermal expansion coefficient in the 12 axis direction. [ipPlateOrthoAlpha2] - Thermal expansion coefficient in the 23 axis direction. [ipPlateOrthoAlpha3] - Thermal expansion coefficient in the 31 axis direction. [ipPlateOrthoViscosity] - Viscous damping coefficient. [ipPlateOrthoDampingRatio] - Damping ratio. [ipPlateOrthoConductivity1] - Thermal conductivity in the 1 axis direction. [ipPlateOrthoConductivity2] - Thermal conductivity in the 2 axis direction. [ipPlateOrthoSpecificHeat] - Specific heat coefficient.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotOrthotropic, ERR7_NoError,
ERR7_UnknownProperty


Properties – Beams, Plates and Bricks
```


---

### `St7SetPlateRubberMaterial`

Sets the rubber material properties for the specified plate property.

**Syntax**

```c
long St7SetPlateRubberMaterial(long uID, long PropNum, long
RubberType, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.
- `RubberType` — Type of rubber material model, one of kNeoHookean, kMooneyRivlin, kGeneralisedMooneyRivlin, kOgden.
- `Doubles[0..15]` — An array describing the rubber material coefficients. The format depends on the material sub-type, with different sub-types requiring a varying number of rubber coefficients following the common data: [ipRubberBulk] - Bulk modulus. [ipRubberDensity] - Density. [ipRubberAlpha] - Thermal expansion coefficient. [ipRubberViscosity] - Viscous damping coefficient. [ipRubberDampingRatio] - Damping ratio. [ipRubberConductivity] - Conductivity. [ipRubberSpecificHeat] - Specific heat. [ipRubberConstC1..ipRubberConstC1+Num] - Rubber coefficients, where: Num = 0 (Neo-Hookean) Num = 1 (Mooney-Rivlin) Num = 8 (Generalised Mooney-Rivlin) Num = 5 (Ogden)

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidRubberModel, ERR7_MaterialNotRubber,
ERR7_NoError, ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7GetPlateRubberMaterial`

Returns the rubber material properties assigned to the specified plate property.

**Syntax**

```c
long St7GetPlateRubberMaterial(long uID, long PropNum,
long* RubberType, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.

**Output Parameters**

- `RubberType` — Type of rubber material model, one of kNeoHookean, kMooneyRivlin, kGeneralisedMooneyRivlin, kOgden.
- `Doubles[0..15]` — An array describing the rubber material coefficients. The format depends on the material sub-type, with different sub-types requiring a varying number of rubber coefficients following the common data: [ipRubberBulk] - Bulk modulus. [ipRubberDensity] - Density. [ipRubberAlpha] - Thermal expansion coefficient. Properties – Beams, Plates and Bricks [ipRubberViscosity] - Viscous damping coefficient. [ipRubberDampingRatio] - Damping ratio. [ipRubberConductivity] - Conductivity. [ipRubberSpecificHeat] - Specific heat. [ipRubberConstC1..ipRubberConstC1+Num] - Rubber coefficients, where: Num = 0 (Neo-Hookean) Num = 1 (Mooney-Rivlin) Num = 8 (Generalised Mooney-Rivlin) Num = 5 (Ogden)

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotRubber, ERR7_NoError, ERR7_UnknownProperty
```


---

### `St7SetPlateAnisotropicMaterial`

Sets the anisotropic material properties for the specified plate property.

**Syntax**

```c
long St7SetPlateAnisotropicMaterial(long uID, long PropNum,
long MatType, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.
- `MatType` — Matrix type, either mtStiffness or mtCompliance.
- `Doubles[0..22]` — [0..5] - In-plane components of the anisotropic material stress-strain matrix D defined by the coefficients D11, D12, D13, D22, D23 and D33, respectively. [6..9] - Out-of-plane components of the anisotropic material stress-strain matrix D defined by the coefficients D14, D24, D34, and D44, respectively (plane stress and plane strain elements only). [ipPlateAnisoTransShear1] - Transverse shear modulus in the 13 plane (plate/shell elements only). [ipPlateAnisoTransShear2] - Transverse shear modulus in the 23 plane (plate/shell elements only). [ipPlateAnisoTransShear3] - Transverse shear coupling modulus (plate/shell elements only). [ipPlateAnisoDensity] - Density. [ipPlateAnisoAlpha1] - Thermal expansion coefficient in the 1 axis direction. [ipPlateAnisoAlpha2] - Thermal expansion coefficient in the 2 axis direction. [ipPlateAnisoAlpha3] - Thermal expansion coefficient in the 3 axis direction. [ipPlateAnisoAlpha12] - Thermal expansion coefficient in the 12 axis direction. [ipPlateAnisoViscosity] - Viscous damping coefficient. [ipPlateAnisoDampingRatio] - Damping ratio. [ipPlateAnisoConductivity1] - Conductivity coefficient in the 1 axis direction. [ipPlateAnisoConductivity2] - Conductivity coefficient in the 2 axis direction. [ipPlateAnisoSpecificHeat] - Specific heat coefficient.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,


Properties – Beams, Plates and Bricks

ERR7_InvalidMatrixType, ERR7_MaterialNotAnisotropic,
ERR7_NoError, ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7GetPlateAnisotropicMaterial`

Returns the anisotropic material properties assigned to the specified plate
property.

**Syntax**

```c
long St7GetPlateAnisotropicMaterial(long uID, long PropNum,
long* MatType, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.

**Output Parameters**

- `MatType` — Matrix type, either mtStiffness or mtCompliance.
- `Doubles[0..2]` — [0..5] - In-plane components of the anisotropic material stress-strain matrix D defined by the coefficients D11, D12, D13, D22, D23 and D33, respectively. [6..9] - Out-of-plane components of the anisotropic material stress-strain matrix D defined by the coefficients D14, D24, D34, and D44, respectively (plane stress and plane strain elements only). [ipPlateAnisoTransShear1] - Transverse shear modulus in the 13 plane. [ipPlateAnisoTransShear2] - Transverse shear modulus in the 23 plane. [ipPlateAnisoTransShear3] - Transverse shear coupling modulus. [ipPlateAnisoDensity] - Density. [ipPlateAnisoAlpha1] - Thermal expansion coefficient in the 1 axis direction. [ipPlateAnisoAlpha2] - Thermal expansion coefficient in the 2 axis direction. [ipPlateAnisoAlpha3] - Thermal expansion coefficient in the 3 axis direction. [ipPlateAnisoAlpha12] - Thermal expansion coefficient in the 12 axis direction. [ipPlateAnisoViscosity] - Viscous damping coefficient. [ipPlateAnisoDampingRatio] - Damping ratio. [ipPlateAnisoConductivity1] - Conductivity coefficient in the 1 axis direction. [ipPlateAnisoConductivity2] - Conductivity coefficient in the 2 axis direction. [ipPlateAnisoSpecificHeat] - Specific heat coefficient.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotAnisotropic, ERR7_NoError,
ERR7_UnknownProperty
```


---

### `St7SetPlateUserDefinedMaterial`

Sets the user defined material properties for the specified plate property.

**Syntax**

```c
long St7SetPlateUserDefinedMaterial(long uID, long PropNum,
long MatType, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number. Properties – Beams, Plates and Bricks
- `MatType` — Matrix type, either mtStiffness or mtCompliance.
- `Doubles[0..35]` — [0..5] - Material membrane matrix C defined by the coefficients C11, C12, C13, C22, C23 and C33, respectively. [6..11] - Material bending matrix D defined by the coefficients D11, D12, D13, D22, D23 and D33, respectively. [12..20] - Material membrane-bending coupling matrix D defined by the coefficients D11, D12, D13, D22, D23, D33, D21, D31 and D32 respectively. [ipPlateUserTransShearxz] - Transverse shear modulus G13. [ipPlateUserTransShearyz] - Transverse shear modulus G23. [ipPlateUserTransShearcz] - Transverse shear coupling modulus Gc3. [ipPlateUserDensity] - Density. [ipPlateUserAlphax] - Thermal expansion coefficient in the 1 axis direction. [ipPlateUserAlphay] - Thermal expansion coefficient in the 2 axis direction. [ipPlateUserAlphaxy] - Thermal expansion coefficient in the 12 axis direction. [ipPlateUserBetax] - Thermal curvature expansion coefficient along the 1 axis direction. [ipPlateUserBetay] - Thermal curvature expansion coefficient along the 2 axis direction. [ipPlateUserBetaxy] - Thermal twist expansion coefficient. [ipPlateUserViscosity] - Viscous damping coefficient. [ipPlateUserDampingRatio] - Damping ratio. [ipPlateUserConductivity1] - Conductivity coefficient in the 1 axis direction. [ipPlateUserConductivity2] - Conductivity coefficient in the 2 axis direction. [ipPlateUserSpecificHeat] - Specific heat coefficient.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidMatrixType, ERR7_MaterialNotUserDefined,
ERR7_NoError, ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7GetPlateUserDefinedMaterial`

Returns the user defined material properties assigned to the specified plate
property.

**Syntax**

```c
long St7GetPlateUserDefinedMaterial(long uID, long PropNum,
long* MatType, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.

**Output Parameters**

- `MatType` — Matrix type, either mtStiffness or mtCompliance.
- `Doubles[0..35]` — [0..5] - Material membrane matrix C defined by the coefficients C11, C12, C13, C22, C23 and C33, respectively. [6..11] - Material bending matrix D defined by the coefficients D11, D12, D13, D22, D23 and D33, respectively. [12..20] - Material membrane-bending coupling matrix D defined by the coefficients D11, D12, D13, D22, D23, D33, D21, D31 and D32 respectively. Properties – Beams, Plates and Bricks [ipPlateUserTransShearxz] - Transverse shear modulus G13. [ipPlateUserTransShearyz] - Transverse shear modulus G23. [ipPlateUserTransShearcz] - Transverse shear modulus Gc3. [ipPlateUserDensity] - Density. [ipPlateUserAlphax] - Thermal expansion coefficient in the 1 axis direction. [ipPlateUserAlphay] - Thermal expansion coefficient in the 2 axis direction. [ipPlateUserAlphaxy] - Thermal expansion coefficient in the 12 axis direction. [ipPlateUserBetax] - Thermal curvature expansion coefficient along the 1 axis direction. [ipPlateUserBetay] - Thermal curvature expansion coefficient along the 2 axis direction. [ipPlateUserBetaxy] - Thermal twist expansion coefficient. [ipPlateUserViscosity] - Viscous damping coefficient. [ipPlateUserDampingRatio] - Damping ratio. [ipPlateUserConductivity1] - Conductivity coefficient in the 1 axis direction. [ipPlateUserConductivity2] - Conductivity coefficient in the 2 axis direction. [ipPlateUserSpecificHeat] - Specific heat coefficient.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotUserDefined, ERR7_NoError,
ERR7_UnknownProperty
```


---

### `St7SetPlateMCDPMaterial`

Sets the material properties for the specified Mohr-Coulomb or Drucker-Prager
plate property.

**Syntax**

```c
long St7SetPlateMCDPMaterial(long uID, long PropNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.
- `Doubles[0..1]` — [ipFrictionAngle] - Friction angle. [ipCohesion] - Cohesion value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidPlateType, ERR7_MaterialNotIsotropic,
ERR7_NoError, ERR7_ResultFileIsOpen, ERR7_UnknownProperty,
ERR7_YieldNotMCDP
```


---

### `St7GetPlateMCDPMaterial`

Returns the material properties assigned to the specified Mohr-Coulomb or
Drucker-Prager plate property.

**Syntax**

```c
long St7GetPlateMCDPMaterial(long uID, long PropNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Properties – Beams, Plates and Bricks Strand7 model file ID number.
- `PropNum` — Plate property number.

**Output Parameters**

- `Doubles[0..1]` — [ipFrictionAngle] - Friction angle. [ipCohesion] - Cohesion value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidPlateType, ERR7_MaterialNotIsotropic,
ERR7_NoError, ERR7_UnknownProperty, ERR7_YieldNotMCDP
```


---

### `St7SetPlateSoilDCMaterial`

Sets the soil material properties for the specified Duncan-Chang plate property.

**Syntax**

```c
long St7SetPlateSoilDCMaterial(long uID, long PropNum,
long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.
- `Integers[0..1]` — [ipSoilDCUsePoisson] - Use Poisson’s ratio, either btTrue or btFalse. [ipSoilDCSetLevel] - Set fluid level, either btTrue or btFalse.
- `Doubles[0..16]` — [ipSoilDCModulusK] - Modulus. [ipSoilDCModulusKUR] - Unloading/reloading modulus. [ipSoilDCModulusN] - Modulus exponent. [ipSoilDCPoisson] - Poisson’s ratio. [ipSoilDCBulkK] - Bulk modulus. [ipSoilDCBulkM] - Bulk modulus exponent. [ipSoilDCFrictionAngle] - Friction angle. [ipSoilDCDeltaAngle] - Friction angle change. [ipSoilDCCohesion] - Cohesion value. [ipSoilDCFailureRatio] - Failure ratio. [ipSoilDCFailureMod] - Failure modulus. [ipSoilDCReferenceP] - Reference pressure. [ipSoilDCDensity] - Density. [ipSoilDCHorizontalRatio] - Horizontal stress ratio. [ipSoilDCConductivity] - Conductivity. [ipSoilDCSpecificHeat] - Specific heat. [ipSoilDCFluidLevel] - Fluid level.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotSoil, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_SoilTypeNotDC, ERR7_UnknownProperty
```


---

### `St7GetPlateSoilDCMaterial`

Returns the soil material properties assigned to the specified Duncan-Chang
plate property.


Properties – Beams, Plates and Bricks

**Syntax**

```c
long St7GetPlateSoilDCMaterial(long uID, long PropNum,
long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.

**Output Parameters**

- `Integers[0..1]` — [ipSoilDCUsePoisson] - Use Poisson’s ratio, either btTrue or btFalse. [ipSoilDCSetLevel] - Set fluid level, either btTrue or btFalse.
- `Doubles[0..16]` — [ipSoilDCModulusK] - Modulus. [ipSoilDCModulusKUR] - Unloading/reloading modulus. [ipSoilDCModulusN] - Modulus exponent. [ipSoilDCPoisson] - Poisson’s ratio. [ipSoilDCBulkK] - Bulk modulus. [ipSoilDCBulkM] - Bulk modulus exponent. [ipSoilDCFrictionAngle] - Friction angle. [ipSoilDCDeltaAngle] - Friction angle change. [ipSoilDCCohesion] - Cohesion value. [ipSoilDCFailureRatio] - Failure ratio. [ipSoilDCFailureMod] - Failure modulus. [ipSoilDCReferenceP] - Reference pressure. [ipSoilDCDensity] - Density. [ipSoilDCHorizontalRatio] - Horizontal stress ratio. [ipSoilDCConductivity] - Conductivity. [ipSoilDCSpecificHeat] - Specific heat. [ipSoilDCFluidLevel] - Fluid level.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotSoil, ERR7_NoError, ERR7_SoilTypeNotDC,
ERR7_UnknownProperty
```


---

### `St7SetPlateSoilCCMaterial`

Sets the soil material properties for the specified Cam-Clay plate property.

**Syntax**

```c
long St7SetPlateSoilCCMaterial(long uID, long PropNum,
long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.
- `Integers[0..3]` — [ipSoilCCUsePoisson] - Use Poisson’s ratio, either btTrue or btFalse. [ipSoilCCDrainedState] - Drained state, either btTrue or btFalse. [ipSoilCCUseOCR] - Overconsolidation, either btTrue or btFalse. [ipSoilCCSetLevel] - Set fluid level, either btTrue or btFalse.
- `Doubles[0..14]` — [ipSoilCCCriticalStateLine] - Critical state line slope. [ipSoilCCConsolidationLine] - Normal consolidation line slope. Properties – Beams, Plates and Bricks [ipSoilCCSwellingLine] - Swelling line slope. [ipSoilCCDensity] - Density. [ipSoilCCPoisson] - Poisson’s ratio. [ipSoilCCModulusG] - Shear modulus at point A. [ipSoilCCModulusB] - Shear modulus at point B. [ipSoilCCHorizontalRatio] - Horizontal stress ratio. [ipSoilCCER] - Reference void ratio. [ipSoilCCPR] - Unit pressure ratio. [ipSoilCCPC0] - Initial consolidation pressure. [ipSoilCCOCR] - Overconsolidation ratio. [ipSoilCCConductivity] - Conductivity. [ipSoilCCSpecificHeat] - Specific heat. [ipSoilCCFluidLevel] - Fluid level.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotSoil, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_SoilTypeNotCC, ERR7_UnknownProperty
```


---

### `St7GetPlateSoilCCMaterial`

Returns the soil material properties assigned to the specified Cam-Clay plate
property.

**Syntax**

```c
long St7GetPlateSoilCCMaterial(long uID, long PropNum,
long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.

**Output Parameters**

- `Integers[0..3]` — [ipSoilCCUsePoisson] - Use Poisson’s ratio, either btTrue or btFalse. [ipSoilCCDrainedState] - Drained state, either btTrue or btFalse. [ipSoilCCUseOCR] - Over-consolidation, either btTrue or btFalse. [ipSoilCCSetLevel] - Set fluid level, either btTrue or btFalse.
- `Doubles[0..14]` — [ipSoilCCCriticalStateLine] - Critical state line slope. [ipSoilCCConsolidationLine] - Normal consolidation line slope. [ipSoilCCSwellingLine] - Swelling line slope. [ipSoilCCDensity] - Density. [ipSoilCCPoisson] - Poisson’s ratio. [ipSoilCCModulusG] - Shear modulus at point A. [ipSoilCCModulusB] - Shear modulus at point B. [ipSoilCCHorizontalRatio] - Horizontal stress ratio. [ipSoilCCER] - Reference void ratio. [ipSoilCCPR] - Unit pressure ratio. [ipSoilCCPC0] - Initial consolidation pressure. [ipSoilCCOCR] - Over-consolidation ratio. [ipSoilCCConductivity] - Conductivity. [ipSoilCCSpecificHeat] - Specific heat. [ipSoilCCFluidLevel] - Fluid level. Properties – Beams, Plates and Bricks

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotSoil, ERR7_NoError, ERR7_SoilTypeNotCC,
ERR7_UnknownProperty
```


---

### `St7SetPlateSoilMCMaterial`

Assigns the Mohr-Coulomb soil parameters for the specified plate property.

**Syntax**

```c
long St7SetPlateSoilMCMaterial(long uID, long PropNum,
long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Property number.
- `Integers[0..0]` — [ipSoilMCSetLevel] - Set a fluid level, either btTrue or btFalse.
- `Doubles[0..9]` — [ipSoilMCModulus] - Modulus. [ipSoilMCPoisson] - Poisson’s ratio. [ipSoilMCDensity] - Density. [ipSoilMCCohesion] - Cohesion value. [ipSoilMCFrictionAngle] - Friction angle. [ipSoilMCHorizontalRatio] - Horizontal stress ratio. [ipSoilMCER] - Void ratio. [ipSoilMCConductivity] - Conductivity. [ipSoilMCSpecificHeat] - Specific heat. [ipSoilMCFluidLevel] - Fluid level.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotSoil, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_SoilTypeNotMC, ERR7_UnknownProperty
```


---

### `St7GetPlateSoilMCMaterial`

Returns the Mohr-Coulomb soil parameters assigned to the specified plate
property.

**Syntax**

```c
long St7GetPlateSoilMCMaterial(long uID, long PropNum,
long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Property number.

**Output Parameters**

- `Integers[0..0]` — [ipSoilMCSetLevel] - Set a fluid level, either btTrue or btFalse.
- `Doubles[0..9]` — [ipSoilMCModulus] - Modulus. [ipSoilMCPoisson] - Poisson’s ratio. [ipSoilMCDensity] - Density. [ipSoilMCCohesion] - Cohesion value. [ipSoilMCFrictionAngle] - Friction angle. Properties – Beams, Plates and Bricks [ipSoilMCHorizontalRatio] - Horizontal stress ratio. [ipSoilMCER] - Void ratio. [ipSoilMCConductivity] - Conductivity. [ipSoilMCSpecificHeat] - Specific heat. [ipSoilMCFluidLevel] - Fluid level.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotSoil, ERR7_NoError, ERR7_SoilTypeNotMC,
ERR7_UnknownProperty
```


---

### `St7SetPlateSoilDPMaterial`

Assigns the Drucker-Prager soil parameters to the specified plate property.

**Syntax**

```c
long St7SetPlateSoilDPMaterial(long uID, long PropNum,
long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Property number.
- `Integers[0..0]` — [ipSoilDPSetLevel] - Set a fluid level, either btTrue or btFalse.
- `Doubles[0..9]` — [ipSoilDPModulus] - Modulus. [ipSoilDPPoisson] - Poisson’s ratio. [ipSoilDPDensity] - Density. [ipSoilDPCohesion] - Cohesion value. [ipSoilDPFrictionAngle] - Friction angle. [ipSoilDPHorizontalRatio] - Horizontal stress ratio. [ipSoilDPER] - Void ratio. [ipSoilDPConductivity] - Conductivity. [ipSoilDPSpecificHeat] - Specific heat. [ipSoilDPFluidLevel] - Fluid level.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotSoil, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_SoilTypeNotDP, ERR7_UnknownProperty
```


---

### `St7GetPlateSoilDPMaterial`

Returns the Drucker-Prager soil parameters assigned to the specified plate
property.

**Syntax**

```c
long St7GetPlateSoilDPMaterial(long uID, long PropNum,
long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Property number.

**Output Parameters**

- `Integers[0..0]` — [ipSoilDPSetLevel] - Set a fluid level, either btTrue or btFalse.
- `Doubles[0..9]` — Properties – Beams, Plates and Bricks [ipSoilDPModulus] - Modulus. [ipSoilDPPoisson] - Poisson’s ratio. [ipSoilDPDensity] - Density. [ipSoilDPCohesion] - Cohesion value. [ipSoilDPFrictionAngle] - Friction angle. [ipSoilDPHorizontalRatio] - Horizontal stress ratio. [ipSoilDPER] - Void ratio. [ipSoilDPConductivity] - Conductivity. [ipSoilDPSpecificHeat] - Specific heat. [ipSoilDPFluidLevel] - Fluid level.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotSoil, ERR7_NoError, ERR7_SoilTypeNotDP,
ERR7_UnknownProperty
```


---

### `St7SetPlateSoilLSMaterial`

Sets the linear elastic soil parameters for the specified plate property.

**Syntax**

```c
long St7SetPlateSoilLSMaterial(long uID, long PropNum,
long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Property number.
- `Integers[0..0]` — [ipSoilLSSetLevel] - Set a fluid level, either btTrue or btFalse.
- `Doubles[0..7]` — [ipSoilLSModulus] - Modulus. [ipSoilLSPoisson] - Poisson’s ratio. [ipSoilLSDensity] - Density. [ipSoilLSHorizontalRatio] - Horizontal stress ratio. [ipSoilLSER] - Void ratio. [ipSoilLSConductivity] - Conductivity. [ipSoilLSSpecificHeat] - Specific heat. [ipSoilLSFluidLevel] - Fluid level.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotSoil, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_SoilTypeNotLS, ERR7_UnknownProperty
```


---

### `St7GetPlateSoilLSMaterial`

Returns the linear elastic soil parameters for the specified plate property.

**Syntax**

```c
long St7GetPlateSoilLSMaterial(long uID, long PropNum,
long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Property number.

**Output Parameters**

- `Integers[0..0]` — Properties – Beams, Plates and Bricks [ipSoilLSSetLevel] - Set a fluid level, either btTrue or btFalse.
- `Doubles[0..7]` — [ipSoilLSModulus] - Modulus. [ipSoilLSPoisson] - Poisson’s ratio. [ipSoilLSDensity] - Density. [ipSoilLSHorizontalRatio] - Horizontal stress ratio. [ipSoilLSER] - Void ratio. [ipSoilLSConductivity] - Conductivity. [ipSoilLSSpecificHeat] - Specific heat. [ipSoilLSFluidLevel] - Fluid level.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotSoil, ERR7_NoError, ERR7_SoilTypeNotLS,
ERR7_UnknownProperty
```


---

### `St7SetPlateFluidMaterial`

Sets the material properties for the specified fluid plate property.

**Syntax**

```c
long St7SetPlateFluidMaterial(long uID, long PropNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.
- `Doubles[0..7]` — [ipFluidModulus] - Modulus. [ipFluidPenaltyParam] - Penalty parameter. [ipFluidDensity] - Density. [ipFluidAlpha] - Thermal expansion coefficient. [ipFluidViscosity] - Viscous damping coefficient. [ipFluidDampingRatio] - Damping ratio. [ipFluidConductivity] - Conductivity. [ipFluidSpecificHeat] - Specific heat.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7GetPlateFluidMaterial`

Returns the material properties assigned to the specified fluid plate property.

**Syntax**

```c
long St7GetPlateFluidMaterial(long uID, long PropNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.

**Output Parameters**

- `Doubles[0..7]` — [ipFluidModulus] - Modulus. [ipFluidPenaltyParam] - Penalty parameter. Properties – Beams, Plates and Bricks [ipFluidDensity] - Density. [ipFluidAlpha] - Thermal expansion coefficient. [ipFluidViscosity] - Viscous damping coefficient. [ipFluidDampingRatio] - Damping ratio. [ipFluidConductivity] - Conductivity. [ipFluidSpecificHeat] - Specific heat.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_UnknownProperty
```


---

### `St7SetPlateUseReducedInt`

Sets the state of the Reduced Integration flag for the specified plate property. This
option is only used for the 2D and Axisymmetric plate property types.

**Syntax**

```c
long St7SetPlateUseReducedInt(long uID, long PropNum, bool
UseReducedInt)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.
- `UseReducedInt` — btTrue to use a reduced order integration scheme.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7GetPlateUseReducedInt`

Returns the state of the Reduced Integration flag for the specified plate property.
This option is only used for the 2D and Axisymmetric plate property types.

**Syntax**

```c
long St7GetPlateUseReducedInt(long uID, long PropNum, bool*
UseReducedInt)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.

**Output Parameters**

- `UseReducedInt` — btTrue to use a reduced order integration scheme.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_UnknownProperty
```


---

### `St7SetPlateLayers`

Sets the number of layers used for MNL integrations through the plate thickness.
The default is ten, and a maximum of 100 layers may be set.

**Syntax**

```c
long St7SetPlateLayers(long uID, long PropNum, long
NumLayers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number. Properties – Beams, Plates and Bricks
- `PropNum` — Plate property number.
- `NumLayers` — Number of integration layers.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty,
ERR7_InvalidNumLayers, ERR7_PlateDoesNotHaveLayers
```


---

### `St7GetPlateLayers`

Returns the number of layers used for MNL integrations through the plate
thickness.

**Syntax**

```c
long St7GetPlateLayers(long uID, long PropNum, long*
NumLayers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.

**Output Parameters**

- `NumLayers` — Number of integration layers.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_UnknownProperty, ERR7_PlateDoesNotHaveLayers
```


---

### `St7NewBrickProperty`

Creates a new brick property.

**Syntax**

```c
long St7NewBrickProperty(long uID, long PropNum, long
MaterialType, char* PropName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Brick property number.
- `MaterialType` — Type of brick material, one of kMaterialTypeNull, kMaterialTypeIsotropic, kMaterialTypeOrthotropic, kMaterialTypeAnisotropic, kMaterialTypeRubber, kMaterialTypeSoil, kMaterialTypeUserDefined, kMaterialTypePly, kMaterialTypeFluid.
- `PropName` — Name of the property.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidMaterialType, ERR7_InvalidPropertyNumber,
ERR7_NoError, ERR7_PropertyAlreadyExists,
ERR7_ResultFileIsOpen
```


---

### `St7GetBrickPropertyData`

Returns the material data assigned to the specified brick property.

**Syntax**

```c
long St7GetBrickPropertyData(long uID, long PropNum, long*
Integers, double* BrickMaterial)


Properties – Beams, Plates and Bricks
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Brick property number.

**Output Parameters**

- `Integers` — This is a dummy variable to allow for future expansion of this function. Any integer variable may be passed and will be returned unchanged.
- `BrickMaterial[0..kNumMaterialData-1]` — [ipModulus] - Modulus. [ipPoisson] - Poisson’s ratio. [ipDensity] - Density.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotIsotropic, ERR7_NoError,
ERR7_UnknownProperty
```


---

### `St7SetBrickPropertyType`

Sets the material type for the specified brick property.

**Syntax**

```c
long St7SetBrickPropertyType(long uID, long PropNum, long
MaterialType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Brick property number.
- `MaterialType` — Type of brick material, one of kMaterialTypeNull, kMaterialTypeIsotropic, kMaterialTypeOrthotropic, kMaterialTypeAnisotropic, kMaterialTypeRubber, kMaterialTypeSoil, kMaterialTypeUserDefined, kMaterialTypePly, kMaterialTypeFluid.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidMaterialType, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7GetBrickPropertyType`

Returns the material type for the specified brick property.

**Syntax**

```c
long St7GetBrickPropertyType(long uID, long PropNum, long*
MaterialType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Brick property number.

**Output Parameters**

- `MaterialType` — Type of brick material, one of kMaterialTypeNull, kMaterialTypeIsotropic, kMaterialTypeOrthotropic, kMaterialTypeAnisotropic, kMaterialTypeRubber, kMaterialTypeSoil, kMaterialTypeUserDefined, kMaterialTypePly, kMaterialTypeFluid.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_UnknownProperty


Properties – Beams, Plates and Bricks
```


---

### `St7SetBrickNonlinearType`

Sets the nonlinear material type for the specified brick property.

**Syntax**

```c
long St7SetBrickNonlinearType(long uID, long PropNum, long
NonlinType, long YieldType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Brick property number.
- `NonlinType` — Nonlinear material type, either ntNonlinElastic or ntElastoPlastic.
- `YieldType` — Yield surface type, one of ycTresca, ycVonMises, ycMaxStress, ycMohrCoulomb or ycDruckerPrager.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_IncompatibleCriterionCombination,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_UnknownProperty
```


---

### `St7GetBrickNonlinearType`

Returns the nonlinear material type assigned to the specified brick property.

**Syntax**

```c
long St7GetBrickNonlinearType(long uID, long PropNum, long*
NonlinType, long* YieldType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Brick property number.

**Output Parameters**

- `NonlinType` — Nonlinear material type, either ntNonlinElastic or ntElastoPlastic.
- `YieldType` — Yield surface type, one of ycTresca, ycVonMises, ycMaxStress, ycMohrCoulomb or ycDruckerPrager.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_IncompatibleCriterionCombination,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_UnknownProperty
```


---

### `St7SetBrickIsotropicMaterial`

Set the isotropic material properties for the specified brick property.

**Syntax**

```c
long St7SetBrickIsotropicMaterial(long uID, long PropNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Brick property number.
- `Doubles[0..7]` — [ipBrickIsoModulus] - Modulus. [ipBrickIsoPoisson] - Poisson’s ratio. [ipBrickIsoDensity] - Density. Properties – Beams, Plates and Bricks [ipBrickIsoAlpha] - Thermal expansion coefficient. [ipBrickIsoViscosity] - Viscous damping coefficient. [ipBrickIsoDampingRatio] - Damping ratio. [ipBrickIsoConductivity] - Conductivity coefficient. [ipBrickIsoSpecificHeat] - Specific heat coefficient.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotIsotropic, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7GetBrickIsotropicMaterial`

Returns the isotropic material properties assigned to the specified brick property.

**Syntax**

```c
long St7GetBrickIsotropicMaterial(long uID, long PropNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Brick property number.

**Output Parameters**

- `Doubles[0..7]` — [ipBrickIsoModulus] - Modulus. [ipBrickIsoPoisson] - Poisson’s ratio. [ipBrickIsoDensity] - Density. [ipBrickIsoAlpha] - Thermal expansion coefficient. [ipBrickIsoViscosity] - Viscous damping coefficient. [ipBrickIsoDampingRatio] - Damping ratio. [ipBrickIsoConductivity] - Conductivity coefficient. [ipBrickIsoSpecificHeat] - Specific heat coefficient.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotIsotropic, ERR7_NoError,
ERR7_UnknownProperty
```


---

### `St7SetBrickOrthotropicMaterial`

Sets the orthotropic material properties for the specified brick property.

**Syntax**

```c
long St7SetBrickOrthotropicMaterial(long uID, long PropNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Brick property number.
- `Doubles[0..18]` — [ipBrickOrthoModulus1] - Modulus in the 1 axis direction. [ipBrickOrthoModulus2] - Modulus in the 2 axis direction. [ipBrickOrthoModulus3] - Modulus in the 3 axis direction. [ipBrickOrthoShear12] - Shear modulus in the 12 axis direction. [ipBrickOrthoShear23] - Shear modulus in the 23 axis direction. [ipBrickOrthoShear31] - Shear modulus in the 31 axis direction. [ipBrickOrthoPoisson12] - Poisson’s ratio in the 12 axis direction. Properties – Beams, Plates and Bricks [ipBrickOrthoPoisson23] - Poisson’s ratio in the 23 axis direction. [ipBrickOrthoPoisson31] - Poisson’s ratio in the 31 axis direction. [ipBrickOrthoDensity] - Density. [ipBrickOrthoAlpha1] - Thermal expansion coefficient in the 1 axis direction. [ipBrickOrthoAlpha2] - Thermal expansion coefficient in the 2 axis direction. [ipBrickOrthoAlpha3] - Thermal expansion coefficient in the 3 axis direction. [ipBrickOrthoViscosity] - Viscous damping coefficient. [ipBrickOrthoDampingRatio] - Damping ratio. [ipBrickOrthoConductivity1] - Conductivity coefficient in the 1 axis direction. [ipBrickOrthoConductivity2] - Conductivity coefficient in the 2 axis direction. [ipBrickOrthoConductivity3] - Conductivity coefficient in the 3 axis direction. [ipBrickOrthoSpecificHeat] - Specific heat coefficient.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotOrthotropic, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7GetBrickOrthotropicMaterial`

Returns the orthotropic material properties assigned to the specified brick
property.

**Syntax**

```c
long St7GetBrickOrthotropicMaterial(long uID, long PropNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Brick property number.

**Output Parameters**

- `Doubles[0..18]` — [ipBrickOrthoModulus1] - Modulus in the 1 axis direction. [ipBrickOrthoModulus2] - Modulus in the 2 axis direction. [ipBrickOrthoModulus3] - Modulus in the 3 axis direction. [ipBrickOrthoShear12] - Shear modulus in the 12 axis direction. [ipBrickOrthoShear23] - Shear modulus in the 23 axis direction. [ipBrickOrthoShear31] - Shear modulus in the 31 axis direction. [ipBrickOrthoPoisson12] - Poisson’s ratio in the 12 axis direction. [ipBrickOrthoPoisson23] - Poisson’s ratio in the 23 axis direction. [ipBrickOrthoPoisson31] - Poisson’s ratio in the 31 axis direction. [ipBrickOrthoDensity] - Density. [ipBrickOrthoAlpha1] - Thermal expansion coefficient in the 1 axis direction. [ipBrickOrthoAlpha2] - Thermal expansion coefficient in the 2 axis direction. [ipBrickOrthoAlpha3] - Thermal expansion coefficient in the 3 axis direction. [ipBrickOrthoViscosity] - Viscous damping coefficient. [ipBrickOrthoDampingRatio] - Damping ratio. [ipBrickOrthoConductivity1] - Conductivity coefficient in the 1 axis direction. Properties – Beams, Plates and Bricks [ipBrickOrthoConductivity2] - Conductivity coefficient in the 2 axis direction. [ipBrickOrthoConductivity3] - Conductivity coefficient in the 3 axis direction. [ipBrickOrthoSpecificHeat] - Specific heat coefficient.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotOrthotropic, ERR7_NoError,
ERR7_UnknownProperty
```


---

### `St7SetBrickAnisotropicMaterial`

Sets the anisotropic material properties for the specified brick property.

**Syntax**

```c
long St7SetBrickAnisotropicMaterial(long uID, long PropNum,
long MatType, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Brick property number.
- `MatType` — Matrix type, either mtStiffness or mtCompliance.
- `Doubles[0..33]` — [0..20] - Complete anisotropic material stress-strain matrix D defined by the upper triangular matrix of coefficients Dij where i < j and i varies quickest; D11, D12,… D22, D23,… D66, respectively. [ipBrickUserDensity] - Density. [ipBrickUserAlpha1] - Thermal expansion coefficient in the 1 axis direction. [ipBrickUserAlpha2] - Thermal expansion coefficient in the 2 axis direction. [ipBrickUserAlpha3] - Thermal expansion coefficient in the 3 axis direction. [ipBrickUserAlpha12] - Thermal expansion coefficient in the 12 axis direction. [ipBrickUserAlpha23] - Thermal expansion coefficient in the 23 axis direction. [ipBrickUserAlpha31] - Thermal expansion coefficient in the 31 axis direction. [ipBrickUserViscosity] - Viscous damping coefficient. [ipBrickUserDampingRatio] - Damping ratio. [ipBrickUserConductivity1] - Conductivity coefficient in the 1 axis direction. [ipBrickUserConductivity2] - Conductivity coefficient in the 2 axis direction. [ipBrickUserConductivity3] - Conductivity coefficient in the 3 axis direction. [ipBrickUserSpecificHeat] - Specific heat coefficient.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidMatrixType, ERR7_MaterialNotAnisotropic,
ERR7_NoError, ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7GetBrickAnisotropicMaterial`

Returns the anisotropic material properties assigned to the specified brick
property.


Properties – Beams, Plates and Bricks

**Syntax**

```c
long St7GetBrickAnisotropicMaterial(long uID, long PropNum,
long* MatType, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Brick property number.

**Output Parameters**

- `MatType` — Matrix type, either mtStiffness or mtCompliance.
- `Doubles[0..33]` — [0..20] - Complete anisotropic material stress-strain matrix D defined by the upper triangular matrix of coefficients Dij where i < j and i varies quickest; D11, D12,… D22, D23,… D66, respectively. [ipBrickUserDensity] - Density. [ipBrickUserAlpha1] - Thermal expansion coefficient in the 1 axis direction. [ipBrickUserAlpha2] - Thermal expansion coefficient in the 2 axis direction. [ipBrickUserAlpha3] - Thermal expansion coefficient in the 3 axis direction. [ipBrickUserAlpha12] - Thermal expansion coefficient in the 12 axis direction. [ipBrickUserAlpha23] - Thermal expansion coefficient in the 23 axis direction. [ipBrickUserAlpha31] - Thermal expansion coefficient in the 31 axis direction. [ipBrickUserViscosity] - Viscous damping coefficient. [ipBrickUserDampingRatio] - Damping ratio. [ipBrickUserConductivity1] - Conductivity coefficient in the 1 axis direction. [ipBrickUserConductivity2] - Conductivity coefficient in the 2 axis direction. [ipBrickUserConductivity3] - Conductivity coefficient in the 3 axis direction. [ipBrickUserSpecificHeat] - Specific heat coefficient.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotAnisotropic, ERR7_NoError,
ERR7_UnknownProperty
```


---

### `St7SetBrickRubberMaterial`

Sets the rubber material properties for the specified brick property.

**Syntax**

```c
long St7SetBrickRubberMaterial(long uID, long PropNum, long
RubberType, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Brick property number.
- `RubberType` — Rubber material model type, one of kNeoHookean, kMooneyRivlin or kGeneralisedMooneyRivlin.
- `Doubles[0..15]` — An array describing the rubber material coefficients. The format depends on the material sub-type, with different sub-types requiring a varying number of rubber coefficients following the common data: Properties – Beams, Plates and Bricks [ipRubberBulk] - Bulk modulus. [ipRubberDensity] - Density. [ipRubberAlpha] - Thermal expansion coefficient. [ipRubberViscosity] - Viscous damping coefficient. [ipRubberDampingRatio] - Damping ratio. [ipRubberConductivity] - Conductivity. [ipRubberSpecificHeat] - Specific heat. [ipRubberConstC1..ipRubberConstC1+ Num] - Rubber coefficients, where: Num = 0 (Neo-Hookean) Num = 1 (Mooney-Rivlin) Num = 8 (Generalised Mooney-Rivlin)

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidRubberModel, ERR7_MaterialNotRubber,
ERR7_NoError, ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7GetBrickRubberMaterial`

Returns the rubber material properties assigned to the specified brick property.

**Syntax**

```c
long St7GetBrickRubberMaterial(long uID, long PropNum,
long* RubberType, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Brick property number.

**Output Parameters**

- `RubberType` — Rubber material model type, one of kNeoHookean, kMooneyRivlin, kGeneralisedMooneyRivlin.
- `Doubles[0..15]` — An array describing the rubber material coefficients. The format depends on the material sub-type, with different sub-types requiring a varying number of rubber coefficients following the common data: [ipRubberBulk] - Bulk modulus. [ipRubberDensity] - Density. [ipRubberAlpha] - Thermal expansion coefficient. [ipRubberViscosity] - Viscous damping coefficient. [ipRubberDampingRatio] - Damping ratio. [ipRubberConductivity] - Conductivity. [ipRubberSpecificHeat] - Specific heat. [ipRubberConstC1..ipRubberConstC1+ Num] - Rubber coefficients, where: Num = 0 (Neo-Hookean) Num = 1 (Mooney-Rivlin) Num = 8 (Generalised Mooney-Rivlin)

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotRubber, ERR7_NoError, ERR7_UnknownProperty
```


---

### `St7SetBrickMCDPMaterial`

Sets the Mohr-Coulomb and Drucker-Prager material properties for the specified
brick property.


Properties – Beams, Plates and Bricks

**Syntax**

```c
long St7SetBrickMCDPMaterial(long uID, long PropNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Brick property number.
- `Doubles[0..1]` — [ipFrictionAngle] - Friction angle. [ipCohesion] - Cohesion value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotIsotropic, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty,
ERR7_YieldNotMCDP
```


---

### `St7GetBrickMCDPMaterial`

Returns the Mohr-Coulomb and Drucker-Prager material properties assigned to
the specified brick property.

**Syntax**

```c
long St7GetBrickMCDPMaterial(long uID, long PropNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Brick property number.

**Output Parameters**

- `Doubles[0..1]` — [ipFrictionAngle] - Friction angle. [ipCohesion] - Cohesion value.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotIsotropic, ERR7_NoError,
ERR7_UnknownProperty, ERR7_YieldNotMCDP
```


---

### `St7SetBrickSoilDCMaterial`

Sets the Duncan-Chang soil material properties for the specified brick property.

**Syntax**

```c
long St7SetBrickSoilDCMaterial(long uID, long PropNum,
long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Brick property number.
- `Integers[0..1]` — [ipSoilDCUsePoisson] - Use Poisson’s ratio, either btTrue or btFalse. [ipSoilDCSetLevel] - Set fluid level, either btTrue or btFalse.
- `Doubles[0..16]` — [ipSoilDCModulusK] - Modulus. [ipSoilDCModulusKUR] - Unloading/reloading modulus. [ipSoilDCModulusN] - Modulus exponent. [ipSoilDCPoisson] - Poisson’s ratio. Properties – Beams, Plates and Bricks [ipSoilDCBulkK] - Bulk modulus. [ipSoilDCBulkM] - Bulk modulus exponent. [ipSoilDCFrictionAngle] - Friction angle. [ipSoilDCDeltaAngle] - Friction angle change. [ipSoilDCCohesion] - Cohesion value. [ipSoilDCFailureRatio] - Failure ratio. [ipSoilDCFailureMod] - Failure modulus. [ipSoilDCReferenceP] - Reference pressure. [ipSoilDCDensity] - Density. [ipSoilDCHorizontalRatio] - Horizontal stress ratio. [ipSoilDCConductivity] - Conductivity. [ipSoilDCSpecificHeat] - Specific heat. [ipSoilDCFluidLevel] - Fluid level.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotSoil, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_SoilTypeNotDC, ERR7_UnknownProperty
```


---

### `St7GetBrickSoilDCMaterial`

Returns the Duncan-Chang soil material properties assigned to the specified brick
property.

**Syntax**

```c
long St7GetBrickSoilDCMaterial(long uID, long PropNum,
long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Brick property number.

**Output Parameters**

- `Integers[0..1]` — [ipSoilDCUsePoisson] - Use Poisson’s ratio, either btTrue or btFalse. [ipSoilDCSetLevel] - Set fluid level, either btTrue or btFalse.
- `Doubles[0..16]` — [ipSoilDCModulusK] - Modulus. [ipSoilDCModulusKUR] - Unloading/reloading modulus. [ipSoilDCModulusN] - Modulus exponent. [ipSoilDCPoisson] - Poisson’s ratio. [ipSoilDCBulkK] - Bulk modulus. [ipSoilDCBulkM] - Bulk modulus exponent. [ipSoilDCFrictionAngle] - Friction angle. [ipSoilDCDeltaAngle] - Friction angle change. [ipSoilDCCohesion] - Cohesion value. [ipSoilDCFailureRatio] - Failure ratio. [ipSoilDCFailureMod] - Failure modulus. [ipSoilDCReferenceP] - Reference pressure. [ipSoilDCDensity] - Density. [ipSoilDCHorizontalRatio] - Horizontal stress ratio. [ipSoilDCConductivity] - Conductivity. [ipSoilDCSpecificHeat] - Specific heat. [ipSoilDCFluidLevel] - Fluid level. Properties – Beams, Plates and Bricks

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotSoil, ERR7_NoError, ERR7_SoilTypeNotDC,
ERR7_UnknownProperty
```


---

### `St7SetBrickSoilCCMaterial`

Sets the Cam-Clay soil material properties for the specified brick property.

**Syntax**

```c
long St7SetBrickSoilCCMaterial(long uID, long PropNum,
long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Brick property number.
- `Integers[0..3]` — [ipSoilCCUsePoisson] - Use Poisson’s ratio, either btTrue or btFalse. [ipSoilCCDrainedState] - Drained state, either btTrue or btFalse. [ipSoilCCUseOCR] - Overconsolidation, either btTrue or btFalse. [ipSoilCCSetLevel] - Set fluid level, either btTrue or btFalse.
- `Doubles[0..14]` — [ipSoilCCCriticalStateLine] - Critical state line slope. [ipSoilCCConsolidationLine] - Normal consolidation line slope. [ipSoilCCSwellingLine] - Swelling line slope. [ipSoilCCDensity] - Density. [ipSoilCCPoisson] - Poisson’s ratio. [ipSoilCCModulusG] - Shear modulus at point A. [ipSoilCCModulusB] - Shear modulus at point B. [ipSoilCCHorizontalRatio] - Horizontal stress ratio. [ipSoilCCER] - Reference void ratio. [ipSoilCCPR] - Unit pressure ratio. [ipSoilCCPC0] - Initial consolidation pressure. [ipSoilCCOCR] - Overconsolidation ratio. [ipSoilCCConductivity] - Conductivity. [ipSoilCCSpecificHeat] - Specific heat. [ipSoilCCFluidLevel] - Fluid level.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotSoil, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_SoilTypeNotCC, ERR7_UnknownProperty
```


---

### `St7GetBrickSoilCCMaterial`

Returns the Cam-Clay soil material properties assigned to the specified brick
property.

**Syntax**

```c
long St7GetBrickSoilCCMaterial(long uID, long PropNum,
long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Brick property number. Properties – Beams, Plates and Bricks

**Output Parameters**

- `Integers[0..3]` — [ipSoilCCUsePoisson] - Use Poisson’s ratio, either btTrue or btFalse. [ipSoilCCDrainedState] - Drained state, either btTrue or btFalse. [ipSoilCCUseOCR] - Over-consolidation, either btTrue or btFalse. [ipSoilCCSetLevel] - Set fluid level, either btTrue or btFalse.
- `Doubles[0..14]` — [ipSoilCCCriticalStateLine] - Critical state line slope. [ipSoilCCConsolidationLine] - Normal consolidation line slope. [ipSoilCCSwellingLine] - Swelling line slope. [ipSoilCCDensity] - Density. [ipSoilCCPoisson] - Poisson’s ratio. [ipSoilCCModulusG] - Shear modulus at point A. [ipSoilCCModulusB] - Shear modulus at point B. [ipSoilCCHorizontalRatio] - Horizontal stress ratio. [ipSoilCCER] - Reference void ratio. [ipSoilCCPR] - Unit pressure ratio. [ipSoilCCPC0] - Initial consolidation pressure. [ipSoilCCOCR] - Over-consolidation ratio. [ipSoilCCConductivity] - Conductivity. [ipSoilCCSpecificHeat] - Specific heat. [ipSoilCCFluidLevel] - Fluid level.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotSoil, ERR7_NoError, ERR7_SoilTypeNotCC,
ERR7_UnknownProperty
```


---

### `St7SetBrickSoilMCMaterial`

Assigns the Mohr-Coulomb soil parameters for the specified brick property.

**Syntax**

```c
long St7SetBrickSoilMCMaterial(long uID, long PropNum,
long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Property number.
- `Integers[0..0]` — [ipSoilMCSetLevel] - Set a fluid level, either btTrue or btFalse.
- `Doubles[0..9]` — [ipSoilMCModulus] - Modulus. [ipSoilMCPoisson] - Poisson’s ratio. [ipSoilMCDensity] - Density. [ipSoilMCCohesion] - Cohesion value. [ipSoilMCFrictionAngle] - Friction angle. [ipSoilMCHorizontalRatio] - Horizontal stress ratio. [ipSoilMCER] - Void ratio. [ipSoilMCConductivity] - Conductivity. [ipSoilMCSpecificHeat] - Specific heat. [ipSoilMCFluidLevel] - Fluid level.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,


Properties – Beams, Plates and Bricks

ERR7_MaterialNotSoil, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_SoilTypeNotMC, ERR7_UnknownProperty
```


---

### `St7GetBrickSoilMCMaterial`

Returns the Mohr-Coulomb soil parameters assigned to the specified brick
property.

**Syntax**

```c
long St7GetBrickSoilMCMaterial(long uID, long PropNum,
long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Property number.

**Output Parameters**

- `Integers[0..0]` — [ipSoilMCSetLevel] - Set a fluid level, either btTrue or btFalse.
- `Doubles[0..9]` — [ipSoilMCModulus] - Modulus. [ipSoilMCPoisson] - Poisson’s ratio. [ipSoilMCDensity] - Density. [ipSoilMCCohesion] - Cohesion value. [ipSoilMCFrictionAngle] - Friction angle. [ipSoilMCHorizontalRatio] - Horizontal stress ratio. [ipSoilMCER] - Void ratio. [ipSoilMCConductivity] - Conductivity. [ipSoilMCSpecificHeat] - Specific heat. [ipSoilMCFluidLevel] - Fluid level.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotSoil, ERR7_NoError, ERR7_SoilTypeNotMC,
ERR7_UnknownProperty
```


---

### `St7SetBrickSoilDPMaterial`

Assigns the Drucker-Prager soil parameters for the specified brick property.

**Syntax**

```c
long St7SetBrickSoilDPMaterial(long uID, long PropNum,
long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Property number.
- `Integers[0..0]` — [ipSoilDPSetLevel] - Set a fluid level, either btTrue or btFalse.
- `Doubles[0..9]` — [ipSoilDPModulus] - Modulus. [ipSoilDPPoisson] - Poisson’s ratio. [ipSoilDPDensity] - Density. [ipSoilDPCohesion] - Cohesion value. [ipSoilDPFrictionAngle] - Friction angle. [ipSoilDPHorizontalRatio] - Horizontal stress ratio. [ipSoilDPER] - Void ratio. Properties – Beams, Plates and Bricks [ipSoilDPConductivity] - Conductivity. [ipSoilDPSpecificHeat] - Specific heat. [ipSoilDPFluidLevel] - Fluid level.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotSoil, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_SoilTypeNotDP, ERR7_UnknownProperty
```


---

### `St7GetBrickSoilDPMaterial`

Returns the Drucker-Prager soil parameters assigned to the specified brick
property.

**Syntax**

```c
long St7GetBrickSoilDPMaterial(long uID, long PropNum,
long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Property number.

**Output Parameters**

- `Integers[0..0]` — [ipSoilDPSetLevel] - Set a fluid level, either btTrue or btFalse.
- `Doubles[0..9]` — [ipSoilDPModulus] - Modulus. [ipSoilDPPoisson] - Poisson’s ratio. [ipSoilDPDensity] - Density. [ipSoilDPCohesion] - Cohesion value. [ipSoilDPFrictionAngle] - Friction angle. [ipSoilDPHorizontalRatio] - Horizontal stress ratio. [ipSoilDPER] - Void ratio. [ipSoilDPConductivity] - Conductivity. [ipSoilDPSpecificHeat] - Specific heat. [ipSoilDPFluidLevel] - Fluid level.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotSoil, ERR7_NoError, ERR7_SoilTypeNotDP,
ERR7_UnknownProperty
```


---

### `St7SetBrickSoilLSMaterial`

Assigns the linear elastic soil parameters for the specified brick property.

**Syntax**

```c
long St7SetBrickSoilLSMaterial(long uID, long PropNum,
long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Property number.
- `Integers[0..0]` — [ipSoilLSSetLevel] - Set a fluid level, either btTrue or btFalse.
- `Doubles[0..7]` — [ipSoilLSModulus] - Modulus. [ipSoilLSPoisson] - Poisson’s ratio. Properties – Beams, Plates and Bricks [ipSoilLSDensity] - Density. [ipSoilLSHorizontalRatio] - Horizontal stress ratio. [ipSoilLSER] - Void ratio. [ipSoilLSConductivity] - Conductivity. [ipSoilLSSpecificHeat] - Specific heat. [ipSoilLSFluidLevel] - Fluid level.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotSoil, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_SoilTypeNotLS, ERR7_UnknownProperty
```


---

### `St7GetBrickSoilLSMaterial`

Returns the linear elastic soil parameters assigned to the specified brick property.

**Syntax**

```c
long St7GetBrickSoilLSMaterial(long uID, long PropNum,
long* Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Property number.

**Output Parameters**

- `Integers[0..0]` — [ipSoilLSSetLevel] - Set a fluid level, either btTrue or btFalse.
- `Doubles[0..7]` — [ipSoilLSModulus] - Modulus. [ipSoilLSPoisson] - Poisson’s ratio. [ipSoilLSDensity] - Density. [ipSoilLSHorizontalRatio] - Horizontal stress ratio. [ipSoilLSER] - Void ratio. [ipSoilLSConductivity] - Conductivity. [ipSoilLSSpecificHeat] - Specific heat. [ipSoilLSFluidLevel] - Fluid level.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_MaterialNotSoil, ERR7_NoError, ERR7_SoilTypeNotLS,
ERR7_UnknownProperty
```


---

### `St7SetBrickFluidMaterial`

Sets the fluid material properties for the specified brick property.

**Syntax**

```c
long St7SetBrickFluidMaterial(long uID, long PropNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Brick property number.
- `Doubles[0..7]` — [ipFluidModulus] - Modulus. [ipFluidPenaltyParam] - Penalty parameter. [ipFluidDensity] - Density. [ipFluidAlpha] - Thermal expansion coefficient. Properties – Beams, Plates and Bricks [ipFluidViscosity] - Viscous damping coefficient. [ipFluidDampingRatio] - Damping ratio. [ipFluidConductivity] - Conductivity. [ipFluidSpecificHeat] - Specific heat.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7GetBrickFluidMaterial`

Returns the fluid material properties assigned to the specified brick property.

**Syntax**

```c
long St7GetBrickFluidMaterial(long uID, long PropNum,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Brick property number.

**Output Parameters**

- `Doubles[0..7]` — [ipFluidModulus] - Modulus. [ipFluidPenaltyParam] - Penalty parameter. [ipFluidDensity] - Density. [ipFluidAlpha] - Thermal expansion coefficient. [ipFluidViscosity] - Viscous damping coefficient. [ipFluidDampingRatio] - Damping ratio. [ipFluidConductivity] - Conductivity. [ipFluidSpecificHeat] - Specific heat.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_UnknownProperty
```


---

### `St7SetBrickAddBubbleFunction`

Sets the state of the Add Bubble function option for the specified brick property.
This option is only used for Hex8 element types.

**Syntax**

```c
long St7SetBrickAddBubbleFunction(long uID, long PropNum,
bool AddBubbleFunction)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Brick property number.
- `AddBubbleFunction` — btTrue to add the “bubble” contribution to the element shape functions.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7GetBrickAddBubbleFunction`

Returns the state of the Add Bubble function option for the specified brick property.
This option is only used for Hex8 element types.


Properties – Beams, Plates and Bricks

**Syntax**

```c
long St7GetBrickAddBubbleFunction(long uID, long PropNum,
bool* AddBubbleFunction)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Brick property number.

**Output Parameters**

- `AddBubbleFunction` — btTrue to add the “bubble” contribution to the element shape functions.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_UnknownProperty
```


---

### `St7DeleteProperty`

Deletes the specified material property.

**Syntax**

```c
long St7DeleteProperty(long uID, long Entity, long PropNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Property type, one of ptBEAMPROP, ptPLATEPROP, ptBRICKPROP or ptPLYPROP.
- `PropNum` — Entity property number.
