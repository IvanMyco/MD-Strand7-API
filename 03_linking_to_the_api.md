---
title: "Linking to the API"
source: "Strand7 R246 API Manual"
pages: 4–15
---

# Linking to the API

St7APIConst.bas
St7API.cs
St7APIConst.f90
St7APIConst.m

for Microsoft Visual Basic 6 and VBA
for Microsoft Visual C#
for Fortran
for Matlab

The following sections describe how each compiler can use the source/include files
supplied with the Strand7 API Toolkit to create programs that use the Strand7 API.


## Linking to the API with Delphi


Linking to the API with Delphi
There are two Delphi include files in the API toolkit – these are St7ApiCall.pas and
St7ApiConst.pas as described above. An example of a declaration in
St7ApiCall.pas is:

function St7Init():Longint; stdcall external 'St7api.dll';
Linking to the include files involves adding “compiler include” statements, as follows:

unit MainForm;
interface
uses
Windows, Messages, SysUtils, Variants, Classes, Graphics,
Controls, Forms, Dialogs, StdCtrls;
{$i St7APIConst.pas}
{$i St7APICall.pas}

API Strings and Delphi
The Strand7 API uses null-terminated strings. This is different to the so-called Delphi short
string. You should not pass short strings to Strand7 API functions. A null-terminated string
can be passed as either a packed array of AnsiChar or as a PAnsiChar. As shipped,
St7APICall.pas uses the type CharString = packed array[0..kMaxStrLen]
Of AnsiChar, defined in St7APIConst.pas. However, you could replace this with
CharString = PAnsiChar if you prefer.
API Arrays and Delphi
Many Strand7 API functions use arrays of longint or double as parameters. These are
always passed by reference. In most cases, when an array is passed to a Strand7 API
function using the Delphi interface, the array type is specified. For example, the array for
node coordinates is defined as Array3Double = array[0..2] of double. As Delphi
allows you to bypass Pascal’s strong type rules, you could redefine the function:

St7GetNodeXYZ(uID:Longint; NodeNum:Longint; var
XYZ:Array3Doubles):Longint;


as:

St7GetNodeXYZ(uID:Longint; NodeNum:Longint; var
XYZ):Longint;
This would then allow you to pass anything to the function for the XYZ variable. However,
this would increase the possibility of programming errors because the compiler can no
longer detect type conflicts.
As mentioned above, most of the function definitions in St7APICall.pas are typed. There
are some exceptions, e.g. the function:

St7SetBeamSectionProperties(uID:Longint; PropNum:Longint;
var Doubles):Longint;
This is generally done for functions which require arrays of variable lengths. Of course you
can change this declaration if you prefer the full type checking offered by Pascal.


## Linking to the API with C++


Linking to the API with C++
There are two header/include files and one source file included in the Strand7 API Toolkit
– these are St7APICall.h, St7APIConst.h and St7APILoad.cpp as described
above. To use these files include the two header files, and add St7APILoad.cpp to
your project.

#include “St7APIConst.h”
#include “St7APICall.h”
St7APILoad.cpp includes two functions. These functions are LoadSt7API and
FreeSt7API, to load and free the DLL respectively. These must be run by your program
to load the DLL for use and then to unload it after use. LoadSt7API must be called
before the call to St7Init. An example of part of LoadSt7API is as follows:
HMODULE hDLL;
bool LoadSt7API()
{
hSt7API=LoadLibrary("St7api.dll");
// should check if LoadLibrary returns a NULL value
// before proceeding...
if (hSt7API!=NULL)
{
St7Init=(St7InitType)GetProcAddress(hSt7API,"St7Init");
API Strings and C++
The Strand7 API uses null-terminated strings. These are always declared as char* in the
normal C++ convention.
API Arrays and C++
Many Strand7 API functions use arrays of longint or double as parameters. These are
always passed by reference and declared as double* or long*.


Linking to the API with Visual Basic 6 and VBA
There are two source files included in the API Toolkit – these are St7APICall.bas and
St7APIConst.bas as described above. To use these files add them to your project.
API Strings
The Strand7 API uses null-terminated strings. These are always declared as ByVal
StringName As String. Note that as Visual Basic strings will be declared as a fixed
length array, e.g. Dim FileName As String * 255, an API call returning the string
will null-terminate the string via the CHAR=0 at some point. All character values beyond
this point will be undefined.
API Arrays
Many Strand7 API functions use arrays of longint or double as parameters. These are
always passed by reference and declared as ByRef LongArray As Long or ByRef
DoubleArray As Double. The array passing syntax LongArray() As Long or
DoubleArray() As Double should not be used with the Strand7 API. The arrays to be
passed should be declared as Dim LongArray(n) As Long or Dim
DoubleArray(n) As Double, where n is some integer value. When passing these
arrays to a Strand7 API function it is essential that the first index of the array be passed.
The following example further illustrates the correct procedure:

function declaration:
Declare Function St7GetNodeXYZ& Lib "St7API.DLL"(ByVal uID
As Long, ByVal NodeNum As Long, ByRef XYZ As Double)
variable declaration:
Dim XYZ(2) As Double
function call:
ErrorCode = St7GetNodeXYZ(1, NodeNumber, XYZ(0))
API Boolean
Many Strand7 API functions use boolean or arrays of boolean as parameters. These
should always be passed as Byte, (both by value and by reference). This is necessary
because the Strand7 API uses single byte boolean representation, which is compatible
with the Byte type. The Boolean type is two bytes long, therefore not compatible. True
boolean values will therefore be represented by Byte=1 and False boolean values will
be represented by Byte=0.


## Linking to the API with Visual Basic


Linking to the API with Visual Basic
There are two source files included in the API Toolkit – these are St7APICall.vb and
St7APIConst.vb as described above. To use these files add them to your project.
API Strings and Visual Basic
The Strand7 API uses null-terminated strings. These are always declared as ByVal
StringName As String. To pass a string to the API, declare it as Dim StringName
As String and assign it a value, Visual Basic will ensure that the string is null-terminated
when you pass it as an argument. When you need to get a string value back from the
API, the string must be pre-allocated and this is no longer possible in Visual Basic without
assigning it a value. It is therefore necessary to assign the string a value with a length
longer than the specified string length prior to passing to a function that writes to it.
When the string is returned it is also necessary to discard all characters from the first
CHAR=0 to the end of the string.
API Arrays and Visual Basic
Many Strand7 API functions use arrays of longint or double as parameters. These are
always passed by reference and declared as ByRef LongArray As Long or ByRef
DoubleArray As Double. The array passing syntax LongArray() As Long or
DoubleArray() As Double should not be used with the Strand7 API. The arrays to be
passed should be declared as Dim LongArray(n) As Long or Dim
DoubleArray(n) As Double, where n is some integer value. When passing these
arrays to a Strand7 API function via Visual Basic, it is essential that the first index of the
array be passed. The following example further illustrates the correct procedure:

function declaration:
Declare Function St7GetNodeXYZ& Lib "St7API.DLL"(ByVal uID
As Long, ByVal NodeNum As Long, ByRef XYZ As Double)
variable declaration:
Dim XYZ(2) As Double
function call:
ErrorCode = St7GetNodeXYZ(1, NodeNumber, XYZ(0))
API Boolean and Visual Basic
Many Strand7 API functions use boolean or arrays of boolean as parameters. These
should always be passed as Byte in Visual Basic, (both by value and by reference). This
is necessary because the Strand7 API uses single byte boolean representation, which is
compatible with the Visual Basic Byte type. The Visual Basic Boolean type is two bytes


long, therefore not compatible. True boolean values will therefore be represented by
Byte=1 and False boolean values will be represented by Byte=0.


## Linking to the API with Visual C#


Linking to the API with Visual C#
There is one source file included in the API Toolkit - this is St7API.cs as described above.
To use this file add it to your project.
The API functions and constants are declared within a static class called St7. When
calling the API functions and using the API constants it is necessary to prefix the function
or constant name with the St7 class name followed by a period character.
API Strings and Visual C#
The Strand7 API uses null-terminated strings. Strings that are passed to the API are
declared as string StringName and strings that are returned from the API are
declared as StringBuilder StringName. When you pass a string to the API, C# will
ensure that the string is null-terminated. When you wish to retrieve a string from the API
you will need to pass a StringBuilder object with a pre-allocated buffer. The
returned string can be retrieved from the StringBuilder object using the
StringBuilder.ToString() method which will copy the retrieved characters up
until the terminating null character. The following example further illustrates the correct
procedure for retrieving a string:

StringBuilder sb = new StringBuilder(St7.kMaxStrLen);
string errorstring;
St7.St7GetAPIErrorString(12, sb, sb.Capacity);
errorstring = sb.ToString();
API Arrays and Visual C#
Many Strand7 API functions use arrays of longint or double as parameters. These are
always passed by reference and should be declared as double[] DoubleArray =
new double[n] or int[] IntegerArray = new int[n], where n is some integer
value.


Linking to the API with Visual Fortran
There are three source files included in the API Toolkit – these are St7APICall.f90,
St7APIConst.f90 and St7APILoad.f90 as described above. To use these files add
them to your project and insert USE statements at the top of each subroutine that uses
the API.

USE St7APICall
USE St7APIConst
API Strings and Visual Fortran
The Strand7 API uses null-terminated strings. These are always declared as
CHARACTER(LEN=*) in the interface section (St7APICall.f90), and are passed by
reference. Strings will be declared in your program as CHARACTER(LEN=255) (for
example). An API call returning the string will null-terminate the string with CHAR=0 at
some point. All character values beyond this point will be undefined.
API Arrays and Visual Fortran
Many Strand7 API functions use arrays of longint or double as parameters. These are
always passed by reference and should be declared as

REAL(8) :: DOUBLEARRAY(n)
INTEGER(4) :: INTEGERARRAY(n)
where n is some integer value.
API Boolean and Visual Fortran
Many Strand7 API functions use boolean or arrays of boolean as parameters. These
should always be declared as LOGICAL(1) in Visual Fortran. This is necessary because
the Strand7 API uses single byte boolean representation, whereas the Visual Fortran
LOGICAL type can be up to four bytes long.
When passing boolean values to the Strand7 API it is also necessary to pass btTrue and
btFalse in place of Fortran native .TRUE. and .FALSE. . This is required because the
Strand7 API and Visual Fortran interpret boolean values differently.


## Linking to the API with GNU Fortran


Linking to the API with GNU Fortran
There are three source files included in the API Toolkit – these are St7APICall.f90,
St7APIConst.f90 and St7APILoad.f90 as described above. To use these files insert
USE statements at the top of each subroutine that uses the API.

USE St7APICall
USE St7APIConst
USE St7APILoad
API Strings and GNU Fortran
The Strand7 API uses null-terminated strings. These are always declared as

CHARACTER(KIND=C_CHAR) :: CHARARRAY(*)
in the interface section (St7APICall.f90), and are passed by reference. Strings will be
declared in your program as CHARACTER(LEN=255) (for example). An API call
returning the string will null-terminate the string with CHAR=0 at some point. All character
values beyond this point will be undefined.
API Arrays and GNU Fortran
Many Strand7 API functions use arrays of longint or double as parameters. These are
always passed by reference and should be declared as;

REAL(8) :: DOUBLEARRAY(n)
INTEGER(4) :: INTEGERARRAY(n)
where n is some integer value.
API Boolean and GNU Fortran
Many Strand7 API functions use boolean or arrays of boolean as parameters. These
should always be declared as LOGICAL(1) in GNU Fortran. This is necessary because
the Strand7 API uses single byte boolean representation, which is compatible with the
GNU Fortran LOGICAL(1) type. The GNU Fortran LOGICAL type can be up to four bytes
long and therefore not compatible.


Linking to the API with Lahey Fortran
There are two include files included in the API Toolkit – these are St7APICall.f90 and
St7APIConst.f90 as described above. There is an additional import file called
St7APILoad.imp which contains input definitions for the API calls and should be used
at the command line:

lf95.exe @St7APILoad.imp MyCode.f90 -ml bd
API Strings and Lahey Fortran
The Strand7 API uses null-terminated strings. Strings will be declared in your program as
CHARACTER(255) (for example). An API call returning the string will null-terminate the
string via the CHAR=0 at some point. All character values beyond this point will be
undefined.
API Arrays and Lahey Fortran
Many Strand7 API functions use arrays of longint or double as parameters. These are
always passed by reference and should be declared as

REAL(8) :: DOUBLEARRAY(n)
INTEGER(4) :: INTEGERARRAY(n)
where n is some integer value.
API Boolean and Lahey Fortran
Many Strand7 API functions use boolean or arrays of boolean as parameters. These
should always be declared as LOGICAL(1) in Lahey Fortran. This is necessary because
the Strand7 API uses single byte boolean representation, which is compatible with the
Lahey Fortran LOGICAL(1) type. The Lahey Fortran LOGICAL type can be up to four
bytes long and therefore not compatible.
Value Parameters and Lahey Fortran
Many Strand7 API functions pass parameters by value rather than by reference. For
compatibility, these parameters must be wrapped in the CARG() function provided with
Lahey Fortran. Parameters that are passed by reference do not require this special
treatment. In the following example the uID and iNode parameters are passed by
value, and hence the CARG() function is used:

iErr = St7GetNodeXYZ(CARG(uID), CARG(iNode), XYZ)


## Linking to the API with Matlab


Linking to the API with Matlab
There are two header/include files included in the API toolkit – these are St7APICall.h
and St7ApiConst.m as described above.
Matlab includes a series of built-in functions that can be used to load and manipulate
the St7API.dll – see loadlibrary, libisloaded and unloadlibrary within
Matlab for additional information.
Due to Matlab’s interpreted operation, all API calls must be made via the calllib
Matlab built-in function. The complete list of API function arguments is passed into
calllib on the right-hand side, but just the API function’s error return and list of pointer
arguments is assigned on the left-hand side, for example:

XYZ = zeros(3, 1);
[iErr, XYZ] = calllib(‘St7API’, ‘St7GetNodeXYZ’, uID,
NodeNum, XYZ);
The variable iErr is the integer error return from St7GetNodeXYZ, and the array XYZ is
a pointer argument in the function’s argument list (in C notation, this is denoted by an
asterisk in the argument list – long*, double*, bool* or char*). The list of pointer
arguments on the left-hand side must be in the same order as the right-hand side, and
contains both input and output pointer arguments. If a pointer argument is assigned an
output value by the Strand7 API, then it must be allocated before the call to calllib.
Note that text strings are also pointer arguments, even when they are passed into the API
function.
It is possible to pass in dummy variables for the output arguments listed on the right-hand
side. These values are never actually referenced or assigned and exist only so that
calllib can match the number of variables. The list of pointer arguments on the lefthand side may also be truncated, but it must be complete up to the last listed argument.
See calllib within Matlab for additional information.
