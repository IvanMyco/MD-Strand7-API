---
title: "User Defined Results"
source: "Strand7 R246 API Manual"
pages: 1091–1092
---

# User Defined Results

Brick Results

- `ipBrickEnergySpent` — Spent energy.





The calculation of user defined result quantities based on primary result quantities is
made possible by User Defined Results. In the Strand7 GUI, this is a contour option made
available for plates and bricks in the Results Settings dialog, in which a simple text
equation may be entered. The functions St7SetPlateResultUserEquation,
St7GetPlateResultUserEquation, St7SetBrickResultUserEquation and
St7GetBrickResultUserEquation parse the same text equation to define the result, input as
the string Equation.
The following syntax is used for this string, note that its interpretation is case-insensitive
and whitespace is ignored.
Primary result quantities are enclosed in square brackets, with the following convention;

[ABC]
A - Result type; one of stress S, strain E, or additionally force per unit length F,
moment per unit length M or curvature K for plates.
B - Component; one of XX, YY, ZZ, XY, YZ, ZX where XYZ refer to the 123 axis
directions defined by the coordinate system.
C - Coordinate system; one of local L, global G or the selected UCS U.
BC - Combined tensorial invariants; one of 11, 22, 33, MEAN, VM, TR.
Optionally for plate stresses and strains, the surface from which the result comes can be
specified; one of mid-plane [ABC-MP], negative z [ABC-NZ] or positive z [ABC-PZ].
Note that if this is not specified, then the positive z value is taken when the plates are
rendered as surfaces, and the value varies through the thickness when the plates are
rendered as solids.
User defined results for plates also have two extra quantities; membrane thickness [TM]
and bending thickness [TB].
Constants are entered in either simple floating point format #.# (period decimal point) or
in scientific notation #.#E# where E separates the mantissa from the exponent (order of
ten).
For manipulation of the above quantities, the standard operators are defined; addition +,
subtraction -, multiplication *, division / and exponentiation ^, as well as brackets (.)
to control the order of operations (otherwise the standard BODMAS convention applies).
Additionally, there are the following functions F(.).





