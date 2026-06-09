---
title: "Initialisation and File Management"
source: "Strand7 R246 API Manual"
pages: 16–26
---

# Initialisation and File Management

Linking to the API with Python
Both constants and function definitions are in the module St7API.py; the module
should be placed in a directory in the Python path (for example C:\Python33\Lib) so
it can be used without being copied to the directory of each new project. The module is
for 32-bit Python versions and can be used with Python 2.6 upwards, including Python 3.
The module is loaded using;

import St7API
after which functions and constants can be accessed using the prefix St7API, for
example;

St7API.St7Init()
The prefix is omitted if the contents of the module is imported into the current
namespace. For example,

from St7API import *
St7Init()
Types from ctypes are used for input and output with the Strand7 API. Input arguments
of type integer, double, boolean and string (bytes in Python 3) are cast into the
appropriate type, including conversion to pointers. Output arguments must be declared
explicitly using ctypes constructors since the native python types are immutable. For
example, if a function has output argument of type double it should be declared as
ctypes.c_double().
Arrays in Python
Python lists must be converted to ctypes arrays before passing as arguments to Strand7
API calls. A type for an array of length n can be created using the syntax
arrayType = singularType * n. For example,

unitsArray = ctypes.c_int * St7API.kLastUnit
units = unitsArray()
creates an array of integers 6 elements long suitable for passing to functions St7GetUnits,
St7SetUnits and St7ConvertUnits.
Arrays from ctypes are indexed in the same manner as python lists, for example

units[St7API.ipSTRESSU] = St7API.suMEGAPASCAL


---

### `St7Init`

Initialises the Strand7 API DLL. This function should be called before subsequent
API calls are made. If this function is not called first all subsequent API calls will
return an error code.

**Syntax**

```c
long St7Init()
```

**Errors**

```
ERR7_InvalidRegionalSettings, ERR7_InvalidDLLsPresent,
ERR7_NoError, ERR7_UnknownError
```


---

### `St7Release`

Releases the Strand7 API DLL, unloading the Strand7 licence manager and
freeing any active licences. The St7Init function must again be called before
subsequent API operations can be run.

**Syntax**

```c
long St7Release()
```

**Errors**

```
ERR7_FilesStillOpen, ERR7_SolverStillRunning, ERR7_NoError
```


---

### `St7APIVersion`

Returns the version information for the Strand7 API DLL that is currently loaded.

**Syntax**

```c
long St7APIVersion(long* Major, long* Minor, long* Point)
```

**Output Parameters**

- `Major` — Major version number A in the A.B.C format.
- `Minor` — Minor version number B in the A.B.C format.
- `Point` — Point version number C in the A.B.C format.

**Errors**

```
ERR7_NoError
```


---

### `St7OpenFile`

Opens a Strand7 model file. This call is required before any data can be
examined or written to any Strand7 model file. A new Strand7 file may be
opened without closing a currently open file. Multiple files can therefore be
opened simultaneously. Each file that is to be opened must be specified with the
use of a file ID number.

**Syntax**

```c
long St7OpenFile(long uID, char* FileName, char*
ScratchPath)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and filename for the Strand7 model.
- `ScratchPath` — A valid path to be used for temporary storage.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotReadFile, ERR7_FileAlreadyOpen, ERR7_FileIsNewer,
ERR7_FileNotFound, ERR7_FileNotSt7, ERR7_InvalidFileName,
ERR7_InvalidFileUnit, ERR7_InvalidScratchPath, ERR7_NoError
```


---

### `St7CloseFile`

Closes an open Strand7 model file. All associated scratch files that may have
been created are automatically deleted.

**Syntax**

```c
long St7CloseFile(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_UnknownError
```


---

### `St7NewFile`

Creates and opens a new Strand7 model file. Note that if a file of the same name
exists, the existing file will stay open and will not be overwritten until the new file is
saved.

**Syntax**

```c
long St7NewFile(long uID, char* FileName, char*
ScratchPath)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and filename for the Strand7 model.
- `ScratchPath` — A valid path to be used for temporary storage.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileAlreadyOpen, ERR7_InvalidFileName,
ERR7_InvalidFilePath, ERR7_InvalidFileUnit,
ERR7_InvalidScratchPath, ERR7_NoError
```


---

### `St7SaveFile`

Saves a specified Strand7 model file. The file remains open after the call. This
function cannot be called if the file has open result files associated with it.

**Syntax**

```c
long St7SaveFile(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotSaveFile, ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_NoError
```


---

### `St7SaveFileTo`

Saves a specified Strand7 model to a new file. The file remains open after the call.
This function cannot be called if the file has open result files associated with it.

**Syntax**

```c
long St7SaveFileTo(long uID, char* FileName)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and filename for the Strand7 model.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotSaveFile, ERR7_FileNotOpen, ERR7_InvalidFileName,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7OpenResultFile`

Opens a result file associated with a specified Strand7 model. All supported result
file types may be opened.

**Syntax**

```c
long St7OpenResultFile(long uID, char* FileName, char*
SpectralName, bool Combinations, long* NumPrimary,
long* NumSecondary)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and filename for the Strand7 result file.
- `SpectralName` — Full path and filename for the spectral result file to be combined. A null string may be passed to combine with the default spectral file as defined by the user in the Strand7 model.
- `Combinations` — btTrue to calculate all secondary result combinations on open. The “Saved result” setting in Results Options determines whether previously calculated combinations are used – for Prompt, combinations are recalculated. Note that result envelopes are not calculated – use St7GenerateEnvelopes for these.

**Output Parameters**

- `NumPrimary` — Number of primary result cases available.
- `NumSecondary` — Number of secondary result cases available (excluding envelopes).

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidResultFile, ERR7_NoError
```


---

### `St7GenerateLSACombinations`

Generate the secondary result cases for the linear load case combinations in a
Strand7 model. The result file must be open.

**Syntax**

```c
long St7GenerateLSACombinations(long uID, long*
NumSecondary)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumSecondary` — Number of secondary result cases available.

**Errors**

```
ERR7_ExceededResultCase, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7GenerateEnvelopes`

Generate the secondary result cases for the result envelopes specified in the
Strand7 model. The result file must be open.

**Syntax**

```c
long St7GenerateEnvelopes(long uID, long* NumLimitEnvelopes,
long* NumCombinationEnvelopes, long*
NumFactorsEnvelopes)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumLimitEnvelopes` — Number of limit envelope results cases available.
- `NumCombinationEnvelopes` — Number of combination envelope results cases available.
- `NumFactorsEnvelopes` — Number of factors envelope results cases available.

**Errors**

```
ERR7_ExceededResultCase, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileNotOpen
```


---

### `St7CloseResultFile`

Closes any open result file associated with a specified Strand7 model.

**Syntax**

```c
long St7CloseResultFile(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileNotOpen
```


---

### `St7GetDisplayOptionsPath`

Returns the full path name of the display options file.

**Syntax**

```c
long St7GetDisplayOptionsPath(char* ConfigPath, long
MaxStringLen)
```

**Input Parameters**

- `MaxStringLen` — The maximum number of characters allocated for ConfigPath.

**Output Parameters**

- `ConfigPath` — Full path name of the display options file.

**Errors**

```
ERR7_NoError
```


---

### `St7SetDisplayOptionsPath`

Sets the full path to the display options file. If only the directory is given, then
Settings.cfg will be used to control display behaviour. The display options are only
used to define settings for model files created subsequently to this call.

**Syntax**

```c
long St7SetDisplayOptionsPath(char* ConfigPath)
```

**Input Parameters**

- `ConfigPath` — Full path name of the display options file.

**Errors**

```
ERR7_InvalidDisplayOptionsPath, ERR7_NoError
```


---

### `St7GetLibraryPath`

Returns the full path name to the directory containing the Strand7 library files.

**Syntax**

```c
long St7GetLibraryPath(char* LibraryPath, long
MaxStringLen)
```

**Input Parameters**

- `MaxStringLen` — The maximum number of characters allocated for LibraryPath.

**Output Parameters**

- `LibraryPath` — Full path name to the directory containing the Strand7 library files.

**Errors**

```
ERR7_NoError
```


---

### `St7SetLibraryPath`

Sets the full path name to the directory containing the Strand7 library files. Any
subsequent calls to the libraries will use the files contained in this directory.

**Syntax**

```c
long St7SetLibraryPath(char* LibraryPath)
```

**Input Parameters**

- `LibraryPath` — Full path name to the directory containing the Strand7 library files.

**Errors**

```
ERR7_InvalidLibraryPath, ERR7_NoError
```


---

### `St7GetPath`

Returns the full path name to the directory that contains the Strand7 API that is
currently loaded.

**Syntax**

```c
long St7GetPath(char* St7Path, long MaxStringLen)
```

**Input Parameters**

- `MaxStringLen` — Maximum number of characters allocated for St7Path.

**Output Parameters**

- `St7Path` — Full path name to the ..\Strand7\Bin directory that contains the St7API.dll that is currently loaded.

**Errors**

```
ERR7_NoError
```


---

### `St7GetLastError`

Returns the error code generated by the last Strand7 API call.

**Syntax**

```c
long St7GetLastError()
```

**Errors**

```
ERR7_NoError
```


---

### `St7GetAPIErrorString`

Returns the error message corresponding to a specified Strand7 API error code.
Error codes corresponding to a Strand7 solver error should be processed using the
St7GetSolverErrorString function described below.

**Syntax**

```c
long St7GetAPIErrorString(long iErr, char* ErrorString,
long MaxStringLen)
```

**Input Parameters**

- `iErr` — Strand7 API error code.
  MaxStringLen
