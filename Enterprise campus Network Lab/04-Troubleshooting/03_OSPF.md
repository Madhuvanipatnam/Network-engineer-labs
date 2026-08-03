# OSPF Troubleshooting

## Issue

OSPF neighbors were not forming with the distribution switches.

```
show ip ospf neighbor
```

showed

```
No Neighbors
```

---

## Cause

The Layer 3 interfaces between routers and distribution switches were not included in OSPF.

---

## Resolution

Added the missing networks.

Example:

```
router ospf 1

network 192.168.13.0 0.0.0.255 area 0

network 192.168.23.0 0.0.0.255 area 0
```

Performed on all routers and distribution switches.

---

## Verification

```
show ip ospf neighbor
```

Expected

```
FULL
```

---

## Result

✅ OSPF adjacency successfully established.
