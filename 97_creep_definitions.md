---
title: "Creep Definitions"
source: "Strand7 R246 API Manual"
pages: 1093–1094
---

# Creep Definitions

User Defined Results

ABS - absolute value
SQRT - square root
SQR - square
LN - Natural log (base e)
LOG - Log base 10
EXP - Natural exponent (base e)
SIN - sine
COS - cosine
TAN - tangent
ARCSIN - arcsine
ARCCOS - arccosine
ARCTAN - arctangent
IFPOS - returns argument when argument is positive, zero otherwise
IFNEG - returns argument when argument is negative, zero otherwise





A number of the creep laws available in Strand7 require that a number of basic
coefficients be specified. These coefficients are defined via the Doubles array in the
St7SetCreepBasicData and St7GetCreepBasicData as follows:

Primary Power Law Creep

[0..3] - Coefficients C1, C2, C3 and CT.

Secondary Power Law Creep

[0..2] - Coefficients C1, C2 and CT.

Primary + Secondary Power Law Creep

[0..6] - Coefficients C1, C2, C3, CT1, C4, C5 and CT2.

Secondary Hyperbolic Creep

[0..3] - Coefficients C1, C2, C3 and CT.

Secondary Exponential Creep

[0..2] - Coefficients C1, C2 and CT.

Theta Projection Creep

[0..3] - Coefficients A1, A2, A3 and A4.
[4..7] - Coefficients B1, B2, B3 and B4.
[8..11] - Coefficients C1, C2, C3 and C4.
[12..15] - Coefficients D1, D2, D3 and D4.





