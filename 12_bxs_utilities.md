---
title: "BXS Utilities"
source: "Strand7 R246 API Manual"
pages: 111–115
---

# BXS Utilities

General Model
Syntax

long St7GetPlateNumPlies(long uID, long EltNum, long*
NumPlies)
Input Parameters

uID
Strand7 model file ID number.

EltNum
Plate number.
Output Parameters

NumPlies
Number of plies.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededTotal, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_UnknownProperty


---

### `St7GetNumBXSLoopsAndPlates`

Returns the number of loops and plates in a specified BXS.

**Syntax**

```c
long St7GetNumBXSLoopsAndPlates(long uID, long PropNum,
long* NumLoops, long* NumPlates)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — BXS property number.

**Output Parameters**

- `NumLoops` — Number of loops in the BXS.
- `NumPlates` — Number of plates in the BXS.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_BeamIsNotBXS, ERR7_CannotReadBXS, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_UnknownProperty
```


---

### `St7GetNumBXSLoopPoints`

Returns the number of points contained in a specified loop in a BXS.

**Syntax**

```c
long St7GetNumBXSLoopPoints(long uID, long PropNum, long
LoopNum, long* NumPoints)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — The BXS property number.
- `LoopNum` — The loop number within the BXS.

**Output Parameters**

- `NumPoints` — The number of points within LoopNum.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotReadBXS, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_UnknownProperty
```


---

### `St7GetBXSLoop`

Returns the coordinates of the points in a specified loop of a BXS. The points are
always specified in a 2D plane. Use St7GetNumBXSLoopPoints to determine the
number of points in a loop.

**Syntax**

```c
long St7GetBXSLoop(long uID, long PropNum, long LoopNum,
long MaxPoints, long* NumPoints, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PropNum` — The BXS property number.
- `LoopNum` — The loop number.
- `MaxPoints` — The maximum number of points allocated in Doubles, returns all points if set greater than or equal to NumPoints.

**Output Parameters**

- `NumPoints` — The number of points in the specified loop.
- `Doubles[0..2*MaxPoints-1]` — An array containing the XY coordinates of the points in the loop. The XY coordinates of point i are contained in Doubles[2*i-2..2*i-1].

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotReadBXS, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_UnknownProperty
```


---

### `St7GenerateBXS`

Generates a BXS property and returns the section data.

**Syntax**

```c
long St7GenerateBXS(long uID, char* BXSName, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BXSName` — String containing the name of the BXS.

**Output Parameters**

- `Doubles[0.33]` — [ipBXSXBar] - Centroid X coordinate. [ipBXSYBar] - Centroid Y coordinate. [ipBXSArea] - Section area. [ipBXSI11] - Second moment of area about the principal 1 axis. [ipBXSI22] - Second moment of area about the principal 2 axis. [ipBXSAngle] Orientation angle between the local X and principal 1 axes. [ipBXSZ11Plus] - Positive section modulus about the principal 1 axis. [ipBXSZ11Minus] - Negative section modulus about the principal 1 axis. [ipBXSZ22Plus] - Positive section modulus about the principal 2 axis. [ipBXSZ22Minus] - Negative section modulus about the principal 2 axis. [ipBXSS11] - Plastic modulus about the principal 1 axis. [ipBXSS22] - Plastic modulus about the principal 2 axis. [ipBXSr1] - Radius of gyration in the principal 1 axis direction. [ipBXSr2] - Radius of gyration in the principal 2 axis direction. [ipBXSSA1] - Shear area in the principal 1 axis direction. [ipBXSSA2] - Shear area in the principal 2 axis direction. [ipBXSSL1] - Shear centre offset in the principal 1 axis direction. [ipBXSSL2] - Shear centre offset in the principal 2 axis direction. [ipBXSIXX] - Second moment of area about the global X axis. [ipBXSIYY] - Second moment of area about the global Y axis. [ipBXSIXY] - Second moment of area about the global XY axes. [ipBXSIxxL] - Second moment of area about the local X axis. [ipBXSIyyL] - Second moment of area about the local Y axis. [ipBXSIxyL] - Second moment of area about the local XY axes. [ipBXSZxxPlus] - Positive section modulus about the local X axis. [ipBXSZxxMinus] - Negative section modulus about the local X axis. [ipBXSZyyPlus] - Positive section modulus about the local Y axis. [ipBXSZyyMinus] - Negative section modulus about the local Y axis.
