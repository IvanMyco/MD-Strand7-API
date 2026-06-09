---
title: "Properties – Ply"
source: "Strand7 R246 API Manual"
pages: 620–626
---

# Properties – Ply

Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileIsOpen, ERR7_UnknownProperty


---

### `St7DeleteUnusedProperties`

Deletes all unused properties in the specified model.

**Syntax**

```c
long St7DeleteUnusedProperties(long uID, long Entity, long*
NumDeleted)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Property type, one of ptBEAMPROP, ptPLATEPROP, ptBRICKPROP or ptPLYPROP.

**Output Parameters**

- `NumDeleted` — Number of properties deleted.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7NewPlyProperty`

Creates a new ply property.

**Syntax**

```c
long St7NewPlyProperty(long uID, long PropNum, char*
PropName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Ply property number.
- `PropName` — Name of the property.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidPropertyNumber, ERR7_NoError,
ERR7_PropertyAlreadyExists, ERR7_ResultFileIsOpen
```


---

### `St7SetPlyMaterial`

Sets the material properties for the specified ply property.

**Syntax**

```c
long St7SetPlyMaterial(long uID, long PropNum, long*
Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Ply property number.
- `Integers[0..0]` — [ipPlyWeaveType] - Weave type, one of wtPlyUniDirectional, wtPlyBiDirectional, wtPlyTriDirectional or wtPlyQuasiIsotropic.
- `Doubles[0..20]` — [ipPlyModulus1] - Modulus in the 1 axis direction. [ipPlyModulus2] - Modulus in the 2 axis direction. [ipPlyPoisson] - Poisson’s ratio. [ipPlyShear12] - Shear modulus in the 12 axis direction. [ipPlyShear13] - Shear modulus in the 23 axis direction. [ipPlyShear23] - Shear modulus in the 31 axis direction. [ipPlyAlpha1] - Thermal expansion coefficient in the 1 axis direction. [ipPlyAlpha2] - Thermal expansion coefficient in the 2 axis direction. [ipPlyDensity] - Density. [ipPlyThickness] - Thickness. [ipPlyS1Tension] - Tensile stress limit in the 1 axis direction. [ipPlyS2Tension] - Tensile stress limit in the 2 axis direction. [ipPlyS1Compression] - Compressive stress limit in the 1 axis direction. [ipPlyS2Compression] - Compressive stress limit in the 2 axis direction. [ipPlySShear] - Shear stress limit. [ipPlyE1Tension] - Tensile strain limit in the 1 axis direction. [ipPlyE2Tension] - Tensile strain limit in the 2 axis direction. [ipPlyE1Compression] - Compressive strain limit in the 1 axis direction. [ipPlyE2Compression] - Compressive strain limit in the 2 axis direction. [ipPlyEShear] - Shear strain limit. [ipPlyInterLaminaShear] - Interlamina shear stress limit.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7GetPlyMaterial`

Returns the material properties assigned to the specified ply property.

**Syntax**

```c
long St7GetPlyMaterial(long uID, long PropNum, long*
Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Ply property number.

**Output Parameters**

- `Integers[0..0]` — [ipPlyWeaveType] - Weave type, one of wtPlyUniDirectional, wtPlyBiDirectional, wtPlyTriDirectional or wtPlyQuasiIsotropic.
- `Doubles[0..20]` — [ipPlyModulus1] - Modulus in the 1 axis direction. [ipPlyModulus2] - Modulus in the 2 axis direction. [ipPlyPoisson] - Poisson’s ratio. [ipPlyShear12] - Shear modulus in the 12 axis direction. [ipPlyShear13] - Shear modulus in the 23 axis direction. [ipPlyShear23] - Shear modulus in the 31 axis direction. [ipPlyAlpha1] - Thermal expansion coefficient in the 1 axis direction. [ipPlyAlpha2] - Thermal expansion coefficient in the 2 axis direction. [ipPlyDensity] - Density. [ipPlyThickness] - Thickness. [ipPlyS1Tension] - Tensile stress limit in the 1 axis direction. [ipPlyS2Tension] - Tensile stress limit in the 2 axis direction. [ipPlyS1Compression] - Compressive stress limit in the 1 axis direction. [ipPlyS2Compression] - Compressive stress limit in the 2 axis direction. [ipPlySShear] - Shear stress limit. [ipPlyE1Tension] - Tensile strain limit in the 1 axis direction. [ipPlyE2Tension] - Tensile strain limit in the 2 axis direction. [ipPlyE1Compression] - Compressive strain limit in the 1 axis direction. [ipPlyE2Compression] - Compressive strain limit in the 2 axis direction. [ipPlyEShear] - Shear strain limit. [ipPlyInterLaminaShear] - Interlamina shear stress limit.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_UnknownProperty
```


---

### `St7SetPlateLaminateMaterial`

Sets the laminate material properties for the specified plate property. Not all
parameters returned by the St7GetPlateLaminateMaterial function can be set, as
some parameters are based the ply properties in the layup.

**Syntax**

```c
long St7SetPlateLaminateMaterial(long uID, long PropNum,
long LamNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.
- `LamNum` — Laminate number.
- `Doubles[0..4]` — [ipLaminateViscosity] - Viscous damping coefficient. [ipLaminateDampingRatio] - Damping ratio. [ipLaminateConductivity1] - Conductivity coefficient in the x-axis direction. [ipLaminateConductivity2] - Conductivity coefficient in the y-axis direction. [ipLaminateSpecificHeat] - Specific heat coefficient.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_UnknownProperty
```


---

### `St7GetPlateLaminateMaterial`

Returns the laminate material properties for the specified plate property.

**Syntax**

```c
long St7GetPlateLaminateMaterial(long uID, long PropNum,
long* LamNum, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — Plate property number.

**Output Parameters**

- `LamNum` — Laminate number.
- `Doubles[0..17]` — [ipLaminateViscosity] - Viscous damping coefficient. [ipLaminateDampingRatio] - Damping ratio. [ipLaminateConductivity1] - Conductivity coefficient in the x-axis direction. [ipLaminateConductivity2] - Conductivity coefficient in the y-axis direction. [ipLaminateSpecificHeat] - Specific heat coefficient. [ipLaminateDensity] - Density. [ipLaminateAlphax] - Effective membrane thermal expansion coefficient in the x-axis direction. [ipLaminateAlphay] - Effective membrane thermal expansion coefficient in the y-axis direction. [ipLaminateAlphaxy] - Effective membrane shear thermal expansion coefficient in the xy plane. [ipLaminateBetax] - Effective bending thermal expansion coefficient in the x-direction. [ipLaminateBetay] - Effective bending thermal expansion coefficient in the y-direction. [ipLaminateBetaxy] - Effective twisting thermal expansion coefficient out of the xy plane. [ipLaminateModulusx] - Modulus in the x-axis direction. [ipLaminateModulusy] - Modulus in the y-axis direction. [ipLaminateShearxy] - Shear modulus in the xy plane.
