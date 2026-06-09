---
title: "Using the Strand7 API"
source: "Strand7 R246 API Manual"
pages: 2–3
---

# Using the Strand7 API

Introduction
The Strand7 Application Programming Interface (API) allows programmers to interface
their code to Strand7. This makes it possible to create a program that can access
geometric and result data from Strand7 models. Data obtained can then be used by the
program for display or further processing.
The Strand7 API consists of a Dynamic Link Library (DLL) file (St7API.dll) and a number of
header and include files. The DLL file contains functions that can be used to: read
Strand7 finite element data; modify or create Strand7 finite element data; launch the
Strand7 solvers; and read Strand7 result data.
The header files allow external programs to communicate with St7API.dll. They define all
the constants used and the function calling conventions for each language supported
(all functions in the Strand7 API use the Windows calling convention “stdcall”). A different
set of header files is needed for each language (e.g. Delphi, C++, Fortran, etc). Note
that in some cases, header files are even compiler product dependent - e.g. the header
files for Visual Fortran will be different to the header files for Lahey Fortran. Release 2.4.6
comes with header files for Delphi, C/C++, Compaq/Intel Visual Fortran, Lahey Fortran,
Microsoft Visual Basic (including VBA), Microsoft Visual C# and Matlab. New header files
are being added to meet user requirements – please contact us if you need header files
for a different language.
The majority of this documentation is devoted to describing each of the functions in the
Strand7 API. The C syntax for the available functions is given, along with the input and
output parameters and example code.
The remainder of the documentation lists error codes and conventions and types for
property information, attributes and results.
For compiler specific information, see the Using the Strand7 API section.


This section summarises the steps needed for preparing a program to use the Strand7 API.
In general:
1. To enable the Strand7 API for operation, it must be licenced with the Strand7
keycode. You can check if your version of the API is enabled via the Help/Licence
Information option on the Strand7 main menu.
2. The Strand7 API file St7API.dll must be located in a directory where it can be
found by the calling program. This means that St7API.dll must be in a directory
that is within the Windows search path. Alternatively, it is possible to specify where
the DLL is located via the Windows API function LOADLIBRARY. See the Win32 API for
more information about this.
3. To call the functions in the API, an interface file that declares the exported function
calls in St7API.dll is needed. This file is provided in the Strand7 API Toolkit and its
name is dependent on the compiler:

St7APICall.pas
St7APICall.h
St7APICall.vb
St7APICall.bas
St7API.cs
St7APICall.f90

for Delphi
for C/C++ and Matlab
for Microsoft Visual Basic
for Microsoft Visual Basic 6 and VBA
for Microsoft Visual C#
for Fortran

4. For some languages, explicit loading of St7API.dll is required via the Windows API
call LOADLIBRARY. The code to do this is also provided in the Strand7 API Toolkit for
the languages where it is needed:

St7APILoad.cpp
St7APILoad.f90

for C++
for Compaq/Intel Visual Fortran

5. As most of the API functions employ pre-defined constants, these are conveniently
defined within an external file in the Strand7 API Toolkit. It is not essential that you use
this file, especially if you prefer to declare your arrays as 1-based instead of the 0based approach used. The name of the constants file is dependent on the compiler:

St7APIConst.pas
St7APIConst.h
St7APIConst.vb

for Delphi
for C/C++
for Microsoft Visual Basic
