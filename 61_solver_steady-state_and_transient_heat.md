---
title: "Solver – Steady-State and Transient Heat"
source: "Strand7 R246 API Manual"
pages: 843–843
---

# Solver – Steady-State and Transient Heat

Solver – Quasi-Static and Transient Dynamic


---

### `St7GetMovingLoadState`

Returns the state of the specified moving load path for Quasi-Static and Transient
analysis.

**Syntax**

```c
long St7GetMovingLoadState(long uID, long LoadPathID, bool*
State)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathID` — Load path ID number.

**Output Parameters**

- `State` — btTrue if the load path is enabled.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadPath, ERR7_InvalidLoadPathID, ERR7_NoError
```
