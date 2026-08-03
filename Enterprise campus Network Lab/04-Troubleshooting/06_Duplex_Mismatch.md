# Duplex Mismatch

## Issue

Cisco generated CDP warnings.

```
%CDP-4-DUPLEX_MISMATCH
```

---

## Cause

One side of the link was configured for half duplex while the other side used full duplex.

---

## Resolution

Configured both ends with the same duplex setting.

Example

```
interface Ethernet5/0

duplex auto

speed auto
```

or

```
duplex full

speed 1000
```

on both devices.

---

## Verification

The CDP warning disappeared.

---

## Result

✅ Duplex mismatch resolved.
