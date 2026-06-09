---
title: "Type Definitions"
source: "Strand7 R246 API Manual"
pages: 975–977
---

# Type Definitions

Tools
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidPolygonToFaceParameters, ERR7_NoError,
ERR7_NoPolygonWasConverted, ERR7_ResultFileIsOpen





The Strand7 API uses a number of pre-defined types for the input and output parameters
of function calls. This section lists those types for Pascal implementations, what base
types they inherit and the range of the array they represent.
Calls to functions in C do not use these types. However, the corresponding pointers must
point to arrays that are similar in definition. That is, they must be of the same base type
and contain at least as much pre-allocated space. If less space is allocated for functions
that write to the arrays, then an access violation can occur.
Note that, by default, both the C and Pascal parameters are zero based. Many types
are defined in size by other constants. These are listed below.
Predefined Type

Inherited Type

Range

CharString

Char

- `kMaxStrLen`

EntityTotalsArray

Longint

- `kMaxEntityTotals`

BeamDispArray

Double

- `kMaxDisp`

ConnectionArray

Longint

kMaxElementNode+1

BigResultArray

Double

- `kMaxBeamResult`

BeamResultArray

Double

- `kMaxBeamResult`

BeamReleasedArray

Boolean

- `kMaxBeamRelease`

BeamReleaseDoublesArray

Double

- `kMaxBeamRelease`

BeamSectionArray

Double

kNumBeamSectionData

PlateResultArray

Double

- `kMaxPlateResult`

BrickResultArray

Double

- `kMaxBrickResult`

MaterialArray

Double

kNumMaterialData

UnitsArray

Longint

kLastUnit

AttributeDoublesArray

Double

- `kMaxAttributeDoubles`

AttributeLongintArray

Longint

- `kMaxAttributeLongint`

AttributeLogicalsArray

Boolean

- `kMaxAttributeLogicals`

UCSDoublesArray

Double

- `kMaxUCSDoubles`

NodeResultArray

Double







LoadCaseDefaultsArray

Double


FreedomCaseDefaultsArray

Double


Array3Longint

Longint


Array6Longint

Longint


Array2Doubles

Double


Array3Doubles

Double


Array4Doubles

Double


Array6Doubles

Double


Constants to Define Range
Constant

Value

- `kMaxStrLen`


- `kMaxEntityTotals`


- `kMaxElementNode`


- `kMaxBeamResult`


kNumBeamSectionData


kNumMaterialData


- `kMaxAttributeDoubles`


- `kMaxAttributeLogicals`


- `kMaxAttributeLongint`


kLastUnit


- `kMaxPlateResult`


- `kMaxBrickResult`


- `kMaxBeamRelease`


- `kMaxDisp`


kAllStations


- `kMaxUCSDoubles`






