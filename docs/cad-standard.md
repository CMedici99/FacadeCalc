# CAD Standard

## Purpose

This document defines the CAD requirements for FacadeCalc.

The application will read geometry from a DXF file using fixed layers and block names.

---

# Panel Geometry

Layer:

```
Panel geometry
```

Entity:

```
Closed Polyline
```

Rules:

- Exactly one closed polyline per panel
- Units in mm
- Polyline represents panel extents
- Width and height are extracted automatically

---

# Deadload Supports

Layer:

```
Deadload
```

Block Name:

```
DL
```

Rules:

- Exactly 2 DL blocks required
- Both supports must be at the same elevation
- Block insertion point defines support location

Example:

```
DL1 ---------------- DL2
```

---

# Restraint Supports

Layer:

```
Restrain
```

Block Name:

```
RS
```

Rules:

- Exactly 2 RS blocks required
- Both supports must be at the same elevation
- Block insertion point defines support location

Example:

```
RS1 ---------------- RS2
```

---

# Barrier

Layer:

```
Barrier
```

Block Name:

```
BR
```

Rules:

- Optional
- Maximum 1 BR block
- Block insertion point defines barrier location

---

# Phase 1 Assumptions

The Phase 1 calculator supports:

- 1 panel
- 2 deadload supports
- 2 restraint supports
- Optional barrier load

Arrangement:

```
DL1 ---------------- DL2

|                    |

|       PANEL        |

|                    |

RS1 ---------------- RS2
```

---

# Units

Geometry:

```
mm
```

Loads:

```
kPa
kg/m²
kN
```

Results:

```
kN
```

No automatic unit conversion is permitted.

---

# DXF Validation Requirements

A valid DXF must contain:

- Layer: Panel geometry
- Layer: Deadload
- Layer: Restrain

Optional:

- Layer: Barrier

Required block names:

- DL
- RS

Optional:

- BR
